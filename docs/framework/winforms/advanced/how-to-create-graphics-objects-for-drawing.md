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
# <a name="how-to-create-graphics-objects-for-drawing"></a>Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen
Vor dem Zeichnen von Linien und Formen, dem Rendering von Text oder dem anzeigen und Bearbeiten von Bildern mit GDI+ müssen Sie ein- <xref:System.Drawing.Graphics> Objekt erstellen. Das <xref:System.Drawing.Graphics> -Objekt stellt eine GDI+-Zeichen Oberfläche dar und ist das-Objekt, mit dem grafische Bilder erstellt werden.  
  
 Beim Arbeiten mit Grafiken sind zwei Schritte erforderlich:  
  
1. Erstellen eines- <xref:System.Drawing.Graphics> Objekts.  
  
2. Verwenden des- <xref:System.Drawing.Graphics> Objekts zum Zeichnen von Linien und Formen, zum Rendering von Text oder zum Anzeigen und Bearbeiten von Bildern.  
  
## <a name="creating-a-graphics-object"></a>Erstellen eines Grafik Objekts  
 Ein Grafik Objekt kann auf verschiedene Weise erstellt werden.  
  
#### <a name="to-create-a-graphics-object"></a>So erstellen Sie ein Grafik Objekt  
  
- Empfangen eines Verweises auf ein Grafik Objekt als Teil von <xref:System.Windows.Forms.PaintEventArgs> im- <xref:System.Windows.Forms.Control.Paint> Ereignis eines Formulars oder Steuer Elements. Dies ist normalerweise das Abrufen eines Verweises auf ein Grafik Objekt beim Erstellen von Zeichnungs Code für ein Steuerelement. Auf ähnliche Weise können Sie auch ein Grafik Objekt als Eigenschaft von abrufen, <xref:System.Drawing.Printing.PrintPageEventArgs> Wenn Sie das- <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis für eine verarbeiten <xref:System.Drawing.Printing.PrintDocument> .  
  
     Oder  
  
- Rufen Sie die- <xref:System.Windows.Forms.Control.CreateGraphics%2A> Methode eines Steuer Elements oder Formulars auf, um einen Verweis auf ein-Objekt zu erhalten <xref:System.Drawing.Graphics> , das die Zeichnungs Oberfläche dieses Steuer Elements oder Formulars darstellt. Verwenden Sie diese Methode, wenn Sie ein Formular oder ein Steuerelement erstellen möchten, das bereits vorhanden ist.  
  
     Oder  
  
- Erstellen Sie ein- <xref:System.Drawing.Graphics> Objekt aus einem beliebigen Objekt, das von erbt <xref:System.Drawing.Image> . Diese Vorgehensweise ist hilfreich, wenn Sie ein bereits vorhandenes Image ändern möchten.  
  
     In den folgenden Abschnitten finden Sie Details zu den einzelnen Prozessen.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>"Pinteventargs" im Paint-Ereignis Handler  
 Beim Programmieren der for-Steuer <xref:System.Windows.Forms.PaintEventHandler> Elemente oder der <xref:System.Drawing.Printing.PrintDocument.PrintPage> für einen <xref:System.Drawing.Printing.PrintDocument> wird ein Grafik Objekt als eine der Eigenschaften von <xref:System.Windows.Forms.PaintEventArgs> oder bereitgestellt <xref:System.Drawing.Printing.PrintPageEventArgs> .  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>So rufen Sie einen Verweis auf ein Grafik Objekt aus den "pinteventargs" im Paint-Ereignis ab  
  
1. Deklarieren Sie das- <xref:System.Drawing.Graphics> Objekt.  
  
2. Weisen Sie die Variable zu, um auf das Objekt zu verweisen, das <xref:System.Drawing.Graphics> als Teil von weitergegeben wurde <xref:System.Windows.Forms.PaintEventArgs>  
  
3. Fügen Sie Code ein, um das Formular oder Steuerelement zu zeichnen.  
  
     Im folgenden Beispiel wird gezeigt, wie im-Ereignis auf ein- <xref:System.Drawing.Graphics> Objekt von verwiesen wird <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.Control.Paint> :  
  
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
  
