### 浏览器端

psd.js在浏览器下性能一般：

小文件（10mb）2-3s。

大文件（50mb）10s。

例子：[基于psd.js的前端解析工具](https://imcuttle.github.io/measure/#/source)

### 服务端

高星psd解析库

语言 | 解析库地址 | star | performance | problem
---|--- | --- | --- | ---
node.js | [psd.js](https://github.com/meltingice/psd.js) | 1.5k |  2.5 | unknown
ruby | [psd.rb](https://github.com/layervault/psd.rb) | 2.5k | 1 | unknown
java | [java-psd-library](https://github.com/inevo/java-psd-library) |38 | 4 | unknown
go | [psd](https://github.com/oov/psd) | 43 | 4.5  | unknown
python |[psd-tools](https://github.com/psd-tools/psd-tools)  [psd-tools文档](https://psd-tools.readthedocs.io/en/latest/reference/psd_tools.html)  | 450 | 2 | unknown
c/c++ | [psdump](https://github.com/alco/psdump) | 76 | 5 | 1. 有些psd渲染出来是纯白的，似乎没有完整的渲染功能<br/>2. 不能去掉文本层后颜色失真，似乎有些剪切蒙版没有完全实现

解析结构

`psd.js`

```
{ children: 
   [ { type: 'group',
       visible: false,
       opacity: 1,
       blendingMode: 'normal',
       name: 'Version D',
       left: 0,
       right: 900,
       top: 0,
       bottom: 600,
       height: 600,
       width: 900,
       children: 
        [ { type: 'layer',
            visible: true,
            opacity: 1,
            blendingMode: 'normal',
            name: 'Make a change and save.',
            left: 275,
            right: 636,
            top: 435,
            bottom: 466,
            height: 31,
            width: 361,
            mask: {},
            text: 
             { value: 'Make a change and save.',
               font: 
                { name: 'HelveticaNeue-Light',
                  sizes: [ 33 ],
                  colors: [ [ 85, 96, 110, 255 ] ],
                  alignment: [ 'center' ] },
               left: 0,
               top: 0,
               right: 0,
               bottom: 0,
               transform: { xx: 1, xy: 0, yx: 0, yy: 1, tx: 456, ty: 459 } },
            image: {} } ] } ],
    document: 
       { width: 900,
         height: 600,
         resources: 
          { layerComps: 
             [ { id: 692243163, name: 'Version A', capturedInfo: 1 },
               { id: 725235304, name: 'Version B', capturedInfo: 1 },
               { id: 730932877, name: 'Version C', capturedInfo: 1 } ],
            guides: [],
            slices: [] } } }
```

`psd.rb`

```
{:children=>
  [{:type=>:group,
    :visible=>false,
    :opacity=>1.0,
    :blending_mode=>"normal",
    :name=>"Version D",
    :left=>0,
    :right=>900,
    :top=>0,
    :bottom=>600,
    :height=>900,
    :width=>600,
    :children=>
     [{:type=>:layer,
       :visible=>true,
       :opacity=>1.0,
       :blending_mode=>"normal",
       :name=>"Make a change and save.",
       :left=>275,
       :right=>636,
       :top=>435,
       :bottom=>466,
       :height=>31,
       :width=>361,
       :text=>
        {:value=>"Make a change and save.",
         :font=>
          {:name=>"HelveticaNeue-Light",
           :sizes=>[33.0],
           :colors=>[[255, 19, 120, 98]],
           :css=>
            "font-family: \"HelveticaNeue-Light\", \"AdobeInvisFont\", \"MyriadPro-Regular\";\nfont-size: 33.0pt;\ncolor: rgba(19, 120, 98, 255);"},
         :left=>0,
         :top=>0,
         :right=>0,
         :bottom=>0,
         :transform=>
          {:xx=>1.0, :xy=>0.0, :yx=>0.0, :yy=>1.0, :tx=>456.0, :ty=>459.0}},
       :ref_x=>264.0,
       :ref_y=>-3.0}]
  }],
:document=>{:width=>900, :height=>600}}
```

附录：[The Computer Language
Benchmarks Game](https://benchmarksgame-team.pages.debian.net/benchmarksgame/)






