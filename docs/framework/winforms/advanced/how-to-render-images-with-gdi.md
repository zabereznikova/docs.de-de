---
title: 'Vorgehensweise: Darstellen von Bildern mit GDI+'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: da637152737510847830e885fdcd065ab92f16b3
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505747"
---
# <a name="how-to-render-images-with-gdi"></a><span data-ttu-id="82726-102">Vorgehensweise: Darstellen von Bildern mit GDI+</span><span class="sxs-lookup"><span data-stu-id="82726-102">How to: Render Images with GDI+</span></span>
<span data-ttu-id="82726-103">GDI + können zum Rendern von Bildern, die als Dateien in Ihren Anwendungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="82726-103">You can use GDI+ to render images that exist as files in your applications.</span></span> <span data-ttu-id="82726-104">Hierzu erstellen ein neues Objekt des ein <xref:System.Drawing.Image> Klasse (z. B. <xref:System.Drawing.Bitmap>), wodurch eine <xref:System.Drawing.Graphics> -Objekts einen Verweis auf die Zeichenoberfläche, die Sie verwenden möchten, und dem Aufrufen der <xref:System.Drawing.Graphics.DrawImage%2A> -Methode der der <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="82726-104">You do this by creating a new object of an <xref:System.Drawing.Image> class (such as <xref:System.Drawing.Bitmap>), creating a <xref:System.Drawing.Graphics> object that refers to the drawing surface you want to use, and calling the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="82726-105">Das Bild wird auf die Zeichenoberfläche gezeichnet, die durch die Grafikklasse dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="82726-105">The image will be painted onto the drawing surface represented by the graphics class.</span></span> <span data-ttu-id="82726-106">Sie können die Bildbearbeitung zum Erstellen und Bearbeiten von Bilddateien zur Entwurfszeit verwenden und mit GDI + zur Laufzeit gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="82726-106">You can use the Image Editor to create and edit image files at design time, and render them with GDI+ at run time.</span></span> <span data-ttu-id="82726-107">Weitere Informationen finden Sie unter [Bildbearbeitung für Symbole](/cpp/windows/image-editor-for-icons).</span><span class="sxs-lookup"><span data-stu-id="82726-107">For more information, see [Image Editor for Icons](/cpp/windows/image-editor-for-icons).</span></span>  
  
### <a name="to-render-an-image-with-gdi"></a><span data-ttu-id="82726-108">So rendern Sie ein Bild mit GDI+</span><span class="sxs-lookup"><span data-stu-id="82726-108">To render an image with GDI+</span></span>  
  
1. <span data-ttu-id="82726-109">Erstellen Sie ein Objekt, das das anzuzeigende Bild darstellt.</span><span class="sxs-lookup"><span data-stu-id="82726-109">Create an object representing the image you want to display.</span></span> <span data-ttu-id="82726-110">Dieses Objekt muss ein Member einer Klasse, die von erbt sein <xref:System.Drawing.Image>, z. B. <xref:System.Drawing.Bitmap> oder <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="82726-110">This object must be a member of a class that inherits from <xref:System.Drawing.Image>, such as <xref:System.Drawing.Bitmap> or <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="82726-111">Ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="82726-111">An example is shown:</span></span>  
  
    ```vb  
    ' Uses the System.Environment.GetFolderPath to get the path to the   
    ' current user's MyPictures folder.  
    Dim myBitmap as New Bitmap _  
       (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.MyPictures))  
    ```  
  
    ```csharp  
    // Uses the System.Environment.GetFolderPath to get the path to the   
    // current user's MyPictures folder.  
    Bitmap myBitmap = new Bitmap  
       (System.Environment.GetFolderPath  
          (System.Environment.SpecialFolder.MyPictures));  
    ```  
  
    ```cpp  
    // Uses the System.Environment.GetFolderPath to get the path to the   
    // current user's MyPictures folder.  
    Bitmap^ myBitmap = gcnew Bitmap  
       (System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::MyPictures));  
    ```  
  
2. <span data-ttu-id="82726-112">Erstellen Sie eine <xref:System.Drawing.Graphics> Objekt, das die Zeichenoberfläche darstellt, Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82726-112">Create a <xref:System.Drawing.Graphics> object that represents the drawing surface you want to use.</span></span> <span data-ttu-id="82726-113">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="82726-113">For more information, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
    ```vb  
    ' Creates a Graphics object that represents the drawing surface of   
    ' Button1.  
    Dim g as Graphics = Button1.CreateGraphics  
    ```  
  
    ```csharp  
    // Creates a Graphics object that represents the drawing surface of   
    // Button1.  
    Graphics g = Button1.CreateGraphics();  
    ```  
  
    ```cpp  
    // Creates a Graphics object that represents the drawing surface of   
    // Button1.  
    Graphics^ g = button1->CreateGraphics();  
    ```  
  
3. <span data-ttu-id="82726-114">Rufen Sie die <xref:System.Drawing.Graphics.DrawImage%2A> der Grafikobjekte auf das Bild zu rendern.</span><span class="sxs-lookup"><span data-stu-id="82726-114">Call the <xref:System.Drawing.Graphics.DrawImage%2A> of your graphics object to render the image.</span></span> <span data-ttu-id="82726-115">Sie müssen das Bild angeben, das gezeichnet werden soll, und die Koordinaten, an denen es gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="82726-115">You must specify both the image to be drawn, and the coordinates where it is to be drawn.</span></span>  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="82726-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82726-116">See also</span></span>

- [<span data-ttu-id="82726-117">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="82726-117">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="82726-118">Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="82726-118">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="82726-119">Stifte, Linien und Rechtecke in GDI+</span><span class="sxs-lookup"><span data-stu-id="82726-119">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
- [<span data-ttu-id="82726-120">Vorgehensweise: Zeichnen von Text in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="82726-120">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)
- [<span data-ttu-id="82726-121">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="82726-121">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="82726-122">Zeichnen von Linien oder geschlossenen Körpern</span><span class="sxs-lookup"><span data-stu-id="82726-122">Drawing Lines or Closed Figures</span></span>](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [<span data-ttu-id="82726-123">Bildbearbeitung für Symbole</span><span class="sxs-lookup"><span data-stu-id="82726-123">Image Editor for Icons</span></span>](/cpp/windows/image-editor-for-icons)
