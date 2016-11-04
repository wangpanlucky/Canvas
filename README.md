# Canvas
practice some demo  about &lt;canvas>


基本用法:
1.在body中
<canvas id="drawing" width="200" height="200">A drawing of something.</canvas>

2.要在canvas画布上绘图,需要取得绘图上下文,取得绘图上下文的引用调用getContext()方法,并且传入上下文的名字
传入2d就可以取得2D上下文对象

    var drawing = document.getElementById("drawing");
    //确定浏览器支持<canvas>元素
    if(drawing.getContext){
        var context = drawing.getContext("2d");
        //填写更多代码
    }


3.使用toDataURL()方法,可以导出<canvas>元素上绘制的图像,该方法接受一个参数,即图像的MIME类型格式,而且适用于创建图像的任何上下文
    if(drawing.getContext){
        //取得图像的数据URl
        var imgURL = drawing.toDataURL("image/png");

        //显示图像
        var image = document.createElement("img");
        image.src = imgURL;
        document.body.appendChild(image);
    }

4.如果画布上的图像来自不同的域,toDataURL()方法会抛出错误


