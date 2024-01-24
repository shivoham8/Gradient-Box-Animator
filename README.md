# Animated Gradient Box

A simple HTML and CSS code snippet for creating an animated gradient box with a nested structure. This code produces a visually appealing rotating gradient effect with a blur and shadow, along with a nested box inside.

## Getting Started

You can use this code snippet by copying the HTML and CSS into your project. Customize the colors, dimensions, and other properties to fit your design requirements.

### Prerequisites

No specific prerequisites are required. Simply include the HTML and CSS in your project.

### Website

[Gradient-Box-Animator](https://shivoham8.github.io/Gradient-Box-Animator/)

### Usage

1. Copy the HTML code from [`index.html`](index.html).
2. Paste it into your HTML file.
3. Copy the CSS code from the `<style>` section in the HTML file.
4. Paste it into your CSS file or include it in the `<style>` section of your HTML.

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="box">
        <span></span>
        <div class="box">
            <span></span>
        </div>
    </div>
</body>
</html>
```

```CSS
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: #222;
}

.box {
    position: relative;
    width: 400px;
    height: 300px;
}

.box::before {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-conic-gradient(from var(--a), #0f0, #ff0, #0ff, #f0f, #0ff);
    border-radius: 20px;
    animation: rotating 4s linear infinite;
}

.box::after {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-conic-gradient(from var(--a), #0f0, #ff0, #0ff, #f0f, #0ff);
    border-radius: 20px;
    animation: rotating 4s linear infinite;
    filter: blur(40px);
    opacity: 0.75;
}

.box span {
    position: absolute;
    inset: 4px;
    background: #222;
    border-radius: 16px;
    z-index: 1;
    /* opacity: 0; */
}

@property --a {
    syntax: '<angle>';
    inherits: false;
    initial-value: 0deg;
}

@keyframes rotating {
    0% {
        --a: 0deg;
    }

    50% {
        --a: 180deg;
    }

    100% {
        --a: 360deg;
    }
}

.box .box {
    position: absolute;
    inset: 0 -50px;
    top: 75px;
    height: 150px;
    width: 500px;
}
```

### Customization

Feel free to customize the code to match your project's design. You can adjust colors, dimensions, and other properties by modifying the CSS.

## License

This code is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Inspired by creative CSS animations and gradients.
