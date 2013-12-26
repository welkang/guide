###无线Web开发者指南

====================

####无线Web开发简介


无线Web开发是基于智能手机上的游览器进行的Web开发。现在智能手机主要有Android和IOS两种操作系统的，因此基于手机Web的开发，主要是基于Android和IOS两种操作系统上的web开发。

基于两种操作系统的Web开发的共同点：
* 两者的浏览器引擎是基于webkit的，因此基于手机上的Web开发，主要是基于webkit的游览器开发，对于其他浏览器，例如firefox、ie和opera等游览器，可以不用做兼容考虑。
* 两者都是按照HTML5规范开发，因此对于HTML5的特性支持性都比较好。

不同点：
* android的厂商碎片化比较严重，加上由于webkit的开源特性，导致市面上有非常多的修改版webkit游览器，这些修改版的webkit，厂商会根据自己的需求对webkit进行修改，导致对HTML5的特性碎片化严重。同时HTML5标准不同厂商的实现不同，造成对于HTML5特性的支持度不同。以input type=date 日期控件为例，有些厂商实现了该标准，有些厂商没有实现该标准，就算实现了标准的厂商，对于日期控件的展现、交互也不尽相同。
* android的版本碎片化，android到本文档撰写为止，发展到了4.4的版本，对于web开发而言，主要分为两个阶段2.X和4.X的阶段，由于3.X是为TV等操作系统而做，2.X采用的webkit核心的版本是533.x版本，533的版本，是谷歌专门为当时的手机性能定制的，由于当时的手机，硬件性能不是很好，因此对于533版本的webkit游览器的实现是精简版的，因此对于HTML5标砖的实现不是非常彻底，并且对于某些实现还做了特定保留。此系列版本又可分为2.2以及以下和2.3版本，对于2.2以及下面的版本，对于html5的支持性不是很好，并且即使实现了，对于某些细节实现的比较有问题。2.3版本可以说是一次飞跃，在2.3的版本上，开始移植pc版chrome的核心代码实现，因此从2.3开始，android的web开发开始了新的旅程。
* ios由于其封闭性，并且苹果公司严格按照html5的规范来进行实现，因此在ios上html5的规范实现的较好。
* ios和android对于html5的规范实现在界面层和交互层的实现是不同的，就拿上面的列子来说 type date的日期控件，ios和android的交互实现，完全不同。虽然都按照w3c的标准进行了实现。这个也是在日常web开发中需要注意的。

--------

#### 无线Web开发需要注意的问题

##### HTML标签

###### meta的viewport
在无线Web开发中，在head头部遇到最常见的问题，就是viewport的设置， 
```
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0, user-scalable=0"/>
```
对于这里面的设置，大家可以Google一下，有非常详细的叙述，我这里不太重复,以下有几个地址，大家可以做下参考
https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag
https://developer.apple.com/library/safari/documentation/appleapplications/reference/SafariHTMLRef/Articles/MetaTags.html
等，其实更加具体的，大家可以再overstackflow或者google进行查询。

最佳实践：
* 一般情况下，在所有无线页面的头部，都要加上此viewport的设置，如果不加上此数值，会造成在某些webkit游览器中，游览器会根据自身的某些判断，自行做放大、缩小等，造成页面无法正常访问，特别是某些app中嵌入了webkit游览器来进行访问的时候，会出现以上所说的情况，因此为了保证你说设计的网页在所有手机中显示保持一致，加上此设置
* viewport中的设置数值一般不需要进行修改，因为现在的数值已经满足了绝大多数项目，当然会出现在非常特殊的页面里，需要用户进行手动缩放的操作，不过如果修改了数值，需要在不同的手机上进行详细的测试，否则会有你预期外的事情发生。

###### HTML5的标签使用
在无线Web的开发中，大家会经常使用HTML5的tag标签，对于HTML5的大多数标签使用起来不会遇到问题，比如说nav、footer、article等标签，这些展示型的标签一般可以安全使用，如果不是非常确定某个HTML5标签是否可以使用，建议参考http://caniuse.com/,

