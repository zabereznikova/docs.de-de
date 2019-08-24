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
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="b9164-102">Vorgehensweise: Verfügbarmachen der Eigenschaften konstituierender Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="b9164-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="b9164-103">Die Steuerelemente, die ein zusammengesetztes Steuerelement bilden, sind *konstituierende Steuerelemente*.</span><span class="sxs-lookup"><span data-stu-id="b9164-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="b9164-104">Diese Steuerelemente werden normalerweise als privat deklariert und können daher nicht vom Entwickler aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b9164-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="b9164-105">Wenn Sie für zukünftige Benutzereigenschaften dieser Steuerelemente verfügbar machen möchten, müssen Sie Sie für den Benutzer verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="b9164-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="b9164-106">Eine Eigenschaft eines konstituierenden Steuer Elements wird verfügbar gemacht, indem eine Eigenschaft im Benutzer Steuerelement erstellt `get` und `set` der-Accessor und der-Accessor dieser Eigenschaft verwendet werden, um die Änderung in der private-Eigenschaft des konstituierenden Steuer Elements zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="b9164-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>

 <span data-ttu-id="b9164-107">Stellen Sie sich ein hypothetisches Benutzer Steuerelement mit `MyButton`einer konstituierenden Schaltfläche namens vor</span><span class="sxs-lookup"><span data-stu-id="b9164-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="b9164-108">In diesem Beispiel wird der Wert, der in `ConstituentButtonBackColor` der <xref:System.Windows.Forms.Control.BackColor%2A> -Eigenschaft von gespeichert ist, über `MyButton` mittelt, wenn der Benutzer die-Eigenschaft anfordert.</span><span class="sxs-lookup"><span data-stu-id="b9164-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="b9164-109">Wenn der Benutzer dieser Eigenschaft einen Wert zuweist, wird dieser Wert automatisch an <xref:System.Windows.Forms.Control.BackColor%2A> die-Eigenschaft von über `MyButton` mittelt `set` , und der Code wird ausgeführt, und `MyButton`die Farbe von wird geändert.</span><span class="sxs-lookup"><span data-stu-id="b9164-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>

 <span data-ttu-id="b9164-110">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Forms.Control.BackColor%2A> -Eigenschaft der konstituierenden Schaltfläche verfügbar gemacht wird:</span><span class="sxs-lookup"><span data-stu-id="b9164-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>

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

### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="b9164-111">So machen Sie eine Eigenschaft eines konstituierenden Steuer Elements verfügbar</span><span class="sxs-lookup"><span data-stu-id="b9164-111">To expose a property of a constituent control</span></span>

1. <span data-ttu-id="b9164-112">Erstellen Sie eine öffentliche Eigenschaft für das Benutzer Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b9164-112">Create a public property for your user control.</span></span>

2. <span data-ttu-id="b9164-113">Schreiben Sie im- Abschnittder-EigenschaftCode,derdenWertderEigenschaftabruft,dieSieverfügbarmachenmöchten.`get`</span><span class="sxs-lookup"><span data-stu-id="b9164-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>

3. <span data-ttu-id="b9164-114">Schreiben Sie im- Abschnittder-EigenschaftCode,derdenWertder-Eigenschaftandieverfügbargemachte-EigenschaftdeskonstituierendenSteuerElementsübergibt.`set`</span><span class="sxs-lookup"><span data-stu-id="b9164-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9164-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9164-115">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="b9164-116">Eigenschaften in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="b9164-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="b9164-117">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="b9164-117">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
