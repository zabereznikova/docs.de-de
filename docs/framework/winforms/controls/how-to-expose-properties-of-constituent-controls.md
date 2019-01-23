---
title: 'Vorgehensweise: Verfügbarmachen der Eigenschaften konstituierender Steuerelemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
ms.openlocfilehash: f3ad37032ee2bb85f37a0eb754277cc9bc040a38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532161"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>Vorgehensweise: Verfügbarmachen der Eigenschaften konstituierender Steuerelemente
Die Steuerelemente, die ein zusammengesetztes Steuerelement zu bilden, heißen *konstituierende Steuerelemente*. Diese Steuerelemente werden normalerweise als privat deklariert, und daher können nicht vom Entwickler zugegriffen werden kann. Wenn Sie die Eigenschaften dieser Steuerelemente zukünftigen Benutzern zur Verfügung stellen möchten, müssen Sie für den Benutzer verfügbar machen. Eine Eigenschaft des konstituierenden Steuerelements wird verfügbar gemacht, indem Sie eine Eigenschaft im Benutzersteuerelement erstellt und die `get` und `set` Accessoren der Eigenschaft, die Auswirkungen der Änderung in der privaten Eigenschaft des konstituierenden Steuerelements.  
  
 Betrachten Sie ein hypothetisches Benutzersteuerelement mit der zugehörigen Schaltfläche `MyButton`. In diesem Beispiel, wenn der Benutzer fordert die `ConstituentButtonBackColor` -Eigenschaft, die in gespeicherten Wert der <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft `MyButton` wird übermittelt. Wenn der Benutzer diese Eigenschaft einen Wert zuweist, ist dieser Wert automatisch zum Übergeben der <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft `MyButton` und die `set` Code wird ausgeführt, ändern die Farbe des `MyButton`.  
  
 Das folgende Beispiel zeigt, wie Sie verfügbar machen die <xref:System.Windows.Forms.Control.BackColor%2A> -Eigenschaft der zugehörigen Schaltfläche:  
  
```vb  
Public Property ButtonColor() as System.Drawing.Color  
   Get  
      Return MyButton.BackColor  
   End Get  
   Set(Value as System.Drawing.Color)  
      MyButton.BackColor = Value  
   End Set  
End Property  
```  
  
```csharp  
public Color ButtonColor  
{  
   get  
   {  
      return(myButton.BackColor);  
   }  
   set  
   {  
      myButton.BackColor = value;  
   }  
}  
```  
  
### <a name="to-expose-a-property-of-a-constituent-control"></a>Eine Eigenschaft des konstituierenden Steuerelements verfügbar machen.  
  
1.  Erstellen Sie eine öffentliche Eigenschaft für das Steuerelement.  
  
2.  In der `get` Abschnitt der Eigenschaft, Code schreiben, der den Wert der Eigenschaft abruft, verfügbar machen möchten.  
  
3.  In der `set` Abschnitt der Eigenschaft, Code schreiben, der den Wert der Eigenschaft an die verfügbar gemachten Eigenschaft des konstituierenden Steuerelements übergibt.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.UserControl>
- [Eigenschaften in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
- [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
