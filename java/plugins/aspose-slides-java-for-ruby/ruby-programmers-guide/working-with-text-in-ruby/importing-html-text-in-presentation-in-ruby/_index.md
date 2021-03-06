---
title: Importing HTML Text in Presentation in Ruby
type: docs
weight: 50
url: /java/importing-html-text-in-presentation-in-ruby/
---

## **Aspose.Slides - Importing HTML Text in Presentation**
To Import HTML Text in Presentation using **Aspose.Slides Java for Ruby**, simply invoke **ImportHtml** module. Here you can see example code.

**Ruby Code**

```

 def initialize()

    data_dir = File.dirname(File.dirname(File.dirname(File.dirname(__FILE__)))) + '/data/Text/'



    # Create an instance of Presentation class

    pres = Rjb::import('com.aspose.slides.Presentation').new

    # Get the first slide

    slide = pres.getSlides().get_Item(0)

    # Adding the AutoShape to accomodate the HTML content

    ashape = slide.getShapes().addAutoShape(Rjb::import('com.aspose.slides.ShapeType').Rectangle, 10, 10, pres.getSlideSize().getSize().getWidth(), pres.getSlideSize().getSize().getHeight())

    ashape.getFillFormat().setFillType(Rjb::import('com.aspose.slides.FillType').NoFill)

    # Adding text frame to the shape

    ashape.addTextFrame("")

    # Clearing all paragraphs in added text frame

    ashape.getTextFrame().getParagraphs().clear()

    # Loading the HTML file using InputStream

    input_stream = Rjb::import('java.io.FileInputStream').new(data_dir + "import.html")

    reader = Rjb::import('java.io.InputStreamReader').new(input_stream)

    data = reader.read()

    content = read_file(data_dir + "import.html")

    # Adding text from HTML stream reader in text frame

    ashape.getTextFrame().getParagraphs().addFromHtml(content)

    # Saving Presentation

    pres.save(data_dir + "output.pptx", Rjb::import('com.aspose.slides.SaveFormat').Pptx)



    puts "Done with html import, please check the output file."

end

def read_file(file_name)

    file = Rjb::import('java.io.File').new(file_name)                                                                      

    contents = Rjb::import('java.lang.StringBuilder').new                                                                                                                                                                                                                                                                                                                          

    reader = Rjb::import('java.io.BufferedReader').new(Rjb::import('java.io.FileReader').new(file))                                                                              



    # repeat until all lines is read                                                                  

    while (text = reader.readLine()) != nil                                                     

        contents.append(text).append("\n")

    end   

    contents.toString()         

end   

```
## **Download Running Code**
Download **Importing HTML Text in Presentation (Aspose.Slides)** from any of the below mentioned social coding sites:

- [GitHub](https://github.com/aspose-slides/Aspose.Slides-for-Java/blob/master/Plugins/Aspose_Slides_Java_for_Ruby/lib/asposeslidesjava/Text/importhtml.rb)
