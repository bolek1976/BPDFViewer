
BPDFViewer
=============
BPDFViewer is a PDF document viewer based on M13PDFKit
Screenshots:
-------------

* Main view, with toolbars showing.

<img src="https://raw.github.com/Marxon13/M13PDFKit/master/ReadmeResources/IMG_1041.PNG" width="300px">

* Main view without toolbars.

<img src="https://raw.github.com/Marxon13/M13PDFKit/master/ReadmeResources/IMG_1042.PNG" width="300px">

* Main view, bookmarked page.

<img src="https://raw.github.com/Marxon13/M13PDFKit/master/ReadmeResources/IMG_1043.PNG" width="300px">

* Thumb list, all pages.

<img src="https://raw.github.com/Marxon13/M13PDFKit/master/ReadmeResources/IMG_1044.PNG" width="300px">

* Thumb list, bookmarked pages.

<img src="https://raw.github.com/Marxon13/M13PDFKit/master/ReadmeResources/IMG_1045.PNG" width="300px">



Usage
-------------

*Prerequisite:* In the storyboard, the ViewController that is intended to display the PDF file needs to be in a UINavigationController stack and its corresponding class needs to be `PDFKBasicPDFViewer`

Next, in the `prepareSegue` method of your ViewController which segues to your PDF View Controller you will then need to add the following lines:

**Objective-C**
```objective-c
//Create the document for the viewer when the segue is performed.
PDFKBasicPDFViewer *viewer = (PDFKBasicPDFViewer *)segue.destinationViewController;

//Load the document
PDFKDocument *document = [PDFKDocument documentWithContentsOfFile:[[NSBundle mainBundle] pathForResource:@"Your PDF document actual location" ofType:@"pdf"] password:nil];
[viewer loadDocument:document];
```

**Swift**
```swift
//Create the document for the viewer when the segue is performed.
var viewer: PDFKBasicPDFViewer = segue.destinationViewController as PDFKBasicPDFViewer

//Load the document (pdfUrl represents the path on the phone of the pdf document you wish to load)
var document: PDFKDocument = PDFKDocument(contentsOfFile: pdfUrl!, password: nil)
viewer.loadDocument(document)
```




