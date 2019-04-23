---
title: 'Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
ms.openlocfilehash: 79eae4d37c056fc95ac73c78e00dd1a2b68bcd24
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324200"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="3d7d7-102">Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="3d7d7-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="3d7d7-103">Bevor Sie Linien und Formen zeichnen können, Rendern von Text oder anzeigen und Bearbeiten von Bildern mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], müssen Sie erstellen eine <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-103">Before you can draw lines and shapes, render text, or display and manipulate images with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="3d7d7-104">Die <xref:System.Drawing.Graphics> -Objekt stellt eine [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Zeichenoberfläche und ist das Objekt, das zum Erstellen von Grafiken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-104">The <xref:System.Drawing.Graphics> object represents a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="3d7d7-105">Es gibt zwei Schritte bei der Arbeit mit Grafiken:</span><span class="sxs-lookup"><span data-stu-id="3d7d7-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="3d7d7-106">Erstellen einer <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="3d7d7-107">Mithilfe der <xref:System.Drawing.Graphics> Objekt, das Zeichnen von Linien und Formen, Rendern von Text oder anzeigen und Bearbeiten von Bildern.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="3d7d7-108">Erstellen ein Grafikobjekt</span><span class="sxs-lookup"><span data-stu-id="3d7d7-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="3d7d7-109">Ein Grafikobjekt kann auf verschiedene Arten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="3d7d7-110">Um ein Graphics-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-110">To create a graphics object</span></span>  
  
-   <span data-ttu-id="3d7d7-111">Erhalten Sie einen Verweis auf ein Graphics-Objekt als Teil der <xref:System.Windows.Forms.PaintEventArgs> in die <xref:System.Windows.Forms.Control.Paint> Ereignis eines Formulars oder Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="3d7d7-112">Dies ist in der Regel an, wie Sie einen Verweis auf ein Graphics-Objekt abrufen, beim von Zeichnungscode für ein Steuerelement zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="3d7d7-113">Auf ähnliche Weise können Sie ein Grafikobjekt auch abrufen, als Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs> bei der Verarbeitung der <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis für eine <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="3d7d7-114">- oder - </span><span class="sxs-lookup"><span data-stu-id="3d7d7-114">-or-</span></span>  
  
-   <span data-ttu-id="3d7d7-115">Rufen Sie die <xref:System.Windows.Forms.Control.CreateGraphics%2A> Methode des Steuerelements oder Formulars zum Abrufen eines Verweises auf eine <xref:System.Drawing.Graphics> Objekt, das die Zeichenoberfläche des betreffenden Steuerelements oder Formulars darstellt.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="3d7d7-116">Verwenden Sie diese Methode, wenn Sie auf einem Formular oder Steuerelement, das bereits zeichnen möchten.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="3d7d7-117">- oder - </span><span class="sxs-lookup"><span data-stu-id="3d7d7-117">-or-</span></span>  
  
-   <span data-ttu-id="3d7d7-118">Erstellen Sie eine <xref:System.Drawing.Graphics> Objekt aus einem beliebigen Objekt, das von erbt <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="3d7d7-119">Dieser Ansatz ist hilfreich, wenn Sie ein bereits vorhandenes Bild ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="3d7d7-120">Die folgenden Abschnitte enthalten Details zu jeder dieser Prozesse.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="3d7d7-121">PaintEventArgs in Paint-Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="3d7d7-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="3d7d7-122">Bei der Programmierung der <xref:System.Windows.Forms.PaintEventHandler> für Steuerelemente oder <xref:System.Drawing.Printing.PrintDocument.PrintPage> für eine <xref:System.Drawing.Printing.PrintDocument>, ein Graphics-Objekt dient als eine der Eigenschaften von <xref:System.Windows.Forms.PaintEventArgs> oder <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="3d7d7-123">Um einen Verweis auf ein Grafikobjekt aus den PaintEventArgs im Paint-Ereignis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="3d7d7-124">Deklarieren Sie die <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="3d7d7-125">Weisen Sie die Variable zum Verweisen auf die <xref:System.Drawing.Graphics> -Objekt übergeben, als Teil der <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="3d7d7-126">Fügen Sie Code, um das Formular oder Steuerelement zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="3d7d7-127">Das folgende Beispiel zeigt, wie Sie verweisen auf eine <xref:System.Drawing.Graphics> -Objekt aus der <xref:System.Windows.Forms.PaintEventArgs> in die <xref:System.Windows.Forms.Control.Paint> Ereignis:</span><span class="sxs-lookup"><span data-stu-id="3d7d7-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
    ```vb  
    Private Sub Form1_Paint(sender As Object, pe As PaintEventArgs) Handles _  
       MyBase.Paint  
       ' Declares the Graphics object and sets it to the Graphics object  
       ' supplied in the PaintEventArgs.  
       Dim g As Graphics = pe.Graphics  
       ' Insert code to paint the form here.  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Paint(object sender,   
       System.Windows.Forms.PaintEventArgs pe)   
    {  
       // Declares the Graphics object and sets it to the Graphics object  
       // supplied in the PaintEventArgs.  
       Graphics g = pe.Graphics;  
       // Insert code to paint the form here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void Form1_Paint(System::Object ^ sender,  
          System::Windows::Forms::PaintEventArgs ^ pe)  
       {  
          // Declares the Graphics object and sets it to the Graphics object  
          // supplied in the PaintEventArgs.  
          Graphics ^ g = pe->Graphics;  
          // Insert code to paint the form here.  
       }  
    ```  
  
