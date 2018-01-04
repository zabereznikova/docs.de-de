---
title: "Gewusst wie: Auswählen eines Elements im ListView-Steuerelement in Windows Forms"
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
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef672dc909717ba979d81bd98510dad6419583a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="910d1-102">Gewusst wie: Auswählen eines Elements im ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="910d1-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="910d1-103">In diesem Beispiel wird veranschaulicht, wie ein Element in einer Windows Forms programmgesteuert ausgewählt <xref:System.Windows.Forms.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="910d1-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="910d1-104">Auswählen eines Elements programmgesteuert automatisch ändert nicht den Fokus an das <xref:System.Windows.Forms.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="910d1-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="910d1-105">Aus diesem Grund werden Sie in der Regel auch das Element festlegen möchten, wie sich der Fokus beim Auswählen eines Elements.</span><span class="sxs-lookup"><span data-stu-id="910d1-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="910d1-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="910d1-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="910d1-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="910d1-107">Compiling the Code</span></span>  
 <span data-ttu-id="910d1-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="910d1-108">This example requires:</span></span>  
  
-   <span data-ttu-id="910d1-109">Ein <xref:System.Windows.Forms.ListView> Steuerelement namens `listView1` , die mindestens ein Element enthält.</span><span class="sxs-lookup"><span data-stu-id="910d1-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
-   <span data-ttu-id="910d1-110">Verweise auf die Namespaces <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="910d1-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="910d1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="910d1-111">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
