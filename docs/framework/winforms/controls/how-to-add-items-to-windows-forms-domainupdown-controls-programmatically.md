---
title: Programmgesteuertes Hinzufügen von Elementen zu DomainUpDown-Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 2e9f51fa051bf9b62e95f289db97bffd83450036
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745580"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="d778d-102">Gewusst wie: Programmgesteuertes Hinzufügen von Elementen zu DomainUpDown-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d778d-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="d778d-103">Sie können der Windows Forms <xref:System.Windows.Forms.DomainUpDown>-Steuerelement im Code Elemente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d778d-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="d778d-104">Ruft die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>-oder <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>-Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>-Klasse auf, um der <xref:System.Windows.Forms.DomainUpDown.Items%2A> Eigenschaft des Steuer Elements Elemente hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d778d-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="d778d-105">Die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>-Methode fügt ein Element am Ende einer Auflistung hinzu, während die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>-Methode ein Element an einer angegebenen Position hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="d778d-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="d778d-106">So fügen Sie ein neues Element hinzu</span><span class="sxs-lookup"><span data-stu-id="d778d-106">To add a new item</span></span>  
  
1. <span data-ttu-id="d778d-107">Verwenden Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>-Methode, um am Ende der Liste der Elemente ein Element hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d778d-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="d778d-108">Oder</span><span class="sxs-lookup"><span data-stu-id="d778d-108">-or-</span></span>  
  
2. <span data-ttu-id="d778d-109">Verwenden Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>-Methode, um ein Element an einer bestimmten Position in die Liste einzufügen.</span><span class="sxs-lookup"><span data-stu-id="d778d-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d778d-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d778d-110">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d778d-111">DomainUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d778d-111">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="d778d-112">Übersicht über das DomainUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d778d-112">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
