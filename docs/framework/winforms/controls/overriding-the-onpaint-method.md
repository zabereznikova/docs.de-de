---
title: "&#220;berschreiben der OnPaint-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "OnPaint-Methode, Überschreiben in benutzerdefinierten Windows Forms-Steuerelementen"
  - "Paint-Ereignis, Behandeln in benutzerdefinierten Windows Forms-Steuerelementen"
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# &#220;berschreiben der OnPaint-Methode
Die grundlegenden Schritte zum Überschreiben von in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] definierten Ereignissen sind identisch und werden in der folgenden Liste zusammengefasst.  
  
#### So überschreiben Sie ein geerbtes Ereignis  
  
1.  Überschreiben Sie die geschützte `On`*EventName*\-Methode.  
  
2.  Rufen Sie die `On`*EventName*\-Methode der Basisklasse aus der überschriebenen `On`*EventName*\-Methode auf, sodass registrierte Delegaten das Ereignis empfangen.  
  
 Das <xref:System.Windows.Forms.Control.Paint>\-Ereignis wird hier ausführlich erörtert, da jedes Windows Forms\-Steuerelement das von <xref:System.Windows.Forms.Control> geerbte <xref:System.Windows.Forms.Control.Paint>\-Ereignis überschreiben muss.  Die <xref:System.Windows.Forms.Control>\-Basisklasse "weiß" nicht, wie ein abgeleitetes Steuerelement gezeichnet werden muss, und stellt in der <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode keine Zeichenlogik bereit.  Die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode von <xref:System.Windows.Forms.Control> sendet das <xref:System.Windows.Forms.Control.Paint>\-Ereignis einfach an registrierte Ereignisempfänger.  
  
 Wenn Sie das Beispiel unter [Gewusst wie: Entwickeln eines einfachen Windows Forms\-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md) durchgearbeitet haben, wissen Sie, wie die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode überschrieben wird.  Das folgende Codefragment ist daraus entnommen.  
  
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
  
 Die <xref:System.Windows.Forms.PaintEventArgs>\-Klasse enthält Daten für das <xref:System.Windows.Forms.Control.Paint>\-Ereignis.  Sie verfügt über zwei Eigenschaften, wie im folgenden Code dargestellt.  
  
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
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> ist das zu zeichnende Rechteck, und die <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A>\-Eigenschaft verweist auf ein <xref:System.Drawing.Graphics>\-Objekt.  Die Klassen im <xref:System.Drawing?displayProperty=fullName>\-Namespace sind verwaltete Klassen, die den Zugriff auf die Funktionen von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], die neue Windows\-Graphikbibliothek, ermöglichen.  Das <xref:System.Drawing.Graphics>\-Objekt verfügt über Methoden zum Zeichnen von Punkten, Zeichenfolgen, Linien, Bögen, Ellipsen und vielen anderen Formen.  
  
 Ein Steuerelement ruft seine <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode dann auf, wenn seine visuelle Darstellung geändert werden soll.  Diese Methode löst wiederum das <xref:System.Windows.Forms.Control.Paint>\-Ereignis aus.  
  
## Siehe auch  
 [Ereignisse](../../../../docs/standard/events/index.md)   
 [Wiedergeben eines Windows Forms\-Steuerelements](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)   
 [Definieren eines Ereignisses](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)