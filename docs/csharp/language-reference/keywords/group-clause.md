---
description: group-Klausel – C#-Referenz
title: group-Klausel – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- group
- group_CSharpKeyword
helpviewer_keywords:
- group keyword [C#]
- group clause [C#]
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
ms.openlocfilehash: 5e642492b4b36bb0464baf16baa80c58c19ba9f1
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138227"
---
# <a name="group-clause-c-reference"></a><span data-ttu-id="bcccc-103">group-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bcccc-103">group clause (C# Reference)</span></span>

<span data-ttu-id="bcccc-104">Die `group`-Klausel gibt eine Sequenz von <xref:System.Linq.IGrouping%602>-Objekten zurück, die null oder mehr Elemente enthalten, die mit dem Schlüsselwert für die Gruppe übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="bcccc-104">The `group` clause returns a sequence of <xref:System.Linq.IGrouping%602> objects that contain zero or more items that match the key value for the group.</span></span> <span data-ttu-id="bcccc-105">Sie können z.B. eine Sequenz von Zeichenfolgen entsprechend des ersten Buchstaben in jeder Zeichenfolge gruppieren.</span><span class="sxs-lookup"><span data-stu-id="bcccc-105">For example, you can group a sequence of strings according to the first letter in each string.</span></span> <span data-ttu-id="bcccc-106">In diesem Fall ist der erste Buchstabe der Schlüssel, verfügt über einen Typ [char](../builtin-types/char.md) und wird in der `Key`-Eigenschaft jedes <xref:System.Linq.IGrouping%602>-Objekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bcccc-106">In this case, the first letter is the key and has a type [char](../builtin-types/char.md), and is stored in the `Key` property of each <xref:System.Linq.IGrouping%602> object.</span></span> <span data-ttu-id="bcccc-107">Der Compiler leiten den Typ des Schlüssels her.</span><span class="sxs-lookup"><span data-stu-id="bcccc-107">The compiler infers the type of the key.</span></span>

<span data-ttu-id="bcccc-108">Sie können einen Abfrageausdruck mit einer `group`-Klausel beenden, so wie in folgendem Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="bcccc-108">You can end a query expression with a `group` clause, as shown in the following example:</span></span>

[!code-csharp[cscsrefQueryKeywords#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#10)]

<span data-ttu-id="bcccc-109">Wenn Sie zusätzliche Abfragevorgänge für jede Gruppe ausführen möchten, können Sie einen temporären Bezeichner mithilfe des kontextuellen Schlüsselworts [into](into.md) angeben.</span><span class="sxs-lookup"><span data-stu-id="bcccc-109">If you want to perform additional query operations on each group, you can specify a temporary identifier by using the [into](into.md) contextual keyword.</span></span> <span data-ttu-id="bcccc-110">Wenn Sie `into` verwenden, müssen Sie mit der Abfrage fortfahren und sie entweder mit einer `select`-Anweisung oder einer anderen `group`-Klausel beenden, so wie im folgenden Auszug dargestellt:</span><span class="sxs-lookup"><span data-stu-id="bcccc-110">When you use `into`, you must continue with the query, and eventually end it with either a `select` statement or another `group` clause, as shown in the following excerpt:</span></span>

[!code-csharp[cscsrefQueryKeywords#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#11)]

<span data-ttu-id="bcccc-111">Weitere vollständige Gebrauchsbeispiele für `group` mit und ohne `into` sind im Abschnitt über Beispiele in diesem Artikel enthalten.</span><span class="sxs-lookup"><span data-stu-id="bcccc-111">More complete examples of the use of `group` with and without `into` are provided in the Example section of this article.</span></span>

## <a name="enumerating-the-results-of-a-group-query"></a><span data-ttu-id="bcccc-112">Auflisten der Ergebnisse einer Gruppenabfrage</span><span class="sxs-lookup"><span data-stu-id="bcccc-112">Enumerating the results of a group query</span></span>

<span data-ttu-id="bcccc-113">Da die <xref:System.Linq.IGrouping%602>-Objekte, die von einer `group`-Abfrage erstellt wurden, praktisch eine Liste von Listen sind, müssen Sie eine geschachtelte [foreach](foreach-in.md)-Schleife verwenden, um auf die Elemente in jeder Gruppe zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="bcccc-113">Because the <xref:System.Linq.IGrouping%602> objects produced by a `group` query are essentially a list of lists, you must use a nested [foreach](foreach-in.md) loop to access the items in each group.</span></span> <span data-ttu-id="bcccc-114">Die äußere Schleife durchläuft die Gruppenschlüssel, und die innere Schleife durchläuft jedes Element in der Gruppe selbst.</span><span class="sxs-lookup"><span data-stu-id="bcccc-114">The outer loop iterates over the group keys, and the inner loop iterates over each item in the group itself.</span></span> <span data-ttu-id="bcccc-115">Eine Gruppe kann womöglich über einen Schlüssel verfügen, jedoch nicht über Elemente.</span><span class="sxs-lookup"><span data-stu-id="bcccc-115">A group may have a key but no elements.</span></span> <span data-ttu-id="bcccc-116">Nachstehend finden Sie die `foreach`-Schleife, die die Abfrage in den vorherigen Codebeispielen ausführen:</span><span class="sxs-lookup"><span data-stu-id="bcccc-116">The following is the `foreach` loop that executes the query in the previous code examples:</span></span>

[!code-csharp[cscsrefQueryKeywords#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#12)]

## <a name="key-types"></a><span data-ttu-id="bcccc-117">Schlüsseltypen</span><span class="sxs-lookup"><span data-stu-id="bcccc-117">Key types</span></span>

<span data-ttu-id="bcccc-118">Gruppenschlüssel können von jedem Typ sein, z.B. eine Zeichenfolge, ein integrierter numerischer Typ oder ein benutzerdefinierter benannter oder anonymer Typ.</span><span class="sxs-lookup"><span data-stu-id="bcccc-118">Group keys can be any type, such as a string, a built-in numeric type, or a user-defined named type or anonymous type.</span></span>

### <a name="grouping-by-string"></a><span data-ttu-id="bcccc-119">Gruppieren nach Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="bcccc-119">Grouping by string</span></span>

<span data-ttu-id="bcccc-120">Das vorherige Codebeispiel verwendete einen `char`.</span><span class="sxs-lookup"><span data-stu-id="bcccc-120">The previous code examples used a `char`.</span></span> <span data-ttu-id="bcccc-121">Es hätte stattdessen einfach ein Zeichenfolgenschlüssel angegeben werden können, z.B. der vollständige letzte Name.</span><span class="sxs-lookup"><span data-stu-id="bcccc-121">A string key could easily have been specified instead, for example the complete last name:</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

### <a name="grouping-by-bool"></a><span data-ttu-id="bcccc-122">Gruppieren nach Bool</span><span class="sxs-lookup"><span data-stu-id="bcccc-122">Grouping by bool</span></span>

<span data-ttu-id="bcccc-123">Das folgende Beispiel zeigt die Verwendung eines booleschen Werts für einen Schlüssel, um die Ergebnisse in zwei Gruppen zu unterteilen.</span><span class="sxs-lookup"><span data-stu-id="bcccc-123">The following example shows the use of a bool value for a key to divide the results into two groups.</span></span> <span data-ttu-id="bcccc-124">Beachten Sie, dass der Wert durch einen Unterausdruck in der `group`-Klausel erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bcccc-124">Note that the value is produced by a sub-expression in the `group` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#14)]

### <a name="grouping-by-numeric-range"></a><span data-ttu-id="bcccc-125">Gruppieren nach numerischen Bereich</span><span class="sxs-lookup"><span data-stu-id="bcccc-125">Grouping by numeric range</span></span>

<span data-ttu-id="bcccc-126">Das nächste Beispiel verwendet einen Ausdruck, um einen nummerischen Gruppenschlüssel zu erstellen, der einen Prozentbereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="bcccc-126">The next example uses an expression to create numeric group keys that represent a percentile range.</span></span> <span data-ttu-id="bcccc-127">Beachten Sie, dass [let](let-clause.md) an einer geeigneten Position eingesetzt wird, um Ergebnisse eines Methodenaufrufs zu speichern, damit Sie die Methode nicht zweimal in der `group`-Klausel aufrufen müssen.</span><span class="sxs-lookup"><span data-stu-id="bcccc-127">Note the use of [let](let-clause.md) as a convenient location to store a method call result, so that you don't have to call the method two times in the `group` clause.</span></span> <span data-ttu-id="bcccc-128">Weitere Informationen zur sicheren Verwendung von Methoden in Abfrageausdrücken finden Sie unter [Behandeln von Ausnahmen in Abfrageausdrücken](../../linq/handle-exceptions-in-query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="bcccc-128">For more information about how to safely use methods in query expressions, see [Handle exceptions in query expressions](../../linq/handle-exceptions-in-query-expressions.md).</span></span>

[!code-csharp[cscsrefQueryKeywords#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#15)]

### <a name="grouping-by-composite-keys"></a><span data-ttu-id="bcccc-129">Gruppieren nach zusammengesetzten Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="bcccc-129">Grouping by composite keys</span></span>

<span data-ttu-id="bcccc-130">Verwenden Sie einen zusammengesetzten Schlüssel, wenn Sie Elemente gemäß mehrerer Schlüssel gruppieren möchten.</span><span class="sxs-lookup"><span data-stu-id="bcccc-130">Use a composite key when you want to group elements according to more than one key.</span></span> <span data-ttu-id="bcccc-131">Sie erstellen einen zusammengesetzten Schlüssel, indem Sie einen anonymen Typ oder einen benannten Typ verwenden, um das Schlüsselelement aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="bcccc-131">You create a composite key by using an anonymous type or a named type to hold the key element.</span></span> <span data-ttu-id="bcccc-132">Im folgenden Beispiel wird davon ausgegangen, dass eine `Person`-Klasse mit Elementen namens `surname` und `city` deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="bcccc-132">In the following example, assume that a class `Person` has been declared with members named `surname` and `city`.</span></span> <span data-ttu-id="bcccc-133">Die `group`-Klausel bewirkt, dass eine separate Gruppe für jede Gruppe von Personen mit dem gleichen Nachnamen und der gleichen Stadt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bcccc-133">The `group` clause causes a separate group to be created for each set of persons with the same last name and the same city.</span></span>

```csharp
group person by new {name = person.surname, city = person.city};
```

<span data-ttu-id="bcccc-134">Verwenden Sie einen benannten Typ, wenn Sie die Abfragevariable an eine andere Methode übergeben müssen.</span><span class="sxs-lookup"><span data-stu-id="bcccc-134">Use a named type if you must pass the query variable to another method.</span></span> <span data-ttu-id="bcccc-135">Erstellen Sie eine spezielle Klasse mit automatisch implementierten Eigenschaften für die Schlüssel, und setzen Sie anschließend die Methoden <xref:System.Object.Equals%2A> und <xref:System.Object.GetHashCode%2A> außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="bcccc-135">Create a special class using auto-implemented properties for the keys, and then override the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> methods.</span></span> <span data-ttu-id="bcccc-136">Sie können auch eine Struktur verwenden. In diesem Fall müssen Sie diese Methoden nicht unbedingt außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="bcccc-136">You can also use a struct, in which case you do not strictly have to override those methods.</span></span> <span data-ttu-id="bcccc-137">Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) und [Vorgehensweise: Abfragen von Dateiduplikaten in einer Verzeichnisstruktur](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md).</span><span class="sxs-lookup"><span data-stu-id="bcccc-137">For more information see [How to implement a lightweight class with auto-implemented properties](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) and [How to query for duplicate files in a directory tree](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md).</span></span> <span data-ttu-id="bcccc-138">Der zweite Artikel enthält ein Codebeispiel, in dem dargestellt wird, wie ein zusammengesetzter Schlüssel mit einem benannten Typ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bcccc-138">The latter article has a code example that demonstrates how to use a composite key with a named type.</span></span>

## <a name="example"></a><span data-ttu-id="bcccc-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bcccc-139">Example</span></span>

<span data-ttu-id="bcccc-140">Das folgende Beispiel zeigt das Standardmuster für das Sortieren von Quelldaten in Gruppen, wenn keine zusätzliche Abfragelogik auf die Gruppen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="bcccc-140">The following example shows the standard pattern for ordering source data into groups when no additional query logic is applied to the groups.</span></span> <span data-ttu-id="bcccc-141">Dies wird Gruppierung ohne Fortsetzung genannt.</span><span class="sxs-lookup"><span data-stu-id="bcccc-141">This is called a grouping without a continuation.</span></span> <span data-ttu-id="bcccc-142">Die Elemente in einem Zeichenfolgenarray werden gemäß des ersten Buchstabens gruppiert.</span><span class="sxs-lookup"><span data-stu-id="bcccc-142">The elements in an array of strings are grouped according to their first letter.</span></span> <span data-ttu-id="bcccc-143">Das Ergebnis der Abfrage ist ein <xref:System.Linq.IGrouping%602>-Typ, der eine öffentliche `Key`-Eigenschaft des Typs `char` und eine <xref:System.Collections.Generic.IEnumerable%601>-Sammlung enthält, die jedes Element in der Gruppierung enthält.</span><span class="sxs-lookup"><span data-stu-id="bcccc-143">The result of the query is an <xref:System.Linq.IGrouping%602> type that contains a public `Key` property of type `char` and an <xref:System.Collections.Generic.IEnumerable%601> collection that contains each item in the grouping.</span></span>

<span data-ttu-id="bcccc-144">Das Ergebnis einer `group`-Klausel ist eine Sequenz von Sequenzen.</span><span class="sxs-lookup"><span data-stu-id="bcccc-144">The result of a `group` clause is a sequence of sequences.</span></span> <span data-ttu-id="bcccc-145">Verwenden Sie deshalb eine geschachtelte `foreach`-Schleife innerhalb der Schleife, die die Gruppenschlüssel durchläuft – so wie in folgendem Beispiel gezeigt – um auf die einzelnen Elemente innerhalb jeder zurückgegebenen Gruppe zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="bcccc-145">Therefore, to access the individual elements within each returned group, use a nested `foreach` loop inside the loop that iterates the group keys, as shown in the following example.</span></span>

[!code-csharp[cscsrefQueryKeywords#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#16)]

## <a name="example"></a><span data-ttu-id="bcccc-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bcccc-146">Example</span></span>

<span data-ttu-id="bcccc-147">Dieses Beispiel zeigt, wie zusätzliche Logik auf die Gruppen ausgeführt wird, nachdem Sie diese erstellt haben, indem eine *Fortsetzung* mit `into` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bcccc-147">This example shows how to perform additional logic on the groups after you have created them, by using a *continuation* with `into`.</span></span> <span data-ttu-id="bcccc-148">Weitere Informationen finden Sie unter [into](into.md).</span><span class="sxs-lookup"><span data-stu-id="bcccc-148">For more information, see [into](into.md).</span></span> <span data-ttu-id="bcccc-149">Das folgende Beispiel fragt jede Gruppe ab, wobei nur die Gruppe ausgewählt werden soll, dessen Schlüsselwert ein Vokal ist.</span><span class="sxs-lookup"><span data-stu-id="bcccc-149">The following example queries each group to select only those whose key value is a vowel.</span></span>

[!code-csharp[cscsrefQueryKeywords#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#17)]

## <a name="remarks"></a><span data-ttu-id="bcccc-150">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bcccc-150">Remarks</span></span>

<span data-ttu-id="bcccc-151">`group`-Klauseln werden zur Kompilierzeit in Aufrufe der <xref:System.Linq.Enumerable.GroupBy%2A>-Methode übersetzt.</span><span class="sxs-lookup"><span data-stu-id="bcccc-151">At compile time, `group` clauses are translated into calls to the <xref:System.Linq.Enumerable.GroupBy%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="bcccc-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bcccc-152">See also</span></span>

- <xref:System.Linq.IGrouping%602>
- <xref:System.Linq.Enumerable.GroupBy%2A>
- <xref:System.Linq.Enumerable.ThenBy%2A>
- <xref:System.Linq.Enumerable.ThenByDescending%2A>
- [<span data-ttu-id="bcccc-153">Abfrageschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bcccc-153">Query Keywords</span></span>](query-keywords.md)
- [<span data-ttu-id="bcccc-154">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="bcccc-154">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="bcccc-155">Erstellen einer geschachtelten Gruppe</span><span class="sxs-lookup"><span data-stu-id="bcccc-155">Create a nested group</span></span>](../../linq/create-a-nested-group.md)
- [<span data-ttu-id="bcccc-156">Gruppieren von Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="bcccc-156">Group query results</span></span>](../../linq/group-query-results.md)
- [<span data-ttu-id="bcccc-157">Ausführen einer Unterabfrage für eine Gruppierungsoperation</span><span class="sxs-lookup"><span data-stu-id="bcccc-157">Perform a subquery on a grouping operation</span></span>](../../linq/perform-a-subquery-on-a-grouping-operation.md)
