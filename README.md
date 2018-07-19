# BlindWaterMark
Java 盲水印

.</br>
├── build.gradle</br>
├── gakki-img-dc.png   *反解水印图(图片水印)</br>
├── gakki-text-dc.png  *反解水印图(文字水印)</br>
├── gakki-wm-img.png   *带图片盲水印的图</br>
├── gakki-wm-text.png  *带文字盲水印的图</br>
├── gakki.png          *原图</br>
└── wm.png             *图片水印</br>

###Usage

    打包成jar
    gradle build
    
    Usage: java -jar BlindWaterMark.jar <commands> [args...]
        commands:
                encode <option> <image-src>  <watermark-text>       <image-encoded(text)>
                encode <option> <image-src>  <watermark-image>      <image-encoded(image)>
                decode <image-encode(text)>  <image-decode>
                decode <image-src>           <image-encoded(image)> <image-decode>
        options:
                -i add image watermark
                -t add text  watermark
###Demo
java -jar BlindWaterMark.jar encode -t gakki.png mywife gakki-wm-text.png
![image](https://github.com/ww23/BlindWaterMark/blob/master/gakki.png) + "mywife" -> ![image](https://github.com/ww23/BlindWaterMark/blob/master/gakki-wm-text.png)
java -jar BlindWaterMark.jar encode -i gakki.png wm.png gakki-wm-img.png
![image](https://github.com/ww23/BlindWaterMark/blob/master/gakki.png) + ![image](https://github.com/ww23/BlindWaterMark/blob/master/wm.png) -> ![image](https://github.com/ww23/BlindWaterMark/blob/master/gakki-wm-img.png)
java -jar BlindWaterMark.jar decode gakki-wm-text.png gakki-text-dc.png
![image](https://github.com/ww23/BlindWaterMark/blob/master/gakki-text-dc.png)
java -jar BlindWaterMark.jar decode gakki.png gakki-wm-img.png gakki-img-dc.png
![image](https://github.com/ww23/BlindWaterMark/blob/master/gakki-img-dc.png)
