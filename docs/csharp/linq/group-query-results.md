---
title: Gruppieren von Abfrageergebnissen
description: So gruppieren Sie Ergebnisse.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2e4ec27f-06fb-4de7-8973-0189906d4520
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1c1639651699afbe5fb768db26b98a9b2d734315
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="group-query-results"></a><span data-ttu-id="b03a9-104">Gruppieren von Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="b03a9-104">Group query results</span></span>

<span data-ttu-id="b03a9-105">Das Gruppieren ist eine der leistungsstärksten Funktionen von LINQ.</span><span class="sxs-lookup"><span data-stu-id="b03a9-105">Grouping is one of the most powerful capabilities of LINQ.</span></span> <span data-ttu-id="b03a9-106">Die folgenden Beispiele zeigen Ihnen, wie Sie Daten auf verschiedene Arten und Weisen gruppieren:</span><span class="sxs-lookup"><span data-stu-id="b03a9-106">The following examples show how to group data in various ways:</span></span>  
  
-   <span data-ttu-id="b03a9-107">Nach einer einzelnen Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b03a9-107">By a single property.</span></span>  
  
-   <span data-ttu-id="b03a9-108">Nach dem ersten Buchstaben einer Zeichenfolgeneigenschaft</span><span class="sxs-lookup"><span data-stu-id="b03a9-108">By the first letter of a string property.</span></span>  
  
-   <span data-ttu-id="b03a9-109">Nach einem berechneten numerischen Bereich</span><span class="sxs-lookup"><span data-stu-id="b03a9-109">By a computed numeric range.</span></span>  
  
-   <span data-ttu-id="b03a9-110">Nach einem booleschen Prädikat oder einem anderer Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b03a9-110">By Boolean predicate or other expression.</span></span>  
  
