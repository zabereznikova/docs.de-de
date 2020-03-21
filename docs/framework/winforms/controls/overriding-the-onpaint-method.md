---
title: Überschreiben der OnPaint-Methode
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
ms.openlocfilehash: 863726a6264f01de9f00296b4a64b9fd1bb96765
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182035"
---
# <a name="overriding-the-onpaint-method"></a>Überschreiben der OnPaint-Methode
Die grundlegenden Schritte zum Überschreiben eines in .NET Framework definierten Ereignisses sind identisch und werden in der folgenden Liste zusammengefasst.  
  
#### <a name="to-override-an-inherited-event"></a>So überschreiben Sie ein geerbtes Ereignis  
  
1. Überschreiben Sie `On`die geschützte *EventName-Methode.*  
  
2. Rufen `On`Sie die *EventName-Methode* der `On`Basisklasse aus der überschriebenen *EventName-Methode* auf, damit registrierte Delegaten das Ereignis empfangen.  
  
 Das <xref:System.Windows.Forms.Control.Paint> Ereignis wird hier ausführlich erläutert, da jedes <xref:System.Windows.Forms.Control.Paint> Windows Forms-Steuerelement <xref:System.Windows.Forms.Control>das Ereignis überschreiben muss, von dem es erbt. Die <xref:System.Windows.Forms.Control> Basisklasse weiß nicht, wie ein abgeleitetes Steuerelement gezeichnet werden <xref:System.Windows.Forms.Control.OnPaint%2A> muss, und stellt keine Mallogik in der Methode bereit. Die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode, <xref:System.Windows.Forms.Control> das <xref:System.Windows.Forms.Control.Paint> Ereignis einfach an registrierte Ereignisempfänger zu senden.  
  
 Wenn Sie das Beispiel unter [Gewusst wie: Entwickeln eines einfachen Windows Forms](how-to-develop-a-simple-windows-forms-control.md) <xref:System.Windows.Forms.Control.OnPaint%2A> Control verarbeitet haben, haben Sie ein Beispiel für das Überschreiben der Methode gesehen. Das folgende Codefragment wird diesem Beispiel entnommen.  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class
```  
  
```csharp  
public class FirstControl : Control {  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }
}
```  
  
 Die <xref:System.Windows.Forms.PaintEventArgs> Klasse enthält <xref:System.Windows.Forms.Control.Paint> Daten für das Ereignis. Es hat zwei Eigenschaften, wie im folgenden Code gezeigt.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>ist das rechteckige Rechteck, <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> das gezeichnet <xref:System.Drawing.Graphics> werden soll, und die Eigenschaft bezieht sich auf ein Objekt. Die Klassen <xref:System.Drawing?displayProperty=nameWithType> im Namespace sind verwaltete Klassen, die Zugriff auf die Funktionalität von GDI+, der neuen Windows-Grafikbibliothek, bieten. Das <xref:System.Drawing.Graphics> Objekt verfügt über Methoden zum Zeichnen von Punkten, Zeichenfolgen, Linien, Bogen, Ellipsen und vielen anderen Formen.  
  
 Ein Steuerelement ruft <xref:System.Windows.Forms.Control.OnPaint%2A> seine Methode auf, wenn es seine visuelle Anzeige ändern muss. Diese Methode wiederum <xref:System.Windows.Forms.Control.Paint> löst das Ereignis aus.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ereignisse](../../../standard/events/index.md)
- [Wiedergeben eines Windows Forms-Steuerelements](rendering-a-windows-forms-control.md)
- [Definieren eines Ereignisses](defining-an-event-in-windows-forms-controls.md)
