# PHP+前端开发的Atom常用插件
- simplified-chinese-menu
- emmet
- autocomplete-php
- linter
- linter-php
- atom-beautify
  - 配置executables的php和php-cs-fixer([下载php-cs-fixer-v2.phar](https://github.com/FriendsOfPHP/PHP-CS-Fixer/releases))

# 在线浏览office文档
- https://owa-box.vips100.com/op/view.aspx?src=
- https://view.officeapps.live.com/op/view.aspx?src=
- iframe https://view.officeapps.live.com/op/embed.aspx?src=

# 截取页面为图片
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>    
    <script src="https://cdn.jsdelivr.net/npm/html2canvas@1.0.0-rc.7/dist/html2canvas.min.js"></script>
</head>
<body>
    @*原始图片*@
    <div class="my-div">
        <img style="width: 400px; height: 300px" src="~/Img/longmao.jpg" />
    </div>
    <br />
    <input type="button" onclick="set()" value="截图" />

    @*截取后存放图片的位置*@
    <img id="img" />

    <script>
        function set() {
            //要转换为图片的dom对象
            var element = document.querySelector('body');
            //要显示图片的img标签
            var image = document.querySelector('#img');
            //调用html2image方法
            html2image(element, image);

            function html2image(element, image) {
                html2canvas(element).then(function (canvas) {
                    var imageData = canvas.toDataURL(1);
                    //此时图片已经可以显示了
                    image.src = imageData;
                });
            }
        }
    </script>
</body>
</html>

```
