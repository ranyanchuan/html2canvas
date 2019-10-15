# html2canvas
html2canvas 网页截图

 ```js
import html2canvas from 'html2canvas';

onPrint = () => {
    console.log("----");
    const width=this.getDayNum() * 26 + 80;
    html2canvas(document.querySelector("#columnsGantta"), {
        width:width,
        // windowWidth:width,
        // y:width,
        height: document.getElementById('columnsGantta').clientHeight
    }).then(canvas => {
        var imgUrl = canvas.toDataURL("image/png", 1); // 此方法可以设置截图质量（0-1）
        console.log("base64编码数据：", imgUrl);

        canvas.toBlob(function (blob) {
            saveAs(blob, "hangge.png");
        });
        // document.body.appendChild(canvas);
    });
}
```
