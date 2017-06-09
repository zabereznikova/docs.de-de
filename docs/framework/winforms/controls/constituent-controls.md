---
title: "Konstituierende Steuerelemente | Microsoft Docs"
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
  - "Konstituierende Steuerelemente"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Konstituierende Steuerelemente"
  - "Benutzersteuerelemente [Windows Forms], Konstituierende Steuerelemente"
  - "UserControl-Klasse"
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Konstituierende Steuerelemente
Die Steuerelemente, aus denen ein Benutzersteuerelement gebildet wird, werden als *konstituierende Steuerelemente* bezeichnet. Sie verhalten sich beim Rendering benutzerdefinierter Grafiken relativ unflexibel.  Die Selbstausgabe wird von allen Steuerelementen in Windows Forms mittels der eigenen <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode bewerkstelligt.  Da diese Methode geschützt ist, kann der Entwickler nicht auf sie zugreifen. Daher kann auch nicht verhindert werden, dass die Methode ausgeführt wird, sobald ein Steuerelement gezeichnet wird.  Das bedeutet jedoch nicht, dass kein Code hinzugefügt werden kann, um die Darstellung der konstituierenden Komponenten zu beeinflussen.  Zusätzliches Ausgeben kann ermöglicht werden, indem ein Ereignishandler hinzugefügt wird.  Angenommen, Sie erstellen ein <xref:System.Windows.Forms.UserControl> mit einer Schaltfläche mit der Bezeichnung `MyButton`.  Wenn zusätzliches Rendern eingesetzt werden soll, das über das hinausgeht, was von der [Button\-Klasse](frlrfSystemWebUIWebControlsButtonClassTopic) bereitgestellt wird, würde Code ähnlich dem folgenden zu dem Steuerelement hinzugefügt werden:  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=   
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,   
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
>  Einige Steuerelemente in Windows Forms, z. B. <xref:System.Windows.Forms.TextBox>, werden direkt von Windows gezeichnet.  In solchen Instanzen wird die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode nie aufgerufen und das obige Beispiel daher nie verwendet.  
  
 Hierdurch wird eine Methode erstellt, die jedes Mal ausgeführt wird, sobald das `MyButton.Paint`\-Ereignis ausgeführt wird. So wird dem Steuerelement eine zusätzliche grafische Darstellung hinzugefügt.  Beachten Sie, dass dadurch nicht die Ausführung von `MyButton.OnPaint` verhindert wird. Daher werden zusätzlich zu den benutzerdefinierten Zeichenvorgängen alle Zeichenvorgänge ausgeführt, die in der Regel über eine Schaltfläche vorgenommen werden.  Einzelheiten über die GDI\+\-Technologie und benutzerdefiniertes Rendern finden Sie unter [Erstellen von Grafiken mit GDI\+](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  Der beste Weg zum Erreichen einer einheitlichen Darstellung des Steuerelements besteht darin, ein geerbtes Steuerelement zu erstellen und Code zum benutzerdefinierten Ausgeben dieses Steuerelements zu schreiben.  Einzelheiten dazu finden Sie unter [Benutzerdefinierte Steuerelemente](../../../../docs/framework/winforms/controls/user-drawn-controls.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.UserControl>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Benutzerdefinierte Steuerelemente](../../../../docs/framework/winforms/controls/user-drawn-controls.md)   
 [Gewusst wie: Erstellen von Graphics\-Objekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)