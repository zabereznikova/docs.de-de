---
title: Vergleiche und Sortierungen innerhalb von Sammlungen
ms.date: 04/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data, collections
- IComparable.CompareTo method
- Collections classes
- Equals method
- collections [.NET Framework], comparisons
ms.assetid: 5e4d3b45-97f0-423c-a65f-c492ed40e73b
ms.openlocfilehash: cb9dd3e8af570251b8bcd2e450e686ad69ab78c4
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287977"
---
# <a name="comparisons-and-sorts-within-collections"></a><span data-ttu-id="a3086-102">Vergleiche und Sortierungen innerhalb von Auflistungen</span><span class="sxs-lookup"><span data-stu-id="a3086-102">Comparisons and sorts within collections</span></span>

<span data-ttu-id="a3086-103">Die <xref:System.Collections>-Klassen führen bei nahezu allen Vorgängen zur Verwaltung von Auflistungen Vergleiche durch, sei es bei der Suche nach zu entfernenden Elementen oder bei der Rückgabe eines Schlüssel-Wert-Paars.</span><span class="sxs-lookup"><span data-stu-id="a3086-103">The <xref:System.Collections> classes perform comparisons in almost all the processes involved in managing collections, whether searching for the element to remove or returning the value of a key-and-value pair.</span></span>

<span data-ttu-id="a3086-104">Auflistungen verwenden in der Regel einen Gleichheitsvergleich und/oder einen Reihenfolgenvergleich.</span><span class="sxs-lookup"><span data-stu-id="a3086-104">Collections typically utilize an equality comparer and/or an ordering comparer.</span></span> <span data-ttu-id="a3086-105">Für Vergleiche werden zwei Konstrukte verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3086-105">Two constructs are used for comparisons.</span></span>

<a name="BKMK_Checkingforequality"></a>
## <a name="check-for-equality"></a><span data-ttu-id="a3086-106">Durchführen von Gleichheitsüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="a3086-106">Check for equality</span></span>

<span data-ttu-id="a3086-107">Methoden wie `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>und `Remove` verwenden einen Gleichheitsvergleich für die Elemente der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="a3086-107">Methods such as `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>, and `Remove` use an equality comparer for the collection elements.</span></span> <span data-ttu-id="a3086-108">Wenn die Sammlung generisch ist, werden die Elemente anhand der folgenden Richtlinien auf Gleichheit verglichen:</span><span class="sxs-lookup"><span data-stu-id="a3086-108">If the collection is generic, then items are compared for equality according to the following guidelines:</span></span>

- <span data-ttu-id="a3086-109">Wenn Typ T die generische Schnittstelle <xref:System.IEquatable%601> implementiert, dann ist der Gleichheitsvergleich die <xref:System.IEquatable%601.Equals%2A> -Methode dieser Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a3086-109">If type T implements the <xref:System.IEquatable%601> generic interface, then the equality comparer is the <xref:System.IEquatable%601.Equals%2A> method of that interface.</span></span>

- <span data-ttu-id="a3086-110">Wenn der Typ T <xref:System.IEquatable%601>nicht implementiert, wird <xref:System.Object.Equals%2A?displayProperty=nameWithType> verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3086-110">If type T does not implement <xref:System.IEquatable%601>, <xref:System.Object.Equals%2A?displayProperty=nameWithType> is used.</span></span>

<span data-ttu-id="a3086-111">Darüber hinaus akzeptieren einige Konstruktorüberladungen für Wörterbuchauflistungen eine <xref:System.Collections.Generic.IEqualityComparer%601> -Implementierung, die zum Vergleichen von Schlüsseln auf Gleichheit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a3086-111">In addition, some constructor overloads for dictionary collections accept an <xref:System.Collections.Generic.IEqualityComparer%601> implementation, which is used to compare keys for equality.</span></span> <span data-ttu-id="a3086-112">Ein Beispiel dafür finden Sie unter <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A> -Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="a3086-112">For an example, see the <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A> constructor.</span></span>

<a name="BKMK_Determiningsortorder"></a>
## <a name="determine-sort-order"></a><span data-ttu-id="a3086-113">Festlegen der Sortierreihenfolge</span><span class="sxs-lookup"><span data-stu-id="a3086-113">Determine sort order</span></span>

<span data-ttu-id="a3086-114">Methoden, wie `BinarySearch` und `Sort` , verwenden einen Reihenfolgenvergleich für Elemente der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="a3086-114">Methods such as `BinarySearch` and `Sort` use an ordering comparer for the collection elements.</span></span> <span data-ttu-id="a3086-115">Die Vergleiche können zwischen Elementen in der Auflistung oder zwischen einem Element und einem angegebenen Wert durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a3086-115">The comparisons can be between elements of the collection, or between an element and a specified value.</span></span> <span data-ttu-id="a3086-116">Für den Vergleich von Objekten gibt es die Konzepte `default comparer` und `explicit comparer`.</span><span class="sxs-lookup"><span data-stu-id="a3086-116">For comparing objects, there is the concept of a `default comparer` and an `explicit comparer`.</span></span>

