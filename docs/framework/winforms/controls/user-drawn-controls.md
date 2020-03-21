---
title: Benutzerdefinierte Steuerelemente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
ms.openlocfilehash: c68c8c88376cfe7295962264c466030115f2f3db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182008"
---
# <a name="user-drawn-controls"></a>Benutzerdefinierte Steuerelemente
Mit .NET Framework können Sie ganz einfach eigene Steuerelemente entwickeln. Sie können ein Benutzersteuerelement erstellen, bei dem es sich um einen Satz von Standardsteuerelementen handelt, die durch Code miteinander verbunden sind, oder Sie können Ihr eigenes Steuerelement von Grund auf entwerfen. Sie können sogar vererbung verwenden, um ein Steuerelement zu erstellen, das von einem vorhandenen Steuerelement erbt und seine inhärente Funktionalität ergänzt. Unabhängig von der von Ihnen verfolgten Vorgehensweise bietet .NET Framework die Funktionalität zum Zeichnen einer benutzerdefinierten grafischen Benutzeroberfläche für jedes steuerelement, das Sie erstellen.  
  
 Das Malen eines Steuerelements erfolgt durch die <xref:System.Windows.Forms.Control.OnPaint%2A> Ausführung von Code in der Methode des Steuerelements. Das einzelne Argument <xref:System.Windows.Forms.Control.OnPaint%2A> der <xref:System.Windows.Forms.PaintEventArgs> Methode ist ein Objekt, das alle Informationen und Funktionen bereitstellt, die zum Rendern des Steuerelements erforderlich sind. Der <xref:System.Windows.Forms.PaintEventArgs> stellt als Eigenschaften zwei Hauptobjekte bereit, die beim Rendern des Steuerelements verwendet werden:  
  
- <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>Objekt - das Rechteck, das den Teil des Steuerelements darstellt, der gezeichnet wird. Dies kann das gesamte Steuerelement oder ein Teil des Steuerelements sein, je nachdem, wie das Steuerelement gezeichnet wird.  
  
- <xref:System.Drawing.Graphics>object - Kapselt mehrere grafikorientierte Objekte und Methoden, die die zum Zeichnen des Steuerelements erforderliche Funktionalität bereitstellen.  
  
 Weitere Informationen zum <xref:System.Drawing.Graphics> Objekt und zur Verwendung finden Sie unter [Gewusst wie: Erstellen von Grafikobjekten für das Zeichnen](../advanced/how-to-create-graphics-objects-for-drawing.md).  
  
 Das <xref:System.Windows.Forms.Control.OnPaint%2A> Ereignis wird ausgelöst, wenn das Steuerelement auf dem <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Bildschirm gezeichnet oder aktualisiert wird, und das Objekt stellt das Rechteck dar, in dem das Malen stattfindet. Wenn das gesamte Steuerelement aktualisiert werden <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> muss, stellt der die Größe des gesamten Steuerelements dar. Wenn jedoch nur ein Teil des Steuerelements <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> aktualisiert werden muss, stellt das Objekt nur den Bereich dar, der neu gezeichnet werden muss. Ein Beispiel für einen solchen Fall wäre, wenn ein Steuerelement teilweise durch ein anderes Steuerelement oder Formular in der Benutzeroberfläche verdeckt wurde.  
  
 Beim Erben von der <xref:System.Windows.Forms.Control> Klasse müssen Sie <xref:System.Windows.Forms.Control.OnPaint%2A> die Methode überschreiben und innerhalb von Grafikrenderingcode bereitstellen. Wenn Sie einem Benutzersteuerelement oder einem geerbten Steuerelement eine benutzerdefinierte grafische Benutzeroberfläche <xref:System.Windows.Forms.Control.OnPaint%2A> bereitstellen möchten, können Sie dies auch tun, indem Sie die Methode überschreiben. Unten ist ein Beispiel angegeben:  
  
```vb  
Protected Overrides Sub OnPaint(ByVal e As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(e)  
  
   ' Declare and instantiate a drawing pen.  
   Using myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
      ' Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
   End Using
End Sub  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs e)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(e);  
  
   // Declare and instantiate a new pen.  
   using (System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua))  
   {
      // Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,
         this.Size));  
   }
}  
```  
  
 Im obigen Beispiel wird veranschaulicht, wie ein Steuerelement mit einer sehr einfachen grafischen Darstellung gerendert wird. Es ruft <xref:System.Windows.Forms.Control.OnPaint%2A> die Methode der Basisklasse <xref:System.Drawing.Pen> auf, es erstellt ein Objekt, mit dem gezeichnet <xref:System.Windows.Forms.Control.Location%2A> werden <xref:System.Windows.Forms.Control.Size%2A> soll, und zeichnet schließlich eine Ellipse im Rechteck, das durch das und des Steuerelements bestimmt wird. Obwohl der größte Teil des Rendercodes wesentlich komplizierter ist, <xref:System.Drawing.Graphics> veranschaulicht dieses <xref:System.Windows.Forms.PaintEventArgs> Beispiel die Verwendung des im Objekt enthaltenen Objekts. Beachten Sie, dass Sie die <xref:System.Windows.Forms.UserControl> <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.OnPaint%2A> Methode der Basisklasse nicht aufrufen sollten, wenn Sie von einer Klasse erben, die bereits über eine grafische Darstellung verfügt, z. B. oder , und diese Darstellung nicht in ihr Rendering integrieren möchten.  
  
 Der Code <xref:System.Windows.Forms.Control.OnPaint%2A> in der Methode des Steuerelements wird ausgeführt, wenn das Steuerelement zum ersten Mal gezeichnet wird und wann immer es aktualisiert wird. Um sicherzustellen, dass das Steuerelement bei jeder Größenverwaltung neu gezeichnet wird, fügen Sie dem Konstruktor des Steuerelements die folgende Zeile hinzu:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> Verwenden <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> Sie die Eigenschaft, um ein nicht rechteckiges Steuerelement zu implementieren.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [Gewusst wie: Erstellen von Graphics-Objekten zum Zeichnen](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Konstituierende Steuerelemente](constituent-controls.md)
- [Arten von benutzerdefinierten Steuerelementen](varieties-of-custom-controls.md)
