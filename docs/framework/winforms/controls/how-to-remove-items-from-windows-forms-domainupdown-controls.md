---
title: 'Vorgehensweise: Entfernen von Elementen aus DomainUpDown-Steuerelementen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: 0c07365f5be2e419b4049a466949fed2d884d897
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131403"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="dd594-102">Vorgehensweise: Entfernen von Elementen aus DomainUpDown-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd594-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="dd594-103">Entfernen von Elementen aus den Windows-Formularen <xref:System.Windows.Forms.DomainUpDown> Steuerelement durch Aufrufen der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> oder <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="dd594-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="dd594-104">Die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> -Methode entfernt ein bestimmtes Element, während die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> Methode entfernt ein Element anhand seiner Position.</span><span class="sxs-lookup"><span data-stu-id="dd594-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="dd594-105">So entfernen Sie ein Element</span><span class="sxs-lookup"><span data-stu-id="dd594-105">To remove an item</span></span>  
  
-   <span data-ttu-id="dd594-106">Verwenden der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> Klasse, um ein Element anhand des Namens zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="dd594-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="dd594-107">- oder - </span><span class="sxs-lookup"><span data-stu-id="dd594-107">-or-</span></span>  
  
-   <span data-ttu-id="dd594-108">Verwenden der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> Methode, um ein Element anhand seiner Position zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="dd594-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dd594-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd594-109">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [<span data-ttu-id="dd594-110">DomainUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dd594-110">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="dd594-111">Übersicht über das DomainUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dd594-111">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
