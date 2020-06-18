---
title: 'Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen'
description: Erfahren Sie, wie Sie ein Grafik Objekt erstellen, das Sie zum Zeichnen von Linien und Formen, zum Rendering von Text oder zum Anzeigen und Bearbeiten von Bildern mit GDI+ benötigen.
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
ms.openlocfilehash: 1a0884c1e9956dc6f4608e32372deeea24ef4670
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903206"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="8187e-103">Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="8187e-103">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="8187e-104">Vor dem Zeichnen von Linien und Formen, dem Rendering von Text oder dem anzeigen und Bearbeiten von Bildern mit GDI+ müssen Sie ein- <xref:System.Drawing.Graphics> Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="8187e-104">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="8187e-105">Das <xref:System.Drawing.Graphics> -Objekt stellt eine GDI+-Zeichen Oberfläche dar und ist das-Objekt, mit dem grafische Bilder erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8187e-105">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="8187e-106">Beim Arbeiten mit Grafiken sind zwei Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="8187e-106">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="8187e-107">Erstellen eines- <xref:System.Drawing.Graphics> Objekts.</span><span class="sxs-lookup"><span data-stu-id="8187e-107">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="8187e-108">Verwenden des- <xref:System.Drawing.Graphics> Objekts zum Zeichnen von Linien und Formen, zum Rendering von Text oder zum Anzeigen und Bearbeiten von Bildern.</span><span class="sxs-lookup"><span data-stu-id="8187e-108">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="8187e-109">Erstellen eines Grafik Objekts</span><span class="sxs-lookup"><span data-stu-id="8187e-109">Creating a Graphics Object</span></span>  
 <span data-ttu-id="8187e-110">Ein Grafik Objekt kann auf verschiedene Weise erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8187e-110">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="8187e-111">So erstellen Sie ein Grafik Objekt</span><span class="sxs-lookup"><span data-stu-id="8187e-111">To create a graphics object</span></span>  
  
- <span data-ttu-id="8187e-112">Empfangen eines Verweises auf ein Grafik Objekt als Teil von <xref:System.Windows.Forms.PaintEventArgs> im- <xref:System.Windows.Forms.Control.Paint> Ereignis eines Formulars oder Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="8187e-112">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="8187e-113">Dies ist normalerweise das Abrufen eines Verweises auf ein Grafik Objekt beim Erstellen von Zeichnungs Code für ein Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8187e-113">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="8187e-114">Auf ähnliche Weise können Sie auch ein Grafik Objekt als Eigenschaft von abrufen, <xref:System.Drawing.Printing.PrintPageEventArgs> Wenn Sie das- <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis für eine verarbeiten <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="8187e-114">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="8187e-115">Oder</span><span class="sxs-lookup"><span data-stu-id="8187e-115">-or-</span></span>  
  
- <span data-ttu-id="8187e-116">Rufen Sie die- <xref:System.Windows.Forms.Control.CreateGraphics%2A> Methode eines Steuer Elements oder Formulars auf, um einen Verweis auf ein-Objekt zu erhalten <xref:System.Drawing.Graphics> , das die Zeichnungs Oberfläche dieses Steuer Elements oder Formulars darstellt.</span><span class="sxs-lookup"><span data-stu-id="8187e-116">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="8187e-117">Verwenden Sie diese Methode, wenn Sie ein Formular oder ein Steuerelement erstellen möchten, das bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8187e-117">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="8187e-118">Oder</span><span class="sxs-lookup"><span data-stu-id="8187e-118">-or-</span></span>  
  
