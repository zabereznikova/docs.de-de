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
ms.openlocfilehash: 3d3ab62896f6b799cd38a8180b90f33125a9929b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964342"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen
Vor dem Zeichnen von Linien und Formen, dem Rendering von Text oder dem anzeigen und Bearbeiten von Bildern mit GDI+ müssen Sie ein <xref:System.Drawing.Graphics> -Objekt erstellen. Das <xref:System.Drawing.Graphics> -Objekt stellt eine GDI+-Zeichen Oberfläche dar und ist das-Objekt, mit dem grafische Bilder erstellt werden.  
  
 Beim Arbeiten mit Grafiken sind zwei Schritte erforderlich:  
  
1. Erstellen eines <xref:System.Drawing.Graphics> -Objekts.  
  
2. Verwenden des <xref:System.Drawing.Graphics> -Objekts zum Zeichnen von Linien und Formen, zum Rendering von Text oder zum Anzeigen und Bearbeiten von Bildern.  
  
## <a name="creating-a-graphics-object"></a>Erstellen eines Grafik Objekts  
 Ein Grafik Objekt kann auf verschiedene Weise erstellt werden.  
  
#### <a name="to-create-a-graphics-object"></a>So erstellen Sie ein Grafik Objekt  
  
- Empfangen eines Verweises auf ein Grafik Objekt als Teil von <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.Control.Paint> im-Ereignis eines Formulars oder Steuer Elements. Dies ist normalerweise das Abrufen eines Verweises auf ein Grafik Objekt beim Erstellen von Zeichnungs Code für ein Steuerelement. Auf ähnliche Weise können Sie auch ein Grafik Objekt als Eigenschaft von <xref:System.Drawing.Printing.PrintPageEventArgs> abrufen, wenn Sie das <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis für eine <xref:System.Drawing.Printing.PrintDocument>verarbeiten.  
  
     -oder-  
  
- Rufen Sie <xref:System.Windows.Forms.Control.CreateGraphics%2A> die-Methode eines Steuer Elements oder Formulars auf, um einen <xref:System.Drawing.Graphics> Verweis auf ein-Objekt zu erhalten, das die Zeichnungs Oberfläche dieses Steuer Elements oder Formulars darstellt. Verwenden Sie diese Methode, wenn Sie ein Formular oder ein Steuerelement erstellen möchten, das bereits vorhanden ist.  
  
     -oder-  
  
- Erstellen Sie <xref:System.Drawing.Graphics> ein-Objekt aus einem beliebigen Objekt, <xref:System.Drawing.Image>das von erbt. Diese Vorgehensweise ist hilfreich, wenn Sie ein bereits vorhandenes Image ändern möchten.  
  
     In den folgenden Abschnitten finden Sie Details zu den einzelnen Prozessen.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>"Pinteventargs" im Paint-Ereignis Handler  
 Beim Programmieren <xref:System.Windows.Forms.PaintEventHandler> der for-Steuer <xref:System.Drawing.Printing.PrintDocument.PrintPage> Elemente oder <xref:System.Drawing.Printing.PrintDocument>der für einen wird ein Grafik Objekt als eine der Eigenschaften von <xref:System.Windows.Forms.PaintEventArgs> oder <xref:System.Drawing.Printing.PrintPageEventArgs>bereitgestellt.  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>So rufen Sie einen Verweis auf ein Grafik Objekt aus den "pinteventargs" im Paint-Ereignis ab  
  
1. Deklarieren <xref:System.Drawing.Graphics> Sie das-Objekt.  
  
2. Weisen Sie die Variable zu, um <xref:System.Drawing.Graphics> auf das Objekt zu verweisen, <xref:System.Windows.Forms.PaintEventArgs>das als Teil von weitergegeben wurde  
  
