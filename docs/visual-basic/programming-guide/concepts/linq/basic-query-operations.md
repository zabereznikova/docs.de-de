---
title: Grundlegende Abfragevorgänge
ms.date: 07/20/2015
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
ms.openlocfilehash: efae72c65ad67b4a1b157b67dcc4d4d65f31f77b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266377"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="deed2-102">Grundlegende Abfrageoperationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="deed2-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="deed2-103">Dieses Thema enthält eine kurze Einführung in LINQ-Ausdrücke (Language-Integrated Query) in Visual Basic und zu einigen der typischen Arten von Vorgängen, die Sie in einer Abfrage ausführen.</span><span class="sxs-lookup"><span data-stu-id="deed2-103">This topic provides a brief introduction to Language-Integrated Query (LINQ) expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="deed2-104">Weitere Informationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="deed2-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="deed2-105">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="deed2-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="deed2-106">Abfragen</span><span class="sxs-lookup"><span data-stu-id="deed2-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="deed2-107">Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="deed2-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="deed2-108">Angeben der Datenquelle (Von)</span><span class="sxs-lookup"><span data-stu-id="deed2-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="deed2-109">In einer LINQ-Abfrage besteht der erste Schritt darin, die Datenquelle anzugeben, die Sie abfragen möchten.</span><span class="sxs-lookup"><span data-stu-id="deed2-109">In a LINQ query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="deed2-110">Daher steht `From` die Klausel in einer Abfrage immer an erster Stelle.</span><span class="sxs-lookup"><span data-stu-id="deed2-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="deed2-111">Abfrageoperatoren wählen das Ergebnis basierend auf dem Typ der Quelle aus und formen es.</span><span class="sxs-lookup"><span data-stu-id="deed2-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="deed2-112">Die `From` Klausel gibt die `customers`Datenquelle , und `cust`eine *Bereichsvariable*an , .</span><span class="sxs-lookup"><span data-stu-id="deed2-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="deed2-113">Die Bereichsvariable ist wie eine Schleifeniterationsvariable, mit der Ausnahme, dass in einem Abfrageausdruck keine tatsächliche Iteration stattfindet.</span><span class="sxs-lookup"><span data-stu-id="deed2-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="deed2-114">Wenn die Abfrage ausgeführt wird, `For Each` oft mithilfe einer Schleife, dient die Bereichsvariable als Verweis auf jedes aufeinander folgende Element in `customers`.</span><span class="sxs-lookup"><span data-stu-id="deed2-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="deed2-115">Es ist nicht notwendig, diese explizit anzugeben, da der Compiler den Typ von `cust` ableitet.</span><span class="sxs-lookup"><span data-stu-id="deed2-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="deed2-116">Beispiele für Abfragen, die mit und ohne explizite Eingabe geschrieben wurden, finden Sie unter [Typbeziehungen in Abfragevorgängen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="deed2-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="deed2-117">Weitere Informationen zur Verwendung `From` der Klausel in Visual Basic finden Sie unter [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="deed2-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="deed2-118">Filtern von Daten (Wo)</span><span class="sxs-lookup"><span data-stu-id="deed2-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="deed2-119">Der wahrscheinlich häufigste Abfragevorgang ist das Anwenden eines Filters in Form eines booleschen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="deed2-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="deed2-120">Die Abfrage gibt dann nur die Elemente zurück, für die der Ausdruck wahr ist.</span><span class="sxs-lookup"><span data-stu-id="deed2-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="deed2-121">Eine `Where` Klausel wird verwendet, um die Filterung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="deed2-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="deed2-122">Der Filter gibt an, welche Elemente in der Datenquelle in die resultierende Sequenz eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="deed2-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="deed2-123">Im folgenden Beispiel sind nur Kunden enthalten, die eine Adresse in London haben.</span><span class="sxs-lookup"><span data-stu-id="deed2-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="deed2-124">Sie können logische Operatoren verwenden, z. `And` B. und `Or` zum Kombinieren von Filterausdrücken in einer `Where` Klausel.</span><span class="sxs-lookup"><span data-stu-id="deed2-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="deed2-125">Verwenden Sie beispielsweise den folgenden Code, um nur Kunden zurückzugeben, die aus London stammen und devon nennen:</span><span class="sxs-lookup"><span data-stu-id="deed2-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 <span data-ttu-id="deed2-126">Um Kunden aus London oder Paris zurückzugeben, verwenden Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="deed2-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 <span data-ttu-id="deed2-127">Weitere Informationen zur Verwendung `Where` der Klausel in Visual Basic finden Sie unter [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="deed2-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="deed2-128">Bestelldaten (Bestellung nach)</span><span class="sxs-lookup"><span data-stu-id="deed2-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="deed2-129">Es ist oft bequem, zurückgegebene Daten in einer bestimmten Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="deed2-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="deed2-130">Die `Order By` Klausel bewirkt, dass die Elemente in der zurückgegebenen Sequenz nach einem oder nach bestimmten Feldern sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="deed2-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="deed2-131">Die folgende Abfrage sortiert z. B. die Ergebnisse basierend auf der `Name` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="deed2-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="deed2-132">Da `Name` es sich um eine Zeichenfolge handelt, werden die zurückgegebenen Daten alphabetisch sortiert, von A bis Z.</span><span class="sxs-lookup"><span data-stu-id="deed2-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="deed2-133">Wenn Sie die Ergebnisse andersherum, von Z bis A, sortieren möchten, können Sie die `Order By...Descending`-Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="deed2-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="deed2-134">Der Standardwert `Ascending` `Ascending` ist, wenn weder noch angegeben `Descending` ist.</span><span class="sxs-lookup"><span data-stu-id="deed2-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="deed2-135">Weitere Informationen zur Verwendung `Order By` der Klausel in Visual Basic finden Sie unter [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="deed2-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="deed2-136">Auswählen von Daten (Auswahl)</span><span class="sxs-lookup"><span data-stu-id="deed2-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="deed2-137">Die `Select` Klausel gibt die Form und den Inhalt zurückgegebener Elemente an.</span><span class="sxs-lookup"><span data-stu-id="deed2-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="deed2-138">Sie können z. B. angeben, `Customer` ob die `Customer` Ergebnisse aus vollständigen Objekten, nur einer Eigenschaft, einer Teilmenge von Eigenschaften, einer Kombination von Eigenschaften aus verschiedenen Datenquellen oder einem neuen Ergebnistyp auf der Grundlage einer Berechnung bestehen.</span><span class="sxs-lookup"><span data-stu-id="deed2-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="deed2-139">Wenn die `Select`-Klausel etwas anderes als eine Kopie des Quellelements erzeugt, wird dieser Vorgang als *Projektion* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="deed2-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="deed2-140">Um eine Auflistung abzurufen, die aus vollständigen `Customer` Objekten besteht, wählen Sie die Bereichsvariable selbst aus:</span><span class="sxs-lookup"><span data-stu-id="deed2-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="deed2-141">Wenn `Customer` es sich bei einer Instanz um ein großes Objekt mit vielen Feldern `cust.Name`handelt und Sie nur den Namen abrufen möchten, können Sie auswählen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="deed2-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="deed2-142">Der lokale Typrückschluss erkennt, dass dadurch der `Customer` Ergebnistyp von einer Auflistung von Objekten in eine Auflistung von Zeichenfolgen geändert wird.</span><span class="sxs-lookup"><span data-stu-id="deed2-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="deed2-143">Um mehrere Felder aus der Datenquelle auszuwählen, haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="deed2-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
- <span data-ttu-id="deed2-144">Geben `Select` Sie in der Klausel die Felder an, die Sie in das Ergebnis einbeziehen möchten.</span><span class="sxs-lookup"><span data-stu-id="deed2-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="deed2-145">Der Compiler definiert einen anonymen Typ, der diese Felder als Eigenschaften enthält.</span><span class="sxs-lookup"><span data-stu-id="deed2-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="deed2-146">Weitere Informationen finden Sie unter [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="deed2-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="deed2-147">Da es sich bei den zurückgegebenen Elementen im folgenden Beispiel um Instanzen eines anonymen Typs handelt, können Sie nicht auf den Typ anhand des Namens an anderer Stelle im Code verweisen.</span><span class="sxs-lookup"><span data-stu-id="deed2-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="deed2-148">Der vom Compiler festgelegte Name für den Typ enthält Zeichen, die im normalen Visual Basic-Code ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="deed2-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="deed2-149">Im folgenden Beispiel handelt es sich bei den Elementen `londonCusts4` in der Auflistung, die von der Abfrage zurückgegeben wird, um Instanzen eines anonymen Typs.</span><span class="sxs-lookup"><span data-stu-id="deed2-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="deed2-150">Oder</span><span class="sxs-lookup"><span data-stu-id="deed2-150">-or-</span></span>  
  
- <span data-ttu-id="deed2-151">Definieren Sie einen benannten Typ, der die bestimmten Felder enthält, die Sie in `Select` das Ergebnis einbeziehen möchten, und erstellen und initialisieren Sie Instanzen des Typs in der Klausel.</span><span class="sxs-lookup"><span data-stu-id="deed2-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="deed2-152">Verwenden Sie diese Option nur, wenn Sie einzelne Ergebnisse außerhalb der Auflistung verwenden müssen, in der sie zurückgegeben werden, oder wenn Sie sie als Parameter in Methodenaufrufen übergeben müssen.</span><span class="sxs-lookup"><span data-stu-id="deed2-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="deed2-153">Der Typ `londonCusts5` im folgenden Beispiel ist IEnumerable(Of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="deed2-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="deed2-154">Weitere Informationen zur Verwendung `Select` der Klausel in Visual Basic finden Sie unter [Auswahlklausel](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="deed2-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="deed2-155">Verknüpfen von Daten (Join und Group Join)</span><span class="sxs-lookup"><span data-stu-id="deed2-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="deed2-156">Sie können mehr als eine `From` Datenquelle in der Klausel auf verschiedene Weise kombinieren.</span><span class="sxs-lookup"><span data-stu-id="deed2-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="deed2-157">Der folgende Code verwendet z. B. zwei Datenquellen und kombiniert implizit Eigenschaften aus beiden im Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="deed2-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="deed2-158">Die Abfrage wählt Schüler aus, deren Nachnamen mit einem Vokal beginnen.</span><span class="sxs-lookup"><span data-stu-id="deed2-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> <span data-ttu-id="deed2-159">Sie können diesen Code mit der Liste der Kursteilnehmer ausführen, die unter [Gewusst wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="deed2-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="deed2-160">Das `Join` Schlüsselwort entspricht `INNER JOIN` einem in SQL.</span><span class="sxs-lookup"><span data-stu-id="deed2-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="deed2-161">Es kombiniert zwei Auflistungen basierend auf übereinstimmenden Schlüsselwerten zwischen Elementen in den beiden Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="deed2-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="deed2-162">Die Abfrage gibt alle oder einen Teil der Auflistungselemente zurück, die übereinstimmende Schlüsselwerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="deed2-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="deed2-163">Der folgende Code dupliziert z. B. die Aktion der vorherigen impliziten Verknüpfung.</span><span class="sxs-lookup"><span data-stu-id="deed2-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="deed2-164">`Group Join`kombiniert Auflistungen in einer einzigen hierarchischen Auflistung, genau wie in `LEFT JOIN` SQL.</span><span class="sxs-lookup"><span data-stu-id="deed2-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="deed2-165">Weitere Informationen finden Sie unter [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and Group [Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="deed2-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="deed2-166">Gruppieren von Daten (Gruppe nach)</span><span class="sxs-lookup"><span data-stu-id="deed2-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="deed2-167">Sie können `Group By` eine Klausel hinzufügen, um die Elemente in einem Abfrageergebnis nach einem oder mehreren Feldern der Elemente zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="deed2-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="deed2-168">Der folgende Code gruppiert die Schüler z. B. nach Klassenjahr.</span><span class="sxs-lookup"><span data-stu-id="deed2-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="deed2-169">Wenn Sie diesen Code mit der Liste der Kursteilnehmer ausführen, die unter [Gewusst wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)erstellt wurden, lautet die Ausgabe aus der `For Each` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="deed2-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="deed2-170">Jahr: Junior</span><span class="sxs-lookup"><span data-stu-id="deed2-170">Year: Junior</span></span>  
  
 <span data-ttu-id="deed2-171">Tucker, Michael</span><span class="sxs-lookup"><span data-stu-id="deed2-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="deed2-172">Garcia, Hugo</span><span class="sxs-lookup"><span data-stu-id="deed2-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="deed2-173">Garcia</span><span class="sxs-lookup"><span data-stu-id="deed2-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="deed2-174">Tucker</span><span class="sxs-lookup"><span data-stu-id="deed2-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="deed2-175">Jahr: Senior</span><span class="sxs-lookup"><span data-stu-id="deed2-175">Year: Senior</span></span>  
  
 <span data-ttu-id="deed2-176">Omelchenko</span><span class="sxs-lookup"><span data-stu-id="deed2-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="deed2-177">Osada</span><span class="sxs-lookup"><span data-stu-id="deed2-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="deed2-178">Fakhouri</span><span class="sxs-lookup"><span data-stu-id="deed2-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="deed2-179">Feng</span><span class="sxs-lookup"><span data-stu-id="deed2-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="deed2-180">Adams</span><span class="sxs-lookup"><span data-stu-id="deed2-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="deed2-181">Jahr: Freshman</span><span class="sxs-lookup"><span data-stu-id="deed2-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="deed2-182">Mortensen, Sven</span><span class="sxs-lookup"><span data-stu-id="deed2-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="deed2-183">Garcia</span><span class="sxs-lookup"><span data-stu-id="deed2-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="deed2-184">Die im folgenden Code dargestellte Variante ordnet die Klassenjahre an und ordnet die Schüler dann innerhalb eines jeden Jahres nach Nachnamen an.</span><span class="sxs-lookup"><span data-stu-id="deed2-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="deed2-185">Weitere Informationen `Group By`zu finden Sie unter [Gruppennach-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="deed2-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deed2-186">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="deed2-186">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="deed2-187">Erste Schritte mit LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="deed2-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="deed2-188">Abfragen</span><span class="sxs-lookup"><span data-stu-id="deed2-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="deed2-189">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="deed2-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="deed2-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="deed2-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
