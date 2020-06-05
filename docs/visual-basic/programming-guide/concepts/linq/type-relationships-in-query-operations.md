---
title: Typbeziehungen in Abfragevorgängen
ms.date: 07/20/2015
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
ms.openlocfilehash: 73a287541ddf115510bf6ab5c830eafac370cc3a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406728"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a><span data-ttu-id="abe1a-102">Typbeziehungen in Abfrageoperationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abe1a-102">Type Relationships in Query Operations (Visual Basic)</span></span>

<span data-ttu-id="abe1a-103">Variablen, die in LINQ-Abfrage Vorgängen (Language-Integrated Query) verwendet werden, sind stark typisiert und müssen miteinander kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="abe1a-103">Variables used in Language-Integrated Query (LINQ) query operations are strongly typed and must be compatible with each other.</span></span> <span data-ttu-id="abe1a-104">Starke Typisierung wird in der Datenquelle, in der Abfrage selbst und in der Abfrage Ausführung verwendet.</span><span class="sxs-lookup"><span data-stu-id="abe1a-104">Strong typing is used in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="abe1a-105">In der folgenden Abbildung sind Begriffe aufgeführt, die zum Beschreiben einer LINQ-Abfrage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="abe1a-105">The following illustration identifies terms used to describe a LINQ query.</span></span> <span data-ttu-id="abe1a-106">Weitere Informationen zu den Teilen einer Abfrage finden Sie unter [grundlegende Abfrage Vorgänge (Visual Basic)](basic-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="abe1a-106">For more information about the parts of a query, see [Basic Query Operations (Visual Basic)](basic-query-operations.md).</span></span>

![Screenshot, der eine Pseudo Code-Abfrage mit hervorgehobenen Elementen anzeigt.](./media/type-relationships-in-query-operations/linq-query-description-terms.png)

<span data-ttu-id="abe1a-108">Der Typ der Bereichs Variablen in der Abfrage muss mit dem Typ der Elemente in der Datenquelle kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="abe1a-108">The type of the range variable in the query must be compatible with the type of the elements in the data source.</span></span> <span data-ttu-id="abe1a-109">Der Typ der Abfrage Variablen muss mit dem in der-Klausel definierten Sequence-Element kompatibel sein `Select` .</span><span class="sxs-lookup"><span data-stu-id="abe1a-109">The type of the query variable must be compatible with the sequence element defined in the `Select` clause.</span></span> <span data-ttu-id="abe1a-110">Schließlich muss der Typ der Sequenz Elemente auch mit dem Typ der Schleifen Steuerungsvariablen kompatibel sein, die in der Anweisung verwendet wird `For Each` , die die Abfrage ausführt.</span><span class="sxs-lookup"><span data-stu-id="abe1a-110">Finally, the type of the sequence elements also must be compatible with the type of the loop control variable that is used in the `For Each` statement that executes the query.</span></span> <span data-ttu-id="abe1a-111">Diese starke Typisierung vereinfacht die Identifizierung von Typfehlern zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="abe1a-111">This strong typing facilitates identification of type errors at compile time.</span></span>

<span data-ttu-id="abe1a-112">Mit Visual Basic wird die starke Typisierung durch Implementieren des lokalen Typrückschlusses, auch als *implizite Typisierung*bezeichnet, vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="abe1a-112">Visual Basic makes strong typing convenient by implementing local type inference, also known as *implicit typing*.</span></span> <span data-ttu-id="abe1a-113">Diese Funktion wird im vorherigen Beispiel verwendet, und Sie sehen, dass Sie in den LINQ-Beispielen und in der Dokumentation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="abe1a-113">That feature is used in the previous example, and you will see it used throughout the LINQ samples and documentation.</span></span> <span data-ttu-id="abe1a-114">In Visual Basic wird der lokale Typrückschluss einfach mithilfe einer- `Dim` Anweisung ohne eine- `As` Klausel erreicht.</span><span class="sxs-lookup"><span data-stu-id="abe1a-114">In Visual Basic, local type inference is accomplished simply by using a `Dim` statement without an `As` clause.</span></span> <span data-ttu-id="abe1a-115">Im folgenden Beispiel `city` ist als Zeichenfolge stark typisiert.</span><span class="sxs-lookup"><span data-stu-id="abe1a-115">In the following example, `city` is strongly typed as a string.</span></span>

[!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="abe1a-116">Der lokale Typrückschluss funktioniert nur `Option Infer` , wenn auf festgelegt ist `On` .</span><span class="sxs-lookup"><span data-stu-id="abe1a-116">Local type inference works only when `Option Infer` is set to `On`.</span></span> <span data-ttu-id="abe1a-117">Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="abe1a-117">For more information, see [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md).</span></span>

<span data-ttu-id="abe1a-118">Auch wenn Sie einen lokalen Typrückschluss in einer Abfrage verwenden, sind die gleichen Typbeziehungen zwischen den Variablen in der Datenquelle, der Abfrage Variablen und der Abfrage Ausführungs Schleife vorhanden.</span><span class="sxs-lookup"><span data-stu-id="abe1a-118">However, even if you use local type inference in a query, the same type relationships are present among the variables in the data source, the query variable, and the query execution loop.</span></span> <span data-ttu-id="abe1a-119">Es ist hilfreich, wenn Sie LINQ-Abfragen schreiben oder mit den Beispielen und Codebeispielen in der Dokumentation arbeiten.</span><span class="sxs-lookup"><span data-stu-id="abe1a-119">It is useful to have a basic understanding of these type relationships when you are writing LINQ queries, or working with the samples and code examples in the documentation.</span></span>

<span data-ttu-id="abe1a-120">Möglicherweise müssen Sie einen expliziten Typ für eine Bereichs Variable angeben, der nicht mit dem von der Datenquelle zurückgegebenen Typ identisch ist.</span><span class="sxs-lookup"><span data-stu-id="abe1a-120">You may need to specify an explicit type for a range variable that does not match the type returned from the data source.</span></span> <span data-ttu-id="abe1a-121">Sie können den Typ der Bereichs Variablen angeben, indem Sie eine- `As` Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="abe1a-121">You can specify the type of the range variable by using an `As` clause.</span></span> <span data-ttu-id="abe1a-122">Dies führt jedoch zu einem Fehler, wenn die Konvertierung eine einschränkende [Konvertierung](../../language-features/data-types/widening-and-narrowing-conversions.md) ist und `Option Strict` auf festgelegt ist `On` .</span><span class="sxs-lookup"><span data-stu-id="abe1a-122">However, this results in an error if the conversion is a [narrowing conversion](../../language-features/data-types/widening-and-narrowing-conversions.md) and `Option Strict` is set to `On`.</span></span> <span data-ttu-id="abe1a-123">Daher wird empfohlen, die Konvertierung der aus der Datenquelle abgerufenen Werte durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="abe1a-123">Therefore, we recommend that you perform the conversion on the values retrieved from the data source.</span></span> <span data-ttu-id="abe1a-124">Mithilfe der-Methode können Sie die Werte aus der Datenquelle in den expliziten Range-Variablentyp konvertieren <xref:System.Linq.Enumerable.Cast%2A> .</span><span class="sxs-lookup"><span data-stu-id="abe1a-124">You can convert the values from the data source to the explicit range variable type by using the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="abe1a-125">Sie können auch die in der-Klausel ausgewählten Werte in `Select` einen expliziten Typ umwandeln, der sich vom Typ der Bereichs Variablen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="abe1a-125">You can also cast the values selected in the `Select` clause to an explicit type that is different from the type of the range variable.</span></span> <span data-ttu-id="abe1a-126">Diese Punkte sind im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="abe1a-126">These points are illustrated in the following code.</span></span>

[!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]

## <a name="queries-that-return-entire-elements-of-the-source-data"></a><span data-ttu-id="abe1a-127">Abfragen, die ganze Elemente der Quelldaten zurückgeben</span><span class="sxs-lookup"><span data-stu-id="abe1a-127">Queries That Return Entire Elements of the Source Data</span></span>

<span data-ttu-id="abe1a-128">Das folgende Beispiel zeigt einen LINQ-Abfrage Vorgang, der eine Sequenz von Elementen zurückgibt, die aus den Quelldaten ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="abe1a-128">The following example shows a LINQ query operation that returns a sequence of elements selected from the source data.</span></span> <span data-ttu-id="abe1a-129">Die Quelle, `names` , enthält ein Array von Zeichen folgen, und die Abfrageausgabe ist eine Sequenz mit Zeichen folgen, die mit dem Buchstaben "M" beginnen.</span><span class="sxs-lookup"><span data-stu-id="abe1a-129">The source, `names`, contains an array of strings, and the query output is a sequence containing strings that start with the letter M.</span></span>

[!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]

<span data-ttu-id="abe1a-130">Dies entspricht dem folgenden Code, ist aber viel kürzer und einfacher zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="abe1a-130">This is equivalent to the following code, but is much shorter and easier to write.</span></span> <span data-ttu-id="abe1a-131">Die Abhängigkeit von lokalem Typrückschluss in Abfragen ist der bevorzugte Stil in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="abe1a-131">Reliance on local type inference in queries is the preferred style in Visual Basic.</span></span>

[!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]

<span data-ttu-id="abe1a-132">Die folgenden Beziehungen sind in beiden vorherigen Codebeispielen vorhanden, unabhängig davon, ob die Typen implizit oder explizit bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="abe1a-132">The following relationships exist in both of the previous code examples, whether the types are determined implicitly or explicitly.</span></span>

1. <span data-ttu-id="abe1a-133">Der Typ der Elemente in der Datenquelle, `names` , ist der Typ der Bereichs Variablen `name` in der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="abe1a-133">The type of the elements in the data source, `names`, is the type of the range variable, `name`, in the query.</span></span>

2. <span data-ttu-id="abe1a-134">Der Typ des ausgewählten Objekts, `name` , bestimmt den Typ der Abfrage Variablen `mNames` .</span><span class="sxs-lookup"><span data-stu-id="abe1a-134">The type of the object that is selected, `name`, determines the type of the query variable, `mNames`.</span></span> <span data-ttu-id="abe1a-135">Hier `name` ist eine Zeichenfolge, sodass die Abfrage Variable in Visual Basic IEnumerable (of String) ist.</span><span class="sxs-lookup"><span data-stu-id="abe1a-135">Here `name` is a string, so the query variable is IEnumerable(Of String) in Visual Basic.</span></span>

3. <span data-ttu-id="abe1a-136">Die in definierte Abfrage `mNames` wird in der- `For Each` Schleife ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="abe1a-136">The query defined in `mNames` is executed in the `For Each` loop.</span></span> <span data-ttu-id="abe1a-137">Die Schleife durchläuft das Ergebnis der Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="abe1a-137">The loop iterates over the result of executing the query.</span></span> <span data-ttu-id="abe1a-138">Da `mNames` beim Ausführen von eine Sequenz von Zeichen folgen zurückgibt, ist die Schleifen Iterations Variable, `nm` , ebenfalls eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="abe1a-138">Because `mNames`, when it is executed, will return a sequence of strings, the loop iteration variable, `nm`, also is a string.</span></span>

## <a name="queries-that-return-one-field-from-selected-elements"></a><span data-ttu-id="abe1a-139">Abfragen, die ein Feld aus ausgewählten Elementen zurückgeben</span><span class="sxs-lookup"><span data-stu-id="abe1a-139">Queries That Return One Field from Selected Elements</span></span>

<span data-ttu-id="abe1a-140">Das folgende Beispiel zeigt einen [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] Abfrage Vorgang, der eine Sequenz mit nur einem Teil der einzelnen aus der Datenquelle ausgewählten Elemente zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="abe1a-140">The following example shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that returns a sequence containing only one part of each element selected from the data source.</span></span> <span data-ttu-id="abe1a-141">Die Abfrage nimmt eine Auflistung von `Customer` -Objekten als Datenquelle an und projiziert nur die- `Name` Eigenschaft im Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="abe1a-141">The query takes a collection of `Customer` objects as its data source and projects only the `Name` property in the result.</span></span> <span data-ttu-id="abe1a-142">Da der Kunden Name eine Zeichenfolge ist, erzeugt die Abfrage eine Sequenz von Zeichen folgen als Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="abe1a-142">Because the customer name is a string, the query produces a sequence of strings as output.</span></span>

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim custNames = From cust In customers
                Where cust.City = "London"
                Select cust.Name

For Each custName In custNames
    Console.WriteLine(custName)
Next
```

<span data-ttu-id="abe1a-143">Die Beziehungen zwischen Variablen ähneln denen im einfacheren Beispiel.</span><span class="sxs-lookup"><span data-stu-id="abe1a-143">The relationships between variables are like those in the simpler example.</span></span>

1. <span data-ttu-id="abe1a-144">Der Typ der Elemente in der Datenquelle, `customers` , ist der Typ der Bereichs Variablen `cust` in der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="abe1a-144">The type of the elements in the data source, `customers`, is the type of the range variable, `cust`, in the query.</span></span> <span data-ttu-id="abe1a-145">In diesem Beispiel ist dieser Typ `Customer` .</span><span class="sxs-lookup"><span data-stu-id="abe1a-145">In this example, that type is `Customer`.</span></span>

2. <span data-ttu-id="abe1a-146">Die- `Select` Anweisung gibt die- `Name` Eigenschaft der einzelnen- `Customer` Objekte anstelle des gesamten-Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="abe1a-146">The `Select` statement returns the `Name` property of each `Customer` object instead of the whole object.</span></span> <span data-ttu-id="abe1a-147">Da `Name` eine Zeichenfolge ist, ist die Abfrage Variable, `custNames` , erneut IEnumerable (of String), nicht von `Customer` .</span><span class="sxs-lookup"><span data-stu-id="abe1a-147">Because `Name` is a string, the query variable, `custNames`, will again be IEnumerable(Of String), not of `Customer`.</span></span>

3. <span data-ttu-id="abe1a-148">Da `custNames` eine Sequenz von Zeichen folgen darstellt, `For Each` muss die Iterations Variable der-Schleife `custName` eine Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="abe1a-148">Because `custNames` represents a sequence of strings, the `For Each` loop's iteration variable, `custName`, must be a string.</span></span>

<span data-ttu-id="abe1a-149">Ohne den lokalen Typrückschluss wäre das vorherige Beispiel etwas mühsamer zu schreiben und zu verstehen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="abe1a-149">Without local type inference, the previous example would be more cumbersome to write and to understand, as the following example shows.</span></span>

```vb
' Method GetTable returns a table of Customer objects.
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()
 Dim custNames As IEnumerable(Of String) =
     From cust As Customer In customers
     Where cust.City = "London"
     Select cust.Name

 For Each custName As String In custNames
     Console.WriteLine(custName)
 Next
```

## <a name="queries-that-require-anonymous-types"></a><span data-ttu-id="abe1a-150">Abfragen, die anonyme Typen erfordern</span><span class="sxs-lookup"><span data-stu-id="abe1a-150">Queries That Require Anonymous Types</span></span>

<span data-ttu-id="abe1a-151">Das folgende Beispiel zeigt eine komplexere Situation.</span><span class="sxs-lookup"><span data-stu-id="abe1a-151">The following example shows a more complex situation.</span></span> <span data-ttu-id="abe1a-152">Im vorherigen Beispiel war es unpraktisch, Typen für alle Variablen explizit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="abe1a-152">In the previous example, it was inconvenient to specify types for all the variables explicitly.</span></span> <span data-ttu-id="abe1a-153">In diesem Beispiel ist es nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="abe1a-153">In this example, it is impossible.</span></span> <span data-ttu-id="abe1a-154">Anstatt ganze `Customer` Elemente aus der Datenquelle oder ein einzelnes Feld aus jedem Element auszuwählen, `Select` gibt die-Klausel in dieser Abfrage zwei Eigenschaften des ursprünglichen `Customer` -Objekts zurück: `Name` und `City` .</span><span class="sxs-lookup"><span data-stu-id="abe1a-154">Instead of selecting entire `Customer` elements from the data source, or a single field from each element, the `Select` clause in this query returns two properties of the original `Customer` object: `Name` and `City`.</span></span> <span data-ttu-id="abe1a-155">Als Antwort auf die- `Select` Klausel definiert der Compiler einen anonymen Typ, der diese beiden Eigenschaften enthält.</span><span class="sxs-lookup"><span data-stu-id="abe1a-155">In response to the `Select` clause, the compiler defines an anonymous type that contains those two properties.</span></span> <span data-ttu-id="abe1a-156">Das Ergebnis der Ausführung von `nameCityQuery` in der- `For Each` Schleife ist eine Auflistung von Instanzen des neuen anonymen Typs.</span><span class="sxs-lookup"><span data-stu-id="abe1a-156">The result of executing `nameCityQuery` in the `For Each` loop is a collection of instances of the new anonymous type.</span></span> <span data-ttu-id="abe1a-157">Da der anonyme Typ keinen verwendbaren Namen hat, können Sie den Typ `nameCityQuery` oder nicht `custInfo` explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="abe1a-157">Because the anonymous type has no usable name, you cannot specify the type of `nameCityQuery` or `custInfo` explicitly.</span></span> <span data-ttu-id="abe1a-158">Das heißt, bei einem anonymen Typ haben Sie keinen Typnamen, der anstelle von in verwendet werden kann `String` `IEnumerable(Of String)` .</span><span class="sxs-lookup"><span data-stu-id="abe1a-158">That is, with an anonymous type, you have no type name to use in place of `String` in `IEnumerable(Of String)`.</span></span> <span data-ttu-id="abe1a-159">Weitere Informationen finden Sie unter [Anonyme Typen](../../language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="abe1a-159">For more information, see [Anonymous Types](../../language-features/objects-and-classes/anonymous-types.md).</span></span>

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim nameCityQuery = From cust In customers
                    Where cust.City = "London"
                    Select cust.Name, cust.City

For Each custInfo In nameCityQuery
    Console.WriteLine(custInfo.Name)
Next
```

<span data-ttu-id="abe1a-160">Obwohl es nicht möglich ist, Typen für alle Variablen im vorherigen Beispiel anzugeben, bleiben die Beziehungen unverändert.</span><span class="sxs-lookup"><span data-stu-id="abe1a-160">Although it is not possible to specify types for all the variables in the previous example, the relationships remain the same.</span></span>

1. <span data-ttu-id="abe1a-161">Der Typ der Elemente in der Datenquelle ist wieder der Typ der Bereichs Variablen in der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="abe1a-161">The type of the elements in the data source is again the type of the range variable in the query.</span></span> <span data-ttu-id="abe1a-162">In diesem Beispiel `cust` ist eine Instanz von `Customer` .</span><span class="sxs-lookup"><span data-stu-id="abe1a-162">In this example, `cust` is an instance of `Customer`.</span></span>

2. <span data-ttu-id="abe1a-163">Da die- `Select` Anweisung einen anonymen Typ erzeugt, muss die Abfrage Variable `nameCityQuery` implizit als anonymer Typ typisiert werden.</span><span class="sxs-lookup"><span data-stu-id="abe1a-163">Because the `Select` statement produces an anonymous type, the query variable, `nameCityQuery`, must be implicitly typed as an anonymous type.</span></span> <span data-ttu-id="abe1a-164">Ein anonymer Typ hat keinen verwendbaren Namen und kann daher nicht explizit angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="abe1a-164">An anonymous type has no usable name, and therefore cannot be specified explicitly.</span></span>

3. <span data-ttu-id="abe1a-165">Der Typ der Iterations Variablen in der `For Each` Schleife ist der anonyme Typ, der in Schritt 2 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="abe1a-165">The type of the iteration variable in the `For Each` loop is the anonymous type created in step 2.</span></span> <span data-ttu-id="abe1a-166">Da der Typ keinen verwendbaren Namen hat, muss der Typ der Schleifen Iterations Variablen implizit bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="abe1a-166">Because the type has no usable name, the type of the loop iteration variable must be determined implicitly.</span></span>

## <a name="see-also"></a><span data-ttu-id="abe1a-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="abe1a-167">See also</span></span>

- [<span data-ttu-id="abe1a-168">Erste Schritte mit LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="abe1a-168">Getting Started with LINQ in Visual Basic</span></span>](getting-started-with-linq.md)
- [<span data-ttu-id="abe1a-169">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="abe1a-169">Anonymous Types</span></span>](../../language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="abe1a-170">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="abe1a-170">Local Type Inference</span></span>](../../language-features/variables/local-type-inference.md)
- [<span data-ttu-id="abe1a-171">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="abe1a-171">Introduction to LINQ in Visual Basic</span></span>](../../language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="abe1a-172">LINQ</span><span class="sxs-lookup"><span data-stu-id="abe1a-172">LINQ</span></span>](../../language-features/linq/index.md)
- [<span data-ttu-id="abe1a-173">Abfragen</span><span class="sxs-lookup"><span data-stu-id="abe1a-173">Queries</span></span>](../../../language-reference/queries/index.md)
