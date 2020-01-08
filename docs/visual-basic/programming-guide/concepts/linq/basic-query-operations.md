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
ms.openlocfilehash: b9216dba23f49e4d9fd99687e38f5c13addde8fb
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636873"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="518a2-102">Grundlegende Abfrageoperationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="518a2-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="518a2-103">Dieses Thema bietet eine kurze Einführung in LINQ (Language-Integrated Query)-Ausdrücke in Visual Basic sowie einige typische Arten von Vorgängen, die Sie in einer Abfrage ausführen.</span><span class="sxs-lookup"><span data-stu-id="518a2-103">This topic provides a brief introduction to Language-Integrated Query (LINQ) expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="518a2-104">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="518a2-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="518a2-105">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="518a2-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="518a2-106">Abfragen</span><span class="sxs-lookup"><span data-stu-id="518a2-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="518a2-107">Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="518a2-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="518a2-108">Angeben der Datenquelle (von)</span><span class="sxs-lookup"><span data-stu-id="518a2-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="518a2-109">In einer LINQ-Abfrage besteht der erste Schritt darin, die Datenquelle anzugeben, die Sie Abfragen möchten.</span><span class="sxs-lookup"><span data-stu-id="518a2-109">In a LINQ query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="518a2-110">Daher wird die `From`-Klausel in einer Abfrage immer zuerst angezeigt.</span><span class="sxs-lookup"><span data-stu-id="518a2-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="518a2-111">Abfrage Operatoren wählen und strukturieren das Ergebnis basierend auf dem Typ der Quelle.</span><span class="sxs-lookup"><span data-stu-id="518a2-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="518a2-112">Die `From`-Klausel gibt die Datenquelle, `customers`und eine *Bereichs Variable `cust`an*.</span><span class="sxs-lookup"><span data-stu-id="518a2-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="518a2-113">Die Bereichs Variable ist wie eine Schleifen Iterations Variable, mit dem Unterschied, dass in einem Abfrage Ausdruck keine tatsächliche Iterationen auftritt.</span><span class="sxs-lookup"><span data-stu-id="518a2-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="518a2-114">Wenn die Abfrage ausgeführt wird (häufig mithilfe einer `For Each`-Schleife), fungiert die Bereichs Variable als Verweis auf jedes aufeinander folgende Element in `customers`.</span><span class="sxs-lookup"><span data-stu-id="518a2-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="518a2-115">Es ist nicht notwendig, diese explizit anzugeben, da der Compiler den Typ von `cust` ableitet.</span><span class="sxs-lookup"><span data-stu-id="518a2-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="518a2-116">Beispiele für Abfragen, die mit und ohne explizite Typisierung geschrieben wurden, finden Sie unter [Typbeziehungen in Abfrage Vorgängen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="518a2-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="518a2-117">Weitere Informationen zum Verwenden der `From`-Klausel in Visual Basic finden Sie unter [from-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="518a2-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="518a2-118">Filtern von Daten (wobei)</span><span class="sxs-lookup"><span data-stu-id="518a2-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="518a2-119">Der häufigste Abfrage Vorgang ist wahrscheinlich das Anwenden eines Filters in Form eines booleschen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="518a2-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="518a2-120">Die Abfrage gibt dann nur die Elemente zurück, für die der Ausdruck "true" ist.</span><span class="sxs-lookup"><span data-stu-id="518a2-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="518a2-121">Eine `Where`-Klausel wird verwendet, um die Filterung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="518a2-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="518a2-122">Der Filter gibt an, welche Elemente in der Datenquelle in die resultierende Sequenz eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="518a2-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="518a2-123">Im folgenden Beispiel sind nur die Kunden enthalten, die eine Adresse in London haben.</span><span class="sxs-lookup"><span data-stu-id="518a2-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="518a2-124">Sie können logische Operatoren wie `And` und `Or` verwenden, um Filter Ausdrücke in einer `Where`-Klausel zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="518a2-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="518a2-125">Verwenden Sie z. b. den folgenden Code, um nur die Kunden zurückzugeben, die aus London stammen und deren Name "Devon" ist:</span><span class="sxs-lookup"><span data-stu-id="518a2-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="518a2-126">Um Kunden aus London oder Paris zurückzugeben, verwenden Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="518a2-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="518a2-127">Weitere Informationen zum Verwenden der `Where`-Klausel in Visual Basic finden Sie unter [WHERE-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="518a2-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="518a2-128">Sortieren von Daten (Order by)</span><span class="sxs-lookup"><span data-stu-id="518a2-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="518a2-129">Häufig ist es praktisch, die zurückgegebenen Daten in eine bestimmte Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="518a2-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="518a2-130">Die `Order By`-Klausel bewirkt, dass die Elemente in der zurückgegebenen Sequenz nach einem angegebenen Feld oder Feldern sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="518a2-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="518a2-131">Beispielsweise sortiert die folgende Abfrage die Ergebnisse auf der Grundlage der `Name`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="518a2-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="518a2-132">Da `Name` eine Zeichenfolge ist, werden die zurückgegebenen Daten alphabetisch sortiert, von a bis Z.</span><span class="sxs-lookup"><span data-stu-id="518a2-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="518a2-133">Wenn Sie die Ergebnisse andersherum, von Z bis A, sortieren möchten, können Sie die `Order By...Descending`-Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="518a2-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="518a2-134">Der Standardwert ist `Ascending`, wenn weder `Ascending` noch `Descending` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="518a2-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="518a2-135">Weitere Informationen zum Verwenden der `Order By`-Klausel in Visual Basic finden Sie unter [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="518a2-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="518a2-136">Auswählen von Daten (auswählen)</span><span class="sxs-lookup"><span data-stu-id="518a2-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="518a2-137">Die `Select`-Klausel gibt das Formular und den Inhalt der zurückgegebenen Elemente an.</span><span class="sxs-lookup"><span data-stu-id="518a2-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="518a2-138">Sie können z. b. angeben, ob die Ergebnisse aus kompletten `Customer` Objekten, nur einer `Customer` Eigenschaft, einer Teilmenge von Eigenschaften, einer Kombination von Eigenschaften aus verschiedenen Datenquellen oder einem neuen Ergebnistyp basierend auf einer Berechnung bestehen sollen.</span><span class="sxs-lookup"><span data-stu-id="518a2-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="518a2-139">Wenn die `Select`-Klausel etwas anderes als eine Kopie des Quellelements erzeugt, wird dieser Vorgang als *Projektion* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="518a2-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="518a2-140">Wählen Sie zum Abrufen einer Sammlung, die aus Complete `Customer` Objekten besteht, die Bereichs Variable selbst aus:</span><span class="sxs-lookup"><span data-stu-id="518a2-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="518a2-141">Wenn es sich bei einer `Customer` Instanz um ein großes Objekt mit vielen Feldern handelt und Sie lediglich den Namen abrufen möchten, können Sie `cust.Name`auswählen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="518a2-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="518a2-142">Der lokale Typrückschluss erkennt, dass dadurch der Ergebnistyp aus einer Auflistung von `Customer` Objekten in eine Auflistung von Zeichen folgen geändert wird.</span><span class="sxs-lookup"><span data-stu-id="518a2-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="518a2-143">Wenn Sie mehrere Felder aus der Datenquelle auswählen möchten, haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="518a2-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
- <span data-ttu-id="518a2-144">Geben Sie in der `Select`-Klausel die Felder an, die Sie in das Ergebnis einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="518a2-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="518a2-145">Der Compiler definiert einen anonymen Typ, der diese Felder als Eigenschaften hat.</span><span class="sxs-lookup"><span data-stu-id="518a2-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="518a2-146">Weitere Informationen finden Sie unter [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="518a2-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="518a2-147">Da die zurückgegebenen Elemente im folgenden Beispiel Instanzen eines anonymen Typs sind, können Sie nicht an anderer Stelle im Code auf den Typ verweisen.</span><span class="sxs-lookup"><span data-stu-id="518a2-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="518a2-148">Der vom Compiler angegebene Name für den Typ enthält Zeichen, die in normalem Visual Basic Code nicht gültig sind.</span><span class="sxs-lookup"><span data-stu-id="518a2-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="518a2-149">Im folgenden Beispiel sind die Elemente in der Auflistung, die von der Abfrage in `londonCusts4` zurückgegeben werden, Instanzen eines anonymen Typs.</span><span class="sxs-lookup"><span data-stu-id="518a2-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="518a2-150">\- oder -</span><span class="sxs-lookup"><span data-stu-id="518a2-150">-or-</span></span>  
  
- <span data-ttu-id="518a2-151">Definieren Sie einen benannten Typ, der die Felder enthält, die Sie in das Ergebnis einschließen möchten, und erstellen und initialisieren Sie Instanzen des Typs in der `Select`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="518a2-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="518a2-152">Verwenden Sie diese Option nur, wenn Sie einzelne Ergebnisse außerhalb der Sammlung verwenden müssen, in der Sie zurückgegeben werden, oder wenn Sie Sie als Parameter in Methoden aufrufen übergeben müssen.</span><span class="sxs-lookup"><span data-stu-id="518a2-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="518a2-153">Der `londonCusts5` im folgenden Beispiel ist IEnumerable (of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="518a2-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="518a2-154">Weitere Informationen zum Verwenden der `Select`-Klausel in Visual Basic finden [Sie unter SELECT-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="518a2-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="518a2-155">Verknüpfen von Daten (Join und Group Join)</span><span class="sxs-lookup"><span data-stu-id="518a2-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="518a2-156">Sie können mehr als eine Datenquelle in der `From`-Klausel auf verschiedene Weise kombinieren.</span><span class="sxs-lookup"><span data-stu-id="518a2-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="518a2-157">Im folgenden Code werden z. b. zwei Datenquellen verwendet und implizit Eigenschaften beider Datenquellen im Ergebnis kombiniert.</span><span class="sxs-lookup"><span data-stu-id="518a2-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="518a2-158">Die Abfrage wählt Studenten aus, deren Nachnamen mit einem vowel beginnen.</span><span class="sxs-lookup"><span data-stu-id="518a2-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> <span data-ttu-id="518a2-159">Sie können diesen Code mit der Liste der Studenten ausführen, die unter Gewusst [wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="518a2-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="518a2-160">Das `Join`-Schlüsselwort entspricht einem `INNER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="518a2-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="518a2-161">Es kombiniert zwei Auflistungen basierend auf übereinstimmenden Schlüsselwerten zwischen Elementen in den beiden Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="518a2-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="518a2-162">Die Abfrage gibt alle Elemente oder Teile der Auflistungs Elemente zurück, die übereinstimmende Schlüsselwerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="518a2-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="518a2-163">Mit dem folgenden Code wird beispielsweise die Aktion des vorherigen impliziten Joins dupliziert.</span><span class="sxs-lookup"><span data-stu-id="518a2-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="518a2-164">`Group Join` kombiniert Auflistungen wie eine `LEFT JOIN` in SQL in einer einzelnen hierarchischen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="518a2-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="518a2-165">Weitere Informationen finden Sie unter [Join-Klausel](../../../../visual-basic/language-reference/queries/join-clause.md) und [Group Join-Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="518a2-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="518a2-166">Gruppieren von Daten (Gruppieren nach)</span><span class="sxs-lookup"><span data-stu-id="518a2-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="518a2-167">Sie können eine `Group By`-Klausel hinzufügen, um die Elemente in einem Abfrageergebnis nach einem oder mehreren Feldern der Elemente zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="518a2-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="518a2-168">Im folgenden Code werden z. b. Schüler und Studenten nach Class Year gruppiert.</span><span class="sxs-lookup"><span data-stu-id="518a2-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="518a2-169">Wenn Sie diesen Code mithilfe der Liste der in Gewusst [wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)erstellten Studenten ausführen, lautet die Ausgabe der `For Each`-Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="518a2-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="518a2-170">Jahr: Junior</span><span class="sxs-lookup"><span data-stu-id="518a2-170">Year: Junior</span></span>  
  
 <span data-ttu-id="518a2-171">Tucker, Michael</span><span class="sxs-lookup"><span data-stu-id="518a2-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="518a2-172">Garcia, Hugo</span><span class="sxs-lookup"><span data-stu-id="518a2-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="518a2-173">Garcia, Debra</span><span class="sxs-lookup"><span data-stu-id="518a2-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="518a2-174">Tucker, Lance</span><span class="sxs-lookup"><span data-stu-id="518a2-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="518a2-175">Jahr: Senior</span><span class="sxs-lookup"><span data-stu-id="518a2-175">Year: Senior</span></span>  
  
 <span data-ttu-id="518a2-176">Omeltschenko, Svetlana</span><span class="sxs-lookup"><span data-stu-id="518a2-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="518a2-177">Osada, Michiko</span><span class="sxs-lookup"><span data-stu-id="518a2-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="518a2-178">Fakhuuri, Fadi</span><span class="sxs-lookup"><span data-stu-id="518a2-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="518a2-179">Feng, hanying</span><span class="sxs-lookup"><span data-stu-id="518a2-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="518a2-180">Adams, Terry</span><span class="sxs-lookup"><span data-stu-id="518a2-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="518a2-181">Jahr: Freshman</span><span class="sxs-lookup"><span data-stu-id="518a2-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="518a2-182">Mortensen, Sven</span><span class="sxs-lookup"><span data-stu-id="518a2-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="518a2-183">Garcia, Cesar</span><span class="sxs-lookup"><span data-stu-id="518a2-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="518a2-184">Die im folgenden Code gezeigte Variation ordnet die Klassen Jahre an und ordnet die Schüler/Studenten innerhalb der einzelnen Jahre nach Nachnamen an.</span><span class="sxs-lookup"><span data-stu-id="518a2-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="518a2-185">Weitere Informationen zu `Group By`finden Sie unter [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="518a2-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="518a2-186">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="518a2-186">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="518a2-187">Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="518a2-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="518a2-188">Abfragen</span><span class="sxs-lookup"><span data-stu-id="518a2-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="518a2-189">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="518a2-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="518a2-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="518a2-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