3. Fügen Sie Code ein, um das Formular oder Steuerelement zu zeichnen.  
  
     Im folgenden Beispiel wird gezeigt, wie <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs> im <xref:System.Windows.Forms.Control.Paint> -Ereignis auf ein-Objekt von verwiesen wird:  
  
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
 Sie können auch die <xref:System.Windows.Forms.Control.CreateGraphics%2A> -Methode eines Steuer Elements oder Formulars verwenden, um einen Verweis auf ein <xref:System.Drawing.Graphics> -Objekt zu erhalten, das die Zeichnungs Oberfläche dieses Steuer Elements oder Formulars darstellt.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>So erstellen Sie ein Grafik Objekt mit der Methode "kreategraphics"  
  
- Ruft die <xref:System.Windows.Forms.Control.CreateGraphics%2A> -Methode des Formulars oder Steuer Elements auf, für das Sie Grafiken renderingzeichen erstellen möchten.  
  
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
 Darüber hinaus können Sie ein Grafik Objekt aus jedem-Objekt erstellen, das von <xref:System.Drawing.Image> der-Klasse abgeleitet wird.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>So erstellen Sie ein Grafik Objekt aus einem Bild  
  
- Rufen Sie <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> die-Methode auf, und stellen Sie den Namen der Bild Variable bereit, aus <xref:System.Drawing.Graphics> der Sie ein-Objekt erstellen möchten.  
  
     Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Drawing.Bitmap> -Objekt verwendet wird:  
  
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
> Sie können nur Objekte <xref:System.Drawing.Graphics> aus nicht indizierten BMP-Dateien, z. b. 16-Bit-, 24-Bit-und 32-Bit-BMP-Dateien, erstellen. Jedes Pixel nicht indizierter BMP-Dateien enthält eine Farbe, im Gegensatz zu Pixeln indizierter BMP-Dateien, die einen Index für eine Farbtabelle enthalten.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Zeichnen und manipulieren von Formen und Bildern  
 Nachdem das <xref:System.Drawing.Graphics> Objekt erstellt wurde, kann es verwendet werden, um Linien und Formen zu zeichnen, Text zu erzeugen oder Bilder anzuzeigen und zu bearbeiten. Die Prinzipal Objekte, die mit dem <xref:System.Drawing.Graphics> -Objekt verwendet werden, sind:  
  
- Die <xref:System.Drawing.Pen> Klasse – wird zum Zeichnen von Linien, Gliedern von Formen oder zum Rendern anderer geometrischer Darstellungen verwendet.  
  
- Die <xref:System.Drawing.Brush> Klasse –, die zum Auffüllen von Bereichen von Grafiken verwendet wird, z. b. ausgefüllte Formen, Bilder oder Text.  
  
- Die <xref:System.Drawing.Font> –-Klasse stellt eine Beschreibung der Formen bereit, die beim Rendern von Text verwendet werden sollen.  
  
- Die <xref:System.Drawing.Color> Struktur – stellt die unterschiedlichen Farben dar, die angezeigt werden sollen.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>So verwenden Sie das von Ihnen erstellte Grafik Objekt  
  
- Arbeiten Sie mit dem entsprechenden oben aufgeführten Objekt, um zu zeichnen, was Sie benötigen.  
  
     Weitere Informationen finden Sie unter den folgenden Themen:  
  
    |Zum Rendering|Siehe|  
    |---------------|---------|  
    |Linien|[Vorgehensweise: Zeichnen einer Linie in einem Windows Form](how-to-draw-a-line-on-a-windows-form.md)|  
    |Formen|[Vorgehensweise: Eine umrissform zeichnen](how-to-draw-an-outlined-shape.md)|  
    |Text|[Vorgehensweise: Zeichnen von Text in einem Windows Form](how-to-draw-text-on-a-windows-form.md)|  
    |Bilder|[Vorgehensweise: Rendering von Bildern mit GDI+](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit Grafikprogrammierung](getting-started-with-graphics-programming.md)
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Linien, Kurven und Formen](lines-curves-and-shapes.md)
- [Vorgehensweise: Rendering von Bildern mit GDI+](how-to-render-images-with-gdi.md)
