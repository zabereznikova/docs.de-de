---
title: 'Gewusst wie: Darstellen von Bildern mit GDI+'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: fffe1f1052d7323d234985b7e752866f2e89657d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182507"
---
# <a name="how-to-render-images-with-gdi"></a><span data-ttu-id="08507-102">Gewusst wie: Darstellen von Bildern mit GDI+</span><span class="sxs-lookup"><span data-stu-id="08507-102">How to: Render Images with GDI+</span></span>
<span data-ttu-id="08507-103">Sie können GDI+ verwenden, um Bilder zu rendern, die als Dateien in Ihren Anwendungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="08507-103">You can use GDI+ to render images that exist as files in your applications.</span></span> <span data-ttu-id="08507-104">Dazu erstellen Sie ein neues <xref:System.Drawing.Image> Objekt einer <xref:System.Drawing.Bitmap>Klasse (z. B. ), indem Sie ein <xref:System.Drawing.Graphics> Objekt <xref:System.Drawing.Graphics.DrawImage%2A> erstellen, <xref:System.Drawing.Graphics> das auf die gewünschte Zeichnungsfläche verweist, und die Methode des Objekts aufrufen.</span><span class="sxs-lookup"><span data-stu-id="08507-104">You do this by creating a new object of an <xref:System.Drawing.Image> class (such as <xref:System.Drawing.Bitmap>), creating a <xref:System.Drawing.Graphics> object that refers to the drawing surface you want to use, and calling the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="08507-105">Das Bild wird auf die Zeichenoberfläche gezeichnet, die durch die Grafikklasse dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="08507-105">The image will be painted onto the drawing surface represented by the graphics class.</span></span> <span data-ttu-id="08507-106">Sie können den Bildeditor verwenden, um Bilddateien zur Entwurfszeit zu erstellen und zu bearbeiten und sie zur Laufzeit mit GDI+ zu rendern.</span><span class="sxs-lookup"><span data-stu-id="08507-106">You can use the Image Editor to create and edit image files at design time, and render them with GDI+ at run time.</span></span> <span data-ttu-id="08507-107">Weitere Informationen finden Sie unter [Bildbearbeitung für Symbole](/cpp/windows/image-editor-for-icons).</span><span class="sxs-lookup"><span data-stu-id="08507-107">For more information, see [Image Editor for Icons](/cpp/windows/image-editor-for-icons).</span></span>  
  
### <a name="to-render-an-image-with-gdi"></a><span data-ttu-id="08507-108">So rendern Sie ein Bild mit GDI+</span><span class="sxs-lookup"><span data-stu-id="08507-108">To render an image with GDI+</span></span>  
  
1. <span data-ttu-id="08507-109">Erstellen Sie ein Objekt, das das anzuzeigende Bild darstellt.</span><span class="sxs-lookup"><span data-stu-id="08507-109">Create an object representing the image you want to display.</span></span> <span data-ttu-id="08507-110">Dieses Objekt muss ein Member einer Klasse <xref:System.Drawing.Image>sein, <xref:System.Drawing.Bitmap> die <xref:System.Drawing.Imaging.Metafile>von erbt, z. B. oder .</span><span class="sxs-lookup"><span data-stu-id="08507-110">This object must be a member of a class that inherits from <xref:System.Drawing.Image>, such as <xref:System.Drawing.Bitmap> or <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="08507-111">Ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="08507-111">An example is shown:</span></span>  
  
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
  
2. <span data-ttu-id="08507-112">Erstellen <xref:System.Drawing.Graphics> Sie ein Objekt, das die Zeichnungsfläche darstellt, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="08507-112">Create a <xref:System.Drawing.Graphics> object that represents the drawing surface you want to use.</span></span> <span data-ttu-id="08507-113">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="08507-113">For more information, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
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
  
3. <span data-ttu-id="08507-114">Rufen <xref:System.Drawing.Graphics.DrawImage%2A> Sie das Grafikobjekt auf, um das Bild zu rendern.</span><span class="sxs-lookup"><span data-stu-id="08507-114">Call the <xref:System.Drawing.Graphics.DrawImage%2A> of your graphics object to render the image.</span></span> <span data-ttu-id="08507-115">Sie müssen das Bild angeben, das gezeichnet werden soll, und die Koordinaten, an denen es gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08507-115">You must specify both the image to be drawn, and the coordinates where it is to be drawn.</span></span>  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="08507-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08507-116">See also</span></span>

- [<span data-ttu-id="08507-117">Erste Schritte mit der Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="08507-117">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="08507-118">Gewusst wie: Erstellen von Graphics-Objekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="08507-118">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="08507-119">Stifte, Linien und Rechtecke in GDI+</span><span class="sxs-lookup"><span data-stu-id="08507-119">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
- [<span data-ttu-id="08507-120">Gewusst wie: Zeichnen von Text in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="08507-120">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)
- [<span data-ttu-id="08507-121">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="08507-121">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="08507-122">Zeichnen von Linien oder geschlossenen Figuren</span><span class="sxs-lookup"><span data-stu-id="08507-122">Drawing Lines or Closed Figures</span></span>](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [<span data-ttu-id="08507-123">Bildbearbeitung für Symbole</span><span class="sxs-lookup"><span data-stu-id="08507-123">Image Editor for Icons</span></span>](/cpp/windows/image-editor-for-icons)
