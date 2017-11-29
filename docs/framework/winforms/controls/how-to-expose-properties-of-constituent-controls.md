---
title: "Gewusst wie: Verfügbarmachen der Eigenschaften konstituierender Steuerelemente"
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
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eb85cb77c28ad443fb6837a5305a080c450220f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="a9050-102">Gewusst wie: Verfügbarmachen der Eigenschaften konstituierender Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="a9050-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="a9050-103">Die Steuerelemente, die ein zusammengesetztes Steuerelement bilden heißen *konstituierende Steuerelemente*.</span><span class="sxs-lookup"><span data-stu-id="a9050-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="a9050-104">Diese Steuerelemente werden normalerweise als privat deklariert und kann daher nicht von der Entwickler zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="a9050-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="a9050-105">Wenn Sie die Eigenschaften dieser Steuerelemente zukünftigen Benutzern zur Verfügung stellen möchten, müssen Sie für den Benutzer verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="a9050-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="a9050-106">Eine Eigenschaft eines konstituierenden Steuerelements wird verfügbar gemacht, durch eine Eigenschaft im Benutzersteuerelement erstellen und Verwenden der `get` und `set` Accessoren der Eigenschaft, um die Auswirkungen auf der Änderung in der privaten Eigenschaft des konstituierenden Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="a9050-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>  
  
 <span data-ttu-id="a9050-107">Betrachten Sie ein hypothetisches Benutzersteuerelement mit einer konstituierenden Schaltfläche mit dem Namen `MyButton`.</span><span class="sxs-lookup"><span data-stu-id="a9050-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="a9050-108">In diesem Beispiel, wenn der Benutzer fordert die `ConstituentButtonBackColor` -Eigenschaft, die in gespeicherten Wert der <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft `MyButton` übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="a9050-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="a9050-109">Wenn der Benutzer diese Eigenschaft einen Wert zuweist, wird dieser Wert automatisch zum Übergeben der <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft des `MyButton` und die `set` Code wird ausgeführt, ändern die Farbe des `MyButton`.</span><span class="sxs-lookup"><span data-stu-id="a9050-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>  
  
 <span data-ttu-id="a9050-110">Im folgende Beispiel wird gezeigt, wie verfügbar machen die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft der konstituierenden Schaltfläche:</span><span class="sxs-lookup"><span data-stu-id="a9050-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>  
  
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
  
### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="a9050-111">Eine Eigenschaft eines konstituierenden Steuerelements verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="a9050-111">To expose a property of a constituent control</span></span>  
  
1.  <span data-ttu-id="a9050-112">Erstellen Sie eine öffentliche Eigenschaft für das Benutzersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="a9050-112">Create a public property for your user control.</span></span>  
  
2.  <span data-ttu-id="a9050-113">In der `get` Abschnitt der Eigenschaft, Schreiben Sie Code, der den Wert der Eigenschaft abruft, Sie verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="a9050-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>  
  
3.  <span data-ttu-id="a9050-114">In der `set` Abschnitt der Eigenschaft, Schreiben Sie Code, der den Wert der Eigenschaft an die verfügbar gemachte Eigenschaft des konstituierenden Steuerelements übergibt.</span><span class="sxs-lookup"><span data-stu-id="a9050-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9050-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9050-115">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 [<span data-ttu-id="a9050-116">Eigenschaften in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="a9050-116">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [<span data-ttu-id="a9050-117">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="a9050-117">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
