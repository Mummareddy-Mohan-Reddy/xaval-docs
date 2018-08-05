---
description: A few things about OpenCV.js
---

# OpenCV.js

[OpenCV](https://opencv.org/) is a popular open-source library for image processing and computer vision. It has interfaces in different languages including C++, Python and Java. In addition to these, it has been compiled to [WebAssembly](https://webassembly.org/) via [Emscripten](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/Emscripten), making it possible to run directly in the browser. It's this port of OpenCV that's referred to as [OpenCV.js](https://docs.opencv.org/3.4/d5/d10/tutorial_js_root.html).

Xaval comes with OpenCV.js baked-in, exposed as the global variable `cv`. In addition, Xaval utility methods for working with videos and images often return or support `cv.Mat` to make it easier to work with OpenCV. This is part of what makes Xaval an ideal place to learn and experiment with OpenCV.

One important thing to take note of when using OpenCV.js is that because it allocates memory to Emscripten's heap for some of its objects \(e.g. `cv.Mat` objects\), you have to manually free memory. Such objects have `delete()` method for this purpose. This is obviously not something one is necessarily used to in a Javascript setting, but I do not know whether there's a way around that at the moment. If you do forget to free memory in your program and start getting errors due to reaching the limit allowed by the browser, refreshing the page should clean things up.

While this documentation might contain examples of working with OpenCV.js, it does not focus on teaching it. To learn OpenCV.js, you can get started with the [turorials on the official website](https://docs.opencv.org/3.4/d5/d10/tutorial_js_root.html).

