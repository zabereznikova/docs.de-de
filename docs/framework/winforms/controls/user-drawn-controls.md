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
ms.openlocfilehash: bd7ce150e4dc0ecfe53f92ec8b557459f1e14e3a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651569"
---
# <a name="user-drawn-controls"></a>Benutzerdefinierte Steuerelemente
.NET Framework bietet die Möglichkeit, eigene Steuerelemente problemlos zu entwickeln. Können Sie ein Benutzersteuerelement, das einen Satz der Standardsteuerelemente, die zusammen mit Code gebunden ist, erstellen, oder Sie können Ihr eigenes Steuerelement von Grund auf neu entwerfen, einrichten. Sie können auch die Vererbung verwenden, erstellen ein Steuerelement, das von einem vorhandenen Steuerelement erbt und die gesamte Funktionalität hinzufügen. Für welchen Ansatz Sie verwenden, bietet .NET Framework-Funktionen um eine benutzerdefinierte grafische Benutzeroberfläche für jedes Steuerelement zu zeichnen, die Sie erstellen.  
  
 Zeichnen eines Steuerelements wird erreicht, indem die Ausführung von Code in des Steuerelements <xref:System.Windows.Forms.Control.OnPaint%2A> Methode. Einzelnes Argument des der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode ist eine <xref:System.Windows.Forms.PaintEventArgs> Objekt, das alle Informationen und zum Rendern des Steuerelements erforderliche Funktionalität bereitstellt. Die <xref:System.Windows.Forms.PaintEventArgs> zwei principal-Objekten, die beim Rendern des Steuerelements verwendet wird, als Eigenschaften bereitgestellt:  
  
- <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> -Objekt ist das Rechteck, das den Teil des Steuerelements darstellt, die gezeichnet wird. Dies kann sein, dass das gesamte Steuerelement oder einen Teil des Steuerelements je nachdem, wie das Steuerelement gezeichnet wird.  
  
- <xref:System.Drawing.Graphics> Objekt - kapselt mehrere Graphics-orientierten Objekten und Methoden, die zum Zeichnen des Steuerelements erforderliche Funktionen bereitstellen.  
  
 Weitere Informationen zu den <xref:System.Drawing.Graphics> -Objekt und verwendet werden, finden Sie unter [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](../advanced/how-to-create-graphics-objects-for-drawing.md).  
  
 Die <xref:System.Windows.Forms.Control.OnPaint%2A> Ereignis wird ausgelöst, wenn das Steuerelement gezeichnet oder auf dem Bildschirm aktualisiert wird und die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Objekt darstellt, das Rechteck in der Darstellung wird durchgeführt. Wenn das gesamte Steuerelement aktualisiert werden, werden muss die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> die Größe des gesamten Steuerelements darstellt. Wenn nur ein Teil des Steuerelements muss aktualisiert werden jedoch die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Objekt wird nur in die Region, die zu zeichnenden darstellen. Ein Beispiel der Fall wäre, wenn ein Steuerelement durch ein anderes Steuerelement oder Formular in der Benutzeroberfläche teilweise verdeckt wurde.  
  
 Beim Erben von der <xref:System.Windows.Forms.Control> -Klasse, die Sie überschreiben müssen die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode, und geben Sie Code zum Rendern der Grafiken. Wenn Sie eine benutzerdefinierte grafische Oberfläche zum ein Benutzersteuerelement oder ein geerbtes Steuerelement bereitstellen möchten, Sie können auch dazu überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode. Ein Beispiel ist unten dargestellt:  
  
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
  
 Im vorherige Beispiel veranschaulicht, wie ein Steuerelement mit einer einfachen grafischen Darstellung gerendert wird. Ruft die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode der Basisklasse, erstellt eine <xref:System.Drawing.Pen> Objekt mit dem gezeichnet werden soll, und schließlich zeichnet eine Ellipse, in dem Rechteck aus, die durch bestimmt die <xref:System.Windows.Forms.Control.Location%2A> und <xref:System.Windows.Forms.Control.Size%2A> des Steuerelements. Obwohl die meisten Renderingcode deutlich komplizierter ist als dieser sein wird, wird in diesem Beispiel veranschaulicht die Verwendung der der <xref:System.Drawing.Graphics> Objekt in der <xref:System.Windows.Forms.PaintEventArgs> Objekt. Beachten Sie, dass, wenn Sie von einer Klasse erben, die bereits eine grafische Darstellung, wie z. B. <xref:System.Windows.Forms.UserControl> oder <xref:System.Windows.Forms.Button>, und Sie nicht diese Darstellung in das Rendering integrieren möchten, sollten Sie nicht Ihre Basisklasse aufrufen <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode.  
  
 Der Code in die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode des Steuerelements wird ausgeführt, wenn das Steuerelement zuerst gezeichnet wird, und wenn sie aktualisiert werden. Um sicherzustellen, dass das Steuerelement neu gezeichnet wird, jedes Mal, wenn sie die Größe geändert wird, fügen Sie an den Konstruktor des Steuerelements die folgende Zeile hinzu:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  Verwenden der <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> Eigenschaft, um ein nicht rechteckiges Steuerelement zu implementieren.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Konstituierende Steuerelemente](constituent-controls.md)
- [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](varieties-of-custom-controls.md)
