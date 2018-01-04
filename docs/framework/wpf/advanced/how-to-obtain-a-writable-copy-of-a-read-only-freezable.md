---
title: "Gewusst wie: Erstellen einer überschreibbaren Kopie eines schreibgeschützten Freezable-Objekts"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9fe22e49ee28de60bc76d7a4f543462bbcfac48c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="2e8dd-102">Gewusst wie: Erstellen einer überschreibbaren Kopie eines schreibgeschützten Freezable-Objekts</span><span class="sxs-lookup"><span data-stu-id="2e8dd-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="2e8dd-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.Freezable.Clone%2A> Methode, um eine schreibbare Kopie ein schreibgeschütztes erstellen <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="2e8dd-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="2e8dd-104">Nach einem <xref:System.Windows.Freezable> Objekts gekennzeichnet ist als schreibgeschützt ("eingefroren"), nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="2e8dd-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="2e8dd-105">Sie können jedoch die <xref:System.Windows.Freezable.Clone%2A> Methode, um einen änderbaren Klon des fixierten Objekts erstellen.</span><span class="sxs-lookup"><span data-stu-id="2e8dd-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e8dd-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e8dd-106">Example</span></span>  
 <span data-ttu-id="2e8dd-107">Das folgende Beispiel erstellt einen änderbaren Klon des ein fixierter <xref:System.Windows.Media.SolidColorBrush> Objekt.</span><span class="sxs-lookup"><span data-stu-id="2e8dd-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="2e8dd-108">Weitere Informationen zu <xref:System.Windows.Freezable> anzuzeigen, die [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2e8dd-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e8dd-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e8dd-109">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CloneCurrentValue%2A>  
 [<span data-ttu-id="2e8dd-110">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="2e8dd-110">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="2e8dd-111">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="2e8dd-111">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
