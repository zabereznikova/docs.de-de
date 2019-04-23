---
title: 'Vorgehensweise: Programmgesteuertes Hinzufügen von Elementen zu DomainUpDown-Steuerelementen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: ef44a9e68b8007d57fc7442a178ae98322747c99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343674"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="28317-102">Vorgehensweise: Programmgesteuertes Hinzufügen von Elementen zu DomainUpDown-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="28317-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="28317-103">Sie können Elemente hinzufügen, auf die Windows-Formulare <xref:System.Windows.Forms.DomainUpDown> Steuerelement im Code.</span><span class="sxs-lookup"><span data-stu-id="28317-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="28317-104">Rufen Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> oder <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> Klasse, um die Elemente des Steuerelements hinzufügen <xref:System.Windows.Forms.DomainUpDown.Items%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="28317-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="28317-105">Die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> Methode fügt ein Element am Ende einer Auflistung während der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> Methode fügt ein Element an einer angegebenen Position.</span><span class="sxs-lookup"><span data-stu-id="28317-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="28317-106">Um ein neues Element hinzufügen</span><span class="sxs-lookup"><span data-stu-id="28317-106">To add a new item</span></span>  
  
1. <span data-ttu-id="28317-107">Verwenden der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> Methode, um ein Element am Ende der Liste der Elemente hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="28317-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="28317-108">- oder - </span><span class="sxs-lookup"><span data-stu-id="28317-108">-or-</span></span>  
  
2. <span data-ttu-id="28317-109">Verwenden der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> Methode zum Einfügen eines Elements in der Liste an einer angegebenen Position.</span><span class="sxs-lookup"><span data-stu-id="28317-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="28317-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28317-110">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [<span data-ttu-id="28317-111">DomainUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="28317-111">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="28317-112">Übersicht über das DomainUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="28317-112">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
