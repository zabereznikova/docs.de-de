---
title: Gruppieren von Abfrageergebnissen
description: So gruppieren Sie Ergebnisse.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 2e4ec27f-06fb-4de7-8973-0189906d4520
ms.openlocfilehash: ca68cf96a2c27bbd1999d5445c14fc93e8e2566c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="group-query-results"></a><span data-ttu-id="de453-104">Gruppieren von Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="de453-104">Group query results</span></span>

<span data-ttu-id="de453-105">Das Gruppieren ist eine der leistungsstärksten Funktionen von LINQ.</span><span class="sxs-lookup"><span data-stu-id="de453-105">Grouping is one of the most powerful capabilities of LINQ.</span></span> <span data-ttu-id="de453-106">Die folgenden Beispiele zeigen Ihnen, wie Sie Daten auf verschiedene Arten und Weisen gruppieren:</span><span class="sxs-lookup"><span data-stu-id="de453-106">The following examples show how to group data in various ways:</span></span>  
  
-   <span data-ttu-id="de453-107">Nach einer einzelnen Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="de453-107">By a single property.</span></span>  
  
-   <span data-ttu-id="de453-108">Nach dem ersten Buchstaben einer Zeichenfolgeneigenschaft</span><span class="sxs-lookup"><span data-stu-id="de453-108">By the first letter of a string property.</span></span>  
  
-   <span data-ttu-id="de453-109">Nach einem berechneten numerischen Bereich</span><span class="sxs-lookup"><span data-stu-id="de453-109">By a computed numeric range.</span></span>  
  
-   <span data-ttu-id="de453-110">Nach einem booleschen Prädikat oder einem anderer Ausdruck</span><span class="sxs-lookup"><span data-stu-id="de453-110">By Boolean predicate or other expression.</span></span>  
  
-   <span data-ttu-id="de453-111">Nach einem Verbundschlüssel</span><span class="sxs-lookup"><span data-stu-id="de453-111">By a compound key.</span></span>  
  
 <span data-ttu-id="de453-112">Darüber hinaus projizieren die letzten beiden Abfragen die Ergebnisse in einen neuen anonymen Typ, der nur die Vor- und Nachnamen der Studenten enthält.</span><span class="sxs-lookup"><span data-stu-id="de453-112">In addition, the last two queries project their results into a new anonymous type that contains only the student's first and last name.</span></span> <span data-ttu-id="de453-113">Weitere Informationen finden Sie unter [group-Klausel](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="de453-113">For more information, see the [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="de453-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de453-114">Example</span></span>  
 <span data-ttu-id="de453-115">Alle Beispiele in diesem Thema verwenden die folgenden Hilfsklassen und Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="de453-115">All the examples in this topic use the following helper classes and data sources.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="de453-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de453-116">Example</span></span>  
 <span data-ttu-id="de453-117">Das folgende Beispiel veranschaulicht die Gruppierung von Quellelementen mithilfe einer einzelnen Eigenschaft des Elements als Gruppenschlüssel.</span><span class="sxs-lookup"><span data-stu-id="de453-117">The following example shows how to group source elements by using a single property of the element as the group key.</span></span> <span data-ttu-id="de453-118">In diesem Fall ist der Schlüssel ein `string`, der Nachname des Studenten.</span><span class="sxs-lookup"><span data-stu-id="de453-118">In this case the key is a `string`, the student's last name.</span></span> <span data-ttu-id="de453-119">Es ist auch möglich, eine Teilzeichenfolge als Schlüssel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="de453-119">It is also possible to use a substring for the key.</span></span> <span data-ttu-id="de453-120">Bei der Gruppierungsoperation wird der als Standard für diesen Typ festgelegte Gleichheitsvergleich verwendet.</span><span class="sxs-lookup"><span data-stu-id="de453-120">The grouping operation uses the default equality comparer for the type.</span></span>  
  
 <span data-ttu-id="de453-121">Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="de453-121">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="de453-122">Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupBySingleProperty()`.</span><span class="sxs-lookup"><span data-stu-id="de453-122">Change the calling statement in the `Main` method to `sc.GroupBySingleProperty()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#17](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="de453-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de453-123">Example</span></span>  
 <span data-ttu-id="de453-124">Das folgende Beispiel veranschaulicht die Gruppierung von Quellelemente ohne eine Objekteigenschaft als Gruppenschlüssel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="de453-124">The following example shows how to group source elements by using something other than a property of the object for the group key.</span></span> <span data-ttu-id="de453-125">In diesem Beispiel ist der Schlüssel der erste Buchstabe des Nachnamens des Studenten.</span><span class="sxs-lookup"><span data-stu-id="de453-125">In this example, the key is the first letter of the student's last name.</span></span>  
  
 <span data-ttu-id="de453-126">Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="de453-126">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="de453-127">Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupBySubstring()`.</span><span class="sxs-lookup"><span data-stu-id="de453-127">Change the calling statement in the `Main` method to `sc.GroupBySubstring()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#18](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="de453-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de453-128">Example</span></span>  
 <span data-ttu-id="de453-129">Das folgende Beispiel veranschaulicht die Gruppierung von Quellelementen mithilfe eines numerischen Bereichs als Gruppenschlüssel.</span><span class="sxs-lookup"><span data-stu-id="de453-129">The following example shows how to group source elements by using a numeric range as a group key.</span></span> <span data-ttu-id="de453-130">Die Abfrage projiziert dann die Ergebnisse in einen anonymen Typ, der nur den Vor- und Nachnamen und den Prozentbereich enthält, dem der Student angehört.</span><span class="sxs-lookup"><span data-stu-id="de453-130">The query then projects the results into an anonymous type that contains only the first and last name and the percentile range to which the student belongs.</span></span> <span data-ttu-id="de453-131">Ein anonymer Typ wird verwendet, da es nicht notwendig ist, das gesamte `Student`-Objekt zu nutzen, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="de453-131">An anonymous type is used because it is not necessary to use the complete `Student` object to display the results.</span></span> <span data-ttu-id="de453-132">`GetPercentile` ist eine Hilfsfunktion, die einen Prozentwert berechnet, der auf dem Durchschnittsergebnis des Studenten basiert.</span><span class="sxs-lookup"><span data-stu-id="de453-132">`GetPercentile` is a helper function that calculates a percentile based on the student's average score.</span></span> <span data-ttu-id="de453-133">Die Methode gibt eine ganze Zahl zwischen 0 und 10 zurück.</span><span class="sxs-lookup"><span data-stu-id="de453-133">The method returns an integer between 0 and 10.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#50](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]  
  
 <span data-ttu-id="de453-134">Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="de453-134">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="de453-135">Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupByRange()`.</span><span class="sxs-lookup"><span data-stu-id="de453-135">Change the calling statement in the `Main` method to `sc.GroupByRange()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#19](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]  
  
