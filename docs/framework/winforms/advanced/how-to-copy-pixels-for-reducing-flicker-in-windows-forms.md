---
title: "Gewusst wie: Kopieren von Pixeln zum Vermindern des Flackerns in Windows Forms | Microsoft Docs"
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
  - "Bitblockübertragung"
  - "bitblt"
  - "Flimmern"
  - "Flimmern, Vermindern in Windows Forms"
  - "Grafiken, Kopieren"
  - "Grafiken, Vermindern des Flimmerns"
  - "Pixel, Kopieren"
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Kopieren von Pixeln zum Vermindern des Flackerns in Windows Forms
Wenn Sie eine einfache Grafik animieren, können manchmal Flackern oder andere unerwünschte visuelle Effekte auftreten.  Eine Möglichkeit, dieses Problem möglichst in Grenzen zu halten, besteht darin, in der Grafik einen "bitblt"\-Prozess zu verwenden.  Unter Bitblt versteht man den "Bitblocktransfer" der Farbdaten von einem ursprünglichen Rechteck aus Pixel zu einem Zielrechteck aus Pixel.  
  
 Mit Windows Forms erfolgt der Bitblocktransfer mithilfe der <xref:System.Drawing.Graphics.CopyFromScreen%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse.  In den Parametern der Methode geben Sie die Quelle und das Ziel \(als Punkte\), die Größe des zu kopierenden Bereichs und das zum Zeichnen der neuen Form verwendete Grafikobjekt an.  
  
 Im Beispiel unten wird im <xref:System.Windows.Forms.Control.Paint>\-Ereignishandler eine Form auf dem Formular gezeichnet.  Anschließend wird die Form mithilfe der <xref:System.Drawing.Graphics.CopyFromScreen%2A>\-Methode dupliziert.  
  
> [!NOTE]
>  Durch Festlegen der <xref:System.Windows.Forms.Control.DoubleBuffered%2A>\-Eigenschaft des Formulars auf `true` wird grafikbasierter Code im <xref:System.Windows.Forms.Control.Paint>\-Ereignis doppelt gepuffert.  Zwar führt dies bei Verwendung des nachstehenden Codes zu keinen nennenswerten Leistungsverbesserungen, sollte jedoch im Hinblick auf komplexeren Code zur Grafikbearbeitung beachtet werden.  
  
## Beispiel  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## Kompilieren des Codes  
 Der obige Code wird im <xref:System.Windows.Forms.Control.Paint>\-Ereignishandler des Formulars ausgeführt, sodass die Grafiken erhalten bleiben, wenn das Formular neu gezeichnet wird.  Rufen Sie im <xref:System.Windows.Forms.Form.Load>\-Ereignishandler keine auf Grafiken bezogenen Methoden auf, da der gezeichnete Inhalt nicht neu gezeichnet wird, wenn sich die Größe des Formulars ändert oder es von einem anderen Formular verdeckt wird.  
  
## Siehe auch  
 <xref:System.Drawing.CopyPixelOperation>   
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=fullName>   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)