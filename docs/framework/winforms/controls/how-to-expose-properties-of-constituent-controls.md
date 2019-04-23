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
ms.openlocfilehash: 44b96218e674c754a1985f2f22a36707cd1776b6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59294911"
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
  
1. Erstellen Sie eine öffentliche Eigenschaft für das Steuerelement.  
  
2. In der `get` Abschnitt der Eigenschaft, Code schreiben, der den Wert der Eigenschaft abruft, verfügbar machen möchten.  
  
3. In der `set` Abschnitt der Eigenschaft, Code schreiben, der den Wert der Eigenschaft an die verfügbar gemachten Eigenschaft des konstituierenden Steuerelements übergibt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.UserControl>
- [Eigenschaften in Windows Forms-Steuerelementen](properties-in-windows-forms-controls.md)
- [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](varieties-of-custom-controls.md)