## <a name="creategraphics-method"></a>Methode "kreategraphics"  
 Sie können auch die- <xref:System.Windows.Forms.Control.CreateGraphics%2A> Methode eines Steuer Elements oder Formulars verwenden, um einen Verweis auf ein-Objekt zu erhalten <xref:System.Drawing.Graphics> , das die Zeichnungs Oberfläche dieses Steuer Elements oder Formulars darstellt.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>So erstellen Sie ein Grafik Objekt mit der Methode "kreategraphics"  
  
- Ruft die- <xref:System.Windows.Forms.Control.CreateGraphics%2A> Methode des Formulars oder Steuer Elements auf, für das Sie Grafiken renderingzeichen erstellen möchten.  
  
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
  
## <a name="create-from-an-image-object"></a>Erstellen aus einem Image-Objekt  
 Darüber hinaus können Sie ein Grafik Objekt aus jedem-Objekt erstellen, das von der-Klasse abgeleitet wird <xref:System.Drawing.Image> .  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>So erstellen Sie ein Grafik Objekt aus einem Bild  
  
- Rufen Sie die- <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> Methode auf, und stellen Sie den Namen der Bild Variable bereit, aus der Sie ein-Objekt erstellen möchten <xref:System.Drawing.Graphics> .  
  
     Im folgenden Beispiel wird gezeigt, wie ein-Objekt verwendet wird <xref:System.Drawing.Bitmap> :  
  
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
> Sie können nur <xref:System.Drawing.Graphics> Objekte aus nicht indizierten BMP-Dateien, z. b. 16-Bit-, 24-Bit-und 32-Bit-BMP-Dateien, erstellen. Jedes Pixel nicht indizierter BMP-Dateien enthält eine Farbe, im Gegensatz zu Pixeln indizierter BMP-Dateien, die einen Index für eine Farbtabelle enthalten.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Zeichnen und manipulieren von Formen und Bildern  
 Nachdem das Objekt erstellt wurde, <xref:System.Drawing.Graphics> kann es verwendet werden, um Linien und Formen zu zeichnen, Text zu erzeugen oder Bilder anzuzeigen und zu bearbeiten. Die Prinzipal Objekte, die mit dem-Objekt verwendet werden, <xref:System.Drawing.Graphics> sind:  
  
- Die <xref:System.Drawing.Pen> Klasse – wird zum Zeichnen von Linien, Gliedern von Formen oder zum Rendern anderer geometrischer Darstellungen verwendet.  
  
- Die <xref:System.Drawing.Brush> Klasse –, die zum Auffüllen von Bereichen von Grafiken verwendet wird, z. b. ausgefüllte Formen, Bilder oder Text.  
  
- Die <xref:System.Drawing.Font> –-Klasse stellt eine Beschreibung der Formen bereit, die beim Rendern von Text verwendet werden sollen.  
  
- Die <xref:System.Drawing.Color> Struktur – stellt die unterschiedlichen Farben dar, die angezeigt werden sollen.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>So verwenden Sie das von Ihnen erstellte Grafik Objekt  
  
- Arbeiten Sie mit dem entsprechenden oben aufgeführten Objekt, um zu zeichnen, was Sie benötigen.  
  
     Weitere Informationen finden Sie unter den folgenden Themen:  
  
    |Zum Rendering|Finden Sie unter|  
    |---------------|---------|  
    |Linien|[Vorgehensweise: Zeichnen einer Linie in Windows Forms](how-to-draw-a-line-on-a-windows-form.md)|  
    |Formen|[Vorgehensweise: Zeichnen der Kontur einer Form](how-to-draw-an-outlined-shape.md)|  
    |Text|[Vorgehensweise: Zeichnen von Text in einem Windows Form](how-to-draw-text-on-a-windows-form.md)|  
    |Bilder|[Vorgehensweise: Darstellen von Bildern mit GDI+](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>Weitere Informationen

- [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md)
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Linien, Kurven und Formen](lines-curves-and-shapes.md)
- [Vorgehensweise: Darstellen von Bildern mit GDI+](how-to-render-images-with-gdi.md)