## <a name="creategraphics-method"></a><span data-ttu-id="3d7d7-128">CreateGraphics-Methode</span><span class="sxs-lookup"><span data-stu-id="3d7d7-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="3d7d7-129">Können Sie auch die <xref:System.Windows.Forms.Control.CreateGraphics%2A> Methode des Steuerelements oder Formulars zum Abrufen eines Verweises auf eine <xref:System.Drawing.Graphics> Objekt, das die Zeichenoberfläche des betreffenden Steuerelements oder Formulars darstellt.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="3d7d7-130">Erstellen Sie ein Graphics-Objekt mit der CreateGraphics-Methode</span><span class="sxs-lookup"><span data-stu-id="3d7d7-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
-   <span data-ttu-id="3d7d7-131">Rufen Sie die <xref:System.Windows.Forms.Control.CreateGraphics%2A> -Methode der das Formular oder Steuerelement, von denen Sie Grafiken zu rendern möchten.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
    ```vb  
    Dim g as Graphics  
    ' Sets g to a Graphics object representing the drawing surface of the  
    ' control or form g is a member of.  
    g = Me.CreateGraphics  
    ```  
  
    ```csharp  
    Graphics g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this.CreateGraphics();  
    ```  
  
    ```cpp  
    Graphics ^ g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this->CreateGraphics();  
    ```  
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="3d7d7-132">Erstellen Sie aus einem Image-Objekt</span><span class="sxs-lookup"><span data-stu-id="3d7d7-132">Create from an Image Object</span></span>  
 <span data-ttu-id="3d7d7-133">Darüber hinaus können Sie ein Grafikobjekt erstellen, von der jedes Objekt, das von abgeleitet ist die <xref:System.Drawing.Image> Klasse.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="3d7d7-134">Um ein Grafikobjekt aus einem Image erstellen</span><span class="sxs-lookup"><span data-stu-id="3d7d7-134">To create a Graphics object from an Image</span></span>  
  
