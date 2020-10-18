---
title: "\"For Each\" für den <typename>-Typ ist mehrdeutig, da der Typ mehrere Instanziierungen von System.Collections.Generic.IEnumerable(Of T) implementiert."
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 0f19836efeabcf1d9e5097667c719c1f7d99cbbb
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163466"
---
# <a name="bc32096-for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a><span data-ttu-id="59596-102">BC32096: "for each" für den Typ " \<typename> " ist mehrdeutig, da der Typ mehrere Instanziierungen von "System. Collections. Generic. IEnumerable (of T)" implementiert.</span><span class="sxs-lookup"><span data-stu-id="59596-102">BC32096: 'For Each' on type '\<typename>' is ambiguous because the type implements multiple instantiations of 'System.Collections.Generic.IEnumerable(Of T)'</span></span>

<span data-ttu-id="59596-103">Eine- `For Each` Anweisung gibt eine Iteratorvariable an, die über mehr als eine <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode verfügt.</span><span class="sxs-lookup"><span data-stu-id="59596-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>

 <span data-ttu-id="59596-104">Die Iteratorvariable muss einen Typ aufweisen, der die- <xref:System.Collections.IEnumerable?displayProperty=nameWithType> Schnittstelle oder die- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> Schnittstelle in einem der `Collections` Namespaces des .NET Framework implementiert.</span><span class="sxs-lookup"><span data-stu-id="59596-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the .NET Framework.</span></span> <span data-ttu-id="59596-105">Es ist möglich, dass eine Klasse mehr als eine konstruierte generische Schnittstelle implementiert, wobei für jede Konstruktion ein anderes Typargument verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="59596-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="59596-106">Wenn eine Klasse, die diese verwendet, für die Iteratorvariable verwendet wird, hat diese Variable mehr als eine <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="59596-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="59596-107">In einem solchen Fall können Visual Basic nicht auswählen, welche Methode aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="59596-107">In such a case, Visual Basic cannot choose which method to call.</span></span>

 <span data-ttu-id="59596-108">**Fehler-ID:** BC32096</span><span class="sxs-lookup"><span data-stu-id="59596-108">**Error ID:** BC32096</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="59596-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="59596-109">To correct this error</span></span>

- <span data-ttu-id="59596-110">Verwenden Sie den [DirectCast-Operator](../operators/directcast-operator.md) oder den [TryCast-Operator](../operators/trycast-operator.md) , um den iteratorvariablentyp in die-Schnittstelle umzuwandeln, die die <xref:System.Collections.IEnumerable.GetEnumerator%2A> gewünschte Methode definiert.</span><span class="sxs-lookup"><span data-stu-id="59596-110">Use [DirectCast Operator](../operators/directcast-operator.md) or [TryCast Operator](../operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>

## <a name="see-also"></a><span data-ttu-id="59596-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59596-111">See also</span></span>

- [<span data-ttu-id="59596-112">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59596-112">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="59596-113">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="59596-113">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
