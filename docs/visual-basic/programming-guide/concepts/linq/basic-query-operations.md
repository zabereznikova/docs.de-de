---
title: Grundlegende Abfrageoperationen (Visual Basic)
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
ms.openlocfilehash: 5587a60e97464324659b325e38a18ac25488d30d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="6e9ca-102">Grundlegende Abfrageoperationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e9ca-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="6e9ca-103">Dieses Thema enthält eine kurze Einführung in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Ausdrücke in Visual Basic und einige typischen Arten von Vorgängen, die Sie in einer Abfrage ausführen.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-103">This topic provides a brief introduction to [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="6e9ca-104">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="6e9ca-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="6e9ca-105">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e9ca-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="6e9ca-106">Abfragen</span><span class="sxs-lookup"><span data-stu-id="6e9ca-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [<span data-ttu-id="6e9ca-107">Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e9ca-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="6e9ca-108">Angeben der Datenquelle (von)</span><span class="sxs-lookup"><span data-stu-id="6e9ca-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="6e9ca-109">In einem [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage ist der erste Schritt ist die Datenquelle an, die Sie abfragen möchten.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-109">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="6e9ca-110">Aus diesem Grund die `From` -Klausel in einer Abfrage immer zuerst eintritt.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="6e9ca-111">Abfrageoperatoren auswählen und das Ergebnis basierend auf dem Typ der Quelle Form.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 <span data-ttu-id="6e9ca-112">Die `From` -Klausel gibt die Datenquelle `customers`, und ein *Bereichsvariable*, `cust`.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="6e9ca-113">Die Bereichsvariable ist wie eine Schleifeniterationsvariable mit dem Unterschied, dass in einem Abfrageausdruck keine wirkliche Iteration stattfindet.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="6e9ca-114">Wenn die Abfrage ausgeführt wird, häufig mit einem `For Each` Schleife, die Bereichsvariable dient als Verweis auf jedes darauffolgende Element in `customers`.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="6e9ca-115">Es ist nicht notwendig, diese explizit anzugeben, da der Compiler den Typ von `cust` ableitet.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="6e9ca-116">Beispiele für Abfragen mit und ohne die explizite Typisierung geschrieben, finden Sie unter [Typbeziehungen in Abfrageoperationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="6e9ca-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="6e9ca-117">Weitere Informationen zur Verwendung der `From` -Klausel in Visual Basic finden Sie unter [From-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6e9ca-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="6e9ca-118">Filtern von Daten (Where)</span><span class="sxs-lookup"><span data-stu-id="6e9ca-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="6e9ca-119">Wahrscheinlich wendet üblichste Abfrageoperation einen Filter in Form eines booleschen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="6e9ca-120">Die Abfrage gibt dann nur die Elemente, die für die der Ausdruck "true" aufweist.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="6e9ca-121">Ein `Where` -Klausel wird verwendet, um die Filterung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="6e9ca-122">Der Filter gibt die Elemente in der Datenquelle in der resultierenden Sequenz eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="6e9ca-123">Im folgenden Beispiel sind nur Kunden, die über eine Adresse in London enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 <span data-ttu-id="6e9ca-124">Sie können logische Operatoren wie z. B. `And` und `Or` zum Kombinieren von Filterausdrücken in eine `Where` Klausel.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="6e9ca-125">Damit nur die Kunden zurückgegeben werden, die von London stammen und Namen Devon, verwenden Sie beispielsweise den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="6e9ca-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="6e9ca-126">Um Kunden aus London oder Paris zurückzugeben, verwenden Sie den folgenden Code ein:</span><span class="sxs-lookup"><span data-stu-id="6e9ca-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="6e9ca-127">Weitere Informationen zur Verwendung der `Where` -Klausel in Visual Basic finden Sie unter [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6e9ca-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="6e9ca-128">Sortieren von Daten (Order By)</span><span class="sxs-lookup"><span data-stu-id="6e9ca-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="6e9ca-129">Es ist häufig sinnvoll, um die zurückgegebene Daten in einer bestimmten Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="6e9ca-130">Die `Order By` -Klausel bewirkt, dass die Elemente in der zurückgegebenen Sequenz ein angegebenes Feld oder Felder sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="6e9ca-131">Beispielsweise sortiert die folgende Abfrage die Ergebnisse auf Grundlage der `Name` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="6e9ca-132">Da `Name` ist eine Zeichenfolge, die zurückgegebenen Daten alphabetisch sortiert, von A bis Z.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 <span data-ttu-id="6e9ca-133">Wenn Sie die Ergebnisse andersherum, von Z bis A, sortieren möchten, können Sie die `Order By...Descending`-Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="6e9ca-134">Die Standardeinstellung ist `Ascending` Wenn weder `Ascending` noch `Descending` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="6e9ca-135">Weitere Informationen zur Verwendung der `Order By` -Klausel in Visual Basic finden Sie unter [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6e9ca-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="6e9ca-136">Auswählen von Daten (auswählen)</span><span class="sxs-lookup"><span data-stu-id="6e9ca-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="6e9ca-137">Die `Select` -Klausel gibt die Form und die Inhalte der zurückgegebenen Elemente an.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="6e9ca-138">Sie können beispielsweise angeben, ob die Ergebnisse der vollständigen bestehen `Customer` Objekte aufweist, nur einen `Customer` Eigenschaft, die eine Teilmenge der Eigenschaften, die eine Kombination von Eigenschaften aus verschiedenen Datenquellen oder einem neuen Ergebnistyp auf einer Berechnung basiert.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="6e9ca-139">Wenn die `Select`-Klausel etwas anderes als eine Kopie des Quellelements erzeugt, wird dieser Vorgang als *Projektion* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="6e9ca-140">Abrufen eine Auflistung, aus denen vollständige besteht `Customer` Objekte, wählen Sie die Bereichsvariable selbst:</span><span class="sxs-lookup"><span data-stu-id="6e9ca-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 <span data-ttu-id="6e9ca-141">Wenn eine `Customer` Instanz ist ein großes Objekt, das viele Felder verfügt und Sie abrufen möchten lediglich den Namen, können Sie auswählen `cust.Name`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="6e9ca-142">Lokaler Typrückschluss erkennt, dass dies ändert sich den Ergebnistyp aus einer Auflistung von `Customer` -Objekten, die eine Auflistung von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 <span data-ttu-id="6e9ca-143">Um mehrere Felder aus der Datenquelle auswählen, haben Sie zwei Optionen:</span><span class="sxs-lookup"><span data-stu-id="6e9ca-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
-   <span data-ttu-id="6e9ca-144">In der `Select` -Klausel, geben Sie die Felder im Resultset enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="6e9ca-145">Der Compiler definieren einen anonymen Typ, der diese Felder als Eigenschaften verfügt.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="6e9ca-146">Weitere Informationen finden Sie unter [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="6e9ca-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="6e9ca-147">Da die zurückgegebenen Elemente im folgenden Beispiel Instanzen eines anonymen Typs sind, können nicht Sie in den Typ an anderer Stelle im Code verweisen.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="6e9ca-148">Der vom Compiler festgelegte Name für den Typ enthält Zeichen, die in normaler Visual Basic-Code nicht gültig sind.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="6e9ca-149">Im folgenden Beispiel werden die Elemente in der Auflistung, die von der Abfrage zurückgegeben wird `londonCusts4` sind Instanzen eines anonymen Typs</span><span class="sxs-lookup"><span data-stu-id="6e9ca-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     <span data-ttu-id="6e9ca-150">- oder - </span><span class="sxs-lookup"><span data-stu-id="6e9ca-150">-or-</span></span>  
  
-   <span data-ttu-id="6e9ca-151">Definieren eines benannten Typs, die bestimmte Felder, die Sie verwenden möchten enthält, im Resultset einschließen, erstellen und initialisieren Sie die Instanzen des Typs in, der `Select` Klausel.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="6e9ca-152">Verwenden Sie diese Option nur, wenn Sie keine einzelne Ergebnisse außerhalb der Auflistung verwenden, in dem sie zurückgegeben werden, oder wenn Sie sie als Parameter in Methodenaufrufen übergeben.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="6e9ca-153">Der Typ des `londonCusts5` im folgenden Beispiel wird IEnumerable (Of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="6e9ca-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 <span data-ttu-id="6e9ca-154">Weitere Informationen zur Verwendung der `Select` -Klausel in Visual Basic finden Sie unter [Select-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6e9ca-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="6e9ca-155">Verknüpfen von Daten (Join und Group Join)</span><span class="sxs-lookup"><span data-stu-id="6e9ca-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="6e9ca-156">Sie können mehr als eine Datenquelle im Kombinieren der `From` -Klausel auf unterschiedliche Weise.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="6e9ca-157">Beispielsweise wird der folgende Code verwendet zwei Datenquellen und implizit kombiniert Eigenschaften beide in das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="6e9ca-158">Die Abfrage wählt Studenten, deren Nachnamen mit einem Vokal beginnen.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  <span data-ttu-id="6e9ca-159">Sie können diesen Code ausführen, mit der Liste der Schüler in erstellten [Vorgehensweise: Erstellen Sie eine Liste der Elemente](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="6e9ca-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="6e9ca-160">Die `Join` -Schlüsselwort ist äquivalent zu einer `INNER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="6e9ca-161">Dabei werden zwei Auflistungen, die basierend auf übereinstimmenden Schlüsselwerten zwischen Elementen in die beiden Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="6e9ca-162">Die Abfrage gibt ganz oder teilweise die Elemente der Auflistung, die übereinstimmende Schlüsselwerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="6e9ca-163">Im folgende Code wird z. B. die Aktion des vorherigen impliziten Joins dupliziert.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 <span data-ttu-id="6e9ca-164">`Group Join` Sammlungen in einer einzelnen hierarchischen Auflistung wie kombiniert eine `LEFT JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="6e9ca-165">Weitere Informationen finden Sie unter [Join-Klausel](../../../../visual-basic/language-reference/queries/join-clause.md) und [Group Join-Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6e9ca-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="6e9ca-166">Gruppieren von Daten (Gruppieren nach)</span><span class="sxs-lookup"><span data-stu-id="6e9ca-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="6e9ca-167">Sie können Hinzufügen einer `Group By` -Klausel, um die Elemente in einem Abfrageergebnis gemäß einem oder mehreren Feldern der Elemente zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="6e9ca-168">Im folgende Code werden z. B. Studenten nach Jahr Klasse gruppiert.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 <span data-ttu-id="6e9ca-169">Wenn Sie diesen Code mit der Liste der Schüler in erstellten ausführen [Vorgehensweise: Erstellen Sie eine Liste der Elemente](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), die Ausgabe der `For Each` -Anweisung ist:</span><span class="sxs-lookup"><span data-stu-id="6e9ca-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="6e9ca-170">Jahr: Junior</span><span class="sxs-lookup"><span data-stu-id="6e9ca-170">Year: Junior</span></span>  
  
 <span data-ttu-id="6e9ca-171">Tucker verbleibenden, Michael</span><span class="sxs-lookup"><span data-stu-id="6e9ca-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="6e9ca-172">Garcia Hugo</span><span class="sxs-lookup"><span data-stu-id="6e9ca-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="6e9ca-173">Garcia Sarah</span><span class="sxs-lookup"><span data-stu-id="6e9ca-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="6e9ca-174">Tucker und die verbleibenden Lance</span><span class="sxs-lookup"><span data-stu-id="6e9ca-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="6e9ca-175">Jahr: Senior</span><span class="sxs-lookup"><span data-stu-id="6e9ca-175">Year: Senior</span></span>  
  
 <span data-ttu-id="6e9ca-176">Omelchenko Svetlana</span><span class="sxs-lookup"><span data-stu-id="6e9ca-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="6e9ca-177">Osada Michiko</span><span class="sxs-lookup"><span data-stu-id="6e9ca-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="6e9ca-178">Fakhouri Fadi</span><span class="sxs-lookup"><span data-stu-id="6e9ca-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="6e9ca-179">Feng "," Hanying</span><span class="sxs-lookup"><span data-stu-id="6e9ca-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="6e9ca-180">Kiel, Oliver</span><span class="sxs-lookup"><span data-stu-id="6e9ca-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="6e9ca-181">Jahr: neunte Klasse</span><span class="sxs-lookup"><span data-stu-id="6e9ca-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="6e9ca-182">Mortensen Sven</span><span class="sxs-lookup"><span data-stu-id="6e9ca-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="6e9ca-183">Garcia Cesar</span><span class="sxs-lookup"><span data-stu-id="6e9ca-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="6e9ca-184">Die Variante, die im folgenden Code gezeigt Bestellungen der Jahre Klasse, und klicken Sie dann der Studenten innerhalb jedes Jahr nach dem Nachnamen sortiert.</span><span class="sxs-lookup"><span data-stu-id="6e9ca-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 <span data-ttu-id="6e9ca-185">Weitere Informationen zu `Group By`, finden Sie unter [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6e9ca-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e9ca-186">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e9ca-186">See Also</span></span>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [<span data-ttu-id="6e9ca-187">Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e9ca-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="6e9ca-188">Abfragen</span><span class="sxs-lookup"><span data-stu-id="6e9ca-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="6e9ca-189">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="6e9ca-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="6e9ca-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="6e9ca-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
