---
title: 'Gewusst wie: Kopieren von Pixeln zum Vermindern des Flackerns in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
ms.openlocfilehash: dc5f05ff4ea9f3c2b828cbe37860e1bd241fc604
ms.sourcegitcommit: 3d42e1d73e21c35c540dd4adbea23efcbe1b8b0a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "36270434"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Gewusst wie: Kopieren von Pixeln zum Vermindern des Flackerns in Windows Forms
Wenn Sie eine einfache Grafik animieren, können Benutzer manchmal Flackern oder andere unerwünschte visuelle Effekte auftreten. Eine Möglichkeit, dieses Problem zu beschränken ist, einen "Bitblt" auf die Grafik zu verwenden. BitBlt ist die "Bitblocktransfer" der Farbdaten aus einem Ursprung Rechteck aus Pixeln einen Ziel-Rechteck aus Pixeln.  
  
 Mit Windows Forms Bitblt erfolgt mithilfe der <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode der <xref:System.Drawing.Graphics> Klasse. In den Parametern der Methode geben Sie an der Quelle und Ziel (als Punkte), die Größe des Bereichs, kopiert werden und die Graphics-Objekts verwendet, um die neue Form zu zeichnen.  
  
 Im folgenden Beispiel wird eine Form gezeichnet wird, auf dem Formular in seiner <xref:System.Windows.Forms.Control.Paint> -Ereignishandler. Anschließend wird die <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode wird verwendet, um die Form zu duplizieren.  
  
> [!NOTE]
>  Festlegen des Formulars <xref:System.Windows.Forms.Control.DoubleBuffered%2A> Eigenschaft `true` stellen grafikbasierte Code in die <xref:System.Windows.Forms.Control.Paint> Ereignis werden doppelt gepuffert. Obwohl dies nicht über messbaren Leistungssteigerung besitzt, wenn Sie den folgenden Code verwenden, ist es etwas zu bedenken, bei der Arbeit mit komplexen grafikbearbeitung Code.  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Der obige Code ausgeführt wird, in der Form <xref:System.Windows.Forms.Control.Paint> -Ereignishandler, damit die Grafiken erhalten bleiben, wenn die Form neu gezeichnet wird. Rufen Sie daher keine Arbeit mit Grafiken und Methoden in der <xref:System.Windows.Forms.Form.Load> Ereignishandler, da der gezeichnete Inhalt nicht neu gezeichnet wird, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.CopyPixelOperation>  
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