-   <span data-ttu-id="b03a9-111">Nach einem Verbundschlüssel</span><span class="sxs-lookup"><span data-stu-id="b03a9-111">By a compound key.</span></span>  
  
 <span data-ttu-id="b03a9-112">Darüber hinaus projizieren die letzten beiden Abfragen die Ergebnisse in einen neuen anonymen Typ, der nur die Vor- und Nachnamen der Studenten enthält.</span><span class="sxs-lookup"><span data-stu-id="b03a9-112">In addition, the last two queries project their results into a new anonymous type that contains only the student's first and last name.</span></span> <span data-ttu-id="b03a9-113">Weitere Informationen finden Sie unter [group-Klausel](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b03a9-113">For more information, see the [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b03a9-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b03a9-114">Example</span></span>  
 <span data-ttu-id="b03a9-115">Alle Beispiele in diesem Thema verwenden die folgenden Hilfsklassen und Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="b03a9-115">All the examples in this topic use the following helper classes and data sources.</span></span>  
  
 <span data-ttu-id="b03a9-116">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b03a9-116">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b03a9-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b03a9-117">Example</span></span>  
 <span data-ttu-id="b03a9-118">Das folgende Beispiel veranschaulicht die Gruppierung von Quellelementen mithilfe einer einzelnen Eigenschaft des Elements als Gruppenschlüssel.</span><span class="sxs-lookup"><span data-stu-id="b03a9-118">The following example shows how to group source elements by using a single property of the element as the group key.</span></span> <span data-ttu-id="b03a9-119">In diesem Fall ist der Schlüssel ein `string`, der Nachname des Studenten.</span><span class="sxs-lookup"><span data-stu-id="b03a9-119">In this case the key is a `string`, the student's last name.</span></span> <span data-ttu-id="b03a9-120">Es ist auch möglich, eine Teilzeichenfolge als Schlüssel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b03a9-120">It is also possible to use a substring for the key.</span></span> <span data-ttu-id="b03a9-121">Bei der Gruppierungsoperation wird der als Standard für diesen Typ festgelegte Gleichheitsvergleich verwendet.</span><span class="sxs-lookup"><span data-stu-id="b03a9-121">The grouping operation uses the default equality comparer for the type.</span></span>  
  
 <span data-ttu-id="b03a9-122">Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="b03a9-122">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="b03a9-123">Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupBySingleProperty()`.</span><span class="sxs-lookup"><span data-stu-id="b03a9-123">Change the calling statement in the `Main` method to `sc.GroupBySingleProperty()`.</span></span>  
  
 <span data-ttu-id="b03a9-124">[!code-cs[csProgGuideLINQ#17](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b03a9-124">[!code-cs[csProgGuideLINQ#17](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b03a9-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b03a9-125">Example</span></span>  
 <span data-ttu-id="b03a9-126">Das folgende Beispiel veranschaulicht die Gruppierung von Quellelemente ohne eine Objekteigenschaft als Gruppenschlüssel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b03a9-126">The following example shows how to group source elements by using something other than a property of the object for the group key.</span></span> <span data-ttu-id="b03a9-127">In diesem Beispiel ist der Schlüssel der erste Buchstabe des Nachnamens des Studenten.</span><span class="sxs-lookup"><span data-stu-id="b03a9-127">In this example, the key is the first letter of the student's last name.</span></span>  
  
 <span data-ttu-id="b03a9-128">Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="b03a9-128">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="b03a9-129">Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupBySubstring()`.</span><span class="sxs-lookup"><span data-stu-id="b03a9-129">Change the calling statement in the `Main` method to `sc.GroupBySubstring()`.</span></span>  
  
 <span data-ttu-id="b03a9-130">[!code-cs[csProgGuideLINQ#18](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="b03a9-130">[!code-cs[csProgGuideLINQ#18](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b03a9-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b03a9-131">Example</span></span>  
 <span data-ttu-id="b03a9-132">Das folgende Beispiel veranschaulicht die Gruppierung von Quellelementen mithilfe eines numerischen Bereichs als Gruppenschlüssel.</span><span class="sxs-lookup"><span data-stu-id="b03a9-132">The following example shows how to group source elements by using a numeric range as a group key.</span></span> <span data-ttu-id="b03a9-133">Die Abfrage projiziert dann die Ergebnisse in einen anonymen Typ, der nur den Vor- und Nachnamen und den Prozentbereich enthält, dem der Student angehört.</span><span class="sxs-lookup"><span data-stu-id="b03a9-133">The query then projects the results into an anonymous type that contains only the first and last name and the percentile range to which the student belongs.</span></span> <span data-ttu-id="b03a9-134">Ein anonymer Typ wird verwendet, da es nicht notwendig ist, das gesamte `Student`-Objekt zu nutzen, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b03a9-134">An anonymous type is used because it is not necessary to use the complete `Student` object to display the results.</span></span> <span data-ttu-id="b03a9-135">`GetPercentile` ist eine Hilfsfunktion, die einen Prozentwert berechnet, der auf dem Durchschnittsergebnis des Studenten basiert.</span><span class="sxs-lookup"><span data-stu-id="b03a9-135">`GetPercentile` is a helper function that calculates a percentile based on the student's average score.</span></span> <span data-ttu-id="b03a9-136">Die Methode gibt eine ganze Zahl zwischen 0 und 10 zurück.</span><span class="sxs-lookup"><span data-stu-id="b03a9-136">The method returns an integer between 0 and 10.</span></span>  
  
 <span data-ttu-id="b03a9-137">[!code-cs[csProgGuideLINQ#50](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="b03a9-137">[!code-cs[csProgGuideLINQ#50](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]</span></span>  
  
 <span data-ttu-id="b03a9-138">Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="b03a9-138">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="b03a9-139">Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupByRange()`.</span><span class="sxs-lookup"><span data-stu-id="b03a9-139">Change the calling statement in the `Main` method to `sc.GroupByRange()`.</span></span>  
  
 <span data-ttu-id="b03a9-140">[!code-cs[csProgGuideLINQ#19](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="b03a9-140">[!code-cs[csProgGuideLINQ#19](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b03a9-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b03a9-141">Example</span></span>  
 <span data-ttu-id="b03a9-142">Das folgende Beispiel veranschaulicht die Gruppierung von Vergleichselementen mithilfe eines booleschen Vergleichsausdrucks.</span><span class="sxs-lookup"><span data-stu-id="b03a9-142">The following example shows how to group source elements by using a Boolean comparison expression.</span></span> <span data-ttu-id="b03a9-143">In diesem Beispiel testet der boolesche Ausdruck, ob die durchschnittliche Bewertung der Tests eines Studenten größer als 75 ist.</span><span class="sxs-lookup"><span data-stu-id="b03a9-143">In this example, the Boolean expression tests whether a student's average exam score is greater than 75.</span></span> <span data-ttu-id="b03a9-144">Wie in den vorherigen Beispielen werden die Ergebnisse in einen anonymen Typ projiziert, da nicht das gesamte Quellelement benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="b03a9-144">As in previous examples, the results are projected into an anonymous type because the complete source element is not needed.</span></span> <span data-ttu-id="b03a9-145">Beachten Sie, dass die Eigenschaften im anonymen Typ Eigenschaften des `Key`-Members werden und dass über den Namen auf sie zugegriffen werden kann, wenn die Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b03a9-145">Note that the properties in the anonymous type become properties on the `Key` member and can be accessed by name when the query is executed.</span></span>  
  
 <span data-ttu-id="b03a9-146">Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="b03a9-146">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="b03a9-147">Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupByBoolean()`.</span><span class="sxs-lookup"><span data-stu-id="b03a9-147">Change the calling statement in the `Main` method to `sc.GroupByBoolean()`.</span></span>  
  
 <span data-ttu-id="b03a9-148">[!code-cs[csProgGuideLINQ#20](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="b03a9-148">[!code-cs[csProgGuideLINQ#20](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b03a9-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b03a9-149">Example</span></span>  
 <span data-ttu-id="b03a9-150">Das folgende Beispiel veranschaulicht die Verwendung eines anonymen Typs für die Kapselung eines Schlüssels mit mehreren Werten.</span><span class="sxs-lookup"><span data-stu-id="b03a9-150">The following example shows how to use an anonymous type to encapsulate a key that contains multiple values.</span></span> <span data-ttu-id="b03a9-151">In diesem Beispiel ist der erste Schlüsselwert der erste Buchstabe des Nachnamens des Studenten.</span><span class="sxs-lookup"><span data-stu-id="b03a9-151">In this example, the first key value is the first letter of the student's last name.</span></span> <span data-ttu-id="b03a9-152">Der zweite Schlüsselwert ist ein boolescher Wert, der angibt, ob der Student in der ersten Prüfung ein Ergebnis über 85 erzielt hat.</span><span class="sxs-lookup"><span data-stu-id="b03a9-152">The second key value is a Boolean that specifies whether the student scored over 85 on the first exam.</span></span> <span data-ttu-id="b03a9-153">Sie können die Gruppen anhand jeder Eigenschaft im Schlüssel sortieren.</span><span class="sxs-lookup"><span data-stu-id="b03a9-153">You can order the groups by any property in the key.</span></span>  
  
 <span data-ttu-id="b03a9-154">Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="b03a9-154">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="b03a9-155">Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupByCompositeKey()`.</span><span class="sxs-lookup"><span data-stu-id="b03a9-155">Change the calling statement in the `Main` method to `sc.GroupByCompositeKey()`.</span></span>  
  
 <span data-ttu-id="b03a9-156">[!code-cs[csProgGuideLINQ#21](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="b03a9-156">[!code-cs[csProgGuideLINQ#21](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03a9-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b03a9-157">See also</span></span>  
 <span data-ttu-id="b03a9-158"><xref:System.Linq.Enumerable.GroupBy%2A></span><span class="sxs-lookup"><span data-stu-id="b03a9-158"><xref:System.Linq.Enumerable.GroupBy%2A></span></span>   
 <span data-ttu-id="b03a9-159"><xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="b03a9-159"><xref:System.Linq.IGrouping%602></span></span>   
 <span data-ttu-id="b03a9-160">[LINQ-Abfrageausdrücke](index.md) </span><span class="sxs-lookup"><span data-stu-id="b03a9-160">[LINQ Query Expressions](index.md) </span></span>  
 <span data-ttu-id="b03a9-161">[group-Klausel](../language-reference/keywords/group-clause.md) </span><span class="sxs-lookup"><span data-stu-id="b03a9-161">[group clause](../language-reference/keywords/group-clause.md) </span></span>  
 <span data-ttu-id="b03a9-162">[Anonyme Typen](../programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="b03a9-162">[Anonymous Types](../programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="b03a9-163">[Perform a Subquery on a Grouping Operation (Ausführen einer Unterabfrage für eine Gruppierungsoperation)](perform-a-subquery-on-a-grouping-operation.md) </span><span class="sxs-lookup"><span data-stu-id="b03a9-163">[Perform a Subquery on a Grouping Operation](perform-a-subquery-on-a-grouping-operation.md) </span></span>  
 <span data-ttu-id="b03a9-164">[Create a Nested Group (Erstellen einer geschachtelten Gruppe)](create-a-nested-group.md) </span><span class="sxs-lookup"><span data-stu-id="b03a9-164">[Create a Nested Group](create-a-nested-group.md) </span></span>  
 [<span data-ttu-id="b03a9-165">Gruppieren von Daten</span><span class="sxs-lookup"><span data-stu-id="b03a9-165">Grouping Data</span></span>](../programming-guide/concepts/linq/grouping-data.md)

