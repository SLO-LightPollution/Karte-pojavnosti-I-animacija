# 🌍 SVETLOBNA ONESNAŽENOST 2013 - 2022

Ta repozitorij vsebuje vizualizacije svetlobne onesnaženosti za izbrana slovenska mesta.

## 📌 ANIMACIJE SVETLOBNE ONESNAŽENOSTI

---

### <h2 align="center"><b>LJUBLJANA</b></h2>
<div style="text-align: center; position: relative;">
    <img src="Ljubljana.gif" width="100%">
    <div style="position: relative; display: inline-block;">
        <img src="Ljubljana.png" width="40%" id="pngLjubljana">
        <canvas class="overlayCanvas" data-target="pngLjubljana" style="position: absolute; top: 0; left: 0;"></canvas>
    </div>
</div>

---

### <h2 align="center"><b>TRST IN KOPER</b></h2>
<div style="text-align: center; position: relative;">
    <img src="Trst-Koper.gif" width="100%">
    <div style="position: relative; display: inline-block;">
        <img src="Trst-Koper.png" width="40%" id="pngTrstKoper">
        <canvas class="overlayCanvas" data-target="pngTrstKoper" style="position: absolute; top: 0; left: 0;"></canvas>
    </div>
</div>

---

### <h2 align="center"><b>MARIBOR</b></h2>
<div style="text-align: center; position: relative;">
    <img src="Maribor.gif" width="100%">
    <div style="position: relative; display: inline-block;">
        <img src="Maribor.png" width="40%" id="pngMaribor">
        <canvas class="overlayCanvas" data-target="pngMaribor" style="position: absolute; top: 0; left: 0;"></canvas>
    </div>
</div>

---

### <h2 align="center"><b>CELJE</b></h2>
<div style="text-align: center; position: relative;">
    <img src="Celje.gif" width="100%">
    <div style="position: relative; display: inline-block;">
        <img src="Celje.png" width="40%" id="pngCelje">
        <canvas class="overlayCanvas" data-target="pngCelje" style="position: absolute; top: 0; left: 0;"></canvas>
    </div>
</div>

---

### <h2 align="center"><b>KRANJ</b></h2>
<div style="text-align: center; position: relative;">
    <img src="Kranj.gif" width="100%">
    <div style="position: relative; display: inline-block;">
        <img src="Kranj.png" width="40%" id="pngKranj">
        <canvas class="overlayCanvas" data-target="pngKranj" style="position: absolute; top: 0; left: 0;"></canvas>
    </div>
</div>

---

### <h2 align="center"><b>NOVO MESTO</b></h2>
<div style="text-align: center; position: relative;">
    <img src="Novo-mesto.gif" width="100%">
    <div style="position: relative; display: inline-block;">
        <img src="Novo-mesto.png" width="40%" id="pngNovoMesto">
        <canvas class="overlayCanvas" data-target="pngNovoMesto" style="position: absolute; top: 0; left: 0;"></canvas>
    </div>
</div>

---

<script>
    function animateCanvas() {
        document.querySelectorAll('.overlayCanvas').forEach(canvas => {
            const img = document.getElementById(canvas.getAttribute('data-target'));
            if (!img) return;
            canvas.width = img.width;
            canvas.height = img.height;
            const ctx = canvas.getContext('2d');
            const duration = 5000; // Čas trajanja animacije GIF v milisekundah
            let startTime = null;

            function animate(timestamp) {
                if (!startTime) startTime = timestamp;
                const progress = (timestamp - startTime) / duration;
                if (progress > 1) startTime = timestamp; // Resetira animacijo

                ctx.clearRect(0, 0, canvas.width, canvas.height);
                const x = progress * canvas.width;

                ctx.beginPath();
                ctx.moveTo(x, 0);
                ctx.lineTo(x, canvas.height);
                ctx.strokeStyle = "red";
                ctx.lineWidth = 2;
                ctx.stroke();

                requestAnimationFrame(animate);
            }
            requestAnimationFrame(animate);
        });
    }

    window.onload = animateCanvas;
</script>

## 🔗 POVEZAVE
🌍 [NASA Earthdata - Nighttime Lights](https://www.earthdata.nasa.gov/topics/human-dimensions/nighttime-lights)  
🌍 [Temno Nebo Slovenija](http://www.temnonebo.si/)
