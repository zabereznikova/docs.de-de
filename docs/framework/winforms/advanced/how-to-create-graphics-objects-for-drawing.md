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
ms.openlocfilehash: 54175e27ca46431299db369f67f02051ef08d0d2
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185195"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>Gewusst wie: Erstellen von Graphics-Objekten zum Zeichnen
Bevor Sie Linien und Formen zeichnen können, Rendern von Text oder anzeigen und Bearbeiten von Bildern mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], müssen Sie erstellen eine <xref:System.Drawing.Graphics> Objekt. Die <xref:System.Drawing.Graphics> -Objekt stellt eine [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Zeichenoberfläche und ist das Objekt, das zum Erstellen von Grafiken verwendet wird.  
  
 Es gibt zwei Schritte bei der Arbeit mit Grafiken:  
  
1.  Erstellen einer <xref:System.Drawing.Graphics> Objekt.  
  
2.  Mithilfe der <xref:System.Drawing.Graphics> Objekt, das Zeichnen von Linien und Formen, Rendern von Text oder anzeigen und Bearbeiten von Bildern.  
  
## <a name="creating-a-graphics-object"></a>Erstellen ein Grafikobjekt  
 Ein Grafikobjekt kann auf verschiedene Arten erstellt werden.  
  
#### <a name="to-create-a-graphics-object"></a>Um ein Graphics-Objekt zu erstellen.  
  
-   Erhalten Sie einen Verweis auf ein Graphics-Objekt als Teil der <xref:System.Windows.Forms.PaintEventArgs> in die <xref:System.Windows.Forms.Control.Paint> Ereignis eines Formulars oder Steuerelements. Dies ist in der Regel an, wie Sie einen Verweis auf ein Graphics-Objekt abrufen, beim von Zeichnungscode für ein Steuerelement zu erstellen. Auf ähnliche Weise können Sie ein Grafikobjekt auch abrufen, als Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs> bei der Verarbeitung der <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis für eine <xref:System.Drawing.Printing.PrintDocument>.  
  
     - oder -   
  
-   Rufen Sie die <xref:System.Windows.Forms.Control.CreateGraphics%2A> Methode des Steuerelements oder Formulars zum Abrufen eines Verweises auf eine <xref:System.Drawing.Graphics> Objekt, das die Zeichenoberfläche des betreffenden Steuerelements oder Formulars darstellt. Verwenden Sie diese Methode, wenn Sie auf einem Formular oder Steuerelement, das bereits zeichnen möchten.  
  
     - oder -   
  
-   Erstellen Sie eine <xref:System.Drawing.Graphics> Objekt aus einem beliebigen Objekt, das von erbt <xref:System.Drawing.Image>. Dieser Ansatz ist hilfreich, wenn Sie ein bereits vorhandenes Bild ändern möchten.  
  
     Die folgenden Abschnitte enthalten Details zu jeder dieser Prozesse.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>PaintEventArgs in Paint-Ereignishandler  
 Bei der Programmierung der <xref:System.Windows.Forms.PaintEventHandler> für Steuerelemente oder <xref:System.Drawing.Printing.PrintDocument.PrintPage> für eine <xref:System.Drawing.Printing.PrintDocument>, ein Graphics-Objekt dient als eine der Eigenschaften von <xref:System.Windows.Forms.PaintEventArgs> oder <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>Um einen Verweis auf ein Grafikobjekt aus den PaintEventArgs im Paint-Ereignis zu erhalten.  
  
1.  Deklarieren Sie die <xref:System.Drawing.Graphics> Objekt.  
  
2.  Weisen Sie die Variable zum Verweisen auf die <xref:System.Drawing.Graphics> -Objekt übergeben, als Teil der <xref:System.Windows.Forms.PaintEventArgs>.  
  
3.  Fügen Sie Code, um das Formular oder Steuerelement zu zeichnen.  
  
     Das folgende Beispiel zeigt, wie Sie verweisen auf eine <xref:System.Drawing.Graphics> -Objekt aus der <xref:System.Windows.Forms.PaintEventArgs> in die <xref:System.Windows.Forms.Control.Paint> Ereignis:  
  
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
  
## <a name="creategraphics-method"></a>CreateGraphics-Methode  
 Können Sie auch die <xref:System.Windows.Forms.Control.CreateGraphics%2A> Methode des Steuerelements oder Formulars zum Abrufen eines Verweises auf eine <xref:System.Drawing.Graphics> Objekt, das die Zeichenoberfläche des betreffenden Steuerelements oder Formulars darstellt.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>Erstellen Sie ein Graphics-Objekt mit der CreateGraphics-Methode  
  
-   Rufen Sie die <xref:System.Windows.Forms.Control.CreateGraphics%2A> -Methode der das Formular oder Steuerelement, von denen Sie Grafiken zu rendern möchten.  
  
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
  
## <a name="create-from-an-image-object"></a>Erstellen Sie aus einem Image-Objekt  
 Darüber hinaus können Sie ein Grafikobjekt erstellen, von der jedes Objekt, das von abgeleitet ist die <xref:System.Drawing.Image> Klasse.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>Um ein Grafikobjekt aus einem Image erstellen  
  
-   Rufen Sie die <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> Methode, und geben den Namen des Image-Variablen aus der Sie erstellen möchten eine <xref:System.Drawing.Graphics> Objekt.  
  
     Das folgende Beispiel zeigt, wie Sie mit einem <xref:System.Drawing.Bitmap> Objekt:  
  
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
>  Sie können nur erstellen <xref:System.Drawing.Graphics> Objekte aus einer nicht indizierten BMP-Dateien, z. B. 16-Bit-24-Bit und 32-Bit-BMP-Dateien. Jedes Pixel, der nicht indizierten BMP-Dateien enthält, eine Farbe, im Gegensatz zu Pixel des indizierten BMP-Dateien, die einen Index zu einer Farbtabelle enthalten.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Zeichnen und Bearbeiten von Formen und Bilder  
 Nachdem dieser erstellt wurde, eine <xref:System.Drawing.Graphics> -Objekt zum Zeichnen von Linien und Formen, Rendern von Text oder anzeigen und Bearbeiten von Bildern verwendet werden kann. Die principal-Objekten, mit denen, die <xref:System.Drawing.Graphics> Objekt sind:  
  
-   Die <xref:System.Drawing.Pen> Klasse – zum Zeichnen von Linien, Formen oder Rendern geometrische anderen Darstellungen bereit.  
  
-   Die <xref:System.Drawing.Brush> Klasse, für das Ausfüllen von Grafiken, z. B. gefüllte Formen, Bildern oder Text verwendet.  
  
-   Die <xref:System.Drawing.Font> Klasse – enthält eine Beschreibung der Formen, die zur Verwendung beim Rendern von Text.  
  
-   Die <xref:System.Drawing.Color> Struktur – stellt die verschiedenen Farben angezeigt.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>Das Graphics-Objekt verwenden, die, das Sie erstellt haben  
  
-   Arbeiten Sie mit dem entsprechenden Objekt zeichnen, müssen Sie der oben aufgelisteten.  
  
     Weitere Informationen finden Sie unter den folgenden Themen:  
  
    |Zum Rendern|Siehe|  
    |---------------|---------|  
    |Linien|[Gewusst wie: Zeichnen einer Linie in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)|  
    |Formen|[Gewusst wie: Zeichnen der Kontur einer Form](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)|  
    |Text|[Gewusst wie: Zeichnen von Text in Windows Form](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)|  
    |Bilder|[Gewusst wie: Darstellen von Bildern mit GDI+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte mit Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Gewusst wie: Darstellen von Bildern mit GDI+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
