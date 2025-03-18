# 🌍 SVETLOBNA ONESNAŽENOST 2013 - 2022

Ta repozitorij vsebuje vizualizacije svetlobne onesnaženosti za izbrana slovenska mesta.

## 📌 ANIMACIJE SVETLOBNE ONESNAŽENOSTI

---

### <h2 align="center"><b>LJUBLJANA</b></h2>

<div style="text-align: center;">
    <img src="Ljubljana.gif" width="100%">
    <div style="position: relative; display: inline-block;">
        <img src="Ljubljana.png" width="40%" id="pngLjubljana">
        <canvas id="overlayCanvasLjubljana" style="position: absolute; top: 0; left: 0;"></canvas>
    </div>
</div>

---

### <h2 align="center"><b>TRST IN KOPER</b></h2>

<div style="text-align: center;">
    <img src="Trst-Koper.gif" width="100%">
    <div style="position: relative; display: inline-block;">
        <img src="Trst-Koper.png" width="40%" id="pngTrstKoper">
        <canvas id="overlayCanvasTrstKoper" style="position: absolute; top: 0; left: 0;"></canvas>
    </div>
</div>

---

<script>
    function animateCanvas(imageId, canvasId, duration, steps) {
        const canvas = document.getElementById(canvasId);
        const img = document.getElementById(imageId);
        canvas.width = img.width;
        canvas.height = img.height;
        const ctx = canvas.getContext('2d');
        let startTime = null;

        function animate(timestamp) {
            if (!startTime) startTime = timestamp;
            const progress = (timestamp - startTime) / duration;
            if (progress > 1) startTime = timestamp; // Resetira animacijo

            // Počisti prejšnjo črto
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // Izračun pozicije črte
            const x = progress * canvas.width;

            // Nariši črto
            ctx.beginPath();
            ctx.moveTo(x, 0);
            ctx.lineTo(x, canvas.height);
            ctx.strokeStyle = "red";
            ctx.lineWidth = 2;
            ctx.stroke();

            requestAnimationFrame(animate);
        }
        requestAnimationFrame(animate);
    }

    window.onload = function() {
        animateCanvas('pngLjubljana', 'overlayCanvasLjubljana', 5000, 10);
        animateCanvas('pngTrstKoper', 'overlayCanvasTrstKoper', 5000, 10);
    };
</script>

---

## 🔗 POVEZAVE
🌍 [NASA Earthdata - Nighttime Lights](https://www.earthdata.nasa.gov/topics/human-dimensions/nighttime-lights)  
🌍 [Temno Nebo Slovenija](http://www.temnonebo.si/)
