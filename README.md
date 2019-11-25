# Add to Homescreen call out

Script for mobile devices, it automatically shows an overlaying message encouraging to add the web app to the homescreen. Compatible with iOS 6+ and Chrome for Android (soon WinPhone).

## Installation

Add `addtohomescreen.css` and `addtohomescreen.js` to the head of your projects index file. Then, call `addToHomescreen();` as soon as possible. For example:

```html
<head>
<title>Add To Home</title>
...
<link rel="stylesheet" type="text/css" href="../../style/addtohomescreen.css">
</head>
<body>
<!--To get the Add to Homescreen on IOS devices, see readme for more informations-->
<script src="lib/addtohomescreen.js"></script>
<script>
		const isIos = () => {
			// eslint-disable-next-line sap-no-navigator
			const userAgent = window.navigator.userAgent.toLowerCase();
			return /iphone|ipad|ipod/.test(userAgent);
		};
	
		// eslint-disable-next-line sap-no-navigator
		const isInStandaloneMode = () => ("standalone" in window.navigator) && (window.navigator.standalone);
	
		if (isIos() && !isInStandaloneMode()) {
			if (typeof addToHomescreen !== "undefined") {
				addToHomescreen({
					skipFirstVisit: false,
					startDelay: 0,
					displayPace: 0,
					autostart: true
				});
			} else {
				console.error("addToHomeScreen has not been imported");
			}
		}
	</script>
    <noscript>
        <div>
            <p>
                🚧 The application requires Javascript to works properly 🚧
            </p>
            <p>
                Enable it in your settings and reload the page.
            </p>
        </div>
      </noscript>
</body>
```

For more, consult the [project website](http://cubiq.org/add-to-home-screen).

## License

Copyright (c) 2014 Matteo Spinelli, http://cubiq.org/

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the "Software"), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.
