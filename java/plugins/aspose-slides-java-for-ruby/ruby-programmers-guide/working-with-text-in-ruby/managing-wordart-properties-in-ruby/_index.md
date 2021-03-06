---
title: Managing WordArt Properties in Ruby
type: docs
weight: 150
url: /java/managing-wordart-properties-in-ruby/
---

## **Aspose.Slides - Managing WordArt Properties**
To Manage WordArt Properties using **Aspose.Slides Java for Ruby**, simply invoke **WordArt** module. Here you can see example code.

**Ruby Code**

```

 data_dir = File.dirname(File.dirname(File.dirname(File.dirname(__FILE__)))) + '/data/Text/'



\# Create an instance of Presentation class

pres = Rjb::import('com.aspose.slides.Presentation').new

\# Get the first slide

slide = pres.getSlides().get_Item(0)

\# Add an AutoShape of Rectangle type

ashp = slide.getShapes().addAutoShape(Rjb::import('com.aspose.slides.ShapeType').Rectangle, 150, 75, 400, 300)

ashp.getFillFormat().setFillType(Rjb::import('com.aspose.slides.FillType').NoFill)

\# Add TextFrame to the Rectangle

ashp.addTextFrame("Aspose TextBox")

port = ashp.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0)

pf = port.getPortionFormat()

pf.setFontHeight(50)

\# Enable InnerShadowEffect            

ef = pf.getEffectFormat()

ef.enableInnerShadowEffect()

\# Set all necessary parameters

ef.getInnerShadowEffect().setBlurRadius(8.0)

ef.getInnerShadowEffect().setDirection(90)

ef.getInnerShadowEffect().setDistance(6.0)

ef.getInnerShadowEffect().getShadowColor().setB(189)

\# Set ColorType as Scheme

ef.getInnerShadowEffect().getShadowColor().setColorType(Rjb::import('com.aspose.slides.ColorType').Scheme)

\# Set Scheme Color

ef.getInnerShadowEffect().getShadowColor().setSchemeColor(Rjb::import('com.aspose.slides.SchemeColor').Accent1)

\# Write the presentation as a PPTX file 

save_format = Rjb::import('com.aspose.slides.SaveFormat')

pres.save(data_dir + "WordArt.pptx", save_format.Pptx)

puts "Done with word art, please check the output file."

```
## **Download Running Code**
Download **Managing WordArt Properties (Aspose.Slides)** from any of the below mentioned social coding sites:

- [GitHub](https://github.com/aspose-slides/Aspose.Slides-for-Java/blob/master/Plugins/Aspose_Slides_Java_for_Ruby/lib/asposeslidesjava/Text/wordart.rb)
