---
title: 'Gewusst wie: Auswählen eines Elements im ListView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
ms.openlocfilehash: 8256eaeddf98c5a0dd80357bcd562e8f66db85b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532820"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="e9680-102">Gewusst wie: Auswählen eines Elements im ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e9680-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="e9680-103">In diesem Beispiel wird veranschaulicht, wie ein Element in einer Windows Forms programmgesteuert ausgewählt <xref:System.Windows.Forms.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e9680-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="e9680-104">Auswählen eines Elements programmgesteuert automatisch ändert nicht den Fokus an das <xref:System.Windows.Forms.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e9680-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="e9680-105">Aus diesem Grund werden Sie in der Regel auch das Element festlegen möchten, wie sich der Fokus beim Auswählen eines Elements.</span><span class="sxs-lookup"><span data-stu-id="e9680-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9680-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9680-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e9680-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e9680-107">Compiling the Code</span></span>  
 <span data-ttu-id="e9680-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e9680-108">This example requires:</span></span>  
  
-   <span data-ttu-id="e9680-109">Ein <xref:System.Windows.Forms.ListView> Steuerelement namens `listView1` , die mindestens ein Element enthält.</span><span class="sxs-lookup"><span data-stu-id="e9680-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
-   <span data-ttu-id="e9680-110">Verweise auf die Namespaces <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e9680-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9680-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9680-111">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
