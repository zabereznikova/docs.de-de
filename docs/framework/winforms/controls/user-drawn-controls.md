---
title: Benutzerdefinierte Steuerelemente
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
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42f208d10b1c111f98af3c803148590466baddf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="user-drawn-controls"></a>Benutzerdefinierte Steuerelemente
.NET Framework bietet die Möglichkeit, eigene Steuerelemente entwickeln. Können Sie ein Benutzersteuerelement, das einen Satz von Standardsteuerelementen zusammen in Code vorgesehen ist, erstellen, oder Sie können ein eigenes Steuerelement von Grund auf neu entwerfen, einrichten. Sie können sogar Vererbung verwenden, erstellen ein Steuerelement, das von einem vorhandenen Steuerelement erbt und dessen implementierte Funktionalität hinzufügen. Welchen Ansatz Sie verwenden, stellt .NET Framework die Funktionalität, um eine benutzerdefinierte grafische Benutzeroberfläche für jedes Steuerelement gezeichnet werden soll, die Sie erstellen.  
  
 Zeichnen eines Steuerelements wird erreicht, indem die Ausführung von Code in des Steuerelements <xref:System.Windows.Forms.Control.OnPaint%2A> Methode. Das Argument der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode ist ein <xref:System.Windows.Forms.PaintEventArgs> Objekt, das alle Informationen und zum Rendern des Steuerelements erforderliche Funktionalität bereitstellt. Die <xref:System.Windows.Forms.PaintEventArgs> zwei principal-Objekte, die beim Rendern des Steuerelements verwendet werden, als Eigenschaften bereitgestellt:  
  
-   <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>Objekt – das Rechteck, das den Teil des Steuerelements darstellt, die gezeichnet wird. Dies kann das gesamte Steuerelement oder einen Teil des Steuerelements abhängig davon, wie das Steuerelement gezeichnet wird.  
  
-   <xref:System.Drawing.Graphics>Objekt - kapselt mehrere Graphics-orientierten Objekte und Methoden, die zum Zeichnen des Steuerelements erforderliche Funktionen bereitstellen.  
  
 Weitere Informationen zu den <xref:System.Drawing.Graphics> -Objekt und zum verwenden, finden Sie unter [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
 Die <xref:System.Windows.Forms.Control.OnPaint%2A> Ereignis wird ausgelöst, wenn das Steuerelement gezeichnet oder auf dem Bildschirm aktualisiert wird und die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Objekt darstellt, das Rechteck, in dem gezeichnet werden stattfinden. Wenn das gesamte Steuerelement aktualisiert werden, werden muss die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> wird die Größe des gesamten Steuerelements darstellen. Wenn nur ein Teil des Steuerelements muss aktualisiert werden, werden jedoch die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Objekt repräsentiert nur den Bereich mit der neu gezeichnet werden muss. Ein Beispiel der Fall wäre, wenn ein Steuerelement von einem anderen Steuerelement oder ein Formular in der Benutzeroberfläche teilweise verdeckt werden wurde.  
  
 Beim Erben von der <xref:System.Windows.Forms.Control> -Klasse, die Sie überschreiben müssen die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode, und geben Sie Code zum Rendern der Grafiken. Wenn Sie eine benutzerdefinierte grafische Benutzeroberfläche für ein benutzerdefiniertes Steuerelement oder ein geerbtes Steuerelement bereitstellen möchten, können Sie auch dies tun durch Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode. Ein Beispiel ist unten dargestellt:  
  
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
  
 Im vorherige Beispiel veranschaulicht, wie ein Steuerelement mit einer sehr einfachen grafischen Darstellung gerendert wird. Aufruft der <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode der Basisklasse er erstellt eine <xref:System.Drawing.Pen> -Objekt mit dem gezeichnet werden soll, und schließlich zeichnet eine Ellipse, die in dem Rechteck, bestimmt durch die <xref:System.Windows.Forms.Control.Location%2A> und <xref:System.Windows.Forms.Control.Size%2A> des Steuerelements. Obwohl die meisten Renderingcodes deutlich komplizierter als das sein wird, wird dieses Beispiel veranschaulicht die Verwendung von der <xref:System.Drawing.Graphics> Objekt in der <xref:System.Windows.Forms.PaintEventArgs> Objekt. Beachten Sie, dass, wenn Sie von einer Klasse erben, die bereits eine grafische Darstellung, wie z. B. <xref:System.Windows.Forms.UserControl> oder <xref:System.Windows.Forms.Button>, und Sie nicht diese Darstellung in das Rendering integrieren möchten, rufen Sie nicht die Basisklasse <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.  
  
 Der Code in der <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode des Steuerelements wird ausgeführt, wenn das Steuerelement zuerst gezeichnet wird, und wenn sie aktualisiert wird. Um sicherzustellen, dass das Steuerelement neu gezeichnet wird jedes Mal, wenn er geändert wird, fügen Sie an den Konstruktor des Steuerelements die folgende Zeile hinzu:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  Verwenden der <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> Eigenschaft, um ein viereckig Steuerelement zu implementieren.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Control.Region%2A>  
 <xref:System.Windows.Forms.ControlStyles>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Windows.Forms.PaintEventArgs>  
 [Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Konstituierende Steuerelemente](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
