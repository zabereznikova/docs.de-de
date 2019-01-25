---
title: 'Vorgehensweise: Erstellen einer überschreibbaren Kopie eines schreibgeschützten Freezable-Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 2853b1e02e1223cbb2b6dff4acbddb0a41d882cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629955"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="dbd29-102">Vorgehensweise: Erstellen einer überschreibbaren Kopie eines schreibgeschützten Freezable-Objekts</span><span class="sxs-lookup"><span data-stu-id="dbd29-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="dbd29-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Freezable.Clone%2A> Methode zum Erstellen einer überschreibbaren Kopie eine schreibgeschützte <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="dbd29-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="dbd29-104">Nach einem <xref:System.Windows.Freezable> Objekt markiert ist als schreibgeschützt ("eingefroren"), nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="dbd29-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="dbd29-105">Sie können jedoch die <xref:System.Windows.Freezable.Clone%2A> Methode, um einen änderbaren Klon des fixierten Objekts zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dbd29-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbd29-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dbd29-106">Example</span></span>  
 <span data-ttu-id="dbd29-107">Das folgende Beispiel erstellt einen änderbaren Klon eines fixierten <xref:System.Windows.Media.SolidColorBrush> Objekt.</span><span class="sxs-lookup"><span data-stu-id="dbd29-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="dbd29-108">Weitere Informationen zu <xref:System.Windows.Freezable> Objekten finden Sie die [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dbd29-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd29-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbd29-109">See also</span></span>
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [<span data-ttu-id="dbd29-110">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="dbd29-110">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [<span data-ttu-id="dbd29-111">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="dbd29-111">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
