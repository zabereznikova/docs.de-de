---
title: 'Gewusst wie: Kopieren von Pixeln zum Reduzieren von Flicker'
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
ms.openlocfilehash: a25295532d7123d92bcacc6828d3e8cfcc839d6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182587"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Gewusst wie: Kopieren von Pixeln zum Vermindern des Flackerns in Windows Forms
Wenn Sie eine einfache Grafik animieren, können Benutzer manchmal auf Flimmern oder andere unerwünschte visuelle Effekte stoßen. Eine Möglichkeit, dieses Problem zu begrenzen, besteht darin, einen "bitblt"-Prozess in der Grafik zu verwenden. Bitblt ist die "Bitblockübertragung" der Farbdaten von einem Ursprungsrechteck aus Pixeln zu einem Zielrechteck aus Pixeln.  
  
 Mit Windows Forms wird bitblt <xref:System.Drawing.Graphics.CopyFromScreen%2A> mit <xref:System.Drawing.Graphics> der Methode der Klasse ausgeführt. In den Parametern der Methode geben Sie die Quelle und das Ziel (als Punkte), die Größe des zu kopierenden Bereichs und das Grafikobjekt an, das zum Zeichnen der neuen Form verwendet wird.  
  
 Im folgenden Beispiel wird ein Shape auf <xref:System.Windows.Forms.Control.Paint> das Formular in seinem Ereignishandler gezeichnet. Anschließend wird <xref:System.Drawing.Graphics.CopyFromScreen%2A> die Methode verwendet, um die Form zu duplizieren.  
  
> [!NOTE]
> Wenn Sie die <xref:System.Windows.Forms.Control.DoubleBuffered%2A> Eigenschaft `true` des Formulars so <xref:System.Windows.Forms.Control.Paint> festlegen, dass grafikbasierter Code im Ereignis doppelt gepuffert wird. Während dies keine erkennbaren Leistungssteigerungen bei der Verwendung des untenstehenden Codes haben wird, ist es etwas, das Sie bei der Arbeit mit komplexerem Grafikmanipulationscode beachten sollten.  
  
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
 Der obige Code wird im <xref:System.Windows.Forms.Control.Paint> Ereignishandler des Formulars ausgeführt, sodass die Grafiken beim neu zeichnendes Formular beibehalten werden. Rufen Sie daher keine grafikbezogenen Methoden <xref:System.Windows.Forms.Form.Load> im Ereignishandler auf, da der gezeichnete Inhalt nicht neu gezeichnet wird, wenn die Größe des Formulars durch ein anderes Formular geändert oder verdeckt wird.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](using-a-pen-to-draw-lines-and-shapes.md)