- <span data-ttu-id="8187e-119">Erstellen Sie ein- <xref:System.Drawing.Graphics> Objekt aus einem beliebigen Objekt, das von erbt <xref:System.Drawing.Image> .</span><span class="sxs-lookup"><span data-stu-id="8187e-119">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="8187e-120">Diese Vorgehensweise ist hilfreich, wenn Sie ein bereits vorhandenes Image ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="8187e-120">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="8187e-121">In den folgenden Abschnitten finden Sie Details zu den einzelnen Prozessen.</span><span class="sxs-lookup"><span data-stu-id="8187e-121">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="8187e-122">"Pinteventargs" im Paint-Ereignis Handler</span><span class="sxs-lookup"><span data-stu-id="8187e-122">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="8187e-123">Beim Programmieren der for-Steuer <xref:System.Windows.Forms.PaintEventHandler> Elemente oder der <xref:System.Drawing.Printing.PrintDocument.PrintPage> für einen <xref:System.Drawing.Printing.PrintDocument> wird ein Grafik Objekt als eine der Eigenschaften von <xref:System.Windows.Forms.PaintEventArgs> oder bereitgestellt <xref:System.Drawing.Printing.PrintPageEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="8187e-123">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="8187e-124">So rufen Sie einen Verweis auf ein Grafik Objekt aus den "pinteventargs" im Paint-Ereignis ab</span><span class="sxs-lookup"><span data-stu-id="8187e-124">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="8187e-125">Deklarieren Sie das- <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="8187e-125">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="8187e-126">Weisen Sie die Variable zu, um auf das Objekt zu verweisen, das <xref:System.Drawing.Graphics> als Teil von weitergegeben wurde <xref:System.Windows.Forms.PaintEventArgs></span><span class="sxs-lookup"><span data-stu-id="8187e-126">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="8187e-127">Fügen Sie Code ein, um das Formular oder Steuerelement zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="8187e-127">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="8187e-128">Im folgenden Beispiel wird gezeigt, wie im-Ereignis auf ein- <xref:System.Drawing.Graphics> Objekt von verwiesen wird <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.Control.Paint> :</span><span class="sxs-lookup"><span data-stu-id="8187e-128">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="8187e-129">Methode "kreategraphics"</span><span class="sxs-lookup"><span data-stu-id="8187e-129">CreateGraphics Method</span></span>  
 <span data-ttu-id="8187e-130">Sie können auch die- <xref:System.Windows.Forms.Control.CreateGraphics%2A> Methode eines Steuer Elements oder Formulars verwenden, um einen Verweis auf ein-Objekt zu erhalten <xref:System.Drawing.Graphics> , das die Zeichnungs Oberfläche dieses Steuer Elements oder Formulars darstellt.</span><span class="sxs-lookup"><span data-stu-id="8187e-130">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="8187e-131">So erstellen Sie ein Grafik Objekt mit der Methode "kreategraphics"</span><span class="sxs-lookup"><span data-stu-id="8187e-131">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="8187e-132">Ruft die- <xref:System.Windows.Forms.Control.CreateGraphics%2A> Methode des Formulars oder Steuer Elements auf, für das Sie Grafiken renderingzeichen erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="8187e-132">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="8187e-133">Erstellen aus einem Image-Objekt</span><span class="sxs-lookup"><span data-stu-id="8187e-133">Create from an Image Object</span></span>  
 <span data-ttu-id="8187e-134">Darüber hinaus können Sie ein Grafik Objekt aus jedem-Objekt erstellen, das von der-Klasse abgeleitet wird <xref:System.Drawing.Image> .</span><span class="sxs-lookup"><span data-stu-id="8187e-134">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="8187e-135">So erstellen Sie ein Grafik Objekt aus einem Bild</span><span class="sxs-lookup"><span data-stu-id="8187e-135">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="8187e-136">Rufen Sie die- <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> Methode auf, und stellen Sie den Namen der Bild Variable bereit, aus der Sie ein-Objekt erstellen möchten <xref:System.Drawing.Graphics> .</span><span class="sxs-lookup"><span data-stu-id="8187e-136">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="8187e-137">Im folgenden Beispiel wird gezeigt, wie ein-Objekt verwendet wird <xref:System.Drawing.Bitmap> :</span><span class="sxs-lookup"><span data-stu-id="8187e-137">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
> <span data-ttu-id="8187e-138">Sie können nur <xref:System.Drawing.Graphics> Objekte aus nicht indizierten BMP-Dateien, z. b. 16-Bit-, 24-Bit-und 32-Bit-BMP-Dateien, erstellen.</span><span class="sxs-lookup"><span data-stu-id="8187e-138">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="8187e-139">Jedes Pixel nicht indizierter BMP-Dateien enthält eine Farbe, im Gegensatz zu Pixeln indizierter BMP-Dateien, die einen Index für eine Farbtabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="8187e-139">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="8187e-140">Zeichnen und manipulieren von Formen und Bildern</span><span class="sxs-lookup"><span data-stu-id="8187e-140">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="8187e-141">Nachdem das Objekt erstellt wurde, <xref:System.Drawing.Graphics> kann es verwendet werden, um Linien und Formen zu zeichnen, Text zu erzeugen oder Bilder anzuzeigen und zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8187e-141">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="8187e-142">Die Prinzipal Objekte, die mit dem-Objekt verwendet werden, <xref:System.Drawing.Graphics> sind:</span><span class="sxs-lookup"><span data-stu-id="8187e-142">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="8187e-143">Die <xref:System.Drawing.Pen> Klasse – wird zum Zeichnen von Linien, Gliedern von Formen oder zum Rendern anderer geometrischer Darstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8187e-143">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="8187e-144">Die <xref:System.Drawing.Brush> Klasse –, die zum Auffüllen von Bereichen von Grafiken verwendet wird, z. b. ausgefüllte Formen, Bilder oder Text.</span><span class="sxs-lookup"><span data-stu-id="8187e-144">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="8187e-145">Die <xref:System.Drawing.Font> –-Klasse stellt eine Beschreibung der Formen bereit, die beim Rendern von Text verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8187e-145">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="8187e-146">Die <xref:System.Drawing.Color> Struktur – stellt die unterschiedlichen Farben dar, die angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8187e-146">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="8187e-147">So verwenden Sie das von Ihnen erstellte Grafik Objekt</span><span class="sxs-lookup"><span data-stu-id="8187e-147">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="8187e-148">Arbeiten Sie mit dem entsprechenden oben aufgeführten Objekt, um zu zeichnen, was Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="8187e-148">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="8187e-149">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8187e-149">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="8187e-150">Zum Rendering</span><span class="sxs-lookup"><span data-stu-id="8187e-150">To render</span></span>|<span data-ttu-id="8187e-151">Finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="8187e-151">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="8187e-152">Linien</span><span class="sxs-lookup"><span data-stu-id="8187e-152">Lines</span></span>|[<span data-ttu-id="8187e-153">Vorgehensweise: Zeichnen einer Linie in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8187e-153">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="8187e-154">Formen</span><span class="sxs-lookup"><span data-stu-id="8187e-154">Shapes</span></span>|[<span data-ttu-id="8187e-155">Vorgehensweise: Zeichnen der Kontur einer Form</span><span class="sxs-lookup"><span data-stu-id="8187e-155">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="8187e-156">Text</span><span class="sxs-lookup"><span data-stu-id="8187e-156">Text</span></span>|[<span data-ttu-id="8187e-157">Vorgehensweise: Zeichnen von Text in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="8187e-157">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="8187e-158">Bilder</span><span class="sxs-lookup"><span data-stu-id="8187e-158">Images</span></span>|[<span data-ttu-id="8187e-159">Vorgehensweise: Darstellen von Bildern mit GDI+</span><span class="sxs-lookup"><span data-stu-id="8187e-159">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="8187e-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8187e-160">See also</span></span>

- [<span data-ttu-id="8187e-161">Erste Schritte mit der Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="8187e-161">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="8187e-162">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8187e-162">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="8187e-163">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="8187e-163">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="8187e-164">Vorgehensweise: Darstellen von Bildern mit GDI+</span><span class="sxs-lookup"><span data-stu-id="8187e-164">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
