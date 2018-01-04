---
title: "Überschreiben der OnPaint-Methode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d9012d1a31eeaf50560b6166d32ac58662c5aa4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="overriding-the-onpaint-method"></a>Überschreiben der OnPaint-Methode
Die grundlegenden Schritte zum Überschreiben von Ereignissen definiert, der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] identisch sind und in der folgenden Liste zusammengefasst werden.  
  
#### <a name="to-override-an-inherited-event"></a>Überschreiben ein geerbtes Ereignisses  
  
1.  Überschreiben Sie die geschützte `On` *EventName* Methode.  
  
2.  Rufen Sie die `On` *EventName* -Methode der Basisklasse, von der überschriebenen `On` *EventName* Methode, damit registrierte Delegaten das Ereignis empfangen.  
  
 Die <xref:System.Windows.Forms.Control.Paint> Ereignis wird im folgenden ausführlich erläutert, da jedes Windows Forms-Steuerelement überschreiben, muss die <xref:System.Windows.Forms.Control.Paint> Ereignis, das von der erbt <xref:System.Windows.Forms.Control>. Die Basis <xref:System.Windows.Forms.Control> Klasse weiß nicht, wie ein abgeleitetes Steuerelement gezeichnet werden muss und keine Zeichnungslogik in die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode. Die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode <xref:System.Windows.Forms.Control> einfach verteilt die <xref:System.Windows.Forms.Control.Paint> Ereignis registrierten Ereignisempfänger.  
  
 Wenn Sie das Beispiel in durchgearbeitet [Vorgehensweise: Entwickeln eines einfachen Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), Sie haben gelernt, dass ein Beispiel zum Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode. Das folgende Codefragment stammt aus dem Beispiel.  
  
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
public class FirstControl : Control{  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 Die <xref:System.Windows.Forms.PaintEventArgs> Klasse enthält Daten für die <xref:System.Windows.Forms.Control.Paint> Ereignis. Er verfügt über zwei Eigenschaften, wie im folgenden Code gezeigt.  
  
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
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>ist das Rechteck gezeichnet werden, und die <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> Eigenschaft bezieht sich auf eine <xref:System.Drawing.Graphics> Objekt. Die Klassen in der <xref:System.Drawing?displayProperty=nameWithType> Namespace sind verwaltete Klassen, die Zugriff auf die Funktionalität bereitstellen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], die neue Windows-Grafikbibliothek. Die <xref:System.Drawing.Graphics> Objekt verfügt über Methoden, die Punkte, Zeichenfolgen, Linien, Bögen, Ellipsen und vielen anderen Formen gezeichnet werden soll.  
  
 Ein Steuerelement ruft seine <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode auf, wenn sie die visuelle Darstellung geändert werden muss. Diese Methode löst wiederum die <xref:System.Windows.Forms.Control.Paint> Ereignis.  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisse](../../../../docs/standard/events/index.md)  
 [Wiedergeben eines Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 [Definieren eines Ereignisses](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
