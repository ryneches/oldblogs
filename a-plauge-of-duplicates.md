Title: A plauge of duplicates
Date: 2008-04-19 07:47:44
Category: general
Slug: a-plauge-of-duplicates
Author: Russell Neches
Tags: code, software, python
Summary: 


I have a bad habit. I often open my IMAP mailbox directly on the mail
host with mutt. This inevitably causes occasional complicated messes
when I butterfinger something. For example, a few days ago I
accidentally moved all of the read messages to a separate mailbox. I
merged the message back in, but not before my desktop, which was
patiently monitoring my IMAP mailbox on the other side of town, decided
to synchronize a few thousand messages with the IMAP server. This
resulted in lots and lots of duplicate messages.

The trouble was, the duplicate messages had different X-IDs so, their
MD5 hashes would be different. After fiddling around with formail for a
few minutes, I got impatient and banged out this fun little Python hack
:

    import email, imaplib, getpass

    M = imaplib.IMAP4_SSL( '**********' )

    typ, data = M.login( getpass.getuser(), getpass.getpass() )
    if typ != 'OK' :
        raise Exception, 'Login failed.'

    typ, data = M.select()
    if typ != 'OK' :
        raise Exception, 'Selection failed.'

    typ, data = M.search( None, 'ALL' )
    if typ != 'OK' :
        raise Exception, 'Could not get message IDs.'

    id_list = data[0].split()
    mids = []
    for id in id_list :
        typ, data = M.fetch( id, '(RFC822)' )
        if typ != 'OK' :
            raise Exception, 'Could not fetch message ' + id
        mail = email.message_from_string( data[0][1] )
        mID = mail.get( 'message-id' )
        print mID
        mids.append( (mID, id) )

    mids.sort()

    dupes = []
    for i in range(len(mids)) :
        if m[i] == m[i+1] :
            dupes.append( m[i+1] )

    print 'Found ' + len(dupes) + ' duplicate messages.'

    for m in dupes :
        typ, data = M.store( m[1], "+FLAGS", '(\\Deleted)')

    print 'Marked ' + len(dupes) + ' for deletion.'

    typ, data = M.expunge()

    print 'Expunged ' + len(data.split()) + ' messages.'

Duplicates begone!

It's a little annoying that imaplib doesn't have a friendly wrapper
function for marking messages for deletion, but M.store( m[1], "+FLAGS",
'(\\\\Deleted)') does the job just fine.
