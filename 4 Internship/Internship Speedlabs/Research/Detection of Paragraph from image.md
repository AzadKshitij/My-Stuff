---
link: /vault/4 Internship/Internship Speedlabs/Research/Detection of Paragraph from image.md
---
# [Detect multiple blocks of text from an image of a document](https://stackoverflow.com/questions/63960038/how-to-detect-multiple-blocks-of-text-from-an-image-of-a-document)
1.  First you need to convert the image into grayscale
2.  Perform otsu'threshold which does better binarization in removing the background.
3.  Specify structure shape and kernel size. Kernel size increases or decreases the area of the rectangle to be detected.
4.  Applying dilation on the threshold image with the kernel when you dilated it gets thicker.
5.  Finding contours
6.  Looping through the identified contours Then the rectangular part is can be drawn using cv2.rectangle method
```python
import cv2
img = cv2.imread("text.jpg") 
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY) 
blur = cv2.GaussianBlur(gray,(5,5),0)

ret, thresh1 = cv2.threshold(blur, 0, 255, cv2.THRESH_OTSU + cv2.THRESH_BINARY_INV) 


rect_kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (18, 18)) 

dilation = cv2.dilate(thresh1, rect_kernel, iterations = 1) 

contours, hierarchy = cv2.findContours(dilation, cv2.RETR_EXTERNAL, 
                                                cv2.CHAIN_APPROX_NONE) 

for cnt in contours: 
    x, y, w, h = cv2.boundingRect(cnt) 
    
    # Drawing a rectangle on copied image 
    rect = cv2.rectangle(img, (x, y), (x + w, y + h), (0, 255, 0), 2) 
    
cv2.imwrite('drawed.png', img)
```

![[Pasted image 20220604215149.png]]


[python - Detect text region in image using Opencv - Stack Overflow](https://stackoverflow.com/questions/24385714/detect-text-region-in-image-using-opencv)

vault/Internship/Internship Speedlabs/Research/Detection of Paragraph from image

## 2022-06-09 22:40:34
https://ai2-website.s3.amazonaws.com/publications/pdf2.0.pdf


## 2022-06-10 11:43
## PDFigCapX and FigSplit - a Pipeline for Extracting Figures, SubFigures and Captions from Scientific Publications, Pengyuan Li - UD Capture | University of Delaware
URL: https://capture.udel.edu/media/PDFigCapX+and+FigSplit+-+a+Pipeline+for+Extracting+Figures%2C+SubFigures+and+Captions+from+Scientific+Publications%2C+Pengyuan+Li/1_cnwdpx05

## 2022-06-10 12:03:42
https://github.com/topics/literature-mining
## 2022-06-10 13:20:50
http://felix.abecassis.me/2011/10/opencv-bounding-box-skew-angle/
