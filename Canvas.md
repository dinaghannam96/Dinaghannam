Canvas API
The Canvas API provides a means for drawing graphics via JavaScript and the HTML <canvas> element. Among other things, it can be used for animation, game graphics, data visualization, photo manipulation, and real-time video processing.

The Canvas API largely focuses on 2D graphics. The WebGL API, which also uses the <canvas> element, draws hardware-accelerated 2D and 3D graphics.

Basic example
This simple example draws a green rectangle onto a canvas.

HTML
<canvas id="canvas"></canvas>
JavaScript
The Document.getElementById() method gets a reference to the HTML <canvas> element. Next, the HTMLCanvasElement.getContext() method gets that element's context—the thing onto which the drawing will be rendered.

The actual drawing is done using the CanvasRenderingContext2D interface. The fillStyle property makes the rectangle green. The fillRect() method places its top-left corner at (10, 10), and gives it a size of 150 units wide by 100 tall.

const canvas = document.getElementById('canvas');
const ctx = canvas.getContext('2d');

ctx.fillStyle = 'green';
ctx.fillRect(10, 10, 150, 100);
Result


Reference
HTMLCanvasElement
CanvasRenderingContext2D
CanvasGradient
CanvasImageSource
CanvasPattern
ImageBitmap
ImageData
RenderingContext
TextMetrics
OffscreenCanvas 
Path2D 
ImageBitmapRenderingContext 
Note: The interfaces related to the WebGLRenderingContext are referenced under WebGL.

OffscreenCanvas is also available in web workers.

CanvasCaptureMediaStreamTrack is a related interface.

Guides and tutorials
Canvas tutorial
A comprehensive tutorial covering both the basic usage of the Canvas API and its advanced features.
HTML5 Canvas Deep Dive
A hands-on, book-length introduction to the Canvas API and WebGL.
Canvas Handbook
A handy reference for the Canvas API.
Demo: A basic ray-caster
A demo of ray-tracing animation using canvas.
Manipulating video using canvas
Combining <video> and <canvas> to manipulate video data in real time.
Libraries
The Canvas API is extremely powerful, but not always simple to use. The libraries listed below can make the creation of canvas-based projects faster and easier.

EaselJS is an open-source canvas library that makes creating games, generative art, and other highly graphical experiences easy.
Fabric.js is an open-source canvas library with SVG parsing capabilities.
heatmap.js is an open-source library for creating canvas-based data heat maps.
JavaScript InfoVis Toolkit creates interactive data visualizations.
Konva.js is a 2D canvas library for desktop and mobile applications.
p5.js has a full set of canvas drawing functionality for artists, designers, educators, and beginners.
Paper.js is an open-source vector graphics scripting framework that runs on top of the HTML5 Canvas.
Phaser is a fast, free and fun open source framework for Canvas and WebGL powered browser games.
Pts.js is a library for creative coding and visualization in canvas and SVG.
Rekapi is an animation key-framing API for Canvas.
Scrawl-canvas is an open-source JavaScript library for creating and manipulating 2D canvas elements.
The ZIM framework provides conveniences, components, and controls for coding creativity on the canvas — includes accessibility and hundreds of colorful tutorials.
Note: See the WebGL API for 2D and 3D libraries that use WebGL.

Specifications
Specification	Status	Comment
HTML Living Standard
The definition of 'the 2D rendering context' in that specification.	Living Standard	
Browser compatibility
Mozilla applications gained support for <canvas> starting with Gecko 1.8 (Firefox 1.5). The element was originally introduced by Apple for the OS X Dashboard and Safari. Internet Explorer supports <canvas> from version 9 onwards; for earlier versions of IE, a page can effectively add support for <canvas> by including a script from Google's Explorer Canvas project. Google Chrome and Opera 9 also support <canvas>.
  
  source: MDN Website
