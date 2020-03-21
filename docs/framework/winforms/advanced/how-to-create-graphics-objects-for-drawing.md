---
title: 'Gewusst wie: Erstellen von Graphics-Objekten zum Zeichnen'
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
ms.openlocfilehash: d591d65904484e33285e5db7aa99760f3e1909d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142432"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="028ab-102">Gewusst wie: Erstellen von Graphics-Objekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="028ab-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="028ab-103">Bevor Sie Linien und Formen zeichnen, Text rendern oder Bilder mit GDI+ anzeigen und bearbeiten können, müssen Sie ein <xref:System.Drawing.Graphics> Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="028ab-103">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="028ab-104">Das <xref:System.Drawing.Graphics> Objekt stellt eine GDI+-Zeichnungsfläche dar und ist das Objekt, das zum Erstellen grafischer Bilder verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="028ab-104">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="028ab-105">Es gibt zwei Schritte in der Arbeit mit Grafiken:</span><span class="sxs-lookup"><span data-stu-id="028ab-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="028ab-106">Erstellen <xref:System.Drawing.Graphics> eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="028ab-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="028ab-107">Verwenden <xref:System.Drawing.Graphics> des Objekts zum Zeichnen von Linien und Formen, Rendern von Text oder Anzeigen und Bearbeiten von Bildern.</span><span class="sxs-lookup"><span data-stu-id="028ab-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="028ab-108">Erstellen eines Grafikobjekts</span><span class="sxs-lookup"><span data-stu-id="028ab-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="028ab-109">Ein Grafikobjekt kann auf verschiedene Arten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="028ab-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="028ab-110">So erstellen Sie ein Grafikobjekt</span><span class="sxs-lookup"><span data-stu-id="028ab-110">To create a graphics object</span></span>  
  
- <span data-ttu-id="028ab-111">Erhalten Sie einen Verweis auf ein <xref:System.Windows.Forms.PaintEventArgs> Grafikobjekt als Teil des im <xref:System.Windows.Forms.Control.Paint> Falle eines Formulars oder Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="028ab-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="028ab-112">Auf diese Weise erhalten Sie normalerweise einen Verweis auf ein Grafikobjekt, wenn Sie Malcode für ein Steuerelement erstellen.</span><span class="sxs-lookup"><span data-stu-id="028ab-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="028ab-113">Ebenso können Sie ein Grafikobjekt auch als <xref:System.Drawing.Printing.PrintPageEventArgs> Eigenschaft <xref:System.Drawing.Printing.PrintDocument.PrintPage> der abrufen, wenn sie das Ereignis für eine <xref:System.Drawing.Printing.PrintDocument>verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="028ab-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="028ab-114">Oder</span><span class="sxs-lookup"><span data-stu-id="028ab-114">-or-</span></span>  
  
- <span data-ttu-id="028ab-115">Rufen <xref:System.Windows.Forms.Control.CreateGraphics%2A> Sie die Methode eines Steuerelements oder <xref:System.Drawing.Graphics> Formulars auf, um einen Verweis auf ein Objekt abzurufen, das die Zeichnungsfläche dieses Steuerelements oder Formulars darstellt.</span><span class="sxs-lookup"><span data-stu-id="028ab-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="028ab-116">Verwenden Sie diese Methode, wenn Sie auf ein Formular oder Steuerelement zeichnen möchten, das bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="028ab-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="028ab-117">Oder</span><span class="sxs-lookup"><span data-stu-id="028ab-117">-or-</span></span>  
  
- <span data-ttu-id="028ab-118">Erstellen <xref:System.Drawing.Graphics> Sie ein Objekt von jedem <xref:System.Drawing.Image>Objekt, das von erbt.</span><span class="sxs-lookup"><span data-stu-id="028ab-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="028ab-119">Dieser Ansatz ist nützlich, wenn Sie ein bereits vorhandenes Bild ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="028ab-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="028ab-120">In den folgenden Abschnitten finden Sie Details zu den einzelnen Prozessen.</span><span class="sxs-lookup"><span data-stu-id="028ab-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="028ab-121">PaintEventArgs im Paint-Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="028ab-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="028ab-122">Beim Programmieren der <xref:System.Windows.Forms.PaintEventHandler> <xref:System.Drawing.Printing.PrintDocument.PrintPage> für <xref:System.Drawing.Printing.PrintDocument>Steuerelemente oder der für wird ein <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Drawing.Printing.PrintPageEventArgs>Grafikobjekt als eine der Eigenschaften von oder bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="028ab-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="028ab-123">So rufen Sie einen Verweis auf ein Graphics-Objekt aus den PaintEventArgs im Paint-Ereignis ab</span><span class="sxs-lookup"><span data-stu-id="028ab-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="028ab-124">Deklarieren Sie das <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="028ab-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="028ab-125">Weisen Sie die Variable <xref:System.Drawing.Graphics> zu, auf <xref:System.Windows.Forms.PaintEventArgs>das Objekt zu verweisen, das als Teil der übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="028ab-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="028ab-126">Fügen Sie Code ein, um das Formular oder Steuerelement zu malen.</span><span class="sxs-lookup"><span data-stu-id="028ab-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="028ab-127">Das folgende Beispiel zeigt, <xref:System.Drawing.Graphics> wie <xref:System.Windows.Forms.PaintEventArgs> auf <xref:System.Windows.Forms.Control.Paint> ein Objekt aus dem im Ereignis verwiesen wird:</span><span class="sxs-lookup"><span data-stu-id="028ab-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="028ab-128">CreateGraphics-Methode</span><span class="sxs-lookup"><span data-stu-id="028ab-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="028ab-129">Sie können auch <xref:System.Windows.Forms.Control.CreateGraphics%2A> die Methode eines Steuerelements oder <xref:System.Drawing.Graphics> Formulars verwenden, um einen Verweis auf ein Objekt abzuholen, das die Zeichnungsfläche dieses Steuerelements oder Formulars darstellt.</span><span class="sxs-lookup"><span data-stu-id="028ab-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="028ab-130">So erstellen Sie ein Graphics-Objekt mit der CreateGraphics-Methode</span><span class="sxs-lookup"><span data-stu-id="028ab-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="028ab-131">Rufen <xref:System.Windows.Forms.Control.CreateGraphics%2A> Sie die Methode des Formulars oder Steuerelements auf, für das Sie Grafiken rendern möchten.</span><span class="sxs-lookup"><span data-stu-id="028ab-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="028ab-132">Erstellen aus einem Bildobjekt</span><span class="sxs-lookup"><span data-stu-id="028ab-132">Create from an Image Object</span></span>  
 <span data-ttu-id="028ab-133">Darüber hinaus können Sie ein Grafikobjekt aus jedem <xref:System.Drawing.Image> Objekt erstellen, das von der Klasse stammt.</span><span class="sxs-lookup"><span data-stu-id="028ab-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="028ab-134">So erstellen Sie ein Grafikobjekt aus einem Bild</span><span class="sxs-lookup"><span data-stu-id="028ab-134">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="028ab-135">Rufen <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> Sie die Methode auf und geben Sie den Namen <xref:System.Drawing.Graphics> der Image-Variablen an, aus der Sie ein Objekt erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="028ab-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="028ab-136">Das folgende Beispiel zeigt, <xref:System.Drawing.Bitmap> wie ein Objekt verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="028ab-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
> <span data-ttu-id="028ab-137">Sie können <xref:System.Drawing.Graphics> nur Objekte aus nicht indizierten BMP-Dateien erstellen, z. B. 16-Bit-, 24-Bit- und 32-Bit-BMP-Dateien.</span><span class="sxs-lookup"><span data-stu-id="028ab-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="028ab-138">Jedes Pixel nicht indizierter BMP-Dateien enthält eine Farbe im Gegensatz zu Pixeln indizierter BMP-Dateien, die einen Index in einer Farbtabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="028ab-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="028ab-139">Zeichnen und Bearbeiten von Formen und Bildern</span><span class="sxs-lookup"><span data-stu-id="028ab-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="028ab-140">Nach dem Erstellen <xref:System.Drawing.Graphics> kann ein Objekt zum Zeichnen von Linien und Formen, zum Rendern von Text oder zum Anzeigen und Bearbeiten von Bildern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="028ab-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="028ab-141">Die Hauptobjekte, die <xref:System.Drawing.Graphics> mit dem Objekt verwendet werden, sind:</span><span class="sxs-lookup"><span data-stu-id="028ab-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="028ab-142">Die <xref:System.Drawing.Pen> Klasse – Wird zum Zeichnen von Linien, Umreißen von Formen oder Rendern anderer geometrischer Darstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="028ab-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="028ab-143">Die <xref:System.Drawing.Brush> Klasse – Wird zum Füllen von Bereichen von Grafiken verwendet, z. B. gefüllte Formen, Bilder oder Text.</span><span class="sxs-lookup"><span data-stu-id="028ab-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="028ab-144">Die <xref:System.Drawing.Font> Klasse – Stellt eine Beschreibung der Shapes bereit, die beim Rendern von Text verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="028ab-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="028ab-145">Die <xref:System.Drawing.Color> Struktur ( Struktur) – Stellt die verschiedenen anzuzeigenden Farben dar.</span><span class="sxs-lookup"><span data-stu-id="028ab-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="028ab-146">So verwenden Sie das grafikbildbebilde Objekt, das Sie erstellt haben</span><span class="sxs-lookup"><span data-stu-id="028ab-146">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="028ab-147">Arbeiten Sie mit dem oben aufgeführten Objekt, um zu zeichnen, was Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="028ab-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="028ab-148">Weitere Informationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="028ab-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="028ab-149">So rendern Sie</span><span class="sxs-lookup"><span data-stu-id="028ab-149">To render</span></span>|<span data-ttu-id="028ab-150">Finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="028ab-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="028ab-151">Linien</span><span class="sxs-lookup"><span data-stu-id="028ab-151">Lines</span></span>|[<span data-ttu-id="028ab-152">Gewusst wie: Zeichnen einer Linie in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="028ab-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="028ab-153">Formen</span><span class="sxs-lookup"><span data-stu-id="028ab-153">Shapes</span></span>|[<span data-ttu-id="028ab-154">Gewusst wie: Zeichnen der Kontur einer Form</span><span class="sxs-lookup"><span data-stu-id="028ab-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="028ab-155">Text</span><span class="sxs-lookup"><span data-stu-id="028ab-155">Text</span></span>|[<span data-ttu-id="028ab-156">Gewusst wie: Zeichnen von Text in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="028ab-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="028ab-157">Bilder</span><span class="sxs-lookup"><span data-stu-id="028ab-157">Images</span></span>|[<span data-ttu-id="028ab-158">Gewusst wie: Darstellen von Bildern mit GDI+</span><span class="sxs-lookup"><span data-stu-id="028ab-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="028ab-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="028ab-159">See also</span></span>

- [<span data-ttu-id="028ab-160">Erste Schritte mit der Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="028ab-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="028ab-161">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="028ab-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="028ab-162">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="028ab-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="028ab-163">Gewusst wie: Darstellen von Bildern mit GDI+</span><span class="sxs-lookup"><span data-stu-id="028ab-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
