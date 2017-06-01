---
title: "Benutzerdefinierte Steuerelemente | Microsoft Docs"
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
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Benutzerdefiniert"
  - "OnPaint-Methode [Windows Forms]"
  - "Benutzerdefinierte Steuerelemente [Windows Forms]"
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Benutzerdefinierte Steuerelemente
Mit .NET Framework ist es möglich, auf einfache Weise eigene Steuerelemente zu entwickeln.  Sie können ein Benutzersteuerelement, das einen Satz von Standardsteuerelementen darstellt, die durch Code miteinander verbunden sind, erstellen oder ein eigenes Steuerelement von Grund auf neu erstellen.  Sogar Vererbung kann verwendet werden, um ein Steuerelement zu erstellen, das von einem vorhandenen Steuerelement erbt, und um dessen inhärente Funktionalität zu verbessern.  Welche Vorgehensweise auch gewählt wird, mit .NET Framework können Sie für jedes erstellte Steuerelement eine benutzerdefinierte grafische Oberfläche zeichnen.  
  
 Ein Steuerelement wird gezeichnet, indem Code in der <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode des Steuerelements ausgeführt wird.  Bei dem einzigen Argument der <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode handelt es sich um ein <xref:System.Windows.Forms.PaintEventArgs>\-Objekt, das die gesamte Funktionalität und alle Informationen bietet, die zum Rendern des Steuerelements erforderlich sind.  Von <xref:System.Windows.Forms.PaintEventArgs> werden zwei Hauptobjekte, die beim Rendern des Steuerelements verwendet werden, als Eigenschaften bereitgestellt:  
  
-   Das <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>\-Objekt ist das Rechteck, das den Teil des Steuerelements darstellt, der gezeichnet wird.  Dabei kann es sich um das gesamte Steuerelement oder einen Teil des Steuerelements handeln, je nachdem wie das Steuerelement gezeichnet wird.  
  
-   Das <xref:System.Drawing.Graphics>\-Objekt kapselt mehrere grafikorientierte Objekte und Methoden ein, die die erforderliche Funktionalität zum Zeichnen des Steuerelements bieten.  
  
 Weitere Informationen über das <xref:System.Drawing.Graphics>\-Objekt und dessen Verwendung finden Sie unter [Gewusst wie: Erstellen von Graphics\-Objekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
 Das <xref:System.Windows.Forms.Control.OnPaint%2A>\-Ereignis wird jedes Mal ausgelöst, wenn das Steuerelement auf dem Bildschirm gezeichnet oder aktualisiert wird. Das <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>\-Objekt stellt das Rechteck dar, in dem der Zeichenvorgang ausgeführt wird.  Wenn das gesamte Steuerelement aktualisiert werden muss, stellt <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> die Größe des gesamten Steuerelements dar.  Wenn nur ein Teil des Steuerelements aktualisiert werden muss, stellt das <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>\-Objekt jedoch lediglich den Bereich dar, der neu gezeichnet werden muss.  Dies ist beispielsweise der Fall, wenn ein Steuerelement auf der Benutzeroberfläche teilweise von einem anderen Steuerelement oder Formular verdeckt wird.  
  
 Wenn von der <xref:System.Windows.Forms.Control>\-Klasse geerbt wird, muss die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode so überschrieben werden, dass Code zum Rendern der Grafiken bereitgestellt wird.  Wenn eine grafische Oberfläche für eine Benutzeroberfläche oder ein geerbtes Steuerelement bereitgestellt werden soll, kann dies ebenfalls durch Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode erfolgen.  Im Folgenden ein Beispiel:  
  
```vb  
Protected Overrides Sub OnPaint(ByVal pe As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(pe)  
  
   ' Declare and instantiate a drawing pen.  
   Dim myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
  
   ' Draw an aqua rectangle in the rectangle represented by the control.  
   pe.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
End Sub  
  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs pe)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(pe);  
  
   // Declare and instantiate a new pen.  
   System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua);  
  
   // Draw an aqua rectangle in the rectangle represented by the control.  
   pe.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,   
      this.Size));  
}  
  
```  
  
 Im voranstehenden Beispiel wird gezeigt, wie ein Steuerelement mit einer recht einfachen grafischen Darstellung gerendert wird.  Die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode der Basisklasse wird aufgerufen, ein <xref:System.Drawing.Pen>\-Objekt wird erstellt, mit dem die Zeichnung ausgeführt wird, und in dem durch <xref:System.Windows.Forms.Control.Location%2A> und <xref:System.Windows.Forms.Control.Size%2A> des Steuerelements festgelegten Rechteck wird schließlich eine Ellipse gezeichnet.  Auch wenn der Renderingcode meistens deutlich komplizierter ist als in diesem Beispiel, wird die Verwendung des im <xref:System.Windows.Forms.PaintEventArgs>\-Objekt enthaltenen <xref:System.Drawing.Graphics>\-Objekts hier ausreichend veranschaulicht.  Wenn von einer Klasse geerbt wird, die bereits über eine grafische Darstellung verfügt, z. B. <xref:System.Windows.Forms.UserControl> oder <xref:System.Windows.Forms.Button>, und diese Darstellung nicht in das Rendering einbezogen werden soll, darf die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode der Basisklasse nicht aufgerufen werden.  
  
 Der Code in der <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode des Steuerelements wird ausgeführt, wenn das Steuerelement zum ersten Mal gezeichnet oder aktualisiert wird.  Um sicherzustellen, dass das Steuerelement bei jeder Größenänderung neu gezeichnet wird, fügen Sie die folgende Zeile in den Konstruktor des Steuerelements ein:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
  
```  
  
> [!NOTE]
>  Verwenden Sie die <xref:System.Windows.Forms.Control.Region%2A?displayProperty=fullName>\-Eigenschaft, um ein nicht\-rechteckiges Steuerelement zu implementieren.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Control.Region%2A>   
 <xref:System.Windows.Forms.ControlStyles>   
 <xref:System.Drawing.Graphics>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 <xref:System.Windows.Forms.PaintEventArgs>   
 [Gewusst wie: Erstellen von Graphics\-Objekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Konstituierende Steuerelemente](../../../../docs/framework/winforms/controls/constituent-controls.md)   
 [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)