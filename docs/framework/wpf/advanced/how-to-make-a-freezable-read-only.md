---
title: 'Vorgehensweise: Erstellen eines schreibgeschützten Freezable-Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 9b7102db4de0df7183355e50e3b372eac30d81b3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191438"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="273b5-102">Vorgehensweise: Erstellen eines schreibgeschützten Freezable-Objekts</span><span class="sxs-lookup"><span data-stu-id="273b5-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="273b5-103">Dieses Beispiel zeigt, wie Sie eine <xref:System.Windows.Freezable> schreibgeschützte durch Aufrufen der <xref:System.Windows.Freezable.Freeze%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="273b5-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="273b5-104">Sie können nicht eingefroren werden eine <xref:System.Windows.Freezable> Objekt, wenn eine der folgenden Bedingungen ist `true` über das Objekt:</span><span class="sxs-lookup"><span data-stu-id="273b5-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
-   <span data-ttu-id="273b5-105">Es verfügt über animierte oder datengebundene Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="273b5-105">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="273b5-106">Es verfügt über Eigenschaften, die von einer dynamischen Ressource festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="273b5-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="273b5-107">Weitere Informationen zu dynamischen Ressourcen finden Sie unter den [XAML-Ressourcen](xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="273b5-107">For more information about dynamic resources, see the [XAML Resources](xaml-resources.md).</span></span>  
  
-   <span data-ttu-id="273b5-108">Es enthält <xref:System.Windows.Freezable> untergeordnete Objekte, die nicht fixiert werden können.</span><span class="sxs-lookup"><span data-stu-id="273b5-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="273b5-109">Wenn diese Bedingungen sind `false` für Ihre <xref:System.Windows.Freezable> -Objekt, und Sie beabsichtigen nicht, es ändern möchten, sollten das fixieren, um Leistungsvorteile zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="273b5-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="273b5-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="273b5-110">Example</span></span>  
 <span data-ttu-id="273b5-111">Im folgende Beispiel friert ein <xref:System.Windows.Media.SolidColorBrush>, ist ein Typ, der <xref:System.Windows.Freezable> Objekt.</span><span class="sxs-lookup"><span data-stu-id="273b5-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="273b5-112">Weitere Informationen zu <xref:System.Windows.Freezable> Objekten finden Sie die [Übersicht über Freezable-Objekte](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="273b5-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="273b5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="273b5-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="273b5-114">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="273b5-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="273b5-115">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="273b5-115">How-to Topics</span></span>](base-elements-how-to-topics.md)
