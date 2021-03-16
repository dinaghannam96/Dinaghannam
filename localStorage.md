JavaScript and localStorage in a nutshell
Ben Long
February 6th, 2020

Written by

Ben LongBen Long
BEN LONG
Category

HOW-TOS & TUTORIALS
Tagged

JAVASCRIPT
Sometimes you want to get something done in HTML without the added complexity of a backend database. In this case, you can use JavaScript to access localStorage.

But, first...

...we need to understand exactly what we're dealing with; for example, what is localStorage, when can you use it, and is it secure?

If you already know what you’re getting yourself into, you can skip ahead to:

an overview of JavaScript localStorage methods
a simple JavaScript localStorage example
a JavaScript localStorage example with a rich text editor
Otherwise, read on...

What is localStorage?
localStorage allows web applications to store data locally within the user's browser with no expiration date. The data will not be deleted when the browser is closed, and will be available when the browser is opened again.

The good, the bad, and the ugly of localStorage
The good

It stores up to 5-10MB of data (depending on the browser).
Easy to use – no need for a web server or backend database.
Great for getting an idea up and running and for testing purposes.
The bad

It only stores up to 10MB of data (5MB in some browsers).
It can only store strings. This can restrict you from using it for more complex scenarios; although, HTML can be stored as a string – more on that later...
It’s local to the browser and specific to the origin (per domain and protocol), and there’s no guarantee that the data will persist even in that same context.
The ugly

It’s not secure. Don’t store any private or personal information in localStorage.
Okay. Now that we’ve got the housekeeping out of the way, let’s get into it!

JavaScript localStorage methods
There are four basic JavaScript methods you can use to access and work with localStorage:

setItem() - takes a key-value pair and adds it to localStorage
getItem() - takes a key and returns the corresponding value
removeItem() - takes a key and removes the corresponding key-value pair
clear() - clears localStorage (for the domain)
I always think the best way to really understand something is to try it out for yourself. So...

Open your browser console, for example, by opening Developer Tools in Google Chrome and clicking on the Console tab.

Enter localStorage and the current stored data will be returned. For example (assuming it’s empty to begin with):

> localStorage
< Storage {length: 0}

COPY
Enter localStorage.setItem('myKey', 'testValue') and the string testValue will be stored against the key myKey:

> localStorage.setItem('myKey', 'testValue')
< undefined

COPY
undefined just means that no value is returned from that method. Enter localStorage again to view the stored data.

> localStorage
< Storage {myKey: "testValue", length: 1}

COPY
Enter localStorage.getItem('myKey') and the corresponding string will be returned:

> localStorage.getItem('myKey')
< "testValue"

COPY
setItem() and getItem() are the two methods we’ll be using in our example. Feel free to try out the other methods too in a similar way.

TIP: Type localStorage. (with the ‘.’) into the console and a full list of relevant methods will appear.

JavaScript localStorage example
Let’s put these methods into practice.

Create a simple index.html file with a single textarea, and two buttons as follows. The textarea id can be anything – in this example, we’ve called it myTextArea.

<!DOCTYPE html>
<html lang="en">
  <head>
  </head>
  <body>
    <h1>JavaScript localStorage demo</h1>
    <textarea id="myTextarea" rows="10" cols="80"></textarea>
    <p></p>
    <button onclick="mySave()">Save</button>
    <button onclick="myLoad()">Load</button>
    <script>
      function mySave() {
        var myContent = document.getElementById("myTextarea").value;
        localStorage.setItem("myContent", myContent);
      }
      function myLoad() {
        var myContent = localStorage.getItem("myContent");
        document.getElementById("myTextarea").value = myContent;
      }
    </script>
  </body>
</html>

COPY
We’ve defined two JavaScript functions, mySave() and myLoad(). The buttons are configured so that, when they are clicked, they each trigger the relevant JavaScript function. document.getElementById() is used to get/set the value of the element specified. In this case, we are accessing the textarea with id myTextArea. The mySave() function accesses the current value of the textarea and assigns it to a variable myContent. This variable is then used as the value associated with key myContent in localStorage. The myLoad() function operates in a similar way, only in reverse.

Once you’ve created the above HTML file, open it in a browser. What it looks like on your screen will depend on your CSS. (We inserted some custom CSS for the buttons in our example to make them look a little more interesting than the default.)


JavaScript localStorage example running in a browser.
Test it
Type something in the textarea and click Save. (I pasted in a bit of prose from Frankenstein in the image above.) The content will be saved to localStorage. Then, refresh the page, and the content will disappear. Now, click Load and the content will be retrieved from localStorage and appear in the textarea as before.

TIP: While you’re on the page, you could try opening the browser console from within Developer Tools and executing some of the localStorage methods as shown in the previous section to confirm what’s happening behind the scenes.

That’s all there is to it!
source: tiny blue print
