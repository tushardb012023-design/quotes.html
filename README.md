<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Professional Quote Widget</title>
    <style>
        /* Professional Sans-Serif Typography */
        :root {
            --notion-bg: #191919;
            --main-text: rgba(255, 255, 255, 0.9);
            --sub-text: rgba(255, 255, 255, 0.4);
            /* This font stack targets the cleanest sans-serifs available on any device */
            --font-stack: Inter, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            background-color: var(--notion-bg);
            color: var(--main-text);
            font-family: var(--font-stack);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            text-align: center;
            padding: 30px;
            cursor: pointer;
            user-select: none;
            -webkit-font-smoothing: antialiased; /* Makes fonts look smoother */
        }

        #quote-container {
            max-width: 600px;
            transition: opacity 0.5s ease;
        }

        #quote-text {
            font-size: 1.5rem;
            font-weight: 500; /* Medium weight for sans-serif clarity */
            line-height: 1.3;
            margin-bottom: 16px;
            letter-spacing: -0.02em; /* Tighter tracking for a modern look */
        }

        #quote-author {
            font-size: 0.85rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.15em; /* Spaced out author name */
            color: var(--sub-text);
        }

        /* Subtle hover effect to show interactivity */
        body:hover #quote-text {
            color: #ffffff;
        }
    </style>
</head>
<body>

    <div id="quote-container">
        <div id="quote-text">"Loading..."</div>
        <div id="quote-author"></div>
    </div>

    <script>
        const quotes = [
            { text: "Good design is as little design as possible.", author: "Dieter Rams" },
            { text: "Action is the foundational key to all success.", author: "Pablo Picasso" },
            { text: "The details are not the details. They make the design.", author: "Charles Eames" },
            { text: "Simplicity is the keynote of all true elegance.", author: "Coco Chanel" },
            { text: "Your work is going to fill a large part of your life.", author: "Steve Jobs" },
            { text: "Make it simple, but significant.", author: "Don Draper" },
            { text: "Creativity is intelligence having fun.", author: "Albert Einstein" },
            { text: "Logic will get you from A to B. Imagination will take you everywhere.", author: "Albert Einstein" }
        ];

        function newQuote() {
            const container = document.getElementById('quote-container');
            
            // Brief fade out effect
            container.style.opacity = 0;
            
            setTimeout(() => {
                const quote = quotes[Math.floor(Math.random() * quotes.length)];
                document.getElementById('quote-text').textContent = `"${quote.text}"`;
                document.getElementById('quote-author').textContent = `— ${quote.author}`;
                container.style.opacity = 1;
            }, 250);
        }

        // Initialize
        window.onload = newQuote;
        document.body.onclick = newQuote;
    </script>
</body>
</html>
