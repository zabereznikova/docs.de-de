---
title: 'Gewusst wie: Bestimmen, ob ein Freezable-Objekt fixiert ist'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: f6d20025d59a702357b12da9f5dc0f5887968143
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542752"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="f7be4-102">Gewusst wie: Bestimmen, ob ein Freezable-Objekt fixiert ist</span><span class="sxs-lookup"><span data-stu-id="f7be4-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="f7be4-103">Dieses Beispiel zeigt, wie Sie ermitteln, ob ein <xref:System.Windows.Freezable> Objekt eingefroren ist.</span><span class="sxs-lookup"><span data-stu-id="f7be4-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="f7be4-104">Wenn Sie versuchen, ein fixierter ändern <xref:System.Windows.Freezable> -Objekt löst eine <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="f7be4-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="f7be4-105">Verwenden, um zu vermeiden, dass diese Ausnahme ausgelöst, die <xref:System.Windows.Freezable.IsFrozen%2A> Eigenschaft von der <xref:System.Windows.Freezable> bestimmt, ob es eingefroren wurde.</span><span class="sxs-lookup"><span data-stu-id="f7be4-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7be4-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7be4-106">Example</span></span>  
 <span data-ttu-id="f7be4-107">Im folgende Beispiel werden eingefroren eine <xref:System.Windows.Media.SolidColorBrush> und testet dann mithilfe der <xref:System.Windows.Freezable.IsFrozen%2A> Eigenschaft, um zu bestimmen, ob es eingefroren wurde.</span><span class="sxs-lookup"><span data-stu-id="f7be4-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="f7be4-108">Weitere Informationen zu <xref:System.Windows.Freezable> anzuzeigen, die [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f7be4-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7be4-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7be4-109">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.IsFrozen%2A>  
 [<span data-ttu-id="f7be4-110">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="f7be4-110">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="f7be4-111">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="f7be4-111">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
