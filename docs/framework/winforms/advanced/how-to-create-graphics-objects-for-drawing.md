---
title: "Gewusst wie: Erstellen von Graphics-Objekten zum Zeichnen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "GDI+, Erstellen von Bildern"
  - "Grafiken [Windows Forms], Erstellen"
  - "Graphics-Klasse"
  - "Bilder [Windows Forms], Erstellen"
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Erstellen von Graphics-Objekten zum Zeichnen
Damit Sie mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Linien und Formen zeichnen, Text rendern oder Bilder anzeigen und bearbeiten können, müssen Sie zunächst ein <xref:System.Drawing.Graphics>\-Objekt erstellen.  Das <xref:System.Drawing.Graphics>\-Objekt stellt die [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]\-Zeichenoberfläche dar und wird zum Erstellen von Grafiken verwendet.  
  
 Die Arbeit mit Grafiken erfolgt in zwei Schritten:  
  
1.  Erstellen eines <xref:System.Drawing.Graphics>\-Objekts  
  
2.  Verwenden des <xref:System.Drawing.Graphics>\-Objekts zum Zeichnen von Linien und Formen, Rendern von Text oder Anzeigen und Bearbeiten von Bildern  
  
## Erstellen eines Graphics\-Objekts  
 Es gibt viele Möglichkeiten, ein Graphics\-Objekt zu erstellen.  
  
#### So erstellen Sie ein Graphics\-Objekt  
  
-   Rufen Sie im <xref:System.Windows.Forms.Control.Paint>\-Ereignis eines Formulars oder Steuerelements einen Verweis auf ein Graphics\-Objekt als Bestandteil von <xref:System.Windows.Forms.PaintEventArgs> ab.  In der Regel erhalten Sie Verweise auf Grafikobjekte auf diese Art, wenn Sie den Zeichnungscode eines Steuerelements erstellen.  Sie können ein Grafikobjekt auch als Eigenschaft von <xref:System.Drawing.Printing.PrintPageEventArgs> abrufen, wenn Sie das <xref:System.Drawing.Printing.PrintDocument.PrintPage>\-Ereignis für ein <xref:System.Drawing.Printing.PrintDocument>\-Element behandeln.  
  
     \- oder \-  
  
-   Rufen Sie die <xref:System.Windows.Forms.Control.CreateGraphics%2A>\-Methode eines Steuerelements oder Formulars auf, um einen Verweis auf ein <xref:System.Drawing.Graphics>\-Objekt zu erhalten, das die Zeichnungsoberfläche des betreffenden Steuerelements oder Formulars darstellt.  Verwenden Sie diese Methode zum Zeichnen in einem bereits vorhandenen Formular oder Steuerelement.  
  
     \- oder \-  
  
-   Erstellen Sie ein <xref:System.Drawing.Graphics>\-Objekt aus einem beliebigen Objekt, das von <xref:System.Drawing.Image> erbt.  Dies ist sinnvoll, wenn ein bereits vorhandenes Bild geändert werden soll.  
  
     In den folgenden Abschnitten werden die einzelnen Verfahren ausführlich erläutert.  
  
## PaintEventArgs im Paint\-Ereignishandler  
 Wenn Sie ein <xref:System.Windows.Forms.PaintEventHandler>\-Element für Steuerelemente oder das <xref:System.Drawing.Printing.PrintDocument.PrintPage>\-Element für ein <xref:System.Drawing.Printing.PrintDocument>\-Element programmieren, wird ein Grafikobjekt als eine der Eigenschaften von <xref:System.Windows.Forms.PaintEventArgs> oder <xref:System.Drawing.Printing.PrintPageEventArgs> bereitgestellt.  
  
#### So erhalten Sie einen Verweis auf ein Graphics\-Objekt aus den PaintEventArgs im Paint\-Ereignis  
  
1.  Deklarieren Sie das <xref:System.Drawing.Graphics>\-Objekt.  
  
2.  Weisen Sie die Variable zu, mit der auf das als Teil von <xref:System.Windows.Forms.PaintEventArgs> übergebene <xref:System.Drawing.Graphics>\-Objekt verwiesen wird.  
  
