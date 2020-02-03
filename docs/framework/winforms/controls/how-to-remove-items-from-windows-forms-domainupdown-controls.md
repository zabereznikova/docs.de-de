---
title: Entfernen von Elementen aus DomainUpDown-Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: e52af5c5add4fda93e2b51c8afdb90c92e8d2f62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735769"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="1ddc6-102">Gewusst wie: Entfernen von Elementen aus DomainUpDown-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1ddc6-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="1ddc6-103">Sie können Elemente aus der Windows Forms <xref:System.Windows.Forms.DomainUpDown>-Steuerelement entfernen, indem Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>-oder <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>-Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>-Klasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1ddc6-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="1ddc6-104">Die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>-Methode entfernt ein bestimmtes Element, während die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>-Methode ein Element nach seiner Position entfernt.</span><span class="sxs-lookup"><span data-stu-id="1ddc6-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="1ddc6-105">So entfernen Sie ein Element</span><span class="sxs-lookup"><span data-stu-id="1ddc6-105">To remove an item</span></span>  
  
- <span data-ttu-id="1ddc6-106">Verwenden Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>-Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>-Klasse, um ein Element anhand des Namens zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="1ddc6-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="1ddc6-107">Oder</span><span class="sxs-lookup"><span data-stu-id="1ddc6-107">-or-</span></span>  
  
- <span data-ttu-id="1ddc6-108">Verwenden Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>-Methode, um ein Element nach seiner Position zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="1ddc6-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1ddc6-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ddc6-109">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1ddc6-110">DomainUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1ddc6-110">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="1ddc6-111">Übersicht über das DomainUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1ddc6-111">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
