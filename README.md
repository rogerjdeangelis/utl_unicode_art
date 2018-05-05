# utl_unicode_art
Unicode Art. Keywords: sas sql join merge big data analytics macros oracle teradata mysql sas communities stackoverflow statistics artificial inteligence AI Python R Java Javascript WPS Matlab SPSS Scala Perl C C# Excel MS Access JSON graphics maps NLP natural language processing machine learning igraph DOSUBL DOW loop stackoverflow SAS community.
    Unicode Art
    anti-aliasing not needed?

    for output art
    https://github.com/rogerjdeangelis/utl_unicode_art/blob/master/utl_unicode_art.pdf

    github
    https://github.com/rogerjdeangelis/utl_unicode_art

    INPUT
    =====

     WORK.HAVE total obs=6

          UNI1               UNI2               UNI3               UNI4

     ^{unicode 2764}    ^{unicode 263A}    ^{unicode 231A}    ^{unicode 2602}
     ^{unicode 2744}    ^{unicode 262E}    ^{unicode 2604}    ^{unicode 22C8}
     ^{unicode 272B}    ^{unicode 262f}    ^{unicode 2600}    ^{unicode 25D0}
     ^{unicode 2601}    ^{unicode 2606}    ^{unicode 22C6}    ^{unicode 2302}
     ^{unicode 265E}    ^{unicode 263C}    ^{unicode 2605}    ^{unicode 2606}
     ^{unicode 2639}    ^{unicode 2603}    ^{unicode 2318}    ^{unicode 21F3}


    PROCESS
    =======

    %utl_rtflan100;  * see template below;
                     * you - ypu do not need the template - default style is not bad;

    options orientation=landscape;

    ods rtf file="d:/rtf/utl_unicode_art.rtf" style=utl_rtflan100 ;
    ods escapechar='^';

    proc report data=have style(column)={font_size=36 cellwidth=1in just=center};
      title;
      col uni1-uni4;
      define uni1 / display "" ;
      define uni2 / display "" ;
      define uni3 / display "" ;
      define uni4 / display "" ;
      run;quit;

    ods rtf close;


    OUTPUT
    ======

    see

      https://github.com/rogerjdeangelis/utl_unicode_art/blob/master/utl_unicode_art.pdf

    *                _              _       _
     _ __ ___   __ _| | _____    __| | __ _| |_ __ _
    | '_ ` _ \ / _` | |/ / _ \  / _` |/ _` | __/ _` |
    | | | | | | (_| |   <  __/ | (_| | (_| | || (_| |
    |_| |_| |_|\__,_|_|\_\___|  \__,_|\__,_|\__\__,_|

    ;

    data have;
    input (uni1 uni2 uni3 uni4) ($16.);
    cards4;
    ^{unicode 2764} ^{unicode 263A} ^{unicode 231A} ^{unicode 2602}
    ^{unicode 2744} ^{unicode 262E} ^{unicode 2604} ^{unicode 22C8}
    ^{unicode 272B} ^{unicode 262f} ^{unicode 2600} ^{unicode 25D0}
    ^{unicode 2601} ^{unicode 2606} ^{unicode 22C6} ^{unicode 2302}
    ^{unicode 265E} ^{unicode 263C} ^{unicode 2605} ^{unicode 2606}
    ^{unicode 2639} ^{unicode 2603} ^{unicode 2318} ^{unicode 21F3}
    ;;;;
    run;quit;

    *          _       _   _
     ___  ___ | |_   _| |_(_) ___  _ __
    / __|/ _ \| | | | | __| |/ _ \| '_ \
    \__ \ (_) | | |_| | |_| | (_) | | | |
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|

    ;
    %utl_rtflan100;  * see template below;
                     * you - ypu do not need the template - default style is not bad;

    options orientation=landscape;

    ods rtf file="d:/rtf/utl_unicode_art.rtf" style=utl_rtflan100 ;
    ods escapechar='^';

    proc report data=have style(column)={font_size=36 cellwidth=1in just=center};
      title;
      col uni1-uni4;
      define uni1 / display "" ;
      define uni2 / display "" ;
      define uni3 / display "" ;
      define uni4 / display "" ;
      run;quit;

    ods rtf close;


    *_                       _       _
    | |_ ___ _ __ ___  _ __ | | __ _| |_ ___
    | __/ _ \ '_ ` _ \| '_ \| |/ _` | __/ _ \
    | ||  __/ | | | | | |_) | | (_| | ||  __/
     \__\___|_| |_| |_| .__/|_|\__,_|\__\___|
                      |_|
    ;

    %Macro utl_rtflan100
        (
          style=utl_rtflan100
          ,outputwidth=100%
          ,frame=box
          ,TitleFont=14pt
          ,docfont=13pt
          ,fixedfont=12pt
          ,rules=ALL
          ,bottommargin=.25in
          ,topmargin=.25in
          ,rightmargin=.25in
          ,leftmargin=.25in
          ,cellheight=13pt
          ,cellpadding = 2pt
          ,cellspacing = .2pt
          ,borderwidth = .2pt
        ) /  Des="SAS PDF Template for PDF";

    ods path work.templat(update) sasuser.templat(update) sashelp.tmplmst(read);

    Proc Template;

       define style &Style;
       parent=styles.rtf;

            replace body from Document /

                   protectspecialchars=off
                   asis=on
                   bottommargin=&bottommargin
                   topmargin   =&topmargin
                   rightmargin =&rightmargin
                   leftmargin  =&leftmargin
                   ;

            replace color_list /
                  'link' = blue
                   'bgH'  = _undef_
                   'fg'  = black
                   'bg'   = _undef_;

            replace fonts /
                   'TitleFont2'           = ("Arial, Helvetica, Helv",&titlefont,Bold)
                   'TitleFont'            = ("Arial, Helvetica, Helv",&titlefont,Bold)

                   'HeadingFont'          = ("Arial, Helvetica, Helv",&titlefont)
                   'HeadingEmphasisFont'  = ("Arial, Helvetica, Helv",&titlefont,Italic)

                   'StrongFont'           = ("Arial, Helvetica, Helv",&titlefont,Bold)
                   'EmphasisFont'         = ("Arial, Helvetica, Helv",&titlefont,Italic)

                   'FixedFont'            = ("Courier New, Courier",&fixedfont)
                   'FixedEmphasisFont'    = ("Courier New, Courier",&fixedfont,Italic)
                   'FixedStrongFont'      = ("Courier New, Courier",&fixedfont,Bold)
                   'FixedHeadingFont'     = ("Courier New, Courier",&fixedfont,Bold)
                   'BatchFixedFont'       = ("Courier New, Courier",&fixedfont)

                   'docFont'              = ("Arial, Helvetica, Helv",&docfont)

                   'FootFont'             = ("Arial, Helvetica, Helv", 9pt)
                   'StrongFootFont'       = ("Arial, Helvetica, Helv",8pt,Bold)
                   'EmphasisFootFont'     = ("Arial, Helvetica, Helv",8pt,Italic)
                   'FixedFootFont'        = ("Courier New, Courier",8pt)
                   'FixedEmphasisFootFont'= ("Courier New, Courier",8pt,Italic)
                   'FixedStrongFootFont'  = ("Courier New, Courier",7pt,Bold);

            replace GraphFonts /
                   'GraphDataFont'        = ("Arial, Helvetica, Helv",&fixedfont)
                   'GraphValueFont'       = ("Arial, Helvetica, Helv",&fixedfont)
                   'GraphLabelFont'       = ("Arial, Helvetica, Helv",&fixedfont,Bold)
                   'GraphFootnoteFont'    = ("Arial, Helvetica, Helv",8pt)
                   'GraphTitleFont'       = ("Arial, Helvetica, Helv",&titlefont,Bold)
                   'GraphAnnoFont'        = ("Arial, Helvetica, Helv",&fixedfont)
                   'GraphUnicodeFont'     = ("Arial, Helvetica, Helv",&fixedfont)
                   'GraphLabel2Font'      = ("Arial, Helvetica, Helv",&fixedfont)
                   'GraphTitle1Font'      = ("Arial, Helvetica, Helv",&fixedfont);

            style Graph from Output/
                    outputwidth = 100% ;

            style table from table /
                    outputwidth=&outputwidth
                    protectspecialchars=off
                    asis=on
                    background = colors('tablebg')
                    frame=&frame
                    rules=&rules
                    cellheight  = &cellheight
                    cellpadding = &cellpadding
                    cellspacing = &cellspacing
                    bordercolor = colors('tableborder')
                    borderwidth = &borderwidth;

             replace Footer from HeadersAndFooters

                    / font = fonts('FootFont')  just=left asis=on protectspecialchars=off ;

                    replace FooterFixed from Footer
                    / font = fonts('FixedFootFont')  just=left asis=on protectspecialchars=off;

                    replace FooterEmpty from Footer
                    / font = fonts('FootFont')  just=left asis=on protectspecialchars=off;

                    replace FooterEmphasis from Footer
                    / font = fonts('EmphasisFootFont')  just=left asis=on protectspecialchars=off;

                    replace FooterEmphasisFixed from FooterEmphasis
                    / font = fonts('FixedEmphasisFootFont')  just=left asis=on protectspecialchars=off;

                    replace FooterStrong from Footer
                    / font = fonts('StrongFootFont')  just=left asis=on protectspecialchars=off;

                    replace FooterStrongFixed from FooterStrong
                    / font = fonts('FixedStrongFootFont')  just=left asis=on protectspecialchars=off;

                    replace RowFooter from Footer
                    / font = fonts('FootFont')  asis=on protectspecialchars=off just=left;

                    replace RowFooterFixed from RowFooter
                    / font = fonts('FixedFootFont')  just=left asis=on protectspecialchars=off;

                    replace RowFooterEmpty from RowFooter
                    / font = fonts('FootFont')  just=left asis=on protectspecialchars=off;

                    replace RowFooterEmphasis from RowFooter
                    / font = fonts('EmphasisFootFont')  just=left asis=on protectspecialchars=off;

                    replace RowFooterEmphasisFixed from RowFooterEmphasis
                    / font = fonts('FixedEmphasisFootFont')  just=left asis=on protectspecialchars=off;

                    replace RowFooterStrong from RowFooter
                    / font = fonts('StrongFootFont')  just=left asis=on protectspecialchars=off;

                    replace RowFooterStrongFixed from RowFooterStrong
                    / font = fonts('FixedStrongFootFont')  just=left asis=on protectspecialchars=off;

                    replace SystemFooter from TitlesAndFooters / asis=on
                            protectspecialchars=off just=left;
        end;
    run;
    quit;

    %Mend utl_rtflan100;






