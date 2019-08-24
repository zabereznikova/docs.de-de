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
ms.openlocfilehash: f006e42771a5ecc71f6a508fd78d0e2dd8f2d2f2
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015877"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>Vorgehensweise: Verfügbarmachen der Eigenschaften konstituierender Steuerelemente
Die Steuerelemente, die ein zusammengesetztes Steuerelement bilden, sind *konstituierende Steuerelemente*. Diese Steuerelemente werden normalerweise als privat deklariert und können daher nicht vom Entwickler aufgerufen werden. Wenn Sie für zukünftige Benutzereigenschaften dieser Steuerelemente verfügbar machen möchten, müssen Sie Sie für den Benutzer verfügbar machen. Eine Eigenschaft eines konstituierenden Steuer Elements wird verfügbar gemacht, indem eine Eigenschaft im Benutzer Steuerelement erstellt `get` und `set` der-Accessor und der-Accessor dieser Eigenschaft verwendet werden, um die Änderung in der private-Eigenschaft des konstituierenden Steuer Elements zu beeinflussen.

 Stellen Sie sich ein hypothetisches Benutzer Steuerelement mit `MyButton`einer konstituierenden Schaltfläche namens vor In diesem Beispiel wird der Wert, der in `ConstituentButtonBackColor` der <xref:System.Windows.Forms.Control.BackColor%2A> -Eigenschaft von gespeichert ist, über `MyButton` mittelt, wenn der Benutzer die-Eigenschaft anfordert. Wenn der Benutzer dieser Eigenschaft einen Wert zuweist, wird dieser Wert automatisch an <xref:System.Windows.Forms.Control.BackColor%2A> die-Eigenschaft von über `MyButton` mittelt `set` , und der Code wird ausgeführt, und `MyButton`die Farbe von wird geändert.

 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Forms.Control.BackColor%2A> -Eigenschaft der konstituierenden Schaltfläche verfügbar gemacht wird:

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

### <a name="to-expose-a-property-of-a-constituent-control"></a>So machen Sie eine Eigenschaft eines konstituierenden Steuer Elements verfügbar

1. Erstellen Sie eine öffentliche Eigenschaft für das Benutzer Steuerelement.

2. Schreiben Sie im- Abschnittder-EigenschaftCode,derdenWertderEigenschaftabruft,dieSieverfügbarmachenmöchten.`get`

3. Schreiben Sie im- Abschnittder-EigenschaftCode,derdenWertder-Eigenschaftandieverfügbargemachte-EigenschaftdeskonstituierendenSteuerElementsübergibt.`set`

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.UserControl>
- [Eigenschaften in Windows Forms-Steuerelementen](properties-in-windows-forms-controls.md)
- [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](varieties-of-custom-controls.md)
