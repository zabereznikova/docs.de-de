---
title: 'Vorgehensweise: Auswählen eines Elements im ListView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 41a30ba6c242d0587e98b458e41ca213e8885bca
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638203"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="43c22-102">Vorgehensweise: Auswählen eines Elements im ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="43c22-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="43c22-103">In diesem Beispiel wird veranschaulicht, wie ein Element in einem Windows Forms programmgesteuert ausgewählt <xref:System.Windows.Forms.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="43c22-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="43c22-104">Ein Element programmgesteuert ausgewählt automatisch ändert nicht den Fokus an das <xref:System.Windows.Forms.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="43c22-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="43c22-105">Aus diesem Grund werden Sie in der Regel auch das Element festlegen möchten, wie mit Fokus, wenn Sie ein Element auswählen.</span><span class="sxs-lookup"><span data-stu-id="43c22-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43c22-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43c22-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="43c22-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="43c22-107">Compiling the Code</span></span>  
 <span data-ttu-id="43c22-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="43c22-108">This example requires:</span></span>  
  
- <span data-ttu-id="43c22-109">Ein <xref:System.Windows.Forms.ListView> Steuerelement mit dem Namen `listView1` , die mindestens ein Element enthält.</span><span class="sxs-lookup"><span data-stu-id="43c22-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
- <span data-ttu-id="43c22-110">Verweise auf die Namespaces <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="43c22-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c22-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43c22-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
