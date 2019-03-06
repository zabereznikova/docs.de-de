---
title: 'Vorgehensweise: Bestimmen, ob ein Freezable-Objekt fixiert ist'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 005bb27803830a2e38a7b143d2c4cff669ad1da6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362512"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="91098-102">Vorgehensweise: Bestimmen, ob ein Freezable-Objekt fixiert ist</span><span class="sxs-lookup"><span data-stu-id="91098-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="91098-103">Dieses Beispiel zeigt, wie Sie ermitteln, ob eine <xref:System.Windows.Freezable> Objekt eingefroren ist.</span><span class="sxs-lookup"><span data-stu-id="91098-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="91098-104">Wenn Sie versuchen, ein fixiertes ändern <xref:System.Windows.Freezable> -Objekt löst eine <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="91098-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="91098-105">Verwenden, um zu vermeiden, diese Ausnahme auslöst, die <xref:System.Windows.Freezable.IsFrozen%2A> Eigenschaft der <xref:System.Windows.Freezable> bestimmt, ob er fixiert ist.</span><span class="sxs-lookup"><span data-stu-id="91098-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91098-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91098-106">Example</span></span>  
 <span data-ttu-id="91098-107">Im folgende Beispiel friert ein <xref:System.Windows.Media.SolidColorBrush> und testet dann mithilfe der <xref:System.Windows.Freezable.IsFrozen%2A> Eigenschaft, um zu bestimmen, ob er fixiert ist.</span><span class="sxs-lookup"><span data-stu-id="91098-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="91098-108">Weitere Informationen zu <xref:System.Windows.Freezable> Objekten finden Sie die [Übersicht über Freezable-Objekte](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="91098-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91098-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91098-109">See also</span></span>
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [<span data-ttu-id="91098-110">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="91098-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="91098-111">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="91098-111">How-to Topics</span></span>](base-elements-how-to-topics.md)