3.  Fügen Sie Code zum Zeichnen des Formulars oder Steuerelements ein.  
  
     Das folgende Beispiel veranschaulicht, wie über <xref:System.Windows.Forms.PaintEventArgs> im <xref:System.Windows.Forms.Control.Paint>\-Ereignis auf ein <xref:System.Drawing.Graphics>\-Objekt verwiesen wird.  
  
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
  
## CreateGraphics\-Methode  
 Sie können auch die <xref:System.Windows.Forms.Control.CreateGraphics%2A>\-Methode eines Steuerelements oder Formulars verwenden, um einen Verweis auf ein <xref:System.Drawing.Graphics>\-Objekt zu erhalten, das die Zeichnungsoberfläche des betreffenden Steuerelements oder Formulars darstellt.  
  
#### So erstellen Sie ein Graphics\-Objekt mit der CreateGraphics\-Methode  
  
-   Rufen Sie die <xref:System.Windows.Forms.Control.CreateGraphics%2A>\-Methode des Formulars oder Steuerelements auf, in dem Grafiken gerendert werden sollen.  
  
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
  
## Erstellen aus einem Image\-Objekt  
 Graphics\-Objekte können außerdem aus allen Objekten erstellt werden, die von der <xref:System.Drawing.Image>\-Klasse abgeleitet wurden.  
  
#### So erstellen Sie ein Graphics\-Objekt aus einem Image\-Objekt  
  
-   Rufen Sie die <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=fullName>\-Methode auf, und geben Sie dabei den Namen der Image\-Variablen an, aus der ein <xref:System.Drawing.Graphics>\-Objekt erstellt werden soll.  
  
     Das folgende Beispiel veranschaulicht die Verwendung eines <xref:System.Drawing.Bitmap>\-Objekts:  
  
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
>  Sie können <xref:System.Drawing.Graphics>\-Objekte nur aus nicht indizierten BMP\-Dateien erstellen, z. B. BMP\-Dateien mit 16 Bits, 24 Bits und 32 Bits.  Jedes Pixel einer nicht indizierten BMP\-Datei hat eine Farbe. Pixel von indizierten BMP\-Dateien besitzen im Unterschied dazu einen Index zu einer Farbtabelle.  
  
## Zeichnen und Bearbeiten von Formen und Bildern  
 Ein <xref:System.Drawing.Graphics>\-Objekt wird zum Zeichnen von Linien und Formen, Rendern von Text oder Anzeigen und Bearbeiten von Bildern eingesetzt.  Das <xref:System.Drawing.Graphics>\-Objekt wird hauptsächlich mit folgenden Objekten verwendet:  
  
-   <xref:System.Drawing.Pen>\-Klasse – Zum Zeichnen von Linien und Konturen von Formen oder zum Rendern anderer geometrischer Darstellungen.  
  
-   <xref:System.Drawing.Brush>\-Klasse – Zum Ausfüllen von Grafikbereichen wie gefüllten Formen, Bildern oder Texten.  
  
-   <xref:System.Drawing.Font>\-Klasse – Bietet Beschreibungen dazu, welche Formen beim Rendern von Text verwendet werden sollten.  
  
-   <xref:System.Drawing.Color>\-Struktur – Entspricht den verschiedenen anzuzeigenden Farben.  
  
#### So verwenden Sie das erstellte Graphics\-Objekt  
  
-   Um ein bestimmtes Element zu zeichnen, verwenden Sie das entsprechende Objekt aus der vorangehenden Liste.  
  
     Weitere Informationen finden Sie unter den folgenden Themen:  
  
    |Rendern von|Siehe|  
    |-----------------|-----------|  
    |Linien|[Gewusst wie: Zeichnen einer Linie in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)|  
    |Formen|[Gewusst wie: Zeichnen der Kontur einer Form](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)|  
    |Text|[Gewusst wie: Zeichnen von Text in einem Windows Form](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)|  
    |Bilder|[Gewusst wie: Darstellen von Bildern mit GDI\+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)|  
  
## Siehe auch  
 [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Gewusst wie: Darstellen von Bildern mit GDI\+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)