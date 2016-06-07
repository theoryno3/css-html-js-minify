# css-html-js-minify


[![Travis report](https://travis-ci.org/juancarlospaco/css-html-js-minify.svg?branch=master "Travis-C.I. Testing report")](https://travis-ci.org/juancarlospaco/css-html-js-minify) [![GPL License](http://img.shields.io/badge/license-GPL-blue.svg?style=plastic)](http://opensource.org/licenses/GPL-3.0) [![LGPL License](http://img.shields.io/badge/license-LGPL-blue.svg?style=plastic)](http://opensource.org/licenses/LGPL-3.0) [![Python Version](https://img.shields.io/badge/Python-3-brightgreen.svg?style=plastic)](http://python.org) [![Code Issues](http://www.quantifiedcode.com/api/v1/project/abb1afb550964afa8d1e30c82367eb24/badge.svg)](http://www.quantifiedcode.com/app/project/abb1afb550964afa8d1e30c82367eb24)

[![Donate BitCoins](https://www.coinbase.com/assets/buttons/donation_large-5cf4f17cc2d2ae2f45b6b021ee498297409c94dcf0ba1bbf76fd5668e80b0d02.png)](https://www.coinbase.com/checkouts/c3538d335faee0c30c81672ea0223877 "Donate Bitcoins") [![Subscribe with BitCoins](https://www.coinbase.com/assets/buttons/subscription_large-11d991f628216af05156fae88a48ce25c0cb36447a265421a43a62e572af3853.png)](https://www.coinbase.com/checkouts/c3538d335faee0c30c81672ea0223877 "Subscribe with BitCoins") [![Pay with BitCoins](https://www.coinbase.com/assets/buttons/buy_now_large-6f15fa5979d25404827a7329e8a5ec332a42cf4fd73e27a2c3ccda017034e1b0.png)](https://www.coinbase.com/checkouts/c3538d335faee0c30c81672ea0223877 "Pay with BitCoins") [![Donate](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif "Donate with or without Credit Card")](http://goo.gl/cB7PR)


- **StandAlone Async cross-platform Unicode-ready Python3-ready Minifier for the Web.**

https://pypi.python.org/pypi/css-html-js-minify

```shell
css-html-js-minify.py --help

usage: css-html-js-minify.py [-h] [--version] [--wrap] [--prefix PREFIX]
                             [--timestamp] [--quiet] [--obfuscate]
                             [--checkupdates] [--tests] [--hash] [--gzip]
                             [--sort] [--comments] [--overwrite]
                             [--after AFTER] [--before BEFORE] [--watch]
                             [--multiple]
                             fullpath

CSS-HTML-JS-Minify. StandAlone Async cross-platform Unicode-ready Python3-ready Minifier for the Web.

positional arguments:
  fullpath         Full path to local file or folder.

optional arguments:
  -h, --help       show this help message and exit
  --version        show programs version number and exit
  --wrap           Wrap output to ~80 chars per line, CSS only.
  --prefix PREFIX  Prefix string to prepend on output filenames.
  --timestamp      Add a Time Stamp on all CSS/JS output files.
  --quiet          Quiet, Silent, force disable all logging.
  --hash           Add SHA1 HEX-Digest 11chars Hash to Filenames.
  --zipy           GZIP Minified files as '*.gz', CSS/JS only.
  --sort           Alphabetically Sort CSS Properties, CSS only.
  --comments       Keep comments, CSS/HTML only (Not Recommended)
  --overwrite      Force overwrite all in-place (Not Recommended)
  --after AFTER    Command to execute after run (Experimental).
  --before BEFORE  Command to execute before run (Experimental).
  --watch          Re-Compress if file changes (Experimental).
  --multiple       Allow Multiple instances (Not Recommended).
  --beep           Beep sound will be played when it ends at exit.

CSS-HTML-JS-Minify: Takes a file or folder full path string and process all
CSS/HTML/JS found. If argument is not file/folder will fail. Check Updates
works on Python3. Std-In to Std-Out is deprecated since it may fail with
unicode characters. SHA1 HEX-Digest 11 Chars Hash on Filenames is used for
Server Cache. CSS Properties are Alpha-Sorted, to help spot cloned ones,
Selectors not. Watch works for whole folders, with minimum of ~60 Secs between
runs.

```

- Takes a full path to anything, a file or a folder, then parse, optimize and compress for Production.
- If full path is a folder with multiple files it will use Async Multiprocessing.
- Pretty-Printed colored Logging to Standard Output and Log File on OS Temporary Folder.
- Set its own Process name and show up on Process lists.
- Can check for updates for itself.
- Full Unicode/UTF-8 support.
- Smooth CPU usage, Single Instance Checking.
- Can Obfuscate, GZIP and Hash files, also Watch for changes on files.
- Can execute arbitrary commands after and before running.
- `*.css` files are saved as `*.min.css`, `*.js` are saved as `*.min.js`, `*.htm` are saved as `*.html`


# Screenshots:

**Linux:**

![screenshot](https://raw.githubusercontent.com/juancarlospaco/css-html-js-minify/master/linux-css-html-js-compressor.jpg "Linux 32bit/64bit Python2/Python3")

**Apple Mac Os X:**
[ <sup>*(Provided by Loggerhead)*</sup> ](https://github.com/juancarlospaco/css-html-js-minify/issues/7#issuecomment-97280835)
![screenshot](https://raw.githubusercontent.com/juancarlospaco/css-html-js-minify/master/osx-css-html-js-compressor_terminal.jpg "Apple Mac Os X Terminal by Loggerhead")

![screenshot](https://raw.githubusercontent.com/juancarlospaco/css-html-js-minify/master/osx-css-html-js-compressor_iterm2.jpg "Apple Mac Os X iTerm2 by Loggerhead")

**MS Windows:**

![screenshot](https://raw.githubusercontent.com/juancarlospaco/css-html-js-minify/master/windows-css-html-js-compressor.jpg "MS Windows 32bit/64bit Python2/Python3")


# Command-line usage:

```bash
css-html-js-minify.py file.htm

css-html-js-minify.py file.css

css-html-js-minify.py file.js

css-html-js-minify.py /project/static/
```

# Python code usage (py3.5+)

```python
from css_html_js_minify import process_single_html_file, process_single_js_file, process_single_css_file, html_minify, js_minify, css_minify

process_single_html_file('test.htm', overwrite=False)
# 'test.html'
process_single_js_file('test.js', overwrite=False)
# 'test.min.js'
process_single_css_file('test.css', overwrite=False)
# 'test.min.css'

html_minify('  <p>yolo<a  href="/" >o </a >     <!-- hello --></p>')
# '<p>yolo<a href="/" >o </a > </p>'
js_minify('var i = 1; i += 2 ;\n alert( "hello  "  ); //hi')
# 'var i=1;i+=2;alert("hello  ");'
css_minify('body {width: 50px;}\np {margin-top: 1em;/* hi */  }', comments=False)
# '@charset utf-8;body{width:50px}p{margin-top:1em}'
```

The optional arguments that these functions take are almost the same as the command-line flags.
Check the list above *(just use add_hash instead of hash)*. Additionally, you can force a specific path for the output files using ``output_path``.

# Install permanently on the system:

**PIP:** *(Recommended!)*
```
sudo pip3 install css-html-js-minify
```


# Why?:

- **Why another Compressor ?**, there are lots of compressors for web files out there!; *Or maybe not ?*.
- Many of them only work inside Django/Flask, or frameworks of PHP/Java/Ruby, or can not process whole folders.
- This project is the big brother of another project that does the inverse, a [Beautifier for the Web.](https://github.com/juancarlospaco/css-html-prettify#css-html-prettify)

**Input CSS:**
```css
/*!
 * preserve commment
 */


/* delete comment */
.class, #NotHex, input[type="text"], a:hover  {
    font-family : Helvetica Neue, Arial, Helvetica, 'Liberation Sans', sans-serif;
    border: none;
    margin: 0 0 0 0;
    border-color:    fuchsia;
    color:           mediumspringgreen;
    background-position:0 0;;
    transform-origin:0 0;
    margin: 0px !important;
    font-weight :bold;
    color: rgb( 255, 255, 255 );
    padding : 0.9px;
    position : absolute;
    z-index : 100000;
    color: #000000;
    background-color: #FFFFFF;
    background-image: url("data:image/jpeg;base64,R0lGODlhAQABAIAAAAUEBAAAACwAAAAAAQABAAACAkQBADs=");
;}
;;

```

**Uglify (NodeJS):** *(474 Bytes, 0.189 Secs)*

```css
/* * preserve commment */ .class,#NotHex,input[type="text"],a:hover {font-family:Helvetica Neue,Arial,Helvetica,'Liberation Sans',sans-serif;border:0;margin:0;border-color:fuchsia;color:mediumspringgreen;background-position:0 0;transform-origin:0 0;margin:0 !important;font-weight:bold;color:#fff;padding:.9px;position:absolute;z-index:100000;color:#000;background-color:#fff;background-image:url("data:image/jpeg;base64,R0lGODlhAQABAIAAAAUEBAAAACwAAAAAAQABAAACAkQBADs=")};
```

**css-html-js-minify (Python3):** *(469 Bytes, 0.010 Secs)*

```css
/*!* preserve commment */ .class,#NotHex,input[type=text],a:hover{font-family:Helvetica Neue,Arial,Helvetica,'Liberation Sans',sans-serif;border:0;margin:0;border-color:#f0f;color:#00fa9a;background-position:0 0;transform-origin:0 0;margin:0 !important;font-weight:700;color:#fff;padding:.9px;position:absolute;z-index:100000;color:#000;background-color:#FFF;background-image:url(data:image/jpg;base64,R0lGODlhAQABAIAAAAUEBAAAACwAAAAAAQABAAACAkQBADs=)}
```


# Migration:

To keep things simple [KISS](http://en.wikipedia.org/wiki/KISS_principle), the human readable indented commented hackable HTML is kept as `*.htm` and the compressed production-ready as `*.html`. This is inspired from JavaScript/CSS `*.min.js` and `*.min.css`. [We did not "invent" this file extension.](http://en.wikipedia.org/wiki/HTM)

To migrate from typical file extension HTML to HTM, which is the exactly same, you can run this:

```shell
find . -name "*.html" -exec rename "s/.html/.htm/" "{}" \;
```

This will make a copy of all `*.html` renaming them as `*.htm` recursively from the current folder. Nothing deleted.


# Requisites:

- [Python 3.x](https://www.python.org "Python Homepage")


# Coding Style Guide:

- Lint, [PEP-8](https://www.python.org/dev/peps/pep-0008), [PEP-257](https://www.python.org/dev/peps/pep-0257), [PyLama](https://github.com/klen/pylama#-pylama), [iSort](https://github.com/timothycrosley/isort) must Pass Ok. `pip install pep8 pep257 pylama isort`
- If there are any kind of tests, they must pass. No tests is also acceptable, but having tests is better.


# Contributors:

| **Hall of Fame** |
| -------------------------------- |
| [![](https://avatars1.githubusercontent.com/u/1189414?s=50)](https://github.com/juancarlospaco) [![](https://avatars2.githubusercontent.com/u/3127847?s=50)](https://github.com/cassiobotaro) [![](https://avatars1.githubusercontent.com/u/5056390?s=50)](https://github.com/loggerhead) [![](https://avatars3.githubusercontent.com/u/7449642?s=50)](https://github.com/skolsuper) [![](https://avatars0.githubusercontent.com/u/4732915?s=50)](https://github.com/cuducos) [![](https://avatars1.githubusercontent.com/u/517395?s=50)](https://github.com/lowks) [![](https://avatars3.githubusercontent.com/u/6242660?s=50)](https://github.com/alanvinals) [![](https://avatars2.githubusercontent.com/u/1552641?s=50)](https://github.com/JayXon) [![](https://avatars1.githubusercontent.com/u/6053065?s=50)](https://github.com/rokarc) [???](https://github.com/Omniferum) [![](https://avatars1.githubusercontent.com/u/1486592?v=3&s=50)](https://github.com/harrysouthworth) [![](https://avatars2.githubusercontent.com/u/6442863?v=3&s=50)](https://github.com/mverleg)
[![](https://avatars0.githubusercontent.com/u/1102886?v=3&s=50)](https://github.com/Aeyoun) |


- **Please Star this Repo on Github !**, it helps to show up faster on searchs.
- **Ad-Hocracy Meritocracy**: 3 Pull Requests Merged on Master you become Repo Admin. *Join us!*
- [Help](https://help.github.com/articles/using-pull-requests) and more [Help](https://help.github.com/articles/fork-a-repo) and Interactive Quick [Git Tutorial](https://try.github.io).


# Licence:

- GNU GPL Latest Version *AND* GNU LGPL Latest Version *AND* any Licence [YOU Request via Bug Report](https://github.com/juancarlospaco/css-html-js-minify/issues/new).


# Ethics and Humanism Policy:
- May this FLOSS be always Pristine and Clean, No AdWare, No Spamm, No BundleWare, No Infomercial, No MalWare.
- This project is [LGBTQQIAAP friendly](http://www.urbandictionary.com/define.php?term=LGBTQQIAAP "Whats LGBTQQIAAP").


Donate, Charityware :
---------------------

- [Charityware](https://en.wikipedia.org/wiki/Donationware) is a licensing model that supplies fully operational unrestricted software to the user and requests an optional donation be paid to a third-party beneficiary non-profit. The amount may be left to discretion of the user.
- If you want to Donate please [click here](http://www.icrc.org/eng/donations/index.jsp) or [click here](http://www.atheistalliance.org/support-aai/donate) or [click here](http://www.msf.org/donate) or [click here](http://richarddawkins.net/) or [click here](http://www.supportunicef.org/) or [click here](http://www.amnesty.org/en/donate) or [click here](http://www.rescue.org/irc-fast-facts)
