#Hello, World!

**Simple jQuery plugin for changing text to 'Hello, World!'**

*by Ty-Lucas Kelley*

---

It's as easy as:

1. Include jQuery in your HTML
2. Call `.helloWorld()` on a piece of text you'd like to change
3. Customize `color` or `size` if needed by providing an optional argument:

        $(document).ready(function() {
            $('h1.title').helloWorld({
                color: 'rgba(172, 43, 43, 1)',
                size: '38px'
            });
        });
        

Enjoy!