---
title: group-Klausel – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- group
- group_CSharpKeyword
helpviewer_keywords:
- group keyword [C#]
- group clause [C#]
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
ms.openlocfilehash: dd14a4baf9967f41690e7978b8b6cf57c9275e36
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428501"
---
# <a name="group-clause-c-reference"></a><span data-ttu-id="7bfcf-102">group-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7bfcf-102">group clause (C# Reference)</span></span>

<span data-ttu-id="7bfcf-103">Die `group`-Klausel gibt eine Sequenz von <xref:System.Linq.IGrouping%602>-Objekten zurück, die null oder mehr Elemente enthalten, die mit dem Schlüsselwert für die Gruppe übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-103">The `group` clause returns a sequence of <xref:System.Linq.IGrouping%602> objects that contain zero or more items that match the key value for the group.</span></span> <span data-ttu-id="7bfcf-104">Sie können z.B. eine Sequenz von Zeichenfolgen entsprechend des ersten Buchstaben in jeder Zeichenfolge gruppieren.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-104">For example, you can group a sequence of strings according to the first letter in each string.</span></span> <span data-ttu-id="7bfcf-105">In diesem Fall ist der erste Buchstabe der Schlüssel, verfügt über einen Typ [char](../builtin-types/char.md) und wird in der `Key`-Eigenschaft jedes <xref:System.Linq.IGrouping%602>-Objekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-105">In this case, the first letter is the key and has a type [char](../builtin-types/char.md), and is stored in the `Key` property of each <xref:System.Linq.IGrouping%602> object.</span></span> <span data-ttu-id="7bfcf-106">Der Compiler leiten den Typ des Schlüssels her.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-106">The compiler infers the type of the key.</span></span>

<span data-ttu-id="7bfcf-107">Sie können einen Abfrageausdruck mit einer `group`-Klausel beenden, so wie in folgendem Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7bfcf-107">You can end a query expression with a `group` clause, as shown in the following example:</span></span>

[!code-csharp[cscsrefQueryKeywords#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#10)]

<span data-ttu-id="7bfcf-108">Wenn Sie zusätzliche Abfragevorgänge für jede Gruppe ausführen möchten, können Sie einen temporären Bezeichner mithilfe des kontextuellen Schlüsselworts [into](into.md) angeben.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-108">If you want to perform additional query operations on each group, you can specify a temporary identifier by using the [into](into.md) contextual keyword.</span></span> <span data-ttu-id="7bfcf-109">Wenn Sie `into` verwenden, müssen Sie mit der Abfrage fortfahren und sie entweder mit einer `select`-Anweisung oder einer anderen `group`-Klausel beenden, so wie im folgenden Auszug dargestellt:</span><span class="sxs-lookup"><span data-stu-id="7bfcf-109">When you use `into`, you must continue with the query, and eventually end it with either a `select` statement or another `group` clause, as shown in the following excerpt:</span></span>

[!code-csharp[cscsrefQueryKeywords#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#11)]

<span data-ttu-id="7bfcf-110">Weitere vollständige Gebrauchsbeispiele für `group` mit und ohne `into` sind im Abschnitt über Beispiele in diesem Artikel enthalten.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-110">More complete examples of the use of `group` with and without `into` are provided in the Example section of this article.</span></span>

## <a name="enumerating-the-results-of-a-group-query"></a><span data-ttu-id="7bfcf-111">Auflisten der Ergebnisse einer Gruppenabfrage</span><span class="sxs-lookup"><span data-stu-id="7bfcf-111">Enumerating the results of a group query</span></span>

<span data-ttu-id="7bfcf-112">Da die <xref:System.Linq.IGrouping%602>-Objekte, die von einer `group`-Abfrage erstellt wurden, praktisch eine Liste von Listen sind, müssen Sie eine geschachtelte [foreach](foreach-in.md)-Schleife verwenden, um auf die Elemente in jeder Gruppe zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-112">Because the <xref:System.Linq.IGrouping%602> objects produced by a `group` query are essentially a list of lists, you must use a nested [foreach](foreach-in.md) loop to access the items in each group.</span></span> <span data-ttu-id="7bfcf-113">Die äußere Schleife durchläuft die Gruppenschlüssel, und die innere Schleife durchläuft jedes Element in der Gruppe selbst.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-113">The outer loop iterates over the group keys, and the inner loop iterates over each item in the group itself.</span></span> <span data-ttu-id="7bfcf-114">Eine Gruppe kann womöglich über einen Schlüssel verfügen, jedoch nicht über Elemente.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-114">A group may have a key but no elements.</span></span> <span data-ttu-id="7bfcf-115">Nachstehend finden Sie die `foreach`-Schleife, die die Abfrage in den vorherigen Codebeispielen ausführen:</span><span class="sxs-lookup"><span data-stu-id="7bfcf-115">The following is the `foreach` loop that executes the query in the previous code examples:</span></span>

[!code-csharp[cscsrefQueryKeywords#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#12)]

## <a name="key-types"></a><span data-ttu-id="7bfcf-116">Schlüsseltypen</span><span class="sxs-lookup"><span data-stu-id="7bfcf-116">Key types</span></span>

<span data-ttu-id="7bfcf-117">Gruppenschlüssel können von jedem Typ sein, z.B. eine Zeichenfolge, ein integrierter numerischer Typ oder ein benutzerdefinierter benannter oder anonymer Typ.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-117">Group keys can be any type, such as a string, a built-in numeric type, or a user-defined named type or anonymous type.</span></span>

### <a name="grouping-by-string"></a><span data-ttu-id="7bfcf-118">Gruppieren nach Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7bfcf-118">Grouping by string</span></span>

<span data-ttu-id="7bfcf-119">Das vorherige Codebeispiel verwendete einen `char`.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-119">The previous code examples used a `char`.</span></span> <span data-ttu-id="7bfcf-120">Es hätte stattdessen einfach ein Zeichenfolgenschlüssel angegeben werden können, z.B. der vollständige letzte Name.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-120">A string key could easily have been specified instead, for example the complete last name:</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

### <a name="grouping-by-bool"></a><span data-ttu-id="7bfcf-121">Gruppieren nach Bool</span><span class="sxs-lookup"><span data-stu-id="7bfcf-121">Grouping by bool</span></span>

<span data-ttu-id="7bfcf-122">Das folgende Beispiel zeigt die Verwendung eines booleschen Werts für einen Schlüssel, um die Ergebnisse in zwei Gruppen zu unterteilen.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-122">The following example shows the use of a bool value for a key to divide the results into two groups.</span></span> <span data-ttu-id="7bfcf-123">Beachten Sie, dass der Wert durch einen Unterausdruck in der `group`-Klausel erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-123">Note that the value is produced by a sub-expression in the `group` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#14)]

### <a name="grouping-by-numeric-range"></a><span data-ttu-id="7bfcf-124">Gruppieren nach numerischen Bereich</span><span class="sxs-lookup"><span data-stu-id="7bfcf-124">Grouping by numeric range</span></span>

<span data-ttu-id="7bfcf-125">Das nächste Beispiel verwendet einen Ausdruck, um einen nummerischen Gruppenschlüssel zu erstellen, der einen Prozentbereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-125">The next example uses an expression to create numeric group keys that represent a percentile range.</span></span> <span data-ttu-id="7bfcf-126">Beachten Sie, dass [let](let-clause.md) an einer geeigneten Position eingesetzt wird, um Ergebnisse eines Methodenaufrufs zu speichern, damit Sie die Methode nicht zweimal in der `group`-Klausel aufrufen müssen.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-126">Note the use of [let](let-clause.md) as a convenient location to store a method call result, so that you don't have to call the method two times in the `group` clause.</span></span> <span data-ttu-id="7bfcf-127">Weitere Informationen zur sicheren Verwendung von Methoden in Abfrageausdrücken finden Sie unter [Vorgehensweise: Behandeln von Ausnahmen in Abfrageausdrücken](../../linq/handle-exceptions-in-query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7bfcf-127">For more information about how to safely use methods in query expressions, see [How to: Handle Exceptions in Query Expressions](../../linq/handle-exceptions-in-query-expressions.md).</span></span>

[!code-csharp[cscsrefQueryKeywords#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#15)]

### <a name="grouping-by-composite-keys"></a><span data-ttu-id="7bfcf-128">Gruppieren nach zusammengesetzten Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="7bfcf-128">Grouping by composite keys</span></span>

<span data-ttu-id="7bfcf-129">Verwenden Sie einen zusammengesetzten Schlüssel, wenn Sie Elemente gemäß mehrerer Schlüssel gruppieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-129">Use a composite key when you want to group elements according to more than one key.</span></span> <span data-ttu-id="7bfcf-130">Sie erstellen einen zusammengesetzten Schlüssel, indem Sie einen anonymen Typ oder einen benannten Typ verwenden, um das Schlüsselelement aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-130">You create a composite key by using an anonymous type or a named type to hold the key element.</span></span> <span data-ttu-id="7bfcf-131">Im folgenden Beispiel wird davon ausgegangen, dass eine `Person`-Klasse mit Elementen namens `surname` und `city` deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-131">In the following example, assume that a class `Person` has been declared with members named `surname` and `city`.</span></span> <span data-ttu-id="7bfcf-132">Die `group`-Klausel bewirkt, dass eine separate Gruppe für jede Gruppe von Personen mit dem gleichen Nachnamen und der gleichen Stadt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-132">The `group` clause causes a separate group to be created for each set of persons with the same last name and the same city.</span></span>

```csharp
group person by new {name = person.surname, city = person.city};
```

<span data-ttu-id="7bfcf-133">Verwenden Sie einen benannten Typ, wenn Sie die Abfragevariable an eine andere Methode übergeben müssen.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-133">Use a named type if you must pass the query variable to another method.</span></span> <span data-ttu-id="7bfcf-134">Erstellen Sie eine spezielle Klasse mit automatisch implementierten Eigenschaften für die Schlüssel, und setzen Sie anschließend die Methoden <xref:System.Object.Equals%2A> und <xref:System.Object.GetHashCode%2A> außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-134">Create a special class using auto-implemented properties for the keys, and then override the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> methods.</span></span> <span data-ttu-id="7bfcf-135">Sie können auch eine Struktur verwenden. In diesem Fall müssen Sie diese Methoden nicht unbedingt außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-135">You can also use a struct, in which case you do not strictly have to override those methods.</span></span> <span data-ttu-id="7bfcf-136">Weitere Informationen finden Sie unter[Vorgehensweise: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) und unter [Vorgehensweise: Abfragen von Dateiduplikaten in einer Verzeichnisstruktur](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md).</span><span class="sxs-lookup"><span data-stu-id="7bfcf-136">For more information see [How to implement a lightweight class with auto-implemented properties](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) and [How to: Query for Duplicate Files in a Directory Tree](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md).</span></span> <span data-ttu-id="7bfcf-137">Der zweite Artikel enthält ein Codebeispiel, in dem dargestellt wird, wie ein zusammengesetzter Schlüssel mit einem benannten Typ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-137">The latter article has a code example that demonstrates how to use a composite key with a named type.</span></span>

## <a name="example"></a><span data-ttu-id="7bfcf-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7bfcf-138">Example</span></span>

<span data-ttu-id="7bfcf-139">Das folgende Beispiel zeigt das Standardmuster für das Sortieren von Quelldaten in Gruppen, wenn keine zusätzliche Abfragelogik auf die Gruppen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-139">The following example shows the standard pattern for ordering source data into groups when no additional query logic is applied to the groups.</span></span> <span data-ttu-id="7bfcf-140">Dies wird Gruppierung ohne Fortsetzung genannt.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-140">This is called a grouping without a continuation.</span></span> <span data-ttu-id="7bfcf-141">Die Elemente in einem Zeichenfolgenarray werden gemäß des ersten Buchstabens gruppiert.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-141">The elements in an array of strings are grouped according to their first letter.</span></span> <span data-ttu-id="7bfcf-142">Das Ergebnis der Abfrage ist ein <xref:System.Linq.IGrouping%602>-Typ, der eine öffentliche `Key`-Eigenschaft des Typs `char` und eine <xref:System.Collections.Generic.IEnumerable%601>-Sammlung enthält, die jedes Element in der Gruppierung enthält.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-142">The result of the query is an <xref:System.Linq.IGrouping%602> type that contains a public `Key` property of type `char` and an <xref:System.Collections.Generic.IEnumerable%601> collection that contains each item in the grouping.</span></span>

<span data-ttu-id="7bfcf-143">Das Ergebnis einer `group`-Klausel ist eine Sequenz von Sequenzen.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-143">The result of a `group` clause is a sequence of sequences.</span></span> <span data-ttu-id="7bfcf-144">Verwenden Sie deshalb eine geschachtelte `foreach`-Schleife innerhalb der Schleife, die die Gruppenschlüssel durchläuft – so wie in folgendem Beispiel gezeigt – um auf die einzelnen Elemente innerhalb jeder zurückgegebenen Gruppe zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-144">Therefore, to access the individual elements within each returned group, use a nested `foreach` loop inside the loop that iterates the group keys, as shown in the following example.</span></span>

[!code-csharp[cscsrefQueryKeywords#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#16)]

## <a name="example"></a><span data-ttu-id="7bfcf-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7bfcf-145">Example</span></span>

<span data-ttu-id="7bfcf-146">Dieses Beispiel zeigt, wie zusätzliche Logik auf die Gruppen ausgeführt wird, nachdem Sie diese erstellt haben, indem eine *Fortsetzung* mit `into` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-146">This example shows how to perform additional logic on the groups after you have created them, by using a *continuation* with `into`.</span></span> <span data-ttu-id="7bfcf-147">Weitere Informationen finden Sie unter [into](into.md).</span><span class="sxs-lookup"><span data-stu-id="7bfcf-147">For more information, see [into](into.md).</span></span> <span data-ttu-id="7bfcf-148">Das folgende Beispiel fragt jede Gruppe ab, wobei nur die Gruppe ausgewählt werden soll, dessen Schlüsselwert ein Vokal ist.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-148">The following example queries each group to select only those whose key value is a vowel.</span></span>

[!code-csharp[cscsrefQueryKeywords#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#17)]

## <a name="remarks"></a><span data-ttu-id="7bfcf-149">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="7bfcf-149">Remarks</span></span>

<span data-ttu-id="7bfcf-150">`group`-Klauseln werden zur Kompilierzeit in Aufrufe der <xref:System.Linq.Enumerable.GroupBy%2A>-Methode übersetzt.</span><span class="sxs-lookup"><span data-stu-id="7bfcf-150">At compile time, `group` clauses are translated into calls to the <xref:System.Linq.Enumerable.GroupBy%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bfcf-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bfcf-151">See also</span></span>

- <xref:System.Linq.IGrouping%602>
- <xref:System.Linq.Enumerable.GroupBy%2A>
- <xref:System.Linq.Enumerable.ThenBy%2A>
- <xref:System.Linq.Enumerable.ThenByDescending%2A>
- [<span data-ttu-id="7bfcf-152">Schlüsselwörter für Abfragen</span><span class="sxs-lookup"><span data-stu-id="7bfcf-152">Query Keywords</span></span>](query-keywords.md)
- [<span data-ttu-id="7bfcf-153">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="7bfcf-153">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="7bfcf-154">Erstellen einer geschachtelten Gruppe</span><span class="sxs-lookup"><span data-stu-id="7bfcf-154">Create a nested group</span></span>](../../linq/create-a-nested-group.md)
- [<span data-ttu-id="7bfcf-155">Gruppieren von Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="7bfcf-155">Group query results</span></span>](../../linq/group-query-results.md)
- [<span data-ttu-id="7bfcf-156">Ausführen einer Unterabfrage für eine Gruppierungsoperation</span><span class="sxs-lookup"><span data-stu-id="7bfcf-156">Perform a subquery on a grouping operation</span></span>](../../linq/perform-a-subquery-on-a-grouping-operation.md)
