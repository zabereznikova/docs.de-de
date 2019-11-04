---
title: 'Gewusst wie: Erstellen eines schreibgeschützten Freezable-Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 4185966d864be425bc631953461f6f27ab983bee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460068"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="e7753-102">Gewusst wie: Erstellen eines schreibgeschützten Freezable-Objekts</span><span class="sxs-lookup"><span data-stu-id="e7753-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="e7753-103">In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Freezable> schreibgeschützt wird, indem seine <xref:System.Windows.Freezable.Freeze%2A>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e7753-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="e7753-104">Sie können ein <xref:System.Windows.Freezable> Objekt nicht fixieren, wenn eine der folgenden Bedingungen für das Objekt `true` ist:</span><span class="sxs-lookup"><span data-stu-id="e7753-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
- <span data-ttu-id="e7753-105">Sie verfügt über animierte oder Daten gebundene Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e7753-105">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="e7753-106">Sie verfügt über Eigenschaften, die durch eine dynamische Ressource festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e7753-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="e7753-107">Weitere Informationen zu dynamischen Ressourcen finden Sie in den [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="e7753-107">For more information about dynamic resources, see the [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>  
  
- <span data-ttu-id="e7753-108">Sie enthält <xref:System.Windows.Freezable> unter Objekte, die nicht eingefroren werden können.</span><span class="sxs-lookup"><span data-stu-id="e7753-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="e7753-109">Wenn diese Bedingungen für das <xref:System.Windows.Freezable> Objekt `false` werden und Sie es nicht ändern möchten, sollten Sie es in Erwägung nehmen, es zu erwerben, um Leistungsvorteile zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="e7753-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7753-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7753-110">Example</span></span>  
 <span data-ttu-id="e7753-111">Im folgenden Beispiel wird ein-<xref:System.Windows.Media.SolidColorBrush>, bei dem es sich um einen Typ von <xref:System.Windows.Freezable>-Objekt handelt, eingefroren.</span><span class="sxs-lookup"><span data-stu-id="e7753-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="e7753-112">Weitere Informationen zu <xref:System.Windows.Freezable> Objekten finden Sie in der [Übersicht](freezable-objects-overview.md)über frei wählbare Objekte.</span><span class="sxs-lookup"><span data-stu-id="e7753-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7753-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7753-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="e7753-114">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="e7753-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="e7753-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="e7753-115">How-to Topics</span></span>](base-elements-how-to-topics.md)