<span data-ttu-id="a3086-117">Der Standardvergleich beruht auf dem Vergleich von mindestens einem Objekt, um die **IComparable** -Schnittstelle zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="a3086-117">The default comparer relies on at least one of the objects being compared to implement the **IComparable** interface.</span></span> <span data-ttu-id="a3086-118">Es ist empfehlenswert, **IComparable** in allen Klassen zu implementieren, die als Werte in einer Listenauflistung oder als Schlüssel in einer Wörterbuchauflistung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3086-118">It is a good practice to implement **IComparable** on all classes are used as values in a list collection or as keys in a dictionary collection.</span></span> <span data-ttu-id="a3086-119">Bei einer generischen Auflistung wird der Gleichheitsvergleich gemäß dem Folgenden bestimmt:</span><span class="sxs-lookup"><span data-stu-id="a3086-119">For a generic collection, equality comparison is determined according to the following:</span></span>

- <span data-ttu-id="a3086-120">Wenn Typ T die generische Schnittstelle <xref:System.IComparable%601?displayProperty=nameWithType> implementiert, dann ist der Standardvergleich die <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> -Methode dieser Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a3086-120">If type T implements the <xref:System.IComparable%601?displayProperty=nameWithType> generic interface, then the default comparer is the <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> method of that interface</span></span>

- <span data-ttu-id="a3086-121">Wenn Typ T die nicht generische Schnittstelle <xref:System.IComparable?displayProperty=nameWithType> implementiert, dann ist der Standardvergleich die <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> -Methode dieser Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a3086-121">If type T implements the non-generic <xref:System.IComparable?displayProperty=nameWithType> interface, then the default comparer is the <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> method of that interface.</span></span>

- <span data-ttu-id="a3086-122">Wenn Typ T keine der Schnittstellen implementiert, gibt es keinen Standardvergleich, und ein Vergleich oder ein Vergleichsdelegat muss explizit angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a3086-122">If type T doesn't implement either interface, then there is no default comparer, and a comparer or comparison delegate must be provided explicitly.</span></span>

<span data-ttu-id="a3086-123">Um explizite Vergleiche zu ermöglichen, akzeptieren einige Methoden eine **IComparer** -Implementierung als Parameter.</span><span class="sxs-lookup"><span data-stu-id="a3086-123">To provide explicit comparisons, some methods accept an **IComparer** implementation as a parameter.</span></span> <span data-ttu-id="a3086-124">Beispiel: Die <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> -Methode akzeptiert eine <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> -Implementierung.</span><span class="sxs-lookup"><span data-stu-id="a3086-124">For example, the <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> method accepts an <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> implementation.</span></span>

<span data-ttu-id="a3086-125">Die aktuelle Kultureinstellung des Systems kann sich auf die Vergleichs- und Sortiervorgänge innerhalb einer Auflistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="a3086-125">The current culture setting of the system can affect the comparisons and sorts within a collection.</span></span> <span data-ttu-id="a3086-126">Standardmäßig sind die Vergleichs- und Sortiervorgänge in den **Auflistungen** -Klassen kulturabhängig.</span><span class="sxs-lookup"><span data-stu-id="a3086-126">By default, the comparisons and sorts in the **Collections** classes are culture-sensitive.</span></span> <span data-ttu-id="a3086-127">Um die Kultureinstellung zu ignorieren und daher konsistente Vergleichs- und Sortierergebnisse zu erhalten, verwenden Sie <xref:System.Globalization.CultureInfo.InvariantCulture%2A> mit Memberüberladungen, die <xref:System.Globalization.CultureInfo>akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="a3086-127">To ignore the culture setting and therefore obtain consistent comparison and sorting results, use the <xref:System.Globalization.CultureInfo.InvariantCulture%2A> with member overloads that accept a <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="a3086-128">Weitere Informationen finden Sie unter [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Auflistungen](../globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) und [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Arrays](../globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="a3086-128">For more information, see [Performing Culture-Insensitive String Operations in Collections](../globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) and [Performing Culture-Insensitive String Operations in Arrays](../globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).</span></span>

<a name="BKMK_Equalityandsortexample"></a>
## <a name="equality-and-sort-example"></a><span data-ttu-id="a3086-129">Beispiel für Gleichheit und Sortierung</span><span class="sxs-lookup"><span data-stu-id="a3086-129">Equality and sort example</span></span>

<span data-ttu-id="a3086-130">Der folgende Code zeigt eine Implementierung von <xref:System.IEquatable%601> und <xref:System.IComparable%601> für ein einfaches Geschäftsobjekt.</span><span class="sxs-lookup"><span data-stu-id="a3086-130">The following code demonstrates an implementation of <xref:System.IEquatable%601> and <xref:System.IComparable%601> on a simple business object.</span></span> <span data-ttu-id="a3086-131">Wenn das Objekt in einer Liste gespeichert und sortiert wird, sehen Sie darüber hinaus, dass durch den Aufruf der <xref:System.Collections.Generic.List%601.Sort>-Methode der Standardvergleich für den `Part`-Typ verwendet wird und die <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29>-Methode mit einer anonymen Methode implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="a3086-131">In addition, when the object is stored in a list and sorted, you will see that calling the <xref:System.Collections.Generic.List%601.Sort> method results in the use of the default comparer for the `Part` type, and the <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> method implemented by using an anonymous method.</span></span>

[!code-csharp[System.Collections.Generic.List.Sort#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.collections.generic.list.sort/cs/program.cs#1)]
[!code-vb[System.Collections.Generic.List.Sort#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.collections.generic.list.sort/vb/module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="a3086-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3086-132">See also</span></span>

- <xref:System.Collections.IComparer>
- <xref:System.IEquatable%601>
- <xref:System.Collections.Generic.IComparer%601>
- <xref:System.IComparable>
- <xref:System.IComparable%601>