## <a name="example"></a><span data-ttu-id="de453-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de453-136">Example</span></span>  
 <span data-ttu-id="de453-137">Das folgende Beispiel veranschaulicht die Gruppierung von Vergleichselementen mithilfe eines booleschen Vergleichsausdrucks.</span><span class="sxs-lookup"><span data-stu-id="de453-137">The following example shows how to group source elements by using a Boolean comparison expression.</span></span> <span data-ttu-id="de453-138">In diesem Beispiel testet der boolesche Ausdruck, ob die durchschnittliche Bewertung der Tests eines Studenten größer als 75 ist.</span><span class="sxs-lookup"><span data-stu-id="de453-138">In this example, the Boolean expression tests whether a student's average exam score is greater than 75.</span></span> <span data-ttu-id="de453-139">Wie in den vorherigen Beispielen werden die Ergebnisse in einen anonymen Typ projiziert, da nicht das gesamte Quellelement benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="de453-139">As in previous examples, the results are projected into an anonymous type because the complete source element is not needed.</span></span> <span data-ttu-id="de453-140">Beachten Sie, dass die Eigenschaften im anonymen Typ Eigenschaften des `Key`-Members werden und dass über den Namen auf sie zugegriffen werden kann, wenn die Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="de453-140">Note that the properties in the anonymous type become properties on the `Key` member and can be accessed by name when the query is executed.</span></span>  
  
 <span data-ttu-id="de453-141">Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="de453-141">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="de453-142">Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupByBoolean()`.</span><span class="sxs-lookup"><span data-stu-id="de453-142">Change the calling statement in the `Main` method to `sc.GroupByBoolean()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#20](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]  
  
## <a name="example"></a><span data-ttu-id="de453-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de453-143">Example</span></span>  
 <span data-ttu-id="de453-144">Das folgende Beispiel veranschaulicht die Verwendung eines anonymen Typs für die Kapselung eines Schlüssels mit mehreren Werten.</span><span class="sxs-lookup"><span data-stu-id="de453-144">The following example shows how to use an anonymous type to encapsulate a key that contains multiple values.</span></span> <span data-ttu-id="de453-145">In diesem Beispiel ist der erste Schlüsselwert der erste Buchstabe des Nachnamens des Studenten.</span><span class="sxs-lookup"><span data-stu-id="de453-145">In this example, the first key value is the first letter of the student's last name.</span></span> <span data-ttu-id="de453-146">Der zweite Schlüsselwert ist ein boolescher Wert, der angibt, ob der Student in der ersten Prüfung ein Ergebnis über 85 erzielt hat.</span><span class="sxs-lookup"><span data-stu-id="de453-146">The second key value is a Boolean that specifies whether the student scored over 85 on the first exam.</span></span> <span data-ttu-id="de453-147">Sie können die Gruppen anhand jeder Eigenschaft im Schlüssel sortieren.</span><span class="sxs-lookup"><span data-stu-id="de453-147">You can order the groups by any property in the key.</span></span>  
  
 <span data-ttu-id="de453-148">Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="de453-148">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="de453-149">Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupByCompositeKey()`.</span><span class="sxs-lookup"><span data-stu-id="de453-149">Change the calling statement in the `Main` method to `sc.GroupByCompositeKey()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#21](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="de453-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de453-150">See also</span></span>  
 <xref:System.Linq.Enumerable.GroupBy%2A>  
 <xref:System.Linq.IGrouping%602>  
 [<span data-ttu-id="de453-151">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="de453-151">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="de453-152">group-Klausel</span><span class="sxs-lookup"><span data-stu-id="de453-152">group clause</span></span>](../language-reference/keywords/group-clause.md)  
 [<span data-ttu-id="de453-153">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="de453-153">Anonymous Types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="de453-154">Ausführen einer Unterabfrage für eine Gruppierungsoperation</span><span class="sxs-lookup"><span data-stu-id="de453-154">Perform a Subquery on a Grouping Operation</span></span>](perform-a-subquery-on-a-grouping-operation.md)  
 [<span data-ttu-id="de453-155">Erstellen einer geschachtelten Gruppe</span><span class="sxs-lookup"><span data-stu-id="de453-155">Create a Nested Group</span></span>](create-a-nested-group.md)  
 [<span data-ttu-id="de453-156">Gruppieren von Daten</span><span class="sxs-lookup"><span data-stu-id="de453-156">Grouping Data</span></span>](../programming-guide/concepts/linq/grouping-data.md)
