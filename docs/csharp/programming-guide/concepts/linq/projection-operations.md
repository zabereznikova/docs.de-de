---
title: Projektionsvorgänge (C#)
description: Erfahren Sie mehr über Projektionsvorgänge. Diese Vorgänge transformieren ein Objekt in eine neue Form, die häufig nur aus Eigenschaften besteht, die später verwendet werden.
ms.date: 07/20/2015
ms.assetid: 98df573a-aad9-4b8c-9a71-844be2c4fb41
ms.openlocfilehash: 6128b1bb2e7ba3dbb1b428d475acc307ba931013
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186002"
---
# <a name="projection-operations-c"></a><span data-ttu-id="efeb1-104">Projektionsvorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="efeb1-104">Projection Operations (C#)</span></span>

<span data-ttu-id="efeb1-105">Projektion bezieht sich auf einen Vorgang, bei dem ein Objekt in eine neue Form transformiert wird, die häufig nur aus den Eigenschaften besteht, die anschließend verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="efeb1-105">Projection refers to the operation of transforming an object into a new form that often consists only of those properties that will be subsequently used.</span></span> <span data-ttu-id="efeb1-106">Mithilfe der Projektion können Sie einen neuen Typ erstellen, der aus den einzelnen Objekten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="efeb1-106">By using projection, you can construct a new type that is built from each object.</span></span> <span data-ttu-id="efeb1-107">Sie können eine Eigenschaft projizieren und eine mathematische Funktion für sie ausführen.</span><span class="sxs-lookup"><span data-stu-id="efeb1-107">You can project a property and perform a mathematical function on it.</span></span> <span data-ttu-id="efeb1-108">Sie können auch das ursprüngliche Objekt projizieren, ohne es zu ändern.</span><span class="sxs-lookup"><span data-stu-id="efeb1-108">You can also project the original object without changing it.</span></span>  
  
 <span data-ttu-id="efeb1-109">Die Methoden des Standardabfrageoperators, die Projektion ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="efeb1-109">The standard query operator methods that perform projection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="efeb1-110">Methoden</span><span class="sxs-lookup"><span data-stu-id="efeb1-110">Methods</span></span>  
  
|<span data-ttu-id="efeb1-111">Methodenname</span><span class="sxs-lookup"><span data-stu-id="efeb1-111">Method Name</span></span>|<span data-ttu-id="efeb1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efeb1-112">Description</span></span>|<span data-ttu-id="efeb1-113">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="efeb1-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="efeb1-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="efeb1-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="efeb1-115">Auswählen</span><span class="sxs-lookup"><span data-stu-id="efeb1-115">Select</span></span>|<span data-ttu-id="efeb1-116">Projektwerte, die auf einer Transform-Funktion basieren.</span><span class="sxs-lookup"><span data-stu-id="efeb1-116">Projects values that are based on a transform function.</span></span>|`select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="efeb1-117">SelectMany</span><span class="sxs-lookup"><span data-stu-id="efeb1-117">SelectMany</span></span>|<span data-ttu-id="efeb1-118">Projiziert Sequenzen von Werten, die auf einer Transform-Funktion basieren, und fasst diese dann in eine Sequenz zusammen.</span><span class="sxs-lookup"><span data-stu-id="efeb1-118">Projects sequences of values that are based on a transform function and then flattens them into one sequence.</span></span>|<span data-ttu-id="efeb1-119">Mehrere `from`-Klauseln verwenden</span><span class="sxs-lookup"><span data-stu-id="efeb1-119">Use multiple `from` clauses</span></span>|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="efeb1-120">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="efeb1-120">Query Expression Syntax Examples</span></span>  
  
### <a name="select"></a><span data-ttu-id="efeb1-121">Auswählen</span><span class="sxs-lookup"><span data-stu-id="efeb1-121">Select</span></span>  

 <span data-ttu-id="efeb1-122">Im folgenden Beispiel wird die `select`-Klausel verwendet, um den ersten Buchstaben jeder Zeichenfolge in einer Liste von Zeichenfolgen zu projizieren.</span><span class="sxs-lookup"><span data-stu-id="efeb1-122">The following example uses the `select` clause to project the first letter from each string in a list of strings.</span></span>  
  
```csharp  
List<string> words = new List<string>() { "an", "apple", "a", "day" };  
  
var query = from word in words  
            select word.Substring(0, 1);  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    a  
    a  
    a  
    d  
*/  
```  
  
### <a name="selectmany"></a><span data-ttu-id="efeb1-123">SelectMany</span><span class="sxs-lookup"><span data-stu-id="efeb1-123">SelectMany</span></span>  

 <span data-ttu-id="efeb1-124">Im folgenden Beispiel wird die `from`-Klausel verwendet, um jedes Wort aus jeder Zeichenfolge in einer Liste von Zeichenfolgen zu projizieren.</span><span class="sxs-lookup"><span data-stu-id="efeb1-124">The following example uses multiple `from` clauses  to project each word from each string in a list of strings.</span></span>  
  
```csharp  
List<string> phrases = new List<string>() { "an apple a day", "the quick brown fox" };  
  
var query = from phrase in phrases  
            from word in phrase.Split(' ')  
            select word;  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    an  
    apple  
    a  
    day  
    the  
    quick  
    brown  
    fox  
*/  
```  
  
## <a name="select-versus-selectmany"></a><span data-ttu-id="efeb1-125">Select im Vergleich zu SelectMany</span><span class="sxs-lookup"><span data-stu-id="efeb1-125">Select versus SelectMany</span></span>  

 <span data-ttu-id="efeb1-126">Die Arbeit von jeweils `Select()` und `SelectMany()` besteht darin, einen Ergebniswert (oder Werte) aus den Quellwerten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="efeb1-126">The work of both `Select()` and `SelectMany()` is to produce a result value (or values) from source values.</span></span> <span data-ttu-id="efeb1-127">`Select()` generiert einen Ergebniswert für jeden Quellwert.</span><span class="sxs-lookup"><span data-stu-id="efeb1-127">`Select()` produces one result value for every source value.</span></span> <span data-ttu-id="efeb1-128">Das Ergebnis ist daher eine Auflistung, die über die gleiche Anzahl von Elementen wie die Quellauflistung verfügt.</span><span class="sxs-lookup"><span data-stu-id="efeb1-128">The overall result is therefore a collection that has the same number of elements as the source collection.</span></span> <span data-ttu-id="efeb1-129">Im Gegensatz dazu erzeugt `SelectMany()` ein einziges Gesamtergebnis, das verkettete untergeordnete Auflistungen aus jedem Quellwert enthält.</span><span class="sxs-lookup"><span data-stu-id="efeb1-129">In contrast, `SelectMany()` produces a single overall result that contains concatenated sub-collections from each source value.</span></span> <span data-ttu-id="efeb1-130">Die Transform-Funktion, die als Argument an `SelectMany()` übergeben wird, muss eine aufzählbare Sequenz von Werten für jeden Quellwert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="efeb1-130">The transform function that is passed as an argument to `SelectMany()` must return an enumerable sequence of values for each source value.</span></span> <span data-ttu-id="efeb1-131">Diese aufzählbaren Sequenzen werden anschließend von `SelectMany()` zu einer großen Sequenz verkettet.</span><span class="sxs-lookup"><span data-stu-id="efeb1-131">These enumerable sequences are then concatenated by `SelectMany()` to create one large sequence.</span></span>  
  
 <span data-ttu-id="efeb1-132">Die folgenden zwei Abbildungen zeigen den konzeptionellen Unterschied zwischen den Aktionen der beiden Methoden.</span><span class="sxs-lookup"><span data-stu-id="efeb1-132">The following two illustrations show the conceptual difference between the actions of these two methods.</span></span> <span data-ttu-id="efeb1-133">In jedem Fall wird davon ausgegangen, dass die Auswahlfunktion (Transform) das Array von Blumen aus jedem Quellwert auswählt.</span><span class="sxs-lookup"><span data-stu-id="efeb1-133">In each case, assume that the selector (transform) function selects the array of flowers from each source value.</span></span>  
  
 <span data-ttu-id="efeb1-134">Die Abbildung zeigt, wie `Select()` eine Auflistung zurückgibt, die über die gleiche Anzahl von Elementen wie die Quellauflistung verfügt.</span><span class="sxs-lookup"><span data-stu-id="efeb1-134">This illustration depicts how `Select()` returns a collection that has the same number of elements as the source collection.</span></span>  
  
 ![Grafische Darstellung der Aktion Select&#40;&#41;](./media/projection-operations/select-action-graphic.png)  
  
 <span data-ttu-id="efeb1-136">Diese Abbildung zeigt, wie `SelectMany()` die Zwischenmodus-Sequenz von Arrays in einem Endergebniswert verkettet, der jeden Wert aus jedem Zwischenmodus-Array enthält.</span><span class="sxs-lookup"><span data-stu-id="efeb1-136">This illustration depicts how `SelectMany()` concatenates the intermediate sequence of arrays into one final result value that contains each value from each intermediate array.</span></span>  
  
 ![Grafische Darstellung der Aktion SelectMany&#40;&#41;](./media/projection-operations/select-many-action-graphic.png )  
  
### <a name="code-example"></a><span data-ttu-id="efeb1-138">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="efeb1-138">Code Example</span></span>  

 <span data-ttu-id="efeb1-139">Im folgenden Beispiel wird das Verhalten von `Select()` und `SelectMany()` verglichen.</span><span class="sxs-lookup"><span data-stu-id="efeb1-139">The following example compares the behavior of `Select()` and `SelectMany()`.</span></span> <span data-ttu-id="efeb1-140">Der Code erstellt eine „Bouquet“ von Blumen, indem er die ersten beiden Elemente aus jeder Liste der Blumennamen in der Quellauflistung aufführt.</span><span class="sxs-lookup"><span data-stu-id="efeb1-140">The code creates a "bouquet" of flowers by taking the first two items from each list of flower names in the source collection.</span></span> <span data-ttu-id="efeb1-141">In diesem Beispiel ist der „einzelne Wert“, den die Transformationsfunktion <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> verwendet, selbst eine Auflistung von Werten.</span><span class="sxs-lookup"><span data-stu-id="efeb1-141">In this example, the "single value" that the transform function <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> uses is itself a collection of values.</span></span> <span data-ttu-id="efeb1-142">Dies erfordert die zusätzliche `foreach`-Schleife, um jede Zeichenfolge in den einzelnen Untersequenzen aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="efeb1-142">This requires the extra `foreach` loop in order to enumerate each string in each sub-sequence.</span></span>  
  
```csharp  
class Bouquet  
{  
    public List<string> Flowers { get; set; }  
}  
  
static void SelectVsSelectMany()  
{  
    List<Bouquet> bouquets = new List<Bouquet>() {  
        new Bouquet { Flowers = new List<string> { "sunflower", "daisy", "daffodil", "larkspur" }},  
        new Bouquet{ Flowers = new List<string> { "tulip", "rose", "orchid" }},  
        new Bouquet{ Flowers = new List<string> { "gladiolis", "lily", "snapdragon", "aster", "protea" }},  
        new Bouquet{ Flowers = new List<string> { "larkspur", "lilac", "iris", "dahlia" }}  
    };  
  
    // *********** Select ***********
    IEnumerable<List<string>> query1 = bouquets.Select(bq => bq.Flowers);  
  
    // ********* SelectMany *********  
    IEnumerable<string> query2 = bouquets.SelectMany(bq => bq.Flowers);  
  
    Console.WriteLine("Results by using Select():");  
    // Note the extra foreach loop here.  
    foreach (IEnumerable<String> collection in query1)  
        foreach (string item in collection)  
            Console.WriteLine(item);  
  
    Console.WriteLine("\nResults by using SelectMany():");  
    foreach (string item in query2)  
        Console.WriteLine(item);  
  
    /* This code produces the following output:  
  
       Results by using Select():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
  
       Results by using SelectMany():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
    */  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="efeb1-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efeb1-143">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="efeb1-144">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="efeb1-144">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="efeb1-145">select-Klausel</span><span class="sxs-lookup"><span data-stu-id="efeb1-145">select clause</span></span>](../../../language-reference/keywords/select-clause.md)
- [<span data-ttu-id="efeb1-146">Vorgehensweise: Auffüllen von Objektsammlungen mit Daten aus mehreren Quellen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="efeb1-146">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
- [<span data-ttu-id="efeb1-147">Vorgehensweise: Aufteilen einer Datei in mehrere Dateien durch das Verwenden von Gruppen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="efeb1-147">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
