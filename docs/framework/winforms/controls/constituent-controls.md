---
title: Konstituierende Steuerelemente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: 2865a3d85bd56151038ee90c18d199d3a584b5d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182416"
---
# <a name="constituent-controls"></a>Konstituierende Steuerelemente
Die Steuerelemente, aus denen ein Benutzersteuerelement gebildet wird, werden als *konstituierende Steuerelemente* bezeichnet. Sie verhalten sich beim Rendering benutzerdefinierter Grafiken relativ unflexibel. Alle Windows Forms-Steuerelemente verarbeiten <xref:System.Windows.Forms.Control.OnPaint%2A> ihr eigenes Rendering über ihre eigene Methode. Da diese Methode geschützt ist, kann der Entwickler nicht auf sie zugreifen. Daher kann nicht verhindert werden, dass die Methode ausgeführt wird, sobald ein Steuerelement gezeichnet wird. Das bedeutet jedoch nicht, dass kein Code hinzugefügt werden kann, um die Darstellung konstituierender Steuerelemente zu beeinflussen. Zusätzliches Rendering kann ermöglicht werden, indem ein Ereignishandler hinzugefügt wird. Angenommen, Sie haben eine <xref:System.Windows.Forms.UserControl> mit einer `MyButton`Schaltfläche mit dem Namen erstellt. Wenn Sie zusätzliches Rendering haben möchten, <xref:System.Web.UI.WebControls.Button>das über das von der bereitgestellte hinausgeht, fügen Sie dem Benutzersteuerelement Code wie das folgende hinzu:  
  
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
> Einige Windows Forms-Steuerelemente, z. <xref:System.Windows.Forms.TextBox>B. , werden direkt von Windows gezeichnet. In diesen Fällen <xref:System.Windows.Forms.Control.OnPaint%2A> wird die Methode nie aufgerufen, und daher wird das obige Beispiel nie aufgerufen.  
  
 Hierdurch wird eine Methode erstellt, die jedes Mal ausgeführt wird, sobald das `MyButton.Paint`-Ereignis ausgeführt wird. So wird dem Steuerelement eine zusätzliche grafische Darstellung hinzugefügt. Beachten Sie, dass dadurch nicht die Ausführung von `MyButton.OnPaint` verhindert wird. Daher werden zusätzlich zu den benutzerdefinierten Zeichenvorgängen alle Zeichenvorgänge ausgeführt, die in der Regel über eine Schaltfläche erfolgen. Einzelheiten zu GDI+-Technologie und benutzerdefiniertem Rendering finden Sie unter [Erstellen von Grafiken mit GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md). Der beste Weg zum Erreichen einer einheitlichen Darstellung des Steuerelements besteht darin, ein geerbtes Steuerelement zu erstellen und Code zum benutzerdefinierten Ausgeben dieses Steuerelements zu schreiben. Einzelheiten dazu finden Sie unter [Benutzerdefinierte Steuerelemente](user-drawn-controls.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Benutzerdefinierte Steuerelemente](user-drawn-controls.md)
- [Gewusst wie: Erstellen von Graphics-Objekten zum Zeichnen](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Arten von benutzerdefinierten Steuerelementen](varieties-of-custom-controls.md)
