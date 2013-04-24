---
layout: post
title: "A Test On Markdown Language"
description: ""
category: 
tags: [markdown, test]
---
{% include JB/setup %}


# A First Level Header

## A Second Level Header

Please don't use any `<blink>` tags.
Now is the time AT&T, not [Google][] day for all good men to come to
the aid of their country. This is just a
\*this text is surrounded by literal asterisks\*
regular paragraph.Visit [Daring Fireball][] for more information.
``There is a literal backtick (`) here.``
5 &lt; 4 is not true! (I could just type `<` there, but Vim's highlight has problems with it.)

* * *

***

*****

- - -

---------------------------------------

And we went on writing and writing. Yes.

1986\. What a great season.


<blockquote>
    <p>For example.</p>
</blockquote>

*   Candy.
*   Gum.

        So gums are interesting stuff.
        We all appreciate them.
        This is an [example link](http://example.com/).
*   Booze.
-   iCandy.

*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
Suspendisse id sem consectetuer libero luctus adipiscing.
-   iGum.
-   iBooze.
*   This is a list item with two paragraphs.

    This is the second paragraph in the list item. You're
only required to indent the first line. Lorem ipsum dolor
sit amet, consectetuer adipiscing elit.

*   Another item in the same list.
*   A list item with a blockquote:

    > This is a blockquote
    > inside a list item.

1.  This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

    Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

2.  Suspendisse id sem consectetuer libero luctus adipiscing.
        #!/bin/bash
        #
        # shell client of ipgw
        #
        # by jiangzuoyan@gmail.com


        CHARMAP=`locale -c charmap`
        CHARMAP=${CHARMAP#LC_CTYPE}

        IPGWU="1000013731"
        IPGWP="yorungkax"
        # default operation when non option given
        # IPGWOP=connect

Some of these words *are emphasized*.
Some of these words _are emphasized also_.

![This is good text][id0]


![beauty text][id]

I get 10 times more traffic from [Google][1] than from
[Yahoo][2] or [MSN][3].
I start my morning with a cup of coffee and
[The New York Times][NY Times].

Use two asterisks for **strong emphasis**.
Or, if you prefer, __use two underscores instead__.
I strongly recommend against using any `<blink>` tags.
So here is some code:

    #!/bin/bash
    #
    # shell client of ipgw
    #
    # by jiangzuoyan@gmail.com


    CHARMAP=`locale -c charmap`
    CHARMAP=${CHARMAP#LC_CTYPE}

    IPGWU="1000013731"
    IPGWP="yorungkax"
    # default operation when non option given
    # IPGWOP=connect

    ##usage ipgw_operation uid password operation
    function ipgw_operation
    {
        local U=$1
        local P=$2
        local OP=$3
        wget -q --no-check-certificate 'https://162.105.67.5/ipgw/ipgw.ipgw' \
            --post-data "uid=$U&password=$P&range=2&timeout=1&operation=$OP" \
            -O - | \
            iconv -f gbk -t $CHARMAP  | \
            sed -n -e '/<table/,/<\/table>/{s/&nbsp;/ /g;s/<[^>]*>//g;p;}'
    }

    function usage
    {
        echo -e "Usage:\n\tcipgw\t[-u uid -p password] [-c] [-a] [-d] [-h]"
        echo -e "\t -c\tConnect to ipgw"
        echo -e "\t -d\tdisconnect from ipgw"
        echo -e "\t -a\tdisconnectall from ipgw"
        echo -e "\t -h\thelp, print this message then exit"
        echo -e "the last operation action, eg. -ac will just connect"
    }

    while getopts ":p:ucad" Option
    do
        case $Option in
            u   )   IPGWU=$OPTARG;;
            p   )   IPGWP=$OPTARG;;
            c   )   IPGWOP=connect;;
            d   )   IPGWOP=disconnect;;
            a   )   IPGWOP=disconnectall;;
            h|* )   usage
                exit 1;;
        esac
    done



    if [[ -n $IPGWOP && -n $IPGWU && -n $IPGWP ]]; then
        ipgw_operation $IPGWU $IPGWP $IPGWOP;
    else
        echo non ipgw operation or uid or password seted
        usage
    fi

I wish SmartyPants used named entities like `&mdash;`
instead of decimal-encoded entites like `&#8212;`.

If you want your page to validate under XHTML 1.0 Strict,
you've got to put paragraph tags in your blockquotes:

   <blockquote>
       <p>For example.</p>
   </blockquote>

The quick brown fox jumped over the lazy
dog's back.
This is an [example link](http://example.com/ "What title is that!").

### Header 3

![This is good text][id0]

#### Header 4


> This is a blockquote.
> 
> > This is the second paragraph in the blockquote.

> And this is even a blockquite
with these.

> and these.

> ## This is an H2 in a blockquote #
> ### This is an H4 in a blockquite 



[1]: http://google.com/        "Google"
[2]: http://search.yahoo.com/  "Yahoo Search"
[3]: http://search.msn.com/    "MSN Search"
[ny times]: http://www.nytimes.com/
[id]:  /media/Ara_ararauna_Luc_Viatour.jpg "Title"
[id0]: /media/Line_integral_of_scalar_field.gif 
        "Good"
[Google]: http://google.com/
[Daring Fireball]: http://daringfireball.net/