-   <span data-ttu-id="3d7d7-135">Rufen Sie die <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> Methode, und geben den Namen des Image-Variablen aus der Sie erstellen möchten eine <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="3d7d7-136">Das folgende Beispiel zeigt, wie Sie mit einem <xref:System.Drawing.Bitmap> Objekt:</span><span class="sxs-lookup"><span data-stu-id="3d7d7-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
    ```vb  
    Dim myBitmap as New Bitmap("C:\Documents and Settings\Joe\Pics\myPic.bmp")  
    Dim g as Graphics = Graphics.FromImage(myBitmap)  
    ```  
  
    ```csharp  
    Bitmap myBitmap = new Bitmap(@"C:\Documents and   
       Settings\Joe\Pics\myPic.bmp");  
    Graphics g = Graphics.FromImage(myBitmap);  
    ```  
  
    ```cpp  
    Bitmap ^ myBitmap = gcnew  
       Bitmap("D:\\Documents and Settings\\Joe\\Pics\\myPic.bmp");  
    Graphics ^ g = Graphics::FromImage(myBitmap);  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="3d7d7-137">Sie können nur erstellen <xref:System.Drawing.Graphics> Objekte aus einer nicht indizierten BMP-Dateien, z. B. 16-Bit-24-Bit und 32-Bit-BMP-Dateien.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="3d7d7-138">Jedes Pixel, der nicht indizierten BMP-Dateien enthält, eine Farbe, im Gegensatz zu Pixel des indizierten BMP-Dateien, die einen Index zu einer Farbtabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="3d7d7-139">Zeichnen und Bearbeiten von Formen und Bilder</span><span class="sxs-lookup"><span data-stu-id="3d7d7-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="3d7d7-140">Nachdem dieser erstellt wurde, eine <xref:System.Drawing.Graphics> -Objekt zum Zeichnen von Linien und Formen, Rendern von Text oder anzeigen und Bearbeiten von Bildern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="3d7d7-141">Die principal-Objekten, mit denen, die <xref:System.Drawing.Graphics> Objekt sind:</span><span class="sxs-lookup"><span data-stu-id="3d7d7-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
-   <span data-ttu-id="3d7d7-142">Die <xref:System.Drawing.Pen> Klasse – zum Zeichnen von Linien, Formen oder Rendern geometrische anderen Darstellungen bereit.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
-   <span data-ttu-id="3d7d7-143">Die <xref:System.Drawing.Brush> Klasse, für das Ausfüllen von Grafiken, z. B. gefüllte Formen, Bildern oder Text verwendet.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
-   <span data-ttu-id="3d7d7-144">Die <xref:System.Drawing.Font> Klasse – enthält eine Beschreibung der Formen, die zur Verwendung beim Rendern von Text.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
-   <span data-ttu-id="3d7d7-145">Die <xref:System.Drawing.Color> Struktur – stellt die verschiedenen Farben angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="3d7d7-146">Das Graphics-Objekt verwenden, die, das Sie erstellt haben</span><span class="sxs-lookup"><span data-stu-id="3d7d7-146">To use the Graphics object you have created</span></span>  
  
-   <span data-ttu-id="3d7d7-147">Arbeiten Sie mit dem entsprechenden Objekt zeichnen, müssen Sie der oben aufgelisteten.</span><span class="sxs-lookup"><span data-stu-id="3d7d7-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="3d7d7-148">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="3d7d7-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="3d7d7-149">Zum Rendern</span><span class="sxs-lookup"><span data-stu-id="3d7d7-149">To render</span></span>|<span data-ttu-id="3d7d7-150">Siehe</span><span class="sxs-lookup"><span data-stu-id="3d7d7-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="3d7d7-151">Linien</span><span class="sxs-lookup"><span data-stu-id="3d7d7-151">Lines</span></span>|[<span data-ttu-id="3d7d7-152">Vorgehensweise: Zeichnen einer Linie in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="3d7d7-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="3d7d7-153">Formen</span><span class="sxs-lookup"><span data-stu-id="3d7d7-153">Shapes</span></span>|[<span data-ttu-id="3d7d7-154">Vorgehensweise: Zeichnen der Kontur eine Form</span><span class="sxs-lookup"><span data-stu-id="3d7d7-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="3d7d7-155">Text</span><span class="sxs-lookup"><span data-stu-id="3d7d7-155">Text</span></span>|[<span data-ttu-id="3d7d7-156">Vorgehensweise: Zeichnen von Text in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="3d7d7-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="3d7d7-157">Bilder</span><span class="sxs-lookup"><span data-stu-id="3d7d7-157">Images</span></span>|[<span data-ttu-id="3d7d7-158">Vorgehensweise: Darstellen von Bildern mit GDI +</span><span class="sxs-lookup"><span data-stu-id="3d7d7-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="3d7d7-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d7d7-159">See also</span></span>

- [<span data-ttu-id="3d7d7-160">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="3d7d7-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="3d7d7-161">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3d7d7-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="3d7d7-162">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="3d7d7-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="3d7d7-163">Vorgehensweise: Darstellen von Bildern mit GDI +</span><span class="sxs-lookup"><span data-stu-id="3d7d7-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
