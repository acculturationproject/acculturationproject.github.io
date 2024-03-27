---
layout: post
title: "カナダ在住日本人の文化適応とこころの健康に関するオンライン調査について"
categories: misc
---

私たちは現在、カナダ在住の日本人の方々の移住経験やこころの健康について調査しており、参加者を募集しています📣

カナダという異国の地で生活していくうえで、ストレスや困難を感じることもあるかと思います。カナダに住む日本人を対象としたメンタルヘルス研究はほとんどなく、データや知見が足りていません👩‍💻👨‍💻

応募条件をすべて満たす方は、ご参加・ご協力のほどよろしくお願いいたします。

アンケートのURLはこちら: [https://bit.ly/JapaneseCanadaKokoroHealth](https://bit.ly/JapaneseCanadaKokoroHealth)


<html>
<head>
    <title>Responsive PDF Display Example</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/2.7.570/pdf.min.js"></script>
    <style>
        #pdf-canvas {
            width: 100%;
            display: none; /* Initially hide canvas */
        }
        iframe {
            width: 100%;
            height: 100vh;
            display: none; /* Initially hide iframe */
        }
    </style>
</head>
<body>

<canvas id="pdf-canvas"></canvas>
<iframe id="pdf-iframe" frameborder="0"></iframe>

<script>
var screenWidth = window.innerWidth || document.documentElement.clientWidth || document.body.clientWidth;
var devicePixelRatio = window.devicePixelRatio || 1; // デバイスのピクセル比を取得

if (screenWidth < 768) {
    // For mobile devices, use PDF.js to display the PDF
    document.getElementById('pdf-canvas').style.display = 'block';

    var url = 'https://acculturationproject.github.io/assets/pdf/Cultural_Adjustment_and_Mental_Health%20Study_of_Japanese_Residents_in_Canada.pdf';
    pdfjsLib.getDocument(url).promise.then(function(pdfDoc) {
        pdfDoc.getPage(1).then(function(page) {
            var canvas = document.getElementById('pdf-canvas');
            var context = canvas.getContext('2d');
            var viewport = page.getViewport({scale: 1});
            var scale = (screenWidth / viewport.width) * devicePixelRatio;
            var scaledViewport = page.getViewport({scale: scale});

            canvas.style.height = 'auto';
            canvas.style.width = `${screenWidth}px`; // CSSでの幅の設定

            canvas.height = scaledViewport.height * devicePixelRatio; // 実際のピクセル数を考慮
            canvas.width = screenWidth * devicePixelRatio; // CSSの幅とピクセル比を考慮した実際の幅

            // 描画コンテキストのスケールを調整
            context.scale(devicePixelRatio, devicePixelRatio);

            var renderContext = {
                canvasContext: context,
                viewport: scaledViewport
            };
            page.render(renderContext);
        });
    });
} else {
        // パソコンの場合、iframeを使用してPDFを表示
        var iframe = document.getElementById('pdf-iframe');
        iframe.style.display = 'block';
        iframe.src = 'https://acculturationproject.github.io/assets/pdf/Cultural_Adjustment_and_Mental_Health%20Study_of_Japanese_Residents_in_Canada.pdf';
    }
</script>

</body>
</html>
