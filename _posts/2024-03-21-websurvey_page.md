---
layout: post
title: "カナダ在住日本人の文化適応とこころの健康に関するオンライン調査について"
categories: misc
---

私たちは現在、カナダ在住の日本人の方々の移住経験やこころの健康について調査しており、参加者を募集しています📣

カナダという異国の地で生活していくうえで、ストレスや困難を感じることもあるかと思います。カナダに住む日本人を対象としたメンタルヘルス研究はほとんどなく、データや知見が足りていません👩‍💻👨‍💻

応募条件をすべて満たす方は、ご参加・ご協力のほどよろしくお願いいたします。


<!DOCTYPE html>
<html>
<head>
    <title>PDF.js Example</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/2.7.570/pdf.min.js"></script>
</head>
<body>
    <canvas id="pdf-canvas"></canvas>
    <script>
        // PDF.jsを使ってPDFを読み込む
        var url = 'https://acculturationproject.github.io/assets/pdf/Cultural_Adjustment_and_Mental_Health%20Study_of_Japanese_Residents_in_Canada.pdf';

        // PDF文書を取得
        pdfjsLib.getDocument(url).promise.then(function(pdfDoc) {
            // 最初のページを取得
            pdfDoc.getPage(1).then(function(page) {
                var canvas = document.getElementById('pdf-canvas');
                var ctx = canvas.getContext('2d');
                var scale = 1; // スケールは後で調整
                var viewport = page.getViewport({scale: scale});

                // 画面の幅に合わせてスケールを調整
                var scale = document.documentElement.clientWidth / viewport.width;
                viewport = page.getViewport({scale: scale});

                // Canvasのサイズをページのサイズに合わせる
                canvas.width = viewport.width;
                canvas.height = viewport.height;

                // ページをCanvasにレンダリング
                var renderContext = {
                    canvasContext: ctx,
                    viewport: viewport
                };
                page.render(renderContext);
            });
        });
    </script>
</body>
</html>

