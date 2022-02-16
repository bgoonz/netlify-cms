---
title: Netlify Large Media
author: Bryan g
meta_description: Hi
twitter_image: https://d33wubrfki0l68.cloudfront.net/95d5a78ac385cbb2252b70cd416693630f06647a/11edd/images/outdated-packages-732a4523.png
date: 2022-02-16T05:34:44.387Z
weight: 20
description: Html
group: Media
---
[Netlify Large Media](https://www.netlify.com/features/large-media/) is a [Git LFS](https://git-lfs.github.com/) implementation for repositories connected to Netlify sites. This means that you can use Git to work with large asset files like images, audio, and video, without bloating your repository. It does this by replacing the asset files in your repository with text pointer files, then uploading the assets to the Netlify Large Media storage service.

![]()

If you have a Netlify site with Large Media enabled, Netlify CMS (version 2.6.0 and above) will handle Large Media asset files seamlessly, in the same way as files stored directly in the repository.

## Requirements

To use Netlify Large Media with Netlify CMS, you will need to do the following:

* [Upgrade Netlify CMS](/docs/update-the-cms-version/) to version 2.6.0 or above.
* Configure Netlify CMS to use the [Git Gateway backend with Netlify Identity](/docs/git-gateway-backend/#git-gateway-with-netlify-identity).
* Configure the Netlify site and connected repository to use Large Media, following the [Large Media docs on Netlify](https://www.netlify.com/docs/large-media/).

When these are complete, you can use Netlify CMS as normal, and the configured asset files will automatically be handled by Netlify Large Media.

## Image transformations

All JPEG, PNG, and GIF files that are handled with Netlify Large Media also have access to Netlify's on-demand image transformation service. This service allows you to request an image to match the dimensions you specify in a query parameter added to the image URL.

You can learn more about this feature in [Netlify's image transformation docs](https://www.netlify.com/docs/image-transformation/).

### Transformation control for media gallery thumbnails

In repositories enabled with Netlify Large Media, Netlify CMS will use the image transformation query parameters to load thumbnail-sized images for the media gallery view. This makes images in the media gallery load significantly faster.

**Note:** When using this option all tracked file types have to be imported into Large Media. For example if you track `*.jpg` but still have jpg-files that are not imported into Large Media the backend will throw an error. Check the [netlify docs](https://docs.netlify.com/large-media/setup/#migrate-files-from-git-history) on how to add previously committed files to Large Media.

You can disable the automatic image transformations with the `use_large_media_transforms_in_media_library` configuration setting, nested under `backend` in the CMS `config.yml` file:

```
<!DOCTYPE html><html><head><style data-href="/styles.6a2d60a60763591e91f7.css">html{line-height:1.15}main{display:block}hr{overflow:visible}a:focus{outline:thin dotted}.font-fira-sans b,.font-fira-sans strong{font-weight:600}code,kbd,pre,samp{font-family:SFMono-Regular,Menlo,Monaco,Consolas,Liberation Mono,Courier New,monospace}img{border-style:none;vertical-align:middle}button,input,optgroup,select,textarea{font-family:inherit;font-size:100%;line-height:1.15}button,input{overflow:visible}[type=button],[type=reset],[type=submit],button{-webkit-appearance:button}[type=button]::-moz-focus-inner,[type=reset]::-moz-focus-inner,[type=submit]::-moz-focus-inner,button::-moz-focus-inner{border-style:none;padding:0}[type=button]:-moz-focusring,[type=reset]:-moz-focusring,[type=submit]:-moz-focusring,button:-moz-focusring{outline:1px dotted ButtonText}fieldset{padding:.35em .75em .625em}legend{box-sizing:border-box;color:inherit;display:table;max-width:100%;white-space:normal}progress{vertical-align:baseline}[type=checkbox],[type=radio]{box-sizing:border-box;padding:0}[type=number]::-webkit-inner-spin-button,[type=number]::-webkit-outer-spin-button{height:auto}[type=search]{-webkit-appearance:textfield;outline-offset:-2px}[type=search]::-webkit-search-decoration{-webkit-appearance:none}::-webkit-file-upload-button{-webkit-appearance:button;font:inherit}details{display:block}summary{display:list-item}[hidden],template{display:none}html{font-family:Lato,Helvetica,Arial,sans-serif;font-size:100%;scroll-behavior:smooth}iframe{overflow:scroll;resize:both;border:1px dashed #000;padding:10px;box-shadow:inset 0 0 2px #000}body{background:#f8f8fa;color:#424b5f;line-height:1.625;text-rendering:optimizeLegibility;-moz-osx-font-smoothing:grayscale;-webkit-font-smoothing:antialiased}a{color:#00c6ff;text-decoration:underline;transition:color .3s ease}a:hover{color:#424b5f}h1,h2,h3,h4,h5,h6{color:#283040;font-weight:700;line-height:1.2;margin:1.5em 0 .5em;text-rendering:optimizeLegibility}h1:first-child,h2:first-child,h3:first-child,h4:first-child,h5:first-child,h6:first-child{margin-top:0}.save2PDF{font-size:x-large}h2{font-size:1.75em}h3{font-size:1.5em}h4{font-size:1.25em}h5{font-size:1.125em}h6{font-size:1em}p{margin:0 0 1em}ins,mark{background:#fff7e6;color:#283040;padding:.15em;text-decoration:none}pre{background:#283040;border-radius:3px;color:#f8f8fa;font-size:.875em;line-height:1.5;margin:2.14286em 0;padding:1.5em;text-align:left;white-space:pre;word-spacing:normal;word-break:normal;word-wrap:normal}pre:first-child{margin-top:0}:not(pre)>code{background:#ecedf2;border-radius:3px;color:#424b5f;font-size:.875rem;padding:.15em;white-space:normal}blockquote{border-left:5px solid #00c6ff;font-size:1.25em;line-height:1.4;margin:1.25em 0;padding:0 0 0 1em}blockquote:first-child{margin-top:0}blockquote p{margin-bottom:.5em}blockquote cite,blockquote small{color:#67758d;display:block;font-size:.75em;font-style:normal;font-weight:400;line-height:1.5;margin-top:.5em}dl{margin:0}dt{font-weight:700}dd,ol,ul{margin:0 0 1em}ul{list-style:disc;padding:0 0 0 1.125em}ol{list-style:decimal;padding:0 0 0 1.5em}li>ol,li>ul{margin-bottom:0}hr{background-color:#dde0e7;border:0;height:1px;margin:1.875em 0}hr:first-child{margin-top:0}embed,iframe,object,video{max-width:100%}div.wrapper:hover img:not(:hover){Filter:brightness(50%)}img{height:auto;max-width:100%;scroll-snap-align:center}img:hover{Filter:brightness(110%)}figure{overflow:auto;-ms-scroll-snap-type:inline mandatory;scroll-snap-type:inline mandatory}@media only screen and (min-width:641px){blockquote{font-size:1.5em;line-height:1.3}h1{font-size:2.5em}h2{font-size:2.125em}h3{font-size:1.875em}h4{font-size:1.5em}h5{font-size:1.25em}h6{font-size:1.125em}}html{font-family:sans-serif;-ms-text-size-adjust:100%;-webkit-text-size-adjust:100%}article,aside,details,figcaption,figure,footer,header,hgroup,main,menu,nav,section,summary{display:block}audio,canvas,progress,video{display:inline-block;vertical-align:baseline}audio:not([controls]){display:none;height:0}[hidden],template{display:none}a{background-color:transparent}a:active,a:hover{outline:0}abbr[title]{border-bottom:none;text-decoration:underline;-webkit-text-decoration:underline dotted;text-decoration:underline dotted}b,strong{font-weight:700}dfn{font-style:italic}h1{font-size:2em;margin:.67em 0}mark{background:#ff0;color:#000}small{font-size:80%}sub,sup{font-size:75%;line-height:0;position:relative;vertical-align:baseline}sup{top:-.5em}sub{bottom:-.25em}img{border:0}svg:not(:root){overflow:hidden}figure{margin:1em 40px}hr{box-sizing:content-box;height:0}pre{overflow:auto}code,kbd,pre,samp{font-family:monospace,monospace;font-size:1em}button,input,optgroup,select,textarea{color:inherit;font:inherit;margin:0}button{overflow:visible}button,select{text-transform:none}button,html input[type=button],input[type=reset],input[type=submit]{-webkit-appearance:button;cursor:pointer}button[disabled],html input[disabled]{cursor:default}button::-moz-focus-inner,input::-moz-focus-inner{border:0;padding:0}input{line-height:normal}input[type=checkbox],input[type=radio]{box-sizing:border-box;padding:0}input[type=number]::-webkit-inner-spin-button,input[type=number]::-webkit-outer-spin-button{height:auto}input[type=search]{-webkit-appearance:textfield;box-sizing:content-box}input[type=search]::-webkit-search-cancel-button,input[type=search]::-webkit-search-decoration{-webkit-appearance:none}fieldset{border:1px solid silver;margin:0 2px;padding:.35em .625em .75em}legend{border:0;padding:0}textarea{overflow:auto}optgroup{font-weight:700}td,th{padding:0}/*!
        Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */@media print{*,:after,:before{color:#000!important;text-shadow:none!important;background:transparent!important;box-shadow:none!important}a,a:visited{text-decoration:underline}a[href]:after{content:" (" attr(href) ")"}abbr[title]:after{content:" (" attr(title) ")"}a[href^="#"]:after,a[href^="javascript:"]:after{content:""}blockquote,pre{border:1px solid #999;page-break-inside:avoid}thead{display:table-header-group}img,tr{page-break-inside:avoid}img{max-width:100%!important}h2,h3,p{orphans:3;widows:3}h2,h3{page-break-after:avoid}}body,html{min-height:100%}body{margin:0}audio,canvas,iframe,img,svg,video{vertical-align:middle}html{--font-mono:Consolas,"Andale Mono WT","Andale Mono","Lucida Console","Lucida Sans Typewriter","DejaVu Sans Mono","Bitstream Vera Sans Mono","Liberation Mono","Nimbus Mono L",Monaco,"Courier New",Courier,monospace;--ff-rounded:"Nunito",sans-serif;--ff-gothic:"AlternateGothicPro-No1",system-ui,sans-serif;--color-light:#f3f4f6;font-family:var(--ff-rounded);line-height:1.5;font-size:1rem;--user-font-scale:1rem - 16px;background:#130931;background:linear-gradient(180deg,#18083c,#58359c);color:#fff}::-webkit-scrollbar{width:20px;height:5px}::-webkit-scrollbar-thumb{background:linear-gradient(180deg,#f1a195,#b475dc);border-radius:10px}::-webkit-scrollbar-track{background:#43346e;box-shadow:inset 1px 0 10px rgba(0,0,0,.5)}[style*="--aspect-ratio"]>:first-child{width:100%}[style*="--aspect-ratio"]>img{height:auto}@supports (--custom:property){[style*="--aspect-ratio"]{position:relative}[style*="--aspect-ratio"]:before{content:"";display:block;padding-bottom:calc(100%/var(--aspect-ratio))}[style*="--aspect-ratio"]>:first-child{position:absolute;top:0;left:0;height:100%}}p{margin:0 0 1rem}a{color:#9058b5}a:focus,a:hover{-webkit-text-decoration-color:#e1d6eb;text-decoration-color:#e1d6eb}table{border-collapse:collapse;border-spacing:0;line-height:1.5;margin:0;max-width:100%;width:100%}caption,table{text-align:left}caption{color:#67758d;font-size:.875em;font-style:normal;margin-bottom:1em}td,th{border-bottom:1px solid #dde0e7;padding:.5em 5px}th{color:#283040;font-weight:700}:not(.responsive-table)>table{display:block;margin:1.875em 0;overflow-x:auto;-webkit-overflow-scrolling:touch}:not(.responsive-table)>table:first-child{margin-top:0}:not(.responsive-table)>table tbody,:not(.responsive-table)>table thead,:not(.responsive-table)>table tr{width:100%}:not(.responsive-table)>table td{min-width:10em}.responsive-table{display:block;margin:1.875em 0;overflow-x:auto;width:100%}.responsive-table:first-child{margin-top:0}label{color:#283040;font-weight:700;line-height:1.5;margin-bottom:.25em}input[type=checkbox]+label,input[type=radio]+label{font-weight:400;cursor:pointer;padding-left:.25em;padding-right:1em}input[type=email],input[type=number],input[type=password],input[type=search],input[type=tel],input[type=text],input[type=url],select,textarea{background:#fff;border:1px solid #dde0e7;border-radius:3px;box-shadow:none;box-sizing:border-box;color:#283040;display:block;font-size:1em;font-weight:400;line-height:1.5;max-width:100%;padding:.5em;width:100%}input[type=email]:focus,input[type=number]:focus,input[type=password]:focus,input[type=search]:focus,input[type=tel]:focus,input[type=text]:focus,input[type=url]:focus,select:focus,textarea:focus{outline:0}::-webkit-input-placeholder{color:#9aa4b9;opacity:1}:-ms-input-placeholder{color:#9aa4b9;opacity:1}::placeholder{color:#9aa4b9;opacity:1}.form-row{margin-bottom:1em}.form-submit{margin-top:1.66667em}.button{align-items:center;background:#00c6ff;border:0;border-radius:1.95em;box-shadow:none;box-sizing:border-box;color:#fff;cursor:pointer;display:inline-flex;font-size:1em;font-weight:700;justify-content:center;letter-spacing:.035em;line-height:1.6;opacity:1;padding:1.2em 2.14285em;text-decoration:none;transition:.3s ease;vertical-align:middle;box-shadow:0 1px 4px rgba(0,0,0,.3),inset 0 0 40px rgba(0,0,0,.1)}.button:active,.button:focus,.button:hover{color:#fff;opacity:.8;outline:0}.button-secondary{background:0!important;box-shadow:inset 0 0 0 3px currentColor;color:#00c6ff}.button-secondary:active,.button-secondary:focus,.button-secondary:hover{box-shadow:inset 0 0 0 4px currentColor;color:#00c6ff;opacity:1}.button-icon{background:0!important;border:0;color:#000;font-size:1.2em;font-weight:400;letter-spacing:normal;padding:.25em}.button-icon:active,.button-icon:focus,.button-icon:hover{color:#00c6ff;opacity:1}#menu-close,#menu-open,.docs-nav .docs-nav-toggle,.docs-nav .docs-submenu-toggle,.submenu-toggle{background:0;border:0;border-radius:0;box-shadow:none;color:inherit;cursor:pointer;display:block;font-size:inherit;height:30px;padding:0;position:relative;width:30px}#menu-close:active,#menu-close:focus,#menu-close:hover,#menu-open:active,#menu-open:focus,#menu-open:hover,.docs-nav .docs-nav-toggle:active,.docs-nav .docs-nav-toggle:focus,.docs-nav .docs-nav-toggle:hover,.docs-nav .docs-submenu-toggle:active,.docs-nav .docs-submenu-toggle:focus,.docs-nav .docs-submenu-toggle:hover,.submenu-toggle:active,.submenu-toggle:focus,.submenu-toggle:hover{outline:0}.icon{color:inherit;fill:#fff;flex-shrink:0;height:1em;line-height:1;width:1em}.icon-close,.icon-menu{background:#fff;border-radius:1px;color:inherit;height:2px;left:50%;margin-top:-1px;margin-left:-12px;position:absolute;top:50%;width:24px}.icon-close:after,.icon-close:before,.icon-menu:after,.icon-menu:before{background:#fff;border-radius:1px;content:"";height:100%;left:0;position:absolute;width:100%}.icon-menu:before{top:-6px}.icon-menu:after{bottom:-6px}.icon-close{background:0;margin-left:-14px;width:28px}.icon-close:before{top:0;-webkit-transform:rotate(45deg);transform:rotate(45deg)}.icon-close:after{top:0;-webkit-transform:rotate(-45deg);transform:rotate(-45deg)}.icon-angle-right{background:0;border-color:#000;border-style:dashed;border-width:2px 1px 0 0;box-sizing:border-box;height:6px;left:70%;margin-left:-2px;margin-top:-2px;position:absolute;top:50%;width:6px;-webkit-transform:rotate(45deg);transform:rotate(45deg)}.docs-nav-toggle .icon-angle-right{height:12px;left:auto;margin-left:0;margin-right:9px;margin-top:-6px;right:0;width:12px}.docs-section-item .icon-angle-right{left:auto;margin-left:0;margin-right:15px;right:0}.screen-reader-text{clip:rect(1px,1px,1px,1px);-webkit-clip-path:polygon(0 0,0 0,0 0,0 0);clip-path:polygon(0 0,0 0,0 0,0 0);height:1px;overflow:hidden;position:absolute!important;width:1px;word-wrap:normal!important}.line-left{position:relative}.line-left:after{background:#00c6ff;display:block;content:"";height:100%;left:-1px;position:absolute;top:0;width:5px}.js-reframe{margin:1.875em 0}.js-reframe:first-child{margin-top:0}.important,.note{border-radius:5px;color:#283040;margin:1.875em 0;padding:1em 1.125em}.important:first-child,.note:first-child{margin-top:0}.note{background:#fff7e6;border-left:5px solid #fcb41d}.important{background:#ffe9e6;border-left:5px solid #fc381d}.has-gradient{background:#00c6ff;background:linear-gradient(90deg,#0072ff,#00c6ff);color:#fff;position:relative}.has-gradient a:not(.button),.has-gradient h1,.has-gradient h2,.has-gradient h3,.has-gradient h4,.has-gradient h5,.has-gradient h6{color:inherit!important}.has-gradient a:not(.button):hover{opacity:.8}.has-gradient .button:not(.button-secondary){background-color:#fff;color:#00c6ff}.has-gradient .button:not(.button-secondary):active,.has-gradient .button:not(.button-secondary):focus,.has-gradient .button:not(.button-secondary):hover{opacity:.85}.has-gradient .button-secondary{color:#fff!important}.has-gradient .inner-sm{position:relative}.bg-img{-webkit-animation:fadeIn20 .75s ease-in-out;animation:fadeIn20 .75s ease-in-out;background-position:50%;background-size:cover;bottom:0;left:0;opacity:.2;position:absolute;right:0;top:0}.grid{display:flex;border-radius:5px;flex-wrap:wrap;margin-left:-.9375em;margin-right:-.9375em}.grid-item{box-sizing:border-box;padding-left:.9375em;padding-right:.9375em;position:relative;width:100%}.grid-center{justify-content:center}.grid-swap{flex-direction:row-reverse}.grid-middle{align-items:center}@media only screen and (min-width:641px){.grid-col-2 .grid-item{flex:0 0 50%;max-width:50%}}@media only screen and (min-width:761px){.grid-col-3 .grid-item{flex:0 0 33.333%;max-width:33.333%}}@media only screen and (max-width:600px){.grid{margin-left:-1.5vw;margin-right:-1.5vw}.grid-item{padding-left:1.5vw;padding-right:1.5vw}}@-webkit-keyframes fadeIn20{0%{opacity:0}to{opacity:.2}}@keyframes fadeIn20{0%{opacity:0}to{opacity:.2}}.site{display:flex;flex-direction:column;min-height:110vh;position:relative}.site-content{box-sizing:border-box;flex-grow:1;width:100%}.outer{padding-left:3vw;padding-right:3vw}.inner{max-width:1200px}.inner,.inner-md{margin-left:auto;margin-right:auto}.inner-md{max-width:800px}.inner-sm{margin-left:auto;margin-right:auto;max-width:680px}.site-header{background:#000;background-image:url(https://i.imgur.com/CEYEZp8.jpeg);padding-bottom:.4em;padding-top:.2em}.site-header-inside{align-items:center;display:flex}.site-branding{flex:0 1 auto}.site-title{color:#283040;font-size:1.5em;font-weight:700;line-height:1.2;margin:0}.site-logo{margin:0}.site-logo img{max-height:65px}.menu,.submenu{list-style:none;margin:0;padding:0}.menu-item{position:relative}.menu-item.current{color:#00c6ff}.menu-item a:not(.button){display:inline-block;font-size:1.1em;line-height:1.5}#masthead a:not(.button){color:inherit;display:inline-block;text-decoration:none}#masthead a:not(.button):hover{color:#00c6ff}#masthead .site-branding a:hover{color:inherit}@media only screen and (min-width:801px){#menu-close,#menu-open{display:none}.site-navigation{margin-left:auto}.menu{align-items:center;display:flex}.menu-item{display:inline-block;margin:0 0 0 1.25em;padding-bottom:.1875em;padding-top:.1875em}.menu-item a{padding-bottom:.5em;padding-top:.5em}.menu-item a.button:not(.button-icon){padding-left:1.25em;padding-right:1.25em}.menu-item.has-children>a{padding-right:18px;position:relative}.menu-item.has-children>a:after{background:0;border-color:currentcolor;border-style:solid;border-width:1px 1px 0 0;box-sizing:border-box;content:"";height:6px;position:absolute;right:0;top:50%;width:6px;-webkit-transform:translateY(-50%) rotate(135deg);transform:translateY(-50%) rotate(135deg)}.menu-item.has-children>a.button:not(.button-icon){padding-right:2.25em}.menu-item.has-children>a.button:not(.button-icon):after{right:1.25em}.menu-item .submenu-toggle{display:none}.menu-item.has-children:hover>.submenu{opacity:1;transition:margin .3s,opacity .2s;visibility:visible}.submenu{background:#fff;border:4px solid #dde0e7;border-radius:3px;box-shadow:0 1px 2px 0 rgba(0,0,0,.13);left:0;min-width:180px;opacity:0;padding:.5em 0;position:absolute;text-align:left;top:100%;transition:opacity .2s,visibility 0s .2s;visibility:hidden;width:100%;z-index:99}.submenu .menu-item{display:block;margin:0;padding:0 1em}.submenu a:not(.button-icon){display:block}.submenu a.button:not(.button-icon){margin:.5em 0}}@media only screen and (max-width:800px){.site{overflow:hidden;position:relative}.site-branding{margin-right:.625em}.site-header:after{background:rgba(66,75,95,.6);content:"";left:0;opacity:0;transition:opacity .15s ease-in-out,visibility 0s ease-in-out .15s;z-index:998}.site-header:after,.site-navigation{height:100vh;position:absolute;top:0;visibility:hidden;width:100%}.site-navigation{background:#fff;box-sizing:border-box;margin:0;max-width:360px;-webkit-overflow-scrolling:touch;right:-100%;transition:right .3s ease-in-out,visibility 0s ease-in-out .3s;z-index:999}.site-nav-inside{height:100%;overflow:auto;-webkit-overflow-scrolling:touch;position:relative}.menu--opened .site{height:100%;left:0;overflow:hidden;position:fixed;top:0;-webkit-transform:translateZ(0);transform:translateZ(0);width:100%;z-index:997}.menu--opened .site-navigation{right:0;transition:right .3s ease-in-out;visibility:visible}.menu--opened .site-header:after{opacity:1;transition-delay:0s;visibility:visible}.menu{padding:calc(3vw + 2.8125em) 3vw 3em}.submenu{border-top:1px solid #dde0e7;display:none;padding-left:1em}.menu-item{display:block;margin:0}.menu-item:not(.menu-button){border-bottom:1px solid #dde0e7}.menu-item:not(.menu-button):first-child{border-top:1px solid #dde0e7}.menu-item a.button-icon,.menu-item a:not(.button){padding:.75em 0}.menu-item a:not(.button){display:block}.menu-item a.button:not(.button-icon){width:100%}.menu-item.has-children>a{margin-right:2em}.menu-item .menu-item:first-child{border-top:0}.menu-item .menu-item:last-child{border-bottom:0}.menu-item .submenu-toggle{color:#67758d;height:2.8125em;position:absolute;right:0;top:0}.menu-item.active .submenu-toggle .icon-angle-right{-webkit-transform:rotate(135deg);transform:rotate(135deg)}.menu-item.active .submenu{display:block}.menu-button>.button:not(.button-icon){margin-bottom:1.25em;margin-top:1.25em}.menu-button+.menu-button>.button:not(.button-icon){margin-top:0}#menu-open{margin-left:auto}#menu-close{display:block;position:absolute;right:3vw;top:3vw}}.post{margin-bottom:2.5em}.post-feed:last-child,.post-full:last-child{margin-bottom:5em}.has-gradient.page-header,.has-gradient.post-header{padding-bottom:9.5em;padding-top:3.75em;text-align:center;box-shadow:0 1px 4px rgba(0,0,0,.3),inset 0 0 40px rgba(0,0,0,.1)}.has-gradient .page-title,.has-gradient .post-title{color:inherit;font-size:2.25em;margin:0}.page-subtitle,.post-subtitle{font-size:1.125em;line-height:1.5;margin:.5em 0 0;position:relative}.post-title a{color:inherit!important;text-decoration:none}.post-thumbnail{border:0;border-radius:5px 5px 0 0;display:block;margin:0}.post-thumbnail img{border-radius:5px 5px 0 0;width:100%}.post-feed,.post-full .post-content{margin-top:-5em;position:relative}.post-feed .post,.post-full .post-content{background:#fff;border:1px solid #dde0e7;border-radius:5px;box-shadow:0 1px 2px 0 rgba(0,0,0,.13)}.post-full .post-content{padding:1.5em}.post-full .post-meta{margin:0 0 .5em}.post-feed .post{padding:0 0 2.5em}.post-feed .post-meta{color:#67758d;font-size:.875em;margin:0 0 .5em;padding-left:1.71428em;padding-right:1.71428em}.post-feed .post-header{margin:0 0 1.25em;padding-top:1.875em}.post-feed .post-title{font-size:1.5em;margin:0;padding-left:1em;padding-right:1em}.post-feed .post-excerpt{margin-bottom:1.25em;padding-left:1.5em;padding-right:1.5em}.post-feed .read-more{margin:0;padding-left:1.5em;padding-right:1.5em}.post-feed .read-more-link{font-weight:700;text-decoration:none}.post-feed .read-more-link:after{font-size:1.125em;content:"\2192";line-height:1.5;margin-left:5px}.post-feed .read-more-link:hover{color:#424b5f}@media only screen and (min-width:741px){.has-gradient .page-title,.has-gradient .post-title{font-size:3em}.page-subtitle,.post-subtitle{font-size:1.25em}.post-full .post-meta{font-size:1.125em}.post-feed .post-excerpt,.post-feed .post-meta,.post-feed .post-title,.post-feed .read-more,.post-full .post-content{padding-left:7%;padding-right:7%}}@media only screen and (max-width:1200px){.post{margin-bottom:4vw}}.docs-content{padding-top:2.5em}.post.type-docs{margin-bottom:5.625em;max-width:800px}.post.type-docs h1{font-size:1.875em}.post.type-docs h2{font-size:1.5em}.post.type-docs h3{font-size:1.25em}.post.type-docs h4{font-size:1.125em}.post.type-docs h5,.post.type-docs h6{font-size:1em}.post.type-docs .hash-link{float:left;font-size:1.25rem;height:1em;line-height:1;margin-left:-1.1em;opacity:0;text-align:center;text-decoration:none;transition:opacity .2s;width:1em}.post.type-docs .hash-link:before{content:"#";display:inline-block}.post.type-docs .hash-link:focus,.post.type-docs .hash-link:hover{color:#00c6ff}.post.type-docs h2 .hash-link{margin-top:.22em}.post.type-docs h3 .hash-link{margin-top:.1em}.post.type-docs h2:focus .hash-link,.post.type-docs h2:hover .hash-link,.post.type-docs h3:focus .hash-link,.post.type-docs h3:hover .hash-link{opacity:1}.post.type-docs .post-inside{background:#fff;border:1px solid #dde0e7;border-radius:5px;box-shadow:0 1px 2px 0 rgba(0,0,0,.13);padding:2.5em 0}.post.type-docs .post-title{font-size:1.875em;margin:0 0 1.25em;padding:0 1em}.post.type-docs .post-content{padding:0 1.875em}#docs-section-items{display:flex;flex-wrap:wrap;list-style:none;margin-left:-.3125em;margin-right:-.3125em;padding:0}#docs-section-items .docs-section-item{flex:1 1 240px;margin:0 .3125em .9375em}#docs-section-items .docs-item-link{border:1px solid #dde0e7;border-radius:3px;color:#283040;display:block;font-weight:700;padding:.9375em;position:relative;text-decoration:none;transition:border-color .3s ease,color .3s ease}#docs-section-items .docs-item-link:hover{border-color:#00c6ff;color:#00c6ff}.docs-nav{margin-bottom:1.875em}.docs-nav .docs-nav-toggle{color:#283040;font-size:1.125em;margin:0;padding-right:30px;text-align:left;width:100%}.docs-nav .docs-submenu-toggle{color:#67758d;position:absolute;right:0;top:0}#docs-menu{color:#283040;font-weight:700;line-height:1.5;list-style:none;margin:0;padding:0}#docs-menu>.docs-menu-item>a{padding:.1875em 0}#docs-menu a{color:inherit;display:block;text-decoration:none}#docs-menu .current,#docs-menu .current-parent,#docs-menu a:hover{color:#00c6ff}.docs-submenu{border-left:1px solid #dde0e7;color:#424b5f;display:none;font-size:.9375em;font-weight:400;list-style:none;margin-top:.625rem;padding-left:1.25rem}.docs-menu-item{color:inherit;margin-bottom:.625rem}.docs-menu-item.has-children{padding-right:30px;position:relative}.docs-menu-item.has-children.active .docs-submenu{display:block}.docs-menu-item.has-children.active>.docs-submenu-toggle .icon-angle-right{-webkit-transform:rotate(135deg);transform:rotate(135deg)}#page-nav{display:none}#page-nav .page-nav-title{font-size:1em;margin:0 0 .625em}#page-nav ul{font-size:.875rem;line-height:1.5;list-style:none;padding:0}#page-nav ul ul{border-left:1px solid #dde0e7;margin-top:.625rem;padding-left:1.25rem}#page-nav li{margin-bottom:.625rem}#page-nav li.active>a{color:#00c6ff}#page-nav a{color:#424b5f;display:block;text-decoration:none}#page-nav a:hover{color:#00c6ff}#page-nav .page-nav-inside{display:none}#page-nav .page-nav-inside.has-links{display:block}@media only screen and (min-width:841px){.post.type-docs .post-content,.post.type-docs .post-title{padding-left:7%;padding-right:7%}}@media only screen and (min-width:1001px){.docs-content{display:flex;padding-top:3.75em}.post.type-docs{flex:1 1 auto;overflow:hidden}.docs-nav,.page-nav{flex-shrink:0;margin-bottom:5.625em}.docs-nav .sticky,.page-nav .sticky{position:-webkit-sticky;position:sticky;top:1.875em}.docs-nav{padding-right:1.5em;width:12.5em}#page-nav{padding-left:1.5em;width:9.5em}#docs-nav-toggle{display:none}}@media only screen and (min-width:1291px){#page-nav{display:block}}@media only screen and (max-width:1000px){.docs-nav{background:#fff;border:1px solid #dde0e7;border-radius:5px;box-shadow:0 1px 2px 0 rgba(0,0,0,.13);box-sizing:border-box;margin-bottom:5%;padding:.75em 1em}.docs-nav-menu{display:none}.docs-menu--opened .docs-nav-menu{display:block}.docs-menu--opened .docs-nav-toggle .icon-angle-right{-webkit-transform:rotate(135deg);transform:rotate(135deg)}#docs-menu{border-top:1px solid #dde0e7;margin-top:1.25em;padding-top:1.25em}}.block{padding-top:3.75em}.block:not(.block-hero){background:#f8f8fa}.block:last-child{padding-bottom:3.75em}.block-header,.block-image{margin-bottom:1.5em}.block-title{margin:0}.block-subtitle{color:#67758d;line-height:1.5;margin-bottom:0}.block-subtitle:not(:first-child){margin-top:.5em}.block-buttons,.grid-item-buttons{align-items:center;display:flex;flex-wrap:wrap;margin-bottom:.9375em}.block-buttons a,.grid-item-buttons a{font-weight:700;text-decoration:none}.block-buttons{justify-content:center}.block-buttons a{margin:0 .375em .75em}.grid-item-buttons a{margin:0 .75em .75em 0}.has-gradient .block-subtitle{color:inherit}.block-hero .block-buttons:not(:first-child),.block-text .block-buttons:not(:first-child){margin-top:1.875em}.block-text .grid-item{max-width:680px;text-align:center}.block-text .block-title{font-size:1.875em}@media only screen and (min-width:641px){.block-text .block-content{font-size:1.125em}.block-text .block-title{font-size:2.125em}}@media only screen and (min-width:1201px){.block-text .grid-item:not(:only-child){flex:0 0 50%;max-width:50%}.block-body:not(:only-child){text-align:left}.block-body:not(:only-child) .block-buttons{justify-content:flex-start}.block-body:not(:only-child) .block-buttons a{margin-left:0;margin-right:.75em}}@media only screen and (min-width:1001px){.block-image:not(:only-child){padding-right:2.5em}.grid-swap .block-image:not(:only-child){padding-left:2.5em;padding-right:.9375em}}.block-cta .has-gradient{border-radius:5px;margin-bottom:1.875em;padding:3.75em 3vw 1.875em}.block-cta .block-header{max-width:680px;text-align:center}.block-cta .block-title{font-size:1.875em}.block-cta .block-subtitle{font-size:1.125em}@media only screen and (min-width:641px){.block-title{font-size:2.125em}}@media only screen and (min-width:801px){.block-cta .has-gradient{padding-left:7%;padding-right:7%}.block-cta .block-header{flex:0 0 66.666%;max-width:66.666%;text-align:left}.block-cta .block-buttons{flex:0 0 33.333%;margin-top:0;max-width:33.333%}}.block-hero+.block-grid:not(.has-header){background:0;padding-top:0}.block-grid .block-header{margin-bottom:2em;text-align:center}.block-grid .block-title{font-size:1.875em}.block-grid .grid-item{display:flex;flex-direction:column;margin-bottom:1.875em}.grid-item-inside{background:#fff;border:1px solid #dde0e7;border-radius:3px;box-shadow:0 1px 2px 0 rgba(0,0,0,.13);box-sizing:border-box;flex-grow:1;padding-bottom:.75em}.grid-item-image{display:block;width:100%}.grid-item-image,.grid-item-image img{border-radius:3px 3px 0 0}.grid-item-title{font-size:1.5em;margin:1em 0 .5em;padding-left:1em;padding-right:1em}.grid-item-title:first-child{margin-top:1.25em}.grid-item-title a{color:inherit!important;text-decoration:none}.grid-item-buttons,.grid-item-content{padding-left:1.5em;padding-right:1.5em}.grid-item-content{margin-bottom:1.25em}.grid-item-buttons a:not(.button):after{font-size:1.125em;content:"\2192";line-height:1.5;margin-left:5px}@media only screen and (max-width:1000px){.block-grid .grid-item{margin-bottom:4vw}}.block-hero{padding-bottom:7.5em;position:relative;text-align:center}.block-hero .block-header{margin-bottom:.75em}.block-hero .block-title{font-size:2.25em}.block-hero .block-content{font-size:1.125em;line-height:1.5}.block-hero+.block{margin-top:-5em;position:relative}@media only screen and (min-width:641px){.block-hero .block-title{font-size:3em}.block-hero .block-content{font-size:1.25em}.block-hero .block-buttons a{font-size:1em}}.site-footer{background-color:#000;background-image:url(https://i.imgur.com/CEYEZp8.jpeg);padding-bottom:7.5em;padding-top:8.5em;color:#fff!important;border:4px solid #000}#colophon a:not(.button){color:inherit}#colophon a:not(.button):focus,#colophon a:not(.button):hover{color:#00c6ff}.site-info,.social-links{align-items:center;display:flex;flex-wrap:wrap;justify-content:center;font-size:.675em;line-height:1.2}.site-info .button:not(.button-icon),.social-links .button:not(.button-icon){font-size:inherit;line-height:1.2;padding:.3em 1em}.site-info{margin:.25em 0 0;text-align:center}.site-info .copyright,.site-info>a{margin:0 4px .2em 0}.social-links{margin-top:.5375em}.social-links a{margin:0 50px .2em}.social-links .icon{font-size:20px;color:#000;background-color:#000}@media only screen and (min-width:641px){.site-footer-inside{align-items:flex-start;display:flex}.site-info{text-align:left}.site-info,.social-links{justify-content:flex-start}.social-links{flex:0 0 auto;flex-wrap:nowrap;margin-left:auto;margin-top:0}.social-links a{margin-left:20px;margin-right:0}}.palette-green a:not(.button){color:#20c86e}.palette-green a:not(.button):hover{color:#424b5f}.palette-green blockquote{border-color:#20c86e}.palette-green .button,.palette-green .line-left:after{background:#20c86e}.palette-green .has-gradient{background:#20c86e;background:linear-gradient(90deg,#1ba65b,#20c86e)}.palette-green #colophon a:not(.button):hover,.palette-green #docs-menu .current,.palette-green #docs-menu .current-parent,.palette-green #docs-menu a:hover,.palette-green #masthead a:not(.button):hover,.palette-green #page-nav a:hover,.palette-green #page-nav li.active>a,.palette-green .button-icon:active,.palette-green .button-icon:focus,.palette-green .button-icon:hover,.palette-green .button-secondary,.palette-green .has-gradient .button:not(.button-secondary),.palette-green .menu-item.current,.palette-green .post.type-docs .hash-link:focus,.palette-green .post.type-docs .hash-link:hover{color:#20c86e}.palette-green #docs-section-items .docs-item-link:hover{border-color:#20c86e;color:#20c86e}.palette-navy a:not(.button){color:#1b2024}.palette-navy a:not(.button):hover{color:#424b5f}.palette-navy blockquote{border-color:#1b2024}.palette-navy .button,.palette-navy .line-left:after{background:#1b2024}.palette-navy .has-gradient{background:#1b2024;background:linear-gradient(90deg,#000428,#1b2024)}.palette-navy #colophon a:not(.button):hover,.palette-navy #docs-menu .current,.palette-navy #docs-menu .current-parent,.palette-navy #docs-menu a:hover,.palette-navy #masthead a:not(.button):hover,.palette-navy #page-nav a:hover,.palette-navy #page-nav li.active>a,.palette-navy .button-icon:active,.palette-navy .button-icon:focus,.palette-navy .button-icon:hover,.palette-navy .button-secondary,.palette-navy .has-gradient .button:not(.button-secondary),.palette-navy .menu-item.current,.palette-navy .post.type-docs .hash-link:focus,.palette-navy .post.type-docs .hash-link:hover{color:#1b2024}.palette-navy #docs-section-items .docs-item-link:hover{border-color:#1b2024;color:#1b2024}.palette-violet a:not(.button){color:#8e2de2}.palette-violet a:not(.button):hover{color:#424b5f}.palette-violet blockquote{border-color:#8e2de2}.palette-violet .button,.palette-violet .line-left:after{background:#8e2de2}.palette-violet .has-gradient{background:#8e2de2;background:linear-gradient(90deg,#4a00e0,#8e2de2)}.palette-violet #colophon a:not(.button):hover,.palette-violet #docs-menu .current,.palette-violet #docs-menu .current-parent,.palette-violet #docs-menu a:hover,.palette-violet #masthead a:not(.button):hover,.palette-violet #page-nav a:hover,.palette-violet #page-nav li.active>a,.palette-violet .button-icon:active,.palette-violet .button-icon:focus,.palette-violet .button-icon:hover,.palette-violet .button-secondary,.palette-violet .has-gradient .button:not(.button-secondary),.palette-violet .menu-item.current,.palette-violet .post.type-docs .hash-link:focus,.palette-violet .post.type-docs .hash-link:hover{color:#8e2de2}.palette-violet #docs-section-items .docs-item-link:hover{border-color:#8e2de2;color:#8e2de2}code[class*=language-],pre[class*=language-]{-moz-tab-size:4;-o-tab-size:4;tab-size:4;-webkit-hyphens:none;-ms-hyphens:none;hyphens:none}:not(pre)>code[class*=language-]{background:#283040;color:#f8f8fa}.token.cdata,.token.comment,.token.doctype,.token.prolog{color:#8292a2}.token.punctuation{color:#f8f8f2}.token.namespace{opacity:.7}.token.constant,.token.deleted,.token.property,.token.symbol,.token.tag{color:#f92672}.token.boolean,.token.number{color:#ae81ff}.token.attr-name,.token.builtin,.token.char,.token.inserted,.token.selector,.token.string{color:#a6e22e}.language-css .token.string,.style .token.string,.token.entity,.token.operator,.token.url,.token.variable{color:#f8f8f2}.token.atrule,.token.attr-value,.token.class-name,.token.function{color:#e6db74}.token.keyword{color:#66d9ef}.token.important,.token.regex{color:#fd971f}.token.bold,.token.important{font-weight:700}.token.italic{font-style:italic}.token.entity{cursor:help}div.code-toolbar{position:relative}div.code-toolbar>.toolbar{position:absolute;top:0;right:0}div.code-toolbar>.toolbar .toolbar-item{display:block}div.code-toolbar>.toolbar a{border:0;cursor:pointer}div.code-toolbar>.toolbar button{background:none;border:0;border-radius:0;box-shadow:none;color:inherit;font:inherit;line-height:normal;overflow:visible;padding:0;user-select:none;-webkit-user-select:none;-moz-user-select:none;-ms-user-select:none}div.code-toolbar>.toolbar a,div.code-toolbar>.toolbar button,div.code-toolbar>.toolbar span{background:#424b5f;color:#dde0e7!important;display:block;font-size:.75em;line-height:1.5;padding:.25em .5em;text-decoration:none}</style><meta name="generator" content="Gatsby 2.25.4"/><title data-react-helmet="true">Web-Dev-Hub</title><link data-react-helmet="true" rel="preconnect" href="https://fonts.gstatic.com"/><link data-react-helmet="true" href="https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,400;0,700;1,400;1,700&amp;display=swap" rel="stylesheet"/><link data-react-helmet="true" rel="icon" href="/images/enhanced (1).png"/><meta data-react-helmet="true" charSet="utf-8"/><meta data-react-helmet="true" name="viewport" content="width=device-width, initialScale=1.0"/><meta data-react-helmet="true" name="description" content="bigO, Python, Javascript, Audio, Processing, Learning, Blog, React,
PostgreSQL, Scope, Closure, Web Development, Embed, API, Website, Design,
Music, Search"/><meta data-react-helmet="true" property="og:type" content="website"/><meta data-react-helmet="true" property="og:title" content="Web-Dev-Hub"/><meta data-react-helmet="true" property="og:description" content="my resource sharing and blog site ... centered mostly on web development
and just a bit of audio production / generally nerdy things I find
interesting."/><meta data-react-helmet="true" property="og:image" content="https://bgoonz-blog.netlify.app/images/code.png"/><meta data-react-helmet="true" name="twitter:card" content="summary_large_image"/><meta data-react-helmet="true" name="twitter:title" content="Web-Dev-Hub"/><meta data-react-helmet="true" name="twitter:description" content="Web-Dev-Hub"/><meta data-react-helmet="true" name="twitter:image" content="https://bgoonz-blog.netlify.app/images/4.jpg"/><link as="script" rel="preload" href="/webpack-runtime-b44c81ace70ed7d12455.js"/><link as="script" rel="preload" href="/framework-e132d18971612bcf60f3.js"/><link as="script" rel="preload" href="/dc6a8720040df98778fe970bf6c000a41750d3ae-8ef9d1d2adaff6ba0f59.js"/><link as="script" rel="preload" href="/app-10180cc44b3853f61402.js"/><link as="script" rel="preload" href="/styles-7d4153d260c0197f0043.js"/><link as="script" rel="preload" href="/29107295-e9457ed2135dcbbf6ce8.js"/><link as="script" rel="preload" href="/commons-16acaa872427dabf43ef.js"/><link as="script" rel="preload" href="/component---src-templates-advanced-js-6f213d193b5ecf8f0dd1.js"/><link as="fetch" rel="preload" href="/page-data/index/page-data.json" crossorigin="anonymous"/><link as="fetch" rel="preload" href="/page-data/app-data.json" crossorigin="anonymous"/><style>blockquote,
body,
dd,
dl,
figcaption,
figure,
h1,
h2,
h3,
h4,
h5,
li,
ol[class],
p,
ul[class] {
  margin: 0
}

body {
  min-height: 110vh;
  scroll-behavior: smooth;
  text-rendering: optimizeSpeed;
  line-height: 1.6
}





article>*+* {
  margin-top: 1em
}

button,
input,
select,
textarea {
  font: inherit
}

@media(prefers-reduced-motion:reduce) {
  * {
    animation-duration: .01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: .01ms !important;
    scroll-behavior: auto !important
  }
}

html {
  box-sizing: border-box;
}

body {
  font-family: arial, x-locale-body, sans-serif;
  letter-spacing: -.0027777778rem;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 100%;
  line-height: 1.75
}

img {
  height: auto
}

@font-face {
  font-display: swap;
  font-family: zillaslab;
  font-style: normal;
  font-weight: 700;
  src: url(/static/media/ZillaSlab-Bold.subset.0beac26b.woff2) format("woff2"), url(/static/media/ZillaSlab-Bold.subset.72026b3c.woff) format("woff")
}

@font-face {
  font-display: swap;
  font-family: zillaslab;
  font-style: normal;
  font-weight: 400;
  src: url(/static/media/ZillaSlab-Regular.subset.ce3a756d.woff2) format("woff2"), url(/static/media/ZillaSlab-Regular.subset.7e4c05c9.woff) format("woff")
}

h1,
h2,
h3 {
  font-family: zillaslab, palatino, "Palatino Linotype", serif;
  line-height: 1.2
}

h1 {
  font-size: 1.802rem
}

@media (min-width:47.9385em) {
  h1 {
    font-size: 3.052rem
  }
}

h2 {
  font-size: 1.602rem
}

@media (min-width:47.9385em) {
  h2 {
    font-size: 2.441rem
  }
}

h3 {
  font-size: 1.424rem;


  font-family: zillaslab, palatino, "Palatino Linotype", serif;
  font-weight: 400;
  max-width: -webkit-max-content;
  max-width: -moz-max-content;
  max-width: max-content;
  padding: 0 6px;
  margin: 24px 0
}

@media (min-width:47.9385em) {
  h3 {
    font-size: 1.953rem
  }
}

h4 {
  font-size: 1.266rem
}

@media (min-width:47.9385em) {
  h4 {
    font-size: 1.563rem
  }
}

h5 {
  font-size: 1.125rem
}

@media (min-width:47.9385em) {
  h5 {
    font-size: 1.25rem
  }
}

p {
  margin-bottom: 24px
}

a:link,
a:visited {

  text-decoration: none
}

a:link:active,
a:link:focus,
a:link:hover,
a:visited:active,
a:visited:focus,
a:visited:hover {
  text-decoration: underline
}

blockquote {
  max-width: 45rem;
  max-width: 85ch;
  font-size: 1.125rem;
  font-family: zillaslab, palatino, "Palatino Linotype", serif;
  font-weight: 400;
  margin-bottom: 24px
}

@media (min-width:47.9385em) {
  blockquote {
    font-size: 1.25rem
  }
}

blockquote:after,
blockquote:before {
  background-image: linear-gradient(90deg, #00356a, #83d0f2);
  content: "";
  display: block;
  height: 5px;
  margin-bottom: 12px
}

blockquote:after {
  margin-top: 12px
}

blockquote p:last-of-type {
  margin-bottom: 0
}

a {

  text-decoration: none
}

a:focus,
a:hover {
  text-decoration: underline
}

a code {
  -webkit-text-decoration-skip-ink: none;
  text-decoration-skip-ink: none
}


dl dt {
  font-weight: 700
}

dl dd {
  margin: 0 24px 24px
}



</style><meta name="google-site-verification" content="q5W83EYchlVTyA-iYRE4ElQGcbD_vukQF0NKW12N3qU" />
<meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="apple-touch-icon" href="logo-circle.png">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta http-equiv="Content-Type" content="HTML">
  <meta name="Author" content="Bryan Guner">
  <meta name="keywords" content="HTML, Meta Tags, Metadata">
  <meta name="description" content="Learning about Web Development.">
  <link type="image/x-icon" href="./favicon.ico" rel="shortcut icon">
  <meta http-equiv="Content-Type" content="text/html; charset=us-ascii">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, shrink-to-fit=no">
  <meta name="twitter:card" content="summary">
  <meta name="twitter:site" content="@bgoonz">
  <meta name="twitter:creator" content="@bgoonz">
  <meta name="twitter:image:src" content="/logo-circle.png">
  <meta name="twitter:title" content="Web Development Resource Hub Bryan Guner">
  <meta name="twitter:description" content="The new home of my blog resource sharing website.">
<meta property="twitter:card" content="summary_large_image">
  <link
    href="https://instructure-uploads-pdx.s3.us-west-2.amazonaws.com/account_168550000000000001/attachments/537/logo-canvas.png"
    rel="apple-touch-icon">
  <link type="text/css" href="https://fonts.googleapis.com/css?family=Raleway:200,100,400" rel="stylesheet">
<meta property="og:image" content="https://mugshotbot.com/m/DROicc16"><script id="mcjs">!function(c,h,i,m,p){m=c.createElement(h),p=c.getElementsByTagName(h)[0],m.async=1,m.src=i,p.parentNode.insertBefore(m,p)}(document,"script","https://chimpstatic.com/mcjs-connected/js/users/a41d8352dc1deaf4533662699/28d2370bb66d456a5d6411971.js");</script><script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.3/dist/umd/popper.min.js" integrity="sha384-W8fXfP3gkOKtndU4JGtKDvXbO53Wy8SZCQHczT5FMiiqmQfUpWbYdTil/SxwZgAN" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.1/dist/js/bootstrap.min.js" integrity="sha384-skAcpIdS7UcVUC05LJ9Dxay8AXcDYfBJqt1CJ85S/CFujBsIzCIv+l9liuYLaMQ/" crossorigin="anonymous"></script><!-- Insert makerbadge.js (download or use ☁️cloud version) -->

<script type="text/javascript" src="https://makerbadge.s3.amazonaws.com/blmbadge.js"></script>

<!-- Initialise MakerBadge with options -->

<script>
  BLMBadge.init({
       layout:1,
       theme:'dark',
       promoText : 'Send a donation '+String.fromCodePoint(0x2192),
       promoLink : 'https://minnesotafreedomfund.org/',
       message : 'To be silent is to be complicit. Black lives matter.',
       title : '#BlackLivesMatter',
       imageAlt: "Black Lives Matter Badge"
})
</script><script>"use strict";

!function() {
    var t = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjYxZTQzZmFlY2I2NjkwNWMyZGJkMGVmZCIsInRva2VuVHlwZSI6InB1YmxpYyIsImlhdCI6MTY0MjM0ODUyNiwiZXhwIjoxNDI1Njc0ODUyNn0.VD7Lxgh5cWuOzOhV9KH51TZVdPVXvsIJgRUx-oacfVM";
    function e() {
        var e = document.createElement("script"), a = navigator.language || navigator.userLanguage;
        e.type = "text/javascript", e.async = !0, e.src = "https://api.searchbar.org/v1/widget/" + t + "/" + a;
        var n = document.getElementsByTagName("script")[0];
        n.parentNode.insertBefore(e, n);
    }
    "complete" === document.readyState ? e() : window.attachEvent ? window.attachEvent("onload", e) : window.addEventListener("load", e, !1);
}();</script><style>
		@font-face {
            font-family: font-sb;
            src: url(https://api.searchbar.org/fonts/sb.eot?39450784);
            src: url(https://api.searchbar.org/fonts/sb.eot?39450784#iefix) format('embedded-opentype'), url(https://api.searchbar.org/fonts/sb.woff?39450784) format('woff'), url(https://api.searchbar.org/fonts/?39450784) format('truetype'), url(https://api.searchbar.org/fonts/sb.svg?39450784#font-sb) format('svg');
            font-weight: 400;
            font-style: normal
        }

        #sb-search-example p {
            font-family: sans-serif;
            font-size: 18px;
            line-height: 12px;
	        margin: 0;
        }

        #sb-search-example {
            position: static;
            bottom: 0;
            width: auto;
            place-content: center;
            display: inline-block;
            box-shadow: 0px 2px 4px rgba(190, 190, 190, 0.5);
            border: solid 5px white;
            border-radius: 100px;
            flex-shrink: initial;
            flex-grow: initial;
        }


        #sb-search-example .sb-icon {
            font: normal normal 400 26px font-sb;
            align-items: center;
            padding: 10px;
            speak: none;
            display: inline-block;
            text-decoration: inherit;
            text-align: center;
            text-transform: none;
            cursor: pointer;
            margin: 0;
        }

        #sb-search-example .sb-search-icon {
            box-sizing: border-box;
            border: 0px;
            align-items: center;
            background: #007cff;
            color: #fff;
            cursor: pointer;
            display: flex;
            border-radius: 26px;
            padding: 0 20px 0 4px;
        }
	</style><style>
#scrollBtn {
  display: none;
  position: fixed;
  bottom: 140px;
  right: 20px;
  z-index: 99;
  border: 1px black solid;
  outline: none;
  background-color: #044274;
  color: white;
  cursor: pointer;
  padding: 5px;
  border-radius: 28px;
  font-size: 12px;
}

#scrollBtn:hover {
  background-color: #ffffff;
color:#000000;
}

</style><style>
a {
  text-decoration: none;
  color: #007edf;
  text-shadow: none;

  transition: color 0.5s ease;
  transition: text-shadow 0.5s ease;
  -webkit-transition: color 0.5s ease;
  -webkit-transition: text-shadow 0.5s ease;
  -moz-transition: color 0.5s ease;
  -moz-transition: text-shadow 0.5s ease;
  -o-transition: color 0.5s ease;
  -o-transition: text-shadow 0.5s ease;
  -ms-transition: color 0.5s ease;
  -ms-transition: text-shadow 0.5s ease;
}
a:hover, a:focus {text-decoration: underline;}

footer a {
  color: #F2F2F2;
  text-decoration: underline;
}

em {
  font-style: italic;
}

strong {
  font-weight: bold;
}
pre {
  width: 100%;
  padding: 10px;
  box-shadow: 0 0 10px rgba(0,0,0,.1);
  overflow: auto;
}

code {
  padding: 3px;
  margin: 0 3px;
  box-shadow: 0 0 10px rgba(0,0,0,.1);
}

pre code {
  display: block;
  box-shadow: none;
}

blockquote {
  color: #666;
  margin-bottom: 20px;
  padding: 0 0 0 20px;
  border-left: 3px solid #bbb;
}
</style><script>

/*! lazysizes - v5.3.2 */

!function(e){var t=function(u,D,f){"use strict";var k,H;if(function(){var e;var t={lazyClass:"lazyload",loadedClass:"lazyloaded",loadingClass:"lazyloading",preloadClass:"lazypreload",errorClass:"lazyerror",autosizesClass:"lazyautosizes",fastLoadedClass:"ls-is-cached",iframeLoadMode:0,srcAttr:"data-src",srcsetAttr:"data-srcset",sizesAttr:"data-sizes",minSize:40,customMedia:{},init:true,expFactor:1.5,hFac:.8,loadMode:2,loadHidden:true,ricTimeout:0,throttleDelay:125};H=u.lazySizesConfig||u.lazysizesConfig||{};for(e in t){if(!(e in H)){H[e]=t[e]}}}(),!D||!D.getElementsByClassName){return{init:function(){},cfg:H,noSupport:true}}var O=D.documentElement,i=u.HTMLPictureElement,P="addEventListener",$="getAttribute",q=u[P].bind(u),I=u.setTimeout,U=u.requestAnimationFrame||I,o=u.requestIdleCallback,j=/^picture$/i,r=["load","error","lazyincluded","_lazyloaded"],a={},G=Array.prototype.forEach,J=function(e,t){if(!a[t]){a[t]=new RegExp("(\\s|^)"+t+"(\\s|$)")}return a[t].test(e[$]("class")||"")&&a[t]},K=function(e,t){if(!J(e,t)){e.setAttribute("class",(e[$]("class")||"").trim()+" "+t)}},Q=function(e,t){var a;if(a=J(e,t)){e.setAttribute("class",(e[$]("class")||"").replace(a," "))}},V=function(t,a,e){var i=e?P:"removeEventListener";if(e){V(t,a)}r.forEach(function(e){t[i](e,a)})},X=function(e,t,a,i,r){var n=D.createEvent("Event");if(!a){a={}}a.instance=k;n.initEvent(t,!i,!r);n.detail=a;e.dispatchEvent(n);return n},Y=function(e,t){var a;if(!i&&(a=u.picturefill||H.pf)){if(t&&t.src&&!e[$]("srcset")){e.setAttribute("srcset",t.src)}a({reevaluate:true,elements:[e]})}else if(t&&t.src){e.src=t.src}},Z=function(e,t){return(getComputedStyle(e,null)||{})[t]},s=function(e,t,a){a=a||e.offsetWidth;while(a<H.minSize&&t&&!e._lazysizesWidth){a=t.offsetWidth;t=t.parentNode}return a},ee=function(){var a,i;var t=[];var r=[];var n=t;var s=function(){var e=n;n=t.length?r:t;a=true;i=false;while(e.length){e.shift()()}a=false};var e=function(e,t){if(a&&!t){e.apply(this,arguments)}else{n.push(e);if(!i){i=true;(D.hidden?I:U)(s)}}};e._lsFlush=s;return e}(),te=function(a,e){return e?function(){ee(a)}:function(){var e=this;var t=arguments;ee(function(){a.apply(e,t)})}},ae=function(e){var a;var i=0;var r=H.throttleDelay;var n=H.ricTimeout;var t=function(){a=false;i=f.now();e()};var s=o&&n>49?function(){o(t,{timeout:n});if(n!==H.ricTimeout){n=H.ricTimeout}}:te(function(){I(t)},true);return function(e){var t;if(e=e===true){n=33}if(a){return}a=true;t=r-(f.now()-i);if(t<0){t=0}if(e||t<9){s()}else{I(s,t)}}},ie=function(e){var t,a;var i=99;var r=function(){t=null;e()};var n=function(){var e=f.now()-a;if(e<i){I(n,i-e)}else{(o||r)(r)}};return function(){a=f.now();if(!t){t=I(n,i)}}},e=function(){var v,m,c,h,e;var y,z,g,p,C,b,A;var n=/^img$/i;var d=/^iframe$/i;var E="onscroll"in u&&!/(gle|ing)bot/.test(navigator.userAgent);var _=0;var w=0;var M=0;var N=-1;var L=function(e){M--;if(!e||M<0||!e.target){M=0}};var x=function(e){if(A==null){A=Z(D.body,"visibility")=="hidden"}return A||!(Z(e.parentNode,"visibility")=="hidden"&&Z(e,"visibility")=="hidden")};var W=function(e,t){var a;var i=e;var r=x(e);g-=t;b+=t;p-=t;C+=t;while(r&&(i=i.offsetParent)&&i!=D.body&&i!=O){r=(Z(i,"opacity")||1)>0;if(r&&Z(i,"overflow")!="visible"){a=i.getBoundingClientRect();r=C>a.left&&p<a.right&&b>a.top-1&&g<a.bottom+1}}return r};var t=function(){var e,t,a,i,r,n,s,o,l,u,f,c;var d=k.elements;if((h=H.loadMode)&&M<8&&(e=d.length)){t=0;N++;for(;t<e;t++){if(!d[t]||d[t]._lazyRace){continue}if(!E||k.prematureUnveil&&k.prematureUnveil(d[t])){R(d[t]);continue}if(!(o=d[t][$]("data-expand"))||!(n=o*1)){n=w}if(!u){u=!H.expand||H.expand<1?O.clientHeight>500&&O.clientWidth>500?500:370:H.expand;k._defEx=u;f=u*H.expFactor;c=H.hFac;A=null;if(w<f&&M<1&&N>2&&h>2&&!D.hidden){w=f;N=0}else if(h>1&&N>1&&M<6){w=u}else{w=_}}if(l!==n){y=innerWidth+n*c;z=innerHeight+n;s=n*-1;l=n}a=d[t].getBoundingClientRect();if((b=a.bottom)>=s&&(g=a.top)<=z&&(C=a.right)>=s*c&&(p=a.left)<=y&&(b||C||p||g)&&(H.loadHidden||x(d[t]))&&(m&&M<3&&!o&&(h<3||N<4)||W(d[t],n))){R(d[t]);r=true;if(M>9){break}}else if(!r&&m&&!i&&M<4&&N<4&&h>2&&(v[0]||H.preloadAfterLoad)&&(v[0]||!o&&(b||C||p||g||d[t][$](H.sizesAttr)!="auto"))){i=v[0]||d[t]}}if(i&&!r){R(i)}}};var a=ae(t);var S=function(e){var t=e.target;if(t._lazyCache){delete t._lazyCache;return}L(e);K(t,H.loadedClass);Q(t,H.loadingClass);V(t,B);X(t,"lazyloaded")};var i=te(S);var B=function(e){i({target:e.target})};var T=function(e,t){var a=e.getAttribute("data-load-mode")||H.iframeLoadMode;if(a==0){e.contentWindow.location.replace(t)}else if(a==1){e.src=t}};var F=function(e){var t;var a=e[$](H.srcsetAttr);if(t=H.customMedia[e[$]("data-media")||e[$]("media")]){e.setAttribute("media",t)}if(a){e.setAttribute("srcset",a)}};var s=te(function(t,e,a,i,r){var n,s,o,l,u,f;if(!(u=X(t,"lazybeforeunveil",e)).defaultPrevented){if(i){if(a){K(t,H.autosizesClass)}else{t.setAttribute("sizes",i)}}s=t[$](H.srcsetAttr);n=t[$](H.srcAttr);if(r){o=t.parentNode;l=o&&j.test(o.nodeName||"")}f=e.firesLoad||"src"in t&&(s||n||l);u={target:t};K(t,H.loadingClass);if(f){clearTimeout(c);c=I(L,2500);V(t,B,true)}if(l){G.call(o.getElementsByTagName("source"),F)}if(s){t.setAttribute("srcset",s)}else if(n&&!l){if(d.test(t.nodeName)){T(t,n)}else{t.src=n}}if(r&&(s||l)){Y(t,{src:n})}}if(t._lazyRace){delete t._lazyRace}Q(t,H.lazyClass);ee(function(){var e=t.complete&&t.naturalWidth>1;if(!f||e){if(e){K(t,H.fastLoadedClass)}S(u);t._lazyCache=true;I(function(){if("_lazyCache"in t){delete t._lazyCache}},9)}if(t.loading=="lazy"){M--}},true)});var R=function(e){if(e._lazyRace){return}var t;var a=n.test(e.nodeName);var i=a&&(e[$](H.sizesAttr)||e[$]("sizes"));var r=i=="auto";if((r||!m)&&a&&(e[$]("src")||e.srcset)&&!e.complete&&!J(e,H.errorClass)&&J(e,H.lazyClass)){return}t=X(e,"lazyunveilread").detail;if(r){re.updateElem(e,true,e.offsetWidth)}e._lazyRace=true;M++;s(e,t,r,i,a)};var r=ie(function(){H.loadMode=3;a()});var o=function(){if(H.loadMode==3){H.loadMode=2}r()};var l=function(){if(m){return}if(f.now()-e<999){I(l,999);return}m=true;H.loadMode=3;a();q("scroll",o,true)};return{_:function(){e=f.now();k.elements=D.getElementsByClassName(H.lazyClass);v=D.getElementsByClassName(H.lazyClass+" "+H.preloadClass);q("scroll",a,true);q("resize",a,true);q("pageshow",function(e){if(e.persisted){var t=D.querySelectorAll("."+H.loadingClass);if(t.length&&t.forEach){U(function(){t.forEach(function(e){if(e.complete){R(e)}})})}}});if(u.MutationObserver){new MutationObserver(a).observe(O,{childList:true,subtree:true,attributes:true})}else{O[P]("DOMNodeInserted",a,true);O[P]("DOMAttrModified",a,true);setInterval(a,999)}q("hashchange",a,true);["focus","mouseover","click","load","transitionend","animationend"].forEach(function(e){D[P](e,a,true)});if(/d$|^c/.test(D.readyState)){l()}else{q("load",l);D[P]("DOMContentLoaded",a);I(l,2e4)}if(k.elements.length){t();ee._lsFlush()}else{a()}},checkElems:a,unveil:R,_aLSL:o}}(),re=function(){var a;var n=te(function(e,t,a,i){var r,n,s;e._lazysizesWidth=i;i+="px";e.setAttribute("sizes",i);if(j.test(t.nodeName||"")){r=t.getElementsByTagName("source");for(n=0,s=r.length;n<s;n++){r[n].setAttribute("sizes",i)}}if(!a.detail.dataAttr){Y(e,a.detail)}});var i=function(e,t,a){var i;var r=e.parentNode;if(r){a=s(e,r,a);i=X(e,"lazybeforesizes",{width:a,dataAttr:!!t});if(!i.defaultPrevented){a=i.detail.width;if(a&&a!==e._lazysizesWidth){n(e,r,i,a)}}}};var e=function(){var e;var t=a.length;if(t){e=0;for(;e<t;e++){i(a[e])}}};var t=ie(e);return{_:function(){a=D.getElementsByClassName(H.autosizesClass);q("resize",t)},checkElems:t,updateElem:i}}(),t=function(){if(!t.i&&D.getElementsByClassName){t.i=true;re._();e._()}};return I(function(){H.init&&t()}),k={cfg:H,autoSizer:re,loader:e,init:t,uP:Y,aC:K,rC:Q,hC:J,fire:X,gW:s,rAF:ee}}(e,e.document,Date);e.lazySizes=t,"object"==typeof module&&module.exports&&(module.exports=t)}("undefined"!=typeof window?window:{});

</script></head><body class="palette-navy"><noscript id="gatsby-noscript">This app works best with JavaScript enabled.</noscript><div id="___gatsby"><div style="outline:none" tabindex="-1" id="gatsby-focus-wrapper"><div id="page" class="site"><header id="masthead" class="site-header outer"><br/><div class="inner"><div class="site-header-inside"><div class="site-branding"><p class="site-logo"><a aria-current="page" class="" href="/"><img src="https://d33wubrfki0l68.cloudfront.net/e5662f0d4f3e7730aea1a0faf7ff09ea20184700/6ca0b/images/dgqlkqjtmk.png" alt="webdevhub logo"/></a></p></div><nav id="main-navigation" class="site-navigation" aria-label="Main Navigation"><div class="site-nav-inside"><button id="menu-close" class="menu-toggle"><span class="screen-reader-text">Open Menu</span><span class="icon-close" aria-hidden="true"></span></button><ul class="menu"><li class="menu-item has-children menu-button"><a class="button" href="/docs/sitemap">Navigation</a><button class="submenu-toggle"><span class="icon-angle-right" aria-hidden="true"></span><span class="screen-reader-text">Sub-menu</span></button><ul class="submenu"><li class="menu-item menu-button"><a class="button" href="/docs">Docs</a></li><li class="menu-item menu-button"><a class="button" href="/showcase">Showcase</a></li><li class="menu-item menu-button"><a class="button" href="/docs/faq/contact">Contact!</a></li><li class="menu-item menu-button"><a target="_blank" rel="noopener " class="button" href="/docs/python/python-ds">Python</a></li><li class="menu-item menu-button"><a class="button" href="/javascript">JavaScript</a></li></ul></li><li class="menu-item has-children menu-button"><a target="_blank" rel="noopener " class="button" href="/blog/">Blog</a><button class="submenu-toggle"><span class="icon-angle-right" aria-hidden="true"></span><span class="screen-reader-text">Sub-menu</span></button><ul class="submenu"><li class="menu-item menu-button"><a href="https://bgoonz.blogspot.com/" target="_blank" rel="noopener " class="button">Blog-Post-Archive</a></li><li class="menu-item menu-button"><a href="https://blog-w-comments.vercel.app/" class="button">Top Blog Posts</a></li><li class="menu-item menu-button"><a target="_blank" rel="noopener " class="button" href="/blog/platform-docs/">platform docs</a></li><li class="menu-item menu-button"><a target="_blank" rel="noopener " class="button" href="/docs/articles/nodejs/">nodejs</a></li><li class="menu-item menu-button"><a class="button" href="/blogWcomments/">Blog w Comments</a></li></ul></li><li class="menu-item has-children menu-button"><a class="button" href="/docs/interview/job-search-nav/">Job Search</a><button class="submenu-toggle"><span class="icon-angle-right" aria-hidden="true"></span><span class="screen-reader-text">Sub-menu</span></button><ul class="submenu"><li class="menu-item menu-button"><a class="button" href="/interview/job-boards">Job Boards</a></li></ul></li><li class="menu-item has-children menu-button"><a target="_blank" rel="noopener " class="button" href="/docs/tools/Archive">Archive</a><button class="submenu-toggle"><span class="icon-angle-right" aria-hidden="true"></span><span class="screen-reader-text">Sub-menu</span></button><ul class="submenu"><li class="menu-item menu-button"><a href="https://github.com/bgoonz/Learning-Assets" target="_blank" rel="noopener " class="button">Resource-Archive-Server</a></li><li class="menu-item menu-button"><a href="https://lambda-resources.netlify.app/" class="button">Bootcamp Resources</a></li><li class="menu-item menu-button"><a href="https://web-dev-resource-hub.netlify.app/" target="_blank" rel="noopener " class="button">OG-Blog</a></li><li class="menu-item menu-button"><a class="button" href="/docs/gallery">Gallery</a></li><li class="menu-item menu-button"><a class="button" href="/docs">Top Repos</a></li><li class="menu-item menu-button"><a href="https://bryan-guner.gitbook.io/my-docs/" target="_blank" rel="noopener " class="button">MY_DOCS</a></li></ul></li><li class="menu-item has-children menu-button"><a target="_blank" rel="noopener " class="button" href="/docs/projects">Projects</a><button class="submenu-toggle"><span class="icon-angle-right" aria-hidden="true"></span><span class="screen-reader-text">Sub-menu</span></button><ul class="submenu"><li class="menu-item menu-button"><a href="https://potluck-landing.netlify.app/" target="_blank" rel="noopener " class="button">Potluck Planner</a></li><li class="menu-item menu-button"><a href="https://meditate42app.netlify.app/" target="_blank" rel="noopener " class="button">Meditation App</a></li><li class="menu-item menu-button"><a href="https://panoramic-eggplant-452e4.netlify.app/" target="_blank" rel="noopener " class="button">WebAudioLab</a></li><li class="menu-item menu-button"><a href="https://bgoonz.github.io/searchAwesome/" target="_blank" rel="noopener " class="button">SearchAwesome</a></li><li class="menu-item menu-button"><a href="https://bg-portfolio.netlify.app/" target="_blank" rel="noopener " class="button">Condensed -Portfolio</a></li><li class="menu-item menu-button"><a href="https://a.familypromiseservicetracker.dev/" target="_blank" rel="noopener " class="button">Family Promise Tracker</a></li><li class="menu-item menu-button"><a href="https://github.com/bgoonz/Revamped-Automatic-Guitar-Effect-Triggering" class="button">DTW-Guitar-FX-Automation</a></li><li class="menu-item menu-button"><a href="https://friendly-panda-b61ab.netlify.app/" class="button">Embeds Blog</a></li><li class="menu-item menu-button"><a href="https://bgoonz-blog-v3-0.netlify.app/" class="button">alt-blogs</a></li><li class="menu-item menu-button"><a href="https://bgoonz-games.netlify.app/" class="button">Games</a></li><li class="menu-item menu-button"><a href="https://bgoonz-blog-v3-0.netlify.app/" target="_blank" rel="noopener " class="button">Blog Backup</a></li><li class="menu-item menu-button"><a href="https://bgoonz-cv.netlify.app/" class="button">Cover Letter</a></li><li class="menu-item menu-button"><a href="https://project-portfolio42.netlify.app/" class="button">Project Centric</a></li><li class="menu-item menu-button"><a href="https://web-dev-hub.com/" target="_blank" rel="noopener " class="button">Wordpress Blog</a></li><li class="menu-item menu-button"><a href="https://project-portfolio42.netlify.app/" class="button">Project Portfolio Gallery</a></li><li class="menu-item menu-button"><a href="https://bgoonz.github.io/github-stats-website/" class="button">github-stats-website</a></li></ul></li><li class="menu-item has-children menu-button"><a class="button" href="/docs/tools">Tools</a><button class="submenu-toggle"><span class="icon-angle-right" aria-hidden="true"></span><span class="screen-reader-text">Sub-menu</span></button><ul class="submenu"><li class="menu-item menu-button"><a href="https://githtmlpreview.netlify.app/" target="_blank" rel="noopener " class="button">Github HTML Previewer</a></li><li class="menu-item menu-button"><a href="https://devtools42.netlify.app/" target="_blank" rel="noopener " class="button">Text Tools</a></li><li class="menu-item menu-button"><a href="https://ternary42.netlify.app/" target="_blank" rel="noopener " class="button">Ternary 2 If Else</a></li><li class="menu-item menu-button"><a href="https://determined-dijkstra-ee7390.netlify.app/" target="_blank" rel="noopener " class="button">Job Search Resources</a></li><li class="menu-item menu-button"><a href="https://github.com/bgoonz/web-dev-setup-checker" target="_blank" rel="noopener " class="button">Setup Checker</a></li><li class="menu-item menu-button"><a href="https://potluck-landing.netlify.app/" target="_blank" rel="noopener " class="button">PotluckPlanner</a></li><li class="menu-item menu-button"><a href="https://web-dev-interview-prep-quiz-website.netlify.app/" class="button">WebDev Quizzes</a></li><li class="menu-item menu-button"><a href="https://github.com/search/advanced" target="_blank" rel="noopener " class="button button-icon"><svg class="icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"></path></svg><span class="screen-reader-text">Github-Advanced-Search</span></a></li></ul></li></ul></div></nav><button id="menu-open" class="menu-toggle"><span class="screen-reader-text">Close Menu</span><span class="icon-menu" aria-hidden="true"></span></button></div></div><div><div id="search" class="gcse-search search"></div><a class="github-corner" href="https://github.com/bgoonz/BGOONZ_BLOG_2.0" aria-label="View source on Github"><svg aria-hidden="true" width="40" height="40" viewBox="0 0 250 250" style="z-index:100000;fill:black;color:#fff;position:fixed;top:0px;border:0;left:0px;transform:scale(-1.5, 1.5)"><path d="M0,0 L115,115 L130,115 L142,142 L250,250 L250,0 Z"></path><path class="octo-arm" d="M128.3,109.0 C113.8,99.7 119.0,89.6 119.0,89.6 C122.0,82.7 120.5,78.6 120.5,78.6 C119.2,72.0 123.4,76.3 123.4,76.3 C127.3,80.9 125.5,87.3 125.5,87.3 C122.9,97.6 130.6,101.9 134.4,103.2" fill="currentColor" style="transform-origin:130px 106px"></path><path class="octo-body" d="M115.0,115.0 C114.9,115.1 118.7,116.5 119.8,115.4 L133.7,101.6 C136.9,99.2 139.9,98.4 142.2,98.6 C133.8,88.0 127.5,74.4 143.8,58.0 C148.5,53.4 154.0,51.2 159.7,51.0 C160.3,49.4 163.2,43.6 171.4,40.1 C171.4,40.1 176.1,42.5 178.8,56.2 C183.1,58.6 187.2,61.8 190.9,65.4 C194.5,69.0 197.7,73.2 200.1,77.6 C213.8,80.2 216.3,84.9 216.3,84.9 C212.7,93.1 206.9,96.0 205.4,96.6 C205.1,102.4 203.0,107.8 198.3,112.5 C181.9,128.9 168.3,122.5 157.7,114.1 C157.9,116.9 156.7,120.9 152.7,124.9 L141.0,136.5 C139.8,137.7 141.6,141.9 141.8,141.8 Z" fill="currentColor"></path></svg></a></div></header><main id="content" class="site-content"><section id="Intro" class="block block-hero has-gradient outer"><div class="bg-img" style="background-image:url(&#x27;/images/api-c99e353f761d318322c853c03ebcf21b.gif&#x27;)"></div><div class="inner-sm"><div class="block-header"><h1 class="block-title">I am a musician, electrical engineer &amp; web developer</h1></div><div class="block-content"><p><strong>Please note that this website is in development and is often broken!</strong></p><p><a href="https://www.vagrantup.com/"></a><a href="mailto:bryan.guner@gmail.com"><img src="https://img.icons8.com/color/96/000000/gmail.png" alt=""/></a><a href="https://www.youtube.com/channel/UC9-rYyUMsnEBK8G8fCyrXXA/videos"><img src="https://img.icons8.com/color/96/000000/youtube.png" alt=""/></a><a href="https://www.instagram.com/bgoonz/?hl=en"><img src="https://img.icons8.com/color/96/000000/instagram-new.png" alt=""/></a><a href="https://www.pinterest.com/bryanguner/_saved/"><img src="https://img.icons8.com/color/96/000000/pinterest--v1.png" alt=""/></a><a href="https://www.linkedin.com/in/bryan-guner-046199128/"><img src="https://img.icons8.com/color/96/000000/linkedin.png" alt=""/></a></p><p><a href="https://webpack.js.org/"> </a><a href="https://www.adobe.com/products/xd.html"> </a></p><p><a href="https://app.netlify.com/sites/bgoonz-blog/deploys"><img src="https://api.netlify.com/api/v1/badges/a1b7ee1a-11a7-4bd2-a341-2260656e216f/deploy-status" alt="Netlify Status"/></a></p><p><a href="https://github.com/bgoonz/github-readme-activity-graph"><img src="https://activity-graph.herokuapp.com/graph?username=bgoonz&amp;custom_title=This%20is%20Bryans%20Activity&amp;hide_border=true&amp;theme=chartreuse-dark" alt="Bryans github activity graph"/></a></p><p><img src="https://readme-jokes.vercel.app/api" alt="Jokes"/></p><p><img src="https://img.shields.io/badge/-Python-05122A?style=flat&amp;logo=python" alt="Python"/> <img src="https://img.shields.io/badge/-HTML-05122A?style=flat&amp;logo=HTML5" alt="HTML"/> <img src="https://img.shields.io/badge/-CSS-05122A?style=flat&amp;logo=CSS3&amp;logoColor=1572B6" alt="CSS"/> <img src="https://img.shields.io/badge/-JavaScript-05122A?style=flat&amp;logo=javascript" alt="JavaScript"/><img src="https://img.shields.io/badge/-React-05122A?style=flat&amp;logo=react" alt="React"/> <img src="https://img.shields.io/badge/-Node.js-05122A?style=flat&amp;logo=node.js" alt="Node.js"/> <img src="https://img.shields.io/badge/-Visual%20Studio%20Code-05122A?style=flat&amp;logo=visual-studio-code&amp;logoColor=007ACC" alt="Visual Studio Code"/><img src="https://img.shields.io/badge/-Docker-05122A?style=flat&amp;logo=Docker" alt="Docker"/> <img src="https://img.shields.io/badge/-MongoDB-05122A?style=flat&amp;logo=mongodb" alt="MongoDB"/> <img src="https://img.shields.io/badge/-PostgreSQL-05122A?style=flat&amp;logo=postgresql" alt="PostgreSQL"/><img src="https://img.shields.io/badge/-Git-05122A?style=flat&amp;logo=git" alt="Git"/> <img src="https://img.shields.io/badge/-GitHub-05122A?style=flat&amp;logo=github" alt="GitHub"/> <img src="https://img.shields.io/badge/-GitLab-05122A?style=flat&amp;logo=gitlab" alt="GitLab"/> <img src="https://img.shields.io/badge/-Markdown-05122A?style=flat&amp;logo=markdown" alt="Markdown"/></p></div><div class="block-buttons"><a href="https://sidebar-blog.netlify.app/contact/" target="_blank" rel="noopener " class="button button-secondary">Contact</a></div></div></section><section id="features" class="block block-grid outer"><div class="inner"><div class="block-content"><div class="grid grid-col-3"><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/95d5a78ac385cbb2252b70cd416693630f06647a/11edd/images/outdated-packages-732a4523.png"/></div><h3 class="grid-item-title line-left"><a href="https://medium.com/star-gazers/a-quick-guide-to-big-o-notation-memoization-tabulation-and-sorting-algorithms-by-example-803ff193c522">A Quick Guide To Big O</a></h3><div class="grid-item-content"><p>Memoization, Tabulation, and Sorting Algorithms by Example
Why is looking at runtime not a reliable method of calculating time
complexity?</p></div><div class="grid-item-buttons"><a href="https://bgoonz-blog.netlify.app/docs/data-structures/big-o/">Get Started</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/b7d9a8db0d3618dc455abcd5a1eba992281ab78a/2f5a7/images/smiling-maple.png" alt="python"/></div><h3 class="grid-item-title line-left"><a href="https://levelup.gitconnected.com/python-study-guide-for-a-native-javascript-developer-5cfdf3d2bdfb">Python Guide</a></h3><div class="grid-item-content"><p><em>Python has a built in help function that let&#x27;s you see a description
of the source code without having to navigate to it… &quot;-SickNasty …
Autor Unknown&quot;  .</em></p></div><div class="grid-item-buttons"><a href="https://levelup.gitconnected.com/python-study-guide-for-a-native-javascript-developer-5cfdf3d2bdfb">View Posts</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/0632d060c928c60c91038c13991f85f0928bd723/edbf6/images/panoramic-owl.png"/></div><h3 class="grid-item-title line-left"><a href="https://github.com/bgoonz/Revamped-Automatic-Guitar-Effect-Triggering">Guitar Effects Triggering w DTW</a></h3><div class="grid-item-content"><div id="search"></div> <div id="search"></div></div><div class="grid-item-buttons"><a href="/docs/tools">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/a37b8bc089cdd775711785baf935f9b1c4e732b0/0b88f/images/successful-panda.gif" alt="img of dtw"/></div><h3 class="grid-item-title line-left"><a href="https://bryanguner.medium.com/introductory-react-part-2-cda01615a186">Beginner Guide React</a></h3><div class="grid-item-content"><p>As I learn to build web applications in React I will blog about it in
this series in an attempt to capture the questions that a complete
beginner might encounter that a more seasoned developer would take for
granted!</p></div><div class="grid-item-buttons"></div></div></div><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/f318a0bdc5403fb9b59683b46e3c9ec2d75d2ed2/7de75/images/pleasant-birch.png" alt="img of react"/></div><h3 class="grid-item-title line-left"><a href="https://dev.to/bgoonz/scope-and-context-in-javascript-5cma">Scope &amp; Closure</a></h3><div class="grid-item-content"><p>Scope &amp; Context in JS</p><p>The <strong>scope</strong> of a program in JavaScript is the set of variables that are available for use within the program. </p></div><div class="grid-item-buttons"></div></div></div><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/9af799c578c04eb82ec44952c6db4bf54e828720/765f1/images/7a8bc98e902a2f6dea90386cdfb154c2-2d55c637.png" alt="Every idea needs a medium"/></div><h3 class="grid-item-title line-left">Web Audio Daw</h3><div class="grid-item-content"><p>PostgreSQL Cheat Sheet, Everything You Need to Get Started With VSCode</p><ul><li>Extensions &amp; Resources, Super Simple Intro To HTML,  Understanding
Git... etc....</li></ul></div><div class="grid-item-buttons"></div></div></div></div></div></div></section><section id="interests" class="block block-grid outer has-header"><div class="inner"><div class="block-header inner-sm"><h2 class="block-title">Current Interests</h2><p class="block-subtitle">From github repositories to existential questions.</p></div><div class="block-content"><div class="grid grid-col-3"><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/beba3d8052852cedc7fd41d9d05b4dffd4ea1136/d32f7/images/spectacular-turmeric.png" alt="angolia"/></div><h3 class="grid-item-title line-left"><a href="https://www.algolia.com/doc/">Angolia</a></h3><div class="grid-item-content"><h2 id="full-text-search">Full Text Search</h2><p><a href="https://www.algolia.com/">Full Text Search</a></p><h2 id=""></h2></div><div class="grid-item-buttons"></div></div></div><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/589475503098710e5f2f3c1a381015f69e6b4760/0be4d/images/neural.png" alt="neural networks"/></div><h3 class="grid-item-title line-left"><a href="https://dev.to/bgoonz/everything-you-need-to-become-a-machine-learner-1cjp">Convolutional Neural Networks</a></h3><div class="grid-item-content"><p>Artificial neural networks, usually simply called neural networks, are computing systems vaguely inspired by the biological <a href="https://github.com/tensorflow/tensorflow">neural networks</a><img src="/_static/app-assets/neural.PNG" alt=""/></p></div><div class="grid-item-buttons"><a href="#">lorem-ipsum</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/f776b2f35588e0ab71789925ce9564924154c4cf/df9d3/images/jamstack.png" alt="jamstack"/></div><h3 class="grid-item-title line-left"><a href="/jamstack">Jamstack</a></h3><div class="grid-item-content"><blockquote><p>Why Jamstack Jamstack is the new standard architecture for the...</p></blockquote><p>**</p><blockquote><p><em>web. Using Git workflows and modern build tools, pre-rendered content
is served to a CDN and made dynamic through APIs and serverless
functions. Technologies in the stack include JavaScript frameworks,
Static Site Generators, Headless CMSs, and CDNs.</em></p></blockquote></div><div class="grid-item-buttons"></div></div></div><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/fb22b10eaa16e4ac0690115bf6c6987350d38d4b/13c10/images/eventloop.gif" alt="lorem-ipsum"/></div><h3 class="grid-item-title line-left"><a href="/lorem-ipsum">Asynchronous JavaScript</a></h3><div class="grid-item-content"><p>The term <strong>asynchronous</strong> refers to two or more objects or events <strong>not</strong> existing or happening at the same time (or multiple related things happening without waiting for the previous one to complete). In computing, the word &quot;asynchronous&quot; is used in two major contexts.</p></div><div class="grid-item-buttons"><a href="https://bgoonz-blog.netlify.app/docs/javascript/asyncjs/" target="_blank" rel="noopener " class="button button-secondary">lorem-ipsum</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/0acc9a99716e3820bc8a6fa4fc9a5988e380f214/932fa/images/njdev-219301cd.jpg" alt="nj-devils"/></div><h3 class="grid-item-title line-left"><a href="https://www.allaboutthejersey.com/">NJ Devils</a></h3><div class="grid-item-content"><h1 id="new-jersey-devils-hockey-team">New Jersey Devils Hockey Team</h1><h3 id="hockey-in-general">(Hockey in general)</h3><h2 id="team-identity">Team identity</h2><p><a href="https://en.wikipedia.org/wiki/File:OldDevils.png"><img src="https://upload.wikimedia.org/wikipedia/en/thumb/d/da/OldDevils.png/300px-OldDevils.png" alt=""/></a></p><p>The old green style jerseys used from 1982 to 1992The jerseys used from 1992 to 2017<a href="https://en.wikipedia.org/wiki/Sean_Avery">Sean Avery</a> of the <a href="https://en.wikipedia.org/wiki/New_York_Rangers">New York Rangers</a> attempts to distract Brodeur during the <a href="https://en.wikipedia.org/wiki/2008_Stanley_Cup_playoffs">2008 Stanley Cup playoffs</a>. The playoff series was the fifth to feature the <a href="https://en.wikipedia.org/wiki/Devils%E2%80%93Rangers_rivalry">Devils–Rangers rivalry</a>.</p></div><div class="grid-item-buttons"><a href="#">lorem-ipsum</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/c2ae8fae397ffc059312cb9e84ae23dd4bf774bd/00c7f/images/iter-c7508519.jpg" alt="Nuclear Fusion"/></div><h3 class="grid-item-title line-left"><a href="https://www.iter.org/">ITER Fusion Reactor Experiment (Southern France)</a></h3><div class="grid-item-content"><h1 id="break-even-nuclear-fusion-candidate">Break Even Nuclear Fusion Candidate</h1><p>In December, researchers at the Joint European Torus (JET) started
conducting fusion experiments with tritium — a rare and radioactive
isotope of hydrogen. The facility is a one-tenth-volume mock-up of the
US$22-billion ITER project and has the same doughnut-shaped &#x27;tokamak&#x27;
design — the world&#x27;s most developed approach to fusion energy. It is
the first time since 1997 that researchers have done experiments in a
tokamak with any significant amount of tritium.</p></div><div class="grid-item-buttons"><a href="https://www.iter.org/" target="_blank" rel="noopener " class="button button-secondary">Learn More</a></div></div></div></div></div></div></section><section id="features-two-col" class="block block-grid outer has-header"><div class="inner"><div class="block-header inner-sm"><h2 class="block-title">Resume &amp; Portfolio</h2></div><div class="block-content"><div class="grid grid-col-2"><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/b6e6b09f4479310dff86d8dd7af1b73762484f6a/fea3e/images/image-of-resume.png"/></div><h3 class="grid-item-title line-left"><a href="https://github.com/bgoonz/resume-cv-portfolio-samples/raw/master/2021-resume/bryan-guner-resume-2021.pdf">Resume</a></h3><div class="grid-item-buttons"><a href="https://1drv.ms/b/s!AkGiZ9n9CRDSpLsZsnPtiN7p77vq6A" class="button button-secondary">View In One Drive</a><a href="#">lorem-ipsum</a><a href="https://github.com/bgoonz/bgoonz/raw/master/bryan_guner_resume_2021_V9.pdf" class="button button-secondary">Download PDF</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><div class="grid-item-image"><img src="https://d33wubrfki0l68.cloudfront.net/4e66fa2888421bd225aa811c156362cc0b7d4ebc/0053d/images/portfolio-91689538.jpg" alt="portfolio of websites"/></div><h3 class="grid-item-title line-left">Showcase</h3><div class="grid-item-content"><p><img src="/_static/app-assets/lambda-demo1.gif" alt=""/>My Projects!</p></div><div class="grid-item-buttons"><a class="button button-secondary" href="/showcase">Learn More</a></div></div></div></div></div></div></section><section id="Mini Projects" class="block block-text outer"><div class="outter"><div class="inner"><div><div class="block-header"><h2 class="block-title">Blog-Archive-And-Mini-Projects</h2></div><div class="outer"><iframe src="https://random-static-html-deploys.netlify.app/" class="block-content" width="100%  width=" height="1000px!important"></iframe></div><div class="block-buttons"></div></div></div></div></section><section id="new content" class="block block-text outer"><div class="outter"><div class="inner grid-swap"><div class="grid-item block-image"><img src="/images/cool annimation.gif" alt="animated gif"/></div><div><div class="block-header"><h2 class="block-title">Latest &amp; Greatest</h2></div><div class="outer"><h1 id="what-ive-been-working-on-lately"><strong><em>What I&#x27;ve been working on lately:</em></strong></h1><h2 id="web-dev-utilitiy-tools">Web Dev Utilitiy Tools</h2><iframe class="block-content" width="100%  width=" height="1000px!important" src="https://web-dev-utility-tools-bgoonz.netlify.app/" frameBorder="0" allow="accelerometer; autoplay; clipboard-write;
  encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe><iframe class="block-content" width="100%  width=" height="1000px!important" src="https://cheatsheets-42.netlify.app/" frameBorder="0" allow="accelerometer; autoplay; clipboard-write;
  encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe><iframe class="block-content" width="100%  width=" height="1000px!important" src="https://bgoonz.github.io/fb-and-twitter-api-embeds/" frameBorder="0" allow="accelerometer; autoplay; clipboard-write;
  encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe></div><div class="block-buttons"></div></div></div></div></section><section id="tools" class="block block-text outer"><div class="outter"><div class="inner"><div><div class="block-header"><h2 class="block-title">Tools Showcase</h2></div><div class="outer"><p><img src="https://d33wubrfki0l68.cloudfront.net/02b9891f907ff34d41158a8db479618a8f790be2/7fc1d/images/static-server-5bf5ad2d.png" alt=""/>Tool Showcase</p><iframe class="block-content" width="100%  width=" height="1000px!important" src="https://bgoonz.github.io/fb-and-twitter-api-embeds/" frameBorder="0" allow="accelerometer; autoplay; clipboard-write;
  encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe></div><div class="block-buttons"></div></div></div></div></section><section id="Web Audio DAW" class="block block-text outer"><div class="outter"><div class="inner"><div class="grid-item block-image"><img src="https://d33wubrfki0l68.cloudfront.net/e5828552ff6b5743ed241d9c926e60eb925dde97/8dbbf/images/goals.jpg" alt="medium"/></div><div><div class="block-header"><h2 class="block-title">Web Audio DAW</h2></div><div class="block-buttons"><a href="https://mihirbegmusiclab.netlify.app/" target="_blank" rel="noopener " class="button">Go To Web Audio Daw</a></div></div></div></div></section><section id="navigate from the home page" class="block block-grid outer has-header"><div class="inner"><div class="block-header inner-sm"><h2 class="block-title">Quick Links</h2><p class="block-subtitle">quick links home</p></div><div class="block-content"><div class="grid grid-col-2"><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/about/">About</a></h3><div class="grid-item-content"><p>Web-Dev-Hub is my personal blogand documentation site</p></div><div class="grid-item-buttons"><a href="/docs/about/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/articles/">Articles</a></h3><div class="grid-item-content"><p>my web development articles</p></div><div class="grid-item-buttons"><a href="/docs/articles/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/audio/">Audio</a></h3><div class="grid-item-content"><p>Audio Projects and tools / web audio daw</p></div><div class="grid-item-buttons"><a href="/docs/audio/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/career/">Career</a></h3><div class="grid-item-content"><p>Reference materials and descriptions of fundamental concepts as well as visua</p></div><div class="grid-item-buttons"><a href="/docs/career/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/community/">Community</a></h3><div class="grid-item-content"><p>We&#x27;d love it if you participate in the Libris community. Find out how to get connected.</p></div><div class="grid-item-buttons"><a href="/docs/community/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/content/">Content</a></h3><div class="grid-item-content"><p>In this section you&#x27;ll learn how to add syntax highlighting, examples, callouts and much more.</p></div><div class="grid-item-buttons"><a href="/docs/content/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a></a></h3><div class="grid-item-buttons"><a>Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/data-structures/">Data Structures</a></h3><div class="grid-item-content"><p>In this section you&#x27;ll learn how to add syntax highlighting, examples, callouts and much more.</p></div><div class="grid-item-buttons"><a href="/docs/data-structures/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/docs/">Docs</a></h3><div class="grid-item-content"><p>Documentation</p></div><div class="grid-item-buttons"><a href="/docs/docs/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/faq/">FAQ</a></h3><div class="grid-item-content"><p>In this section you&#x27;ll find commonly asked questions regarding the Libris theme. If you have questions, don&#x27;t hesitate to ask us directly.</p></div><div class="grid-item-buttons"><a href="/docs/faq/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/interact/">Interactive</a></h3><div class="grid-item-content"><p>feel free to try the examples</p></div><div class="grid-item-buttons"><a href="/docs/interact/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/javascript/">Javascript</a></h3><div class="grid-item-content"><p>Javascript articles  and docs</p></div><div class="grid-item-buttons"><a href="/docs/javascript/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/interview/">Interviewing</a></h3><div class="grid-item-content"><p>These are some of my active projects.</p></div><div class="grid-item-buttons"><a href="/docs/interview/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/leetcode/">Leetcode</a></h3><div class="grid-item-content"><p>feel free to try the examples</p></div><div class="grid-item-buttons"><a href="/docs/leetcode/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/projects/">Projects</a></h3><div class="grid-item-content"><p>We&#x27;d love it if you participate in the Web-Dev-Hubcommunity. Find out how to get connected.</p></div><div class="grid-item-buttons"><a href="/docs/projects/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/python/">Python</a></h3><div class="grid-item-content"><p>Python</p></div><div class="grid-item-buttons"><a href="/docs/python/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/quick-reference/">QuickRef</a></h3><div class="grid-item-content"><p>In this section you&#x27;ll find basic information about Web-Dev-Hub and how to use it.</p></div><div class="grid-item-buttons"><a href="/docs/quick-reference/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/react/">React</a></h3><div class="grid-item-content"><p>To make it easy to write documentation in plain Markdown, most React are styled using Markdown elements with few additional CSS classes.</p></div><div class="grid-item-buttons"><a href="/docs/react/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/reference/">Reference</a></h3><div class="grid-item-content"><p>helpful reference guides</p></div><div class="grid-item-buttons"><a href="/docs/reference/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/tools/">Tools</a></h3><div class="grid-item-content"><p>See some interesting tools developed by the Web-Dev-Hubcommunity to help automate parts of your workflow.</p></div><div class="grid-item-buttons"><a href="/docs/tools/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/tips/">Tips</a></h3><div class="grid-item-content"><p>lorem-ipsum</p></div><div class="grid-item-buttons"><a href="/docs/tips/">Learn More</a></div></div></div><div class="grid-item"><div class="grid-item-inside"><h3 class="grid-item-title line-left"><a href="/docs/tutorials/">Tutorials</a></h3><div class="grid-item-content"><p>Walkthroughs of various development activities and skills</p></div><div class="grid-item-buttons"><a href="/docs/tutorials/">Learn More</a></div></div></div></div></div></div></section><section id="contact" class="block block-cta outer"><div class="inner"><div class="has-gradient"><div class="grid grid-middle grid-center"><div class="grid-item block-header"><h2 class="block-title">Contact</h2><p class="block-subtitle">get in touch! +1 (551) - 254 - 5505</p></div><div class="grid-item block-buttons"><a class="button" href="/docs/faq/contact">Contact</a><a class="button" href="/mailto:bryan.guner@gmail.com">email</a><a class="button" href="/ https://www.youtube.com/channel/UC9-rYyUMsnEBK8G8fCyrXXA?sub_confirmation=1">Subscribe (Youtube)</a></div></div></div></div></section></main><footer id="colophon" class="site-footer outer"><div><center><br/><div id="search"> <!-- --> </div><br/><table cellPadding="0" cellSpacing="0" border="0"><tbody><tr><td style="font-family:Arial, Helvetica, sans-serif;font-size:7.5pt"><center><table width="95%" cellPadding="0" cellSpacing="0" border="0" style="font-family:Arial, Helvetica, sans-serif;font-size:7.5pt"><tbody><tr><td style="font-family:Arial, Helvetica, sans-serif;font-size:7.5pt" align="left"><a target="_blank" href="https://search.freefind.com/siteindex.html?si=14588965">index</a></td><td style="font-family:Arial, Helvetica, sans-serif;font-size:7.5pt" align="center"><a target="_blank" href="https://search.freefind.com/find.html?si=14588965&amp;m=0&amp;p=0">sitemap</a></td><td style="font-family:Arial, Helvetica, sans-serif;font-size:7.5pt" align="right"><a target="_blank" href="https://search.freefind.com/find.html?si=14588965&amp;pid=a">advanced</a></td></tr></tbody></table></center><form style="margin:0px;margin-top:2px" action="https://search.freefind.com/find.html" method="get" accept-charset="utf-8" target="_self"><input type="hidden" name="si" value="14588965"/><input type="hidden" name="pid" value="r"/><input type="hidden" name="n" value="0"/><input type="hidden" name="_charset_" value="true"/><input type="hidden" name="bcd" value="÷"/><input type="text" name="query" size="15"/><input type="submit" value="search"/></form></td></tr><tr><td style="text-align:center;font-family:Arial, Helvetica, sans-serif;font-size:7.5pt;padding-top:4px"><a style="text-decoration:none;color:transparent" href="https://www.freefind.com" rel="nofollow">search engine</a><a style="text-decoration:none;color:transparent" href="https://www.freefind.com" rel="nofollow">by<span style="color:transparent">freefind</span></a></td></tr></tbody></table><a class="save2PDF" href="//pdfcrowd.com/url_to_pdf/?">Save to PDF</a></center><a aria-current="page" class="site-logo" href="/"><img src="https://d33wubrfki0l68.cloudfront.net/e5662f0d4f3e7730aea1a0faf7ff09ea20184700/6ca0b/images/dgqlkqjtmk.png" alt="webdevhub logo"/></a></div><div class="inner"><div id="search" class="inner"></div><div class="site-footer-inside"><p class="site-info"><span class="copyright">@bgoonz on almost every platform</span><a href="https://random-static-html-deploys.netlify.app/blm.html" target="_blank" rel="noopener " class="button">BLM</a> </p><div class="social-links"><a href="https://twitter.com/bgooonz" target="_blank" rel="noopener " class="button button-icon"><svg class="icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M23.954 4.569a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.691 8.094 4.066 6.13 1.64 3.161a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.061a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.937 4.937 0 004.604 3.417 9.868 9.868 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.054 0 13.999-7.496 13.999-13.986 0-.209 0-.42-.015-.63a9.936 9.936 0 002.46-2.548l-.047-.02z"></path></svg><span class="screen-reader-text">Twitter</span></a><a href="https://www.linkedin.com/in/bryan-guner-046199128/" target="_blank" rel="noopener " class="button button-icon"><svg class="icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"></path></svg><span class="screen-reader-text">LinkedIn</span></a><a href="https://github.com/bgoonz" target="_blank" rel="noopener " class="button button-icon"><svg class="icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"></path></svg><span class="screen-reader-text">GitHub</span></a><a href="https://www.youtube.com/channel/UC9-rYyUMsnEBK8G8fCyrXXA" target="_blank" rel="noopener " class="button button-icon"><svg class="icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M23.495 6.205a3.007 3.007 0 00-2.088-2.088c-1.87-.501-9.396-.501-9.396-.501s-7.507-.01-9.396.501A3.007 3.007 0 00.527 6.205a31.247 31.247 0 00-.522 5.805 31.247 31.247 0 00.522 5.783 3.007 3.007 0 002.088 2.088c1.868.502 9.396.502 9.396.502s7.506 0 9.396-.502a3.007 3.007 0 002.088-2.088 31.247 31.247 0 00.5-5.783 31.247 31.247 0 00-.5-5.805zM9.609 15.601V8.408l6.264 3.602z"></path></svg><span class="screen-reader-text">Youtube</span></a><a href="https://www.instagram.com/bgoonz/?hl=en" target="_blank" rel="noopener " class="button button-icon"><svg class="icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12 0C8.74 0 8.333.015 7.053.072 5.775.132 4.905.333 4.14.63c-.789.306-1.459.717-2.126 1.384S.935 3.35.63 4.14C.333 4.905.131 5.775.072 7.053.012 8.333 0 8.74 0 12s.015 3.667.072 4.947c.06 1.277.261 2.148.558 2.913a5.885 5.885 0 001.384 2.126A5.868 5.868 0 004.14 23.37c.766.296 1.636.499 2.913.558C8.333 23.988 8.74 24 12 24s3.667-.015 4.947-.072c1.277-.06 2.148-.262 2.913-.558a5.898 5.898 0 002.126-1.384 5.86 5.86 0 001.384-2.126c.296-.765.499-1.636.558-2.913.06-1.28.072-1.687.072-4.947s-.015-3.667-.072-4.947c-.06-1.277-.262-2.149-.558-2.913a5.89 5.89 0 00-1.384-2.126A5.847 5.847 0 0019.86.63c-.765-.297-1.636-.499-2.913-.558C15.667.012 15.26 0 12 0zm0 2.16c3.203 0 3.585.016 4.85.071 1.17.055 1.805.249 2.227.415.562.217.96.477 1.382.896.419.42.679.819.896 1.381.164.422.36 1.057.413 2.227.057 1.266.07 1.646.07 4.85s-.015 3.585-.074 4.85c-.061 1.17-.256 1.805-.421 2.227a3.81 3.81 0 01-.899 1.382 3.744 3.744 0 01-1.38.896c-.42.164-1.065.36-2.235.413-1.274.057-1.649.07-4.859.07-3.211 0-3.586-.015-4.859-.074-1.171-.061-1.816-.256-2.236-.421a3.716 3.716 0 01-1.379-.899 3.644 3.644 0 01-.9-1.38c-.165-.42-.359-1.065-.42-2.235-.045-1.26-.061-1.649-.061-4.844 0-3.196.016-3.586.061-4.861.061-1.17.255-1.814.42-2.234.21-.57.479-.96.9-1.381.419-.419.81-.689 1.379-.898.42-.166 1.051-.361 2.221-.421 1.275-.045 1.65-.06 4.859-.06l.045.03zm0 3.678a6.162 6.162 0 100 12.324 6.162 6.162 0 100-12.324zM12 16c-2.21 0-4-1.79-4-4s1.79-4 4-4 4 1.79 4 4-1.79 4-4 4zm7.846-10.405a1.441 1.441 0 01-2.88 0 1.44 1.44 0 012.88 0z"></path></svg><span class="screen-reader-text">Instagram</span></a><a href="https://dev.to/bgoonz" target="_blank" rel="noopener " class="button button-icon"><svg class="icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M7.42 10.05c-.18-.16-.46-.23-.84-.23H6l.02 2.44.04 2.45.56-.02c.41 0 .63-.07.83-.26.24-.24.26-.36.26-2.2 0-1.91-.02-1.96-.29-2.18zM0 4.94v14.12h24V4.94H0zM8.56 15.3c-.44.58-1.06.77-2.53.77H4.71V8.53h1.4c1.67 0 2.16.18 2.6.9.27.43.29.6.32 2.57.05 2.23-.02 2.73-.47 3.3zm5.09-5.47h-2.47v1.77h1.52v1.28l-.72.04-.75.03v1.77l1.22.03 1.2.04v1.28h-1.6c-1.53 0-1.6-.01-1.87-.3l-.3-.28v-3.16c0-3.02.01-3.18.25-3.48.23-.31.25-.31 1.88-.31h1.64v1.3zm4.68 5.45c-.17.43-.64.79-1 .79-.18 0-.45-.15-.67-.39-.32-.32-.45-.63-.82-2.08l-.9-3.39-.45-1.67h.76c.4 0 .75.02.75.05 0 .06 1.16 4.54 1.26 4.83.04.15.32-.7.73-2.3l.66-2.52.74-.04c.4-.02.73 0 .73.04 0 .14-1.67 6.38-1.8 6.68z"></path></svg><span class="screen-reader-text">dev.to</span></a> </div> </div></div></footer></div></div><div id="gatsby-announcer" style="position:absolute;top:0;width:1px;height:1px;padding:0;overflow:hidden;clip:rect(0, 0, 0, 0);white-space:nowrap;border:0" aria-live="assertive" aria-atomic="true"></div></div><script src='https://d33wubrfki0l68.cloudfront.net/bundles/7954008f569678054ddfe09de2549d6c36b16cb9.js'></script><script id="gatsby-script-loader">/*<![CDATA[*/window.pagePath="/";/*]]>*/</script><script id="gatsby-chunk-mapping">/*<![CDATA[*/window.___chunkMapping={"polyfill":["/polyfill-50463aa39b84c4d1ec96.js"],"app":["/app-10180cc44b3853f61402.js"],"component---src-templates-advanced-js":["/component---src-templates-advanced-js-6f213d193b5ecf8f0dd1.js"],"component---src-templates-blog-js":["/component---src-templates-blog-js-d1d7372de9a72caa6ec8.js"],"component---src-templates-docs-js":["/component---src-templates-docs-js-731339ed0815d7cada90.js"],"component---src-templates-page-js":["/component---src-templates-page-js-dcb6b8bc1563f876e59f.js"],"component---src-templates-post-js":["/component---src-templates-post-js-8dfc6c5f64f9cf30c603.js"]};/*]]>*/</script><script nomodule src='https://d33wubrfki0l68.cloudfront.net/js/582b61cb624d3b5bcc6977024571665de2ae7a24/polyfill-50463aa39b84c4d1ec96.js'></script><script async src='https://d33wubrfki0l68.cloudfront.net/bundles/b009af873ded2b7a689d9c19c35e1b6d90c4c941.js'></script><input type="button" style="position: fixed;top: 10px;right: 10px;width:80px;color:white;font-weight:bold;background-color:rgba(0, 0, 0, 0.856); border-radius:15px;" value="Go Back" onclick="history.back(-1)" />
      <?php
        $url = htmlspecialchars($_SERVER['HTTP_REFERER']);
        echo "<a href='$url'></a><script src="https://widget.stackbit.com/init.js" id="stackbit-widget-init" data-stackbit-project-id="609b2d7c71a5dd0016f36326"></script><!-- Go to www.addthis.com/dashboard to customize your tools -->
<script type="text/javascript" src="//s7.addthis.com/js/300/addthis_widget.js#pubid=ra-60dcec1ece575946"></script><script>
let div = window.createElement('div');
div.id('search');
div.style = 'z-index:-1; position:absolute;width: 300px;height: 300px;bottom: 0px;right: 25%;left: 50 %;';
let docscontent = window.getElementByClassName('docs-content');
docscontent.appendChild(div);

let div1 = window.createElement('div');
div1.id('search');
div1.style = 'z-index:-1; position:absolute;width: 300px;height: 300px;background:#063;bottom: 0px;right: 25%;left: 50 %;margin-left: -150px';
let header = window.getElementByClassName('site-header-inside');
header.appendChild('div1');

</script><!-- Default Statcounter code for 2
https://bgoonz-blog.netlify.app/ -->
<script type="text/javascript">
var sc_project=12702211; 
var sc_invisible=0; 
var sc_security="011fbeb6"; 
var sc_text=3; 
var scJsHost = "https://";
document.write("<sc"+"ript type='text/javascript' src='" +
scJsHost+
"statcounter.com/counter/counter.js'></"+"script>");
</script>
<noscript><div class="statcounter"><a title="Web Analytics"
href="https://statcounter.com/" target="_blank"><img
class="statcounter"
src="https://c.statcounter.com/12702211/0/011fbeb6/0/"
alt="Web Analytics"
referrerPolicy="no-referrer-when-downgrade"></a></div></noscript>
<!-- End of Statcounter Code -->
<a href="https://statcounter.com/p12702211/?guest=1">View My
Stats</a><script>
          // Get the button:
          mybutton = document.getElementById("scrollBtn");
          // When the user scrolls down 20px from the top of the document, show the button
          window.onscroll = function () {
            scrollFunction();
          };
          function scrollFunction() {
            if (
              document.body.scrollTop > 20 ||
              document.documentElement.scrollTop > 20
            ) {
              mybutton.style.display = "block";
            } else {
              mybutton.style.display = "none";
            }
          }
          // When the user clicks on the button, scroll to the top of the document
          function topFunction() {
            document.body.scrollTop = 0; // For Safari
            document.documentElement.scrollTop = 0; // For Chrome, Firefox, IE and Opera
          }
        </script>
        <script>
          window.addEventListener("DOMContentLoaded", (event) => {
            console.log("DOM fully loaded and parsed");
            const scrollToTop = () => {
              const c =
                document.documentElement.scrollTop || document.body.scrollTop;
              if (c > 0) {
                window.requestAnimationFrame(scrollToTop);
                window.scrollTo(0, c - c / 8);
              }
            };
            scrollToTop();
          });
        </script>
<button id="scrollBtn" title="Go to top" onclick="topFunction()" style="display: block;">
          Back To Top
        </button><script type="text/javascript" src="//s7.addthis.com/js/300/addthis_widget.js#pubid=ra-60dcec1ece575946"></script></body></html>
```