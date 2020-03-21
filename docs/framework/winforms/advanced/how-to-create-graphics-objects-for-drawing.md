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
# <a name="how-to-create-graphics-objects-for-drawing"></a>Gewusst wie: Erstellen von Graphics-Objekten zum Zeichnen
Bevor Sie Linien und Formen zeichnen, Text rendern oder Bilder mit GDI+ anzeigen und bearbeiten können, müssen Sie ein <xref:System.Drawing.Graphics> Objekt erstellen. Das <xref:System.Drawing.Graphics> Objekt stellt eine GDI+-Zeichnungsfläche dar und ist das Objekt, das zum Erstellen grafischer Bilder verwendet wird.  
  
 Es gibt zwei Schritte in der Arbeit mit Grafiken:  
  
1. Erstellen <xref:System.Drawing.Graphics> eines Objekts.  
  
2. Verwenden <xref:System.Drawing.Graphics> des Objekts zum Zeichnen von Linien und Formen, Rendern von Text oder Anzeigen und Bearbeiten von Bildern.  
  
## <a name="creating-a-graphics-object"></a>Erstellen eines Grafikobjekts  
 Ein Grafikobjekt kann auf verschiedene Arten erstellt werden.  
  
#### <a name="to-create-a-graphics-object"></a>So erstellen Sie ein Grafikobjekt  
  
- Erhalten Sie einen Verweis auf ein <xref:System.Windows.Forms.PaintEventArgs> Grafikobjekt als Teil des im <xref:System.Windows.Forms.Control.Paint> Falle eines Formulars oder Steuerelements. Auf diese Weise erhalten Sie normalerweise einen Verweis auf ein Grafikobjekt, wenn Sie Malcode für ein Steuerelement erstellen. Ebenso können Sie ein Grafikobjekt auch als <xref:System.Drawing.Printing.PrintPageEventArgs> Eigenschaft <xref:System.Drawing.Printing.PrintDocument.PrintPage> der abrufen, wenn sie das Ereignis für eine <xref:System.Drawing.Printing.PrintDocument>verarbeitet.  
  
     Oder  
  
- Rufen <xref:System.Windows.Forms.Control.CreateGraphics%2A> Sie die Methode eines Steuerelements oder <xref:System.Drawing.Graphics> Formulars auf, um einen Verweis auf ein Objekt abzurufen, das die Zeichnungsfläche dieses Steuerelements oder Formulars darstellt. Verwenden Sie diese Methode, wenn Sie auf ein Formular oder Steuerelement zeichnen möchten, das bereits vorhanden ist.  
  
     Oder  
  
- Erstellen <xref:System.Drawing.Graphics> Sie ein Objekt von jedem <xref:System.Drawing.Image>Objekt, das von erbt. Dieser Ansatz ist nützlich, wenn Sie ein bereits vorhandenes Bild ändern möchten.  
  
     In den folgenden Abschnitten finden Sie Details zu den einzelnen Prozessen.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>PaintEventArgs im Paint-Ereignishandler  
 Beim Programmieren der <xref:System.Windows.Forms.PaintEventHandler> <xref:System.Drawing.Printing.PrintDocument.PrintPage> für <xref:System.Drawing.Printing.PrintDocument>Steuerelemente oder der für wird ein <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Drawing.Printing.PrintPageEventArgs>Grafikobjekt als eine der Eigenschaften von oder bereitgestellt.  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>So rufen Sie einen Verweis auf ein Graphics-Objekt aus den PaintEventArgs im Paint-Ereignis ab  
  
1. Deklarieren Sie das <xref:System.Drawing.Graphics> Objekt.  
  
2. Weisen Sie die Variable <xref:System.Drawing.Graphics> zu, auf <xref:System.Windows.Forms.PaintEventArgs>das Objekt zu verweisen, das als Teil der übergeben wird.  
  
3. Fügen Sie Code ein, um das Formular oder Steuerelement zu malen.  
  
     Das folgende Beispiel zeigt, <xref:System.Drawing.Graphics> wie <xref:System.Windows.Forms.PaintEventArgs> auf <xref:System.Windows.Forms.Control.Paint> ein Objekt aus dem im Ereignis verwiesen wird:  
  
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
 Sie können auch <xref:System.Windows.Forms.Control.CreateGraphics%2A> die Methode eines Steuerelements oder <xref:System.Drawing.Graphics> Formulars verwenden, um einen Verweis auf ein Objekt abzuholen, das die Zeichnungsfläche dieses Steuerelements oder Formulars darstellt.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>So erstellen Sie ein Graphics-Objekt mit der CreateGraphics-Methode  
  
- Rufen <xref:System.Windows.Forms.Control.CreateGraphics%2A> Sie die Methode des Formulars oder Steuerelements auf, für das Sie Grafiken rendern möchten.  
  
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
  
## <a name="create-from-an-image-object"></a>Erstellen aus einem Bildobjekt  
 Darüber hinaus können Sie ein Grafikobjekt aus jedem <xref:System.Drawing.Image> Objekt erstellen, das von der Klasse stammt.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>So erstellen Sie ein Grafikobjekt aus einem Bild  
  
- Rufen <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> Sie die Methode auf und geben Sie den Namen <xref:System.Drawing.Graphics> der Image-Variablen an, aus der Sie ein Objekt erstellen möchten.  
  
     Das folgende Beispiel zeigt, <xref:System.Drawing.Bitmap> wie ein Objekt verwendet wird:  
  
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
> Sie können <xref:System.Drawing.Graphics> nur Objekte aus nicht indizierten BMP-Dateien erstellen, z. B. 16-Bit-, 24-Bit- und 32-Bit-BMP-Dateien. Jedes Pixel nicht indizierter BMP-Dateien enthält eine Farbe im Gegensatz zu Pixeln indizierter BMP-Dateien, die einen Index in einer Farbtabelle enthalten.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Zeichnen und Bearbeiten von Formen und Bildern  
 Nach dem Erstellen <xref:System.Drawing.Graphics> kann ein Objekt zum Zeichnen von Linien und Formen, zum Rendern von Text oder zum Anzeigen und Bearbeiten von Bildern verwendet werden. Die Hauptobjekte, die <xref:System.Drawing.Graphics> mit dem Objekt verwendet werden, sind:  
  
- Die <xref:System.Drawing.Pen> Klasse – Wird zum Zeichnen von Linien, Umreißen von Formen oder Rendern anderer geometrischer Darstellungen verwendet.  
  
- Die <xref:System.Drawing.Brush> Klasse – Wird zum Füllen von Bereichen von Grafiken verwendet, z. B. gefüllte Formen, Bilder oder Text.  
  
- Die <xref:System.Drawing.Font> Klasse – Stellt eine Beschreibung der Shapes bereit, die beim Rendern von Text verwendet werden sollen.  
  
- Die <xref:System.Drawing.Color> Struktur ( Struktur) – Stellt die verschiedenen anzuzeigenden Farben dar.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>So verwenden Sie das grafikbildbebilde Objekt, das Sie erstellt haben  
  
- Arbeiten Sie mit dem oben aufgeführten Objekt, um zu zeichnen, was Sie benötigen.  
  
     Weitere Informationen finden Sie in den folgenden Themen:  
  
    |So rendern Sie|Finden Sie unter|  
    |---------------|---------|  
    |Linien|[Gewusst wie: Zeichnen einer Linie in Windows Forms](how-to-draw-a-line-on-a-windows-form.md)|  
    |Formen|[Gewusst wie: Zeichnen der Kontur einer Form](how-to-draw-an-outlined-shape.md)|  
    |Text|[Gewusst wie: Zeichnen von Text in einem Windows Form](how-to-draw-text-on-a-windows-form.md)|  
    |Bilder|[Gewusst wie: Darstellen von Bildern mit GDI+](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>Weitere Informationen

- [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md)
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Linien, Kurven und Formen](lines-curves-and-shapes.md)
- [Gewusst wie: Darstellen von Bildern mit GDI+](how-to-render-images-with-gdi.md)
