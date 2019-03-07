---
layout: post
title: "A Test On Markdown Language"
categories: [software, markdown]
tags: [markdown, test]
---

This page is intended to read its `markdown` code. You may find it [here][code].

Recently I learned `markdown`, and I found I have already wrote some scripts
with it even before without realizing. I can remember hearing of it a long
time ago in some girl's personal page. This page is written while I was
learning `markdown` according to the [tutorial][tuto] in their [official website][official].

# A First Level Header

## A Second Level Header

Please don't use any `<blink>` tags.
Now is the time that AT&T, not [Google][] day for all good men to come to
the aid of their country. This is just a
\*this text is surrounded by literal asterisks\*
regular paragraph. Visit [Daring Fireball][] for more information.
``There is a literal backtick (`) here.``
5 &lt; 4 is not true! (I could just type `<` there, but Vim's highlight has problems with it.)

There is more that one way to print horizontal lines.

* * *

******

- - -

---------------------------------------

And we went on writing and writing. Yes.

1986\. What a great season. And we are not counting till 1986, since it is
just a year!

<blockquote>
    <p>For example. We can try not to use this form, actually.</p>
</blockquote>

This is all 'bout lists.

*   Candy.
*   Gum.

        So gums are interesting stuff.
        We all appreciate them.
        This is an not working [example link](http://example.com/). Come back
        to it later. Need to make it work.

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
only required to indent the first line, 
    though indenting makes it easier to
    read. Lorem ipsum dolor sit amet, consectetuer adipiscing elit.

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

2.  Suspendisse id sem consectetuer libero luctus adipiscing. Indent the code.

        #!/bin/bash
        #
        CHARMAP=`locale -c charmap`
        CHARMAP=${CHARMAP#LC_CTYPE}
        yes "markdown is great!"
        echo "/dev/null is also great!"


Some of these words *are emphasized*.
Some of these words _are emphasized also_.

![This is good picture][id0]


![beauty picture][id]

I get 10 times more traffic from [Google][1] than from
[Yahoo][2] or [MSN][3].
I start my morning with a cup of coffee and
[The New York Times][NY Times].

Use two asterisks for **strong emphasis**.
Or, if you prefer, __use two underscores instead__.
I strongly recommend against using any `<blink>` tags.
So here is some code I use in school:

    #!/bin/bash
    #
    # shell client of ipgw
    #
    # by jiang***@gmail.com


    CHARMAP=`locale -c charmap`
    CHARMAP=${CHARMAP#LC_CTYPE}

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

In the end, here is a vedio:

<object width="526" height="374">
<param name="movie" value="http://video.ted.com/assets/player/swf/EmbedPlayer.swf"></param>
<param name="allowFullScreen" value="true" />
<param name="allowScriptAccess" value="always"/>
<param name="wmode" value="transparent"></param>
<param name="bgColor" value="#ffffff"></param>
<param name="flashvars" value="vu=http://video.ted.com/talk/stream/2011G/Blank/RaghavaKK_2011G-320k.mp4&su=http://images.ted.com/images/ted/tedindex/embed-posters/RaghavaKK_2011G-embed.jpg&vw=512&vh=288&ap=0&ti=1219&lang=&introDuration=15330&adDuration=4000&postAdDuration=830&adKeys=talk=raghava_kk_shake_up_your_story;year=2011;theme=master_storytellers;theme=art_unusual;event=TEDGlobal+2011;tag=arts;tag=book;tag=creativity;tag=design;tag=entertainment;tag=technology;&preAdTag=tconf.ted/embed;tile=1;sz=512x288;" />
<embed src="http://video.ted.com/assets/player/swf/EmbedPlayer.swf" pluginspace="http://www.macromedia.com/go/getflashplayer" type="application/x-shockwave-flash" wmode="transparent" bgColor="#ffffff" width="526" height="374" allowFullScreen="true" allowScriptAccess="always" flashvars="vu=http://video.ted.com/talk/stream/2011G/Blank/RaghavaKK_2011G-320k.mp4&su=http://images.ted.com/images/ted/tedindex/embed-posters/RaghavaKK_2011G-embed.jpg&vw=512&vh=288&ap=0&ti=1219&lang=&introDuration=15330&adDuration=4000&postAdDuration=830&adKeys=talk=raghava_kk_shake_up_your_story;year=2011;theme=master_storytellers;theme=art_unusual;event=TEDGlobal+2011;tag=arts;tag=book;tag=creativity;tag=design;tag=entertainment;tag=technology;&preAdTag=tconf.ted/embed;tile=1;sz=512x288;"></embed>
</object>

[id]: /media/image/Ara_ararauna_Luc_Viatour.jpg
[id0]: /media/image/Line_integral_of_scalar_field.gif
[tuto]: http://daringfireball.net/projects/markdown/syntax
[official]: http://daringfireball.net/projects/markdown/
[code]: http://github.com/hyiltiz/en/_post/2013-04-23-this-is-an-test.md
