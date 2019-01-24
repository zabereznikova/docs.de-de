---
title: '&#39;Für jede&#39; auf &#39; &lt;Typename&gt; &#39; ist mehrdeutig, da der Typ mehrere Instanziierungen von implementiert &#39;System.Collections.Generic.IEnumerable (Of T)&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 7fd779ba34afa2a59fa6c42971597df8ce01495a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597345"
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a><span data-ttu-id="e7b24-102">&#39;Für jede&#39; auf &#39; &lt;Typename&gt; &#39; ist mehrdeutig, da der Typ mehrere Instanziierungen von implementiert &#39;System.Collections.Generic.IEnumerable (Of T)&#39;</span><span class="sxs-lookup"><span data-stu-id="e7b24-102">&#39;For Each&#39; on type &#39;&lt;typename&gt;&#39; is ambiguous because the type implements multiple instantiations of &#39;System.Collections.Generic.IEnumerable(Of T)&#39;</span></span>
<span data-ttu-id="e7b24-103">Ein `For Each` -Anweisung gibt eine Iteratorvariable, die mehr als eine <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="e7b24-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="e7b24-104">Die Iteratorvariable muss von einem Typ sein, die implementiert die <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> Schnittstelle in einer der der `Collections` Namespaces und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7b24-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="e7b24-105">Es ist möglich, dass eine Klasse, um mehr als eine konstruierte generische Schnittstelle, über ein anderes Typargument für jeden Erstellung zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="e7b24-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="e7b24-106">Wenn eine Klasse, die ihn durchführt, die für die Iteratorvariable verwendet wird, wird diese Variable hat mehr als ein <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="e7b24-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="e7b24-107">In diesem Fall können Visual Basic die aufzurufende Methode nicht auswählen.</span><span class="sxs-lookup"><span data-stu-id="e7b24-107">In such a case, Visual Basic cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="e7b24-108">**Fehler-ID:** BC32096</span><span class="sxs-lookup"><span data-stu-id="e7b24-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e7b24-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="e7b24-109">To correct this error</span></span>  
  
-   <span data-ttu-id="e7b24-110">Verwenden Sie [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) oder [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) umzuwandelnde den Typ der Iteratorvariablen auf die Schnittstelle zum Definieren der <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e7b24-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7b24-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7b24-111">See also</span></span>
- [<span data-ttu-id="e7b24-112">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e7b24-112">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="e7b24-113">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e7b24-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
