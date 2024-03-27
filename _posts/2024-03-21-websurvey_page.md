---
layout: post
title: "カナダ在住日本人の文化適応とこころの健康に関するオンライン調査について"
categories: misc
---

私たちは現在、カナダ在住の日本人の方々の移住経験やこころの健康について調査しており、参加者を募集しています📣

カナダという異国の地で生活していくうえで、ストレスや困難を感じることもあるかと思います。カナダに住む日本人を対象としたメンタルヘルス研究はほとんどなく、データや知見が足りていません👩‍💻👨‍💻

応募条件をすべて満たす方は、ご参加・ご協力のほどよろしくお願いいたします。

オンライン調査のURLはこちら: [https://bit.ly/JapaneseCanadaKokoroHealth](https://bit.ly/JapaneseCanadaKokoroHealth)

<html>
<head>
    <title>Responsive PDF Display Corrected</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/2.7.570/pdf.min.js"></script>
</head>
<body>

<canvas id="pdf-canvas"></canvas>

<script>
    var url = 'https://acculturationproject.github.io/assets/pdf/Cultural_Adjustment_and_Mental_Health%20Study_of_Japanese_Residents_in_Canada.pdf';

    // PDFを読み込んで指定のスケールでページをレンダリングする関数
    function renderPDF() {
        pdfjsLib.getDocument(url).promise.then(function(pdfDoc) {
            pdfDoc.getPage(1).then(function(page) {
                var canvas = document.getElementById('pdf-canvas');
                var context = canvas.getContext('2d');

                // 画面の幅に合わせてスケールを計算
                var viewport = page.getViewport({scale: 0.9});
                var scale = window.innerWidth / viewport.width;
                var scaledViewport = page.getViewport({scale: scale});

                canvas.width = scaledViewport.width*0.9;
                canvas.height = scaledViewport.height*0.9;

                var renderContext = {
                    canvasContext: context,
                    viewport: scaledViewport
                };

                page.render(renderContext);
            });
        });
    }

    // ドキュメントのロード時とウィンドウのリサイズ時にPDFを再レンダリング
    function onDocumentLoadOrResize() {
        renderPDF();
    }

    window.addEventListener('load', onDocumentLoadOrResize);
    window.addEventListener('resize', onDocumentLoadOrResize);
</script>

</body>
</html>

