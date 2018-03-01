---
title: "&#39; Für jede &#39; auf Typ &#39; &lt;Typename&gt;&#39; ist mehrdeutig, da der Typ mehrere Instanziierungen von &#39; implementiert. System.Collections.Generic.IEnumerable (Of T) &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a74178f3f0b2e7589b87046973473582993f3ed9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a><span data-ttu-id="f88de-102">&#39; Für jede &#39; auf Typ &#39; &lt;Typename&gt;&#39; ist mehrdeutig, da der Typ mehrere Instanziierungen von &#39; implementiert. System.Collections.Generic.IEnumerable (Of T) &#39;</span><span class="sxs-lookup"><span data-stu-id="f88de-102">&#39;For Each&#39; on type &#39;&lt;typename&gt;&#39; is ambiguous because the type implements multiple instantiations of &#39;System.Collections.Generic.IEnumerable(Of T)&#39;</span></span>
<span data-ttu-id="f88de-103">Ein `For Each` -Anweisung gibt eine Iteratorvariable, die weist mehr als eine <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="f88de-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="f88de-104">Die Iteratorvariable muss ein Typ, implementiert der <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> Schnittstelle in einer der der `Collections` Namespaces und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f88de-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="f88de-105">Es ist möglich, dass eine Klasse, um ein anderes Typargument für jeden Konstruktion mit mehr als eine konstruierte generische-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="f88de-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="f88de-106">Wenn eine Klasse, die dies tut, für die Iteratorvariable verwendet wird, wird diese Variable hat mehr als ein <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="f88de-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="f88de-107">In einem solchen Fall [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] können nicht auswählen, welche Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f88de-107">In such a case, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="f88de-108">**Fehler-ID:** BC32096</span><span class="sxs-lookup"><span data-stu-id="f88de-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f88de-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f88de-109">To correct this error</span></span>  
  
-   <span data-ttu-id="f88de-110">Verwenden Sie [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) oder [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) umwandeln den Iterator Variablentyp auf die Schnittstelle zum Definieren der <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f88de-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f88de-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f88de-111">See Also</span></span>  
 [<span data-ttu-id="f88de-112">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f88de-112">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="f88de-113">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f88de-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
