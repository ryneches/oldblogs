Title: Tasty Python Snacks
Date: 2006-11-06 14:51:01
Category: general
Slug: tasty-python-snacks
Author: Russell Neches
Tags: code
Summary: 


Languages like Python are great for tasks that require manipulating
complicated data. The main complaint about such languages is that they
aren't as fast as compiled languages. For scientific computing (and a
lot of other things), that's a show-stopper. However...

    from weave import inline
    a = 25
    code = \
        """
        int i = a;
        while( i > 1 ) {
            printf("a number: %d\\n",i);
            i = i / 2;
        }
        return_val = i;
        """
    inline(code, ['a'])
    ===output===

    a number: 25
    a number: 12
    a number: 6
    a number: 3
    1

My mind just spins thinking of all the horrible, horrible things I can
do with that.
