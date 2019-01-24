---
title: 'Vorgehensweise: Darstellen von Bildern mit GDI +'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: a289aee211d5115d80e7ad0d9152b05a0eaf5487
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567805"
---
# <a name="how-to-render-images-with-gdi"></a><span data-ttu-id="aabd6-102">Vorgehensweise: Darstellen von Bildern mit GDI +</span><span class="sxs-lookup"><span data-stu-id="aabd6-102">How to: Render Images with GDI+</span></span>
<span data-ttu-id="aabd6-103">Sie können [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] zum Rendern von Bildern verwenden, die als Dateien in den Anwendungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="aabd6-103">You can use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to render images that exist as files in your applications.</span></span> <span data-ttu-id="aabd6-104">Hierzu erstellen ein neues Objekt des ein <xref:System.Drawing.Image> Klasse (z. B. <xref:System.Drawing.Bitmap>), wodurch eine <xref:System.Drawing.Graphics> -Objekts einen Verweis auf die Zeichenoberfläche, die Sie verwenden möchten, und dem Aufrufen der <xref:System.Drawing.Graphics.DrawImage%2A> -Methode der der <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="aabd6-104">You do this by creating a new object of an <xref:System.Drawing.Image> class (such as <xref:System.Drawing.Bitmap>), creating a <xref:System.Drawing.Graphics> object that refers to the drawing surface you want to use, and calling the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="aabd6-105">Das Bild wird auf die Zeichenoberfläche gezeichnet, die durch die Grafikklasse dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="aabd6-105">The image will be painted onto the drawing surface represented by the graphics class.</span></span> <span data-ttu-id="aabd6-106">Sie können mithilfe der Bildbearbeitung Bilddateien zur Entwurfszeit erstellen und bearbeiten und diese mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] zur Laufzeit rendern.</span><span class="sxs-lookup"><span data-stu-id="aabd6-106">You can use the Image Editor to create and edit image files at design time, and render them with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] at run time.</span></span> <span data-ttu-id="aabd6-107">Weitere Informationen finden Sie unter [Bildbearbeitung für Symbole](/cpp/windows/image-editor-for-icons).</span><span class="sxs-lookup"><span data-stu-id="aabd6-107">For more information, see [Image Editor for Icons](/cpp/windows/image-editor-for-icons).</span></span>  
  
### <a name="to-render-an-image-with-gdi"></a><span data-ttu-id="aabd6-108">So rendern Sie ein Bild mit GDI+</span><span class="sxs-lookup"><span data-stu-id="aabd6-108">To render an image with GDI+</span></span>  
  
1.  <span data-ttu-id="aabd6-109">Erstellen Sie ein Objekt, das das anzuzeigende Bild darstellt.</span><span class="sxs-lookup"><span data-stu-id="aabd6-109">Create an object representing the image you want to display.</span></span> <span data-ttu-id="aabd6-110">Dieses Objekt muss ein Member einer Klasse, die von erbt sein <xref:System.Drawing.Image>, z. B. <xref:System.Drawing.Bitmap> oder <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="aabd6-110">This object must be a member of a class that inherits from <xref:System.Drawing.Image>, such as <xref:System.Drawing.Bitmap> or <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="aabd6-111">Ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="aabd6-111">An example is shown:</span></span>  
  
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
  
2.  <span data-ttu-id="aabd6-112">Erstellen Sie eine <xref:System.Drawing.Graphics> Objekt, das die Zeichenoberfläche darstellt, Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="aabd6-112">Create a <xref:System.Drawing.Graphics> object that represents the drawing surface you want to use.</span></span> <span data-ttu-id="aabd6-113">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="aabd6-113">For more information, see [How to: Create Graphics Objects for Drawing](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
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
  
3.  <span data-ttu-id="aabd6-114">Rufen Sie die <xref:System.Drawing.Graphics.DrawImage%2A> der Grafikobjekte auf das Bild zu rendern.</span><span class="sxs-lookup"><span data-stu-id="aabd6-114">Call the <xref:System.Drawing.Graphics.DrawImage%2A> of your graphics object to render the image.</span></span> <span data-ttu-id="aabd6-115">Sie müssen das Bild angeben, das gezeichnet werden soll, und die Koordinaten, an denen es gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="aabd6-115">You must specify both the image to be drawn, and the coordinates where it is to be drawn.</span></span>  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="aabd6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aabd6-116">See also</span></span>
- [<span data-ttu-id="aabd6-117">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="aabd6-117">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [<span data-ttu-id="aabd6-118">Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="aabd6-118">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="aabd6-119">Stifte, Linien und Rechtecke in GDI+</span><span class="sxs-lookup"><span data-stu-id="aabd6-119">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
- [<span data-ttu-id="aabd6-120">Vorgehensweise: Zeichnen von Text in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="aabd6-120">How to: Draw Text on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)
- [<span data-ttu-id="aabd6-121">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aabd6-121">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="aabd6-122">Zeichnen von Linien oder geschlossenen Körpern</span><span class="sxs-lookup"><span data-stu-id="aabd6-122">Drawing Lines or Closed Figures</span></span>](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [<span data-ttu-id="aabd6-123">Bildbearbeitung für Symbole</span><span class="sxs-lookup"><span data-stu-id="aabd6-123">Image Editor for Icons</span></span>](/cpp/windows/image-editor-for-icons)
