# dnie495 meme

![](my_meme.png)

```
library(magick)
library(tidyverse)


first_image  <- image_read("https://d3cm515ijfiu6w.cloudfront.net/wp-content/uploads/2020/05/18123325/Fernando-Alonso-deckchair.jpg") %>% image_scale(500)
second_image <- image_read("https://d3cm515ijfiu6w.cloudfront.net/wp-content/uploads/2020/02/10114608/Fernando-Alonso.png") %>% image_scale(500)

text1 <- image_blank(width = 500, height = 400, color = "#FFFFFF") %>% image_annotate(text = "Relaxing after \nfinishing an \nassignment",
                                                                                      color = "#000000",
                                                                                      size = 50,
                                                                                      font = "Roboto",
                                                                                      gravity = "center")
text2 <- image_blank(width = 500, height = 400, color = "#FFFFFF") %>% image_annotate(text = "Realising that you \nhave 2 tests \nthe next day",
                                                                                      color = "#000000",
                                                                                      size = 50,
                                                                                      font = "Roboto",
                                                                                      gravity = "center")
top_row_image_and_text <- c(first_image, text1)
bottom_row_image_and_text <- c(second_image, text2)

top_row <- image_append(top_row_image_and_text)
bottom_row <- image_append(bottom_row_image_and_text)

meme <- c(top_row, bottom_row) %>% image_append(stack = TRUE) %>% image_scale(600)

meme 
image_write(meme, path = "my_meme.png")
```
