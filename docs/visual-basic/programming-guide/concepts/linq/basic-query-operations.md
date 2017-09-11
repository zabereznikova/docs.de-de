---
title: Grundlegende Abfrageoperationen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
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
caps.latest.revision: 37
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1ced446d6646bd26b9169f5894138e12a38efde7
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="be4d5-102">Grundlegende Abfrageoperationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be4d5-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="be4d5-103">Dieses Thema enthält eine kurze Einführung in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] Ausdrücke in Visual Basic und einige typische Arten von Vorgängen, die Sie in einer Abfrage ausführen.</span><span class="sxs-lookup"><span data-stu-id="be4d5-103">This topic provides a brief introduction to [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="be4d5-104">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="be4d5-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="be4d5-105">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be4d5-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="be4d5-106">Abfragen</span><span class="sxs-lookup"><span data-stu-id="be4d5-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [<span data-ttu-id="be4d5-107">Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be4d5-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="be4d5-108">Angeben der Datenquelle (von)</span><span class="sxs-lookup"><span data-stu-id="be4d5-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="be4d5-109">In einer [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfrage der erste Schritt ist die Datenquelle an, die Sie abfragen möchten.</span><span class="sxs-lookup"><span data-stu-id="be4d5-109">In a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="be4d5-110">Aus diesem Grund die `From` -Klausel in einer Abfrage immer zuerst eintritt.</span><span class="sxs-lookup"><span data-stu-id="be4d5-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="be4d5-111">Abfrageoperatoren wählen und Form des Ergebnisses basierend auf den Typ der Quelle.</span><span class="sxs-lookup"><span data-stu-id="be4d5-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 <span data-ttu-id="be4d5-112">[!code-vb[VbLINQBasicOps&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="be4d5-112">[!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]</span></span>  
  
 <span data-ttu-id="be4d5-113">Die `From` -Klausel gibt die Datenquelle `customers`, und ein *Bereichsvariable*, `cust`.</span><span class="sxs-lookup"><span data-stu-id="be4d5-113">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="be4d5-114">Die Bereichsvariable ist wie eine Schleifeniterationsvariable, mit dem Unterschied, dass in einem Abfrageausdruck keine wirkliche Iteration stattfindet.</span><span class="sxs-lookup"><span data-stu-id="be4d5-114">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="be4d5-115">Wenn die Abfrage ausgeführt wird, häufig mit einem `For Each` -Schleife, dient die Bereichsvariable als Verweis auf jedes darauf folgende Element in `customers`.</span><span class="sxs-lookup"><span data-stu-id="be4d5-115">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="be4d5-116">Da der Compiler den Typ ableiten kann `cust`, Sie müssen nicht explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="be4d5-116">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="be4d5-117">Beispiele für Abfragen mit und ohne explizite Typisierung geschrieben wird, finden Sie unter [Typbeziehungen in Abfrageoperationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="be4d5-117">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="be4d5-118">Weitere Informationen zur Verwendung der `From` -Klausel in Visual Basic finden Sie unter [From-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="be4d5-118">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="be4d5-119">Filtern von Daten (Where)</span><span class="sxs-lookup"><span data-stu-id="be4d5-119">Filtering Data (Where)</span></span>  
 <span data-ttu-id="be4d5-120">Die üblichste Abfrageoperation ist wahrscheinlich ein Filters in Form eines booleschen Ausdrucks anwenden.</span><span class="sxs-lookup"><span data-stu-id="be4d5-120">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="be4d5-121">Die Abfrage gibt dann nur die Elemente, für die der Ausdruck wahr ist.</span><span class="sxs-lookup"><span data-stu-id="be4d5-121">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="be4d5-122">Ein `Where` -Klausel wird verwendet, um die Filterung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="be4d5-122">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="be4d5-123">Der Filter gibt die Elemente in der Datenquelle in der resultierenden Sequenz eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="be4d5-123">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="be4d5-124">Im folgenden Beispiel werden nur die Kunden, die eine Adresse in London haben enthalten.</span><span class="sxs-lookup"><span data-stu-id="be4d5-124">In the following example, only those customers who have an address in London are included.</span></span>  
  
 <span data-ttu-id="be4d5-125">[!code-vb[VbLINQBasicOps&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="be4d5-125">[!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]</span></span>  
  
 <span data-ttu-id="be4d5-126">Sie können logische Operatoren wie z. B. `And` und `Or` zum Kombinieren von Filterausdrücken in einer `Where` Klausel.</span><span class="sxs-lookup"><span data-stu-id="be4d5-126">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="be4d5-127">Um nur die Kunden zurückzugeben, angehören, die aus London und Namen Devon, verwenden Sie z. B. den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="be4d5-127">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="be4d5-128">Um Kunden aus London oder Paris zurückzugeben, verwenden Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="be4d5-128">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="be4d5-129">Weitere Informationen zur Verwendung der `Where` -Klausel in Visual Basic finden Sie unter [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="be4d5-129">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="be4d5-130">Sortieren von Daten (Order By)</span><span class="sxs-lookup"><span data-stu-id="be4d5-130">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="be4d5-131">Es ist häufig sinnvoll, um die zurückgegebene Daten in einer bestimmten Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="be4d5-131">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="be4d5-132">Die `Order By` -Klausel bewirkt, dass die Elemente in der zurückgegebenen Sequenz ein angegebenes Feld oder Felder sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="be4d5-132">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="be4d5-133">Zum Beispiel sortiert die folgende Abfrage die Ergebnisse auf Grundlage der `Name` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="be4d5-133">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="be4d5-134">Da `Name` ist eine Zeichenfolge, die zurückgegebenen Daten alphabetisch sortiert, von A bis Z.</span><span class="sxs-lookup"><span data-stu-id="be4d5-134">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 <span data-ttu-id="be4d5-135">[!code-vb[VbLINQBasicOps&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="be4d5-135">[!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]</span></span>  
  
 <span data-ttu-id="be4d5-136">Verwenden Sie die Ergebnisse in umgekehrter Reihenfolge von Z bis A Sortieren der `Order By...Descending` Klausel.</span><span class="sxs-lookup"><span data-stu-id="be4d5-136">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="be4d5-137">Der Standardwert ist `Ascending` Wenn weder `Ascending` noch `Descending` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="be4d5-137">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="be4d5-138">Weitere Informationen zur Verwendung der `Order By` -Klausel in Visual Basic finden Sie unter [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="be4d5-138">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="be4d5-139">Auswählen von Daten (Select)</span><span class="sxs-lookup"><span data-stu-id="be4d5-139">Selecting Data (Select)</span></span>  
 <span data-ttu-id="be4d5-140">Die `Select` -Klausel gibt die Form und Inhalt der zurückgegebenen Elemente an.</span><span class="sxs-lookup"><span data-stu-id="be4d5-140">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="be4d5-141">Sie können beispielsweise angeben, ob die Ergebnisse der vollständigen bestehen `Customer` Objekte, von denen nur eine `Customer` -Eigenschaft, die eine Teilmenge der Eigenschaften, die eine Kombination von Eigenschaften aus verschiedenen Datenquellen oder einem neuen Ergebnistyp basierend auf der Berechnung.</span><span class="sxs-lookup"><span data-stu-id="be4d5-141">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="be4d5-142">Wenn die `Select` -Klausel erzeugt etwas anderes als eine Kopie des Quellelements, der Vorgang wird aufgerufen, ein *Projektion*.</span><span class="sxs-lookup"><span data-stu-id="be4d5-142">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="be4d5-143">Um eine Auflistung abzurufen, der vollständigen besteht `Customer` Objekte, wählen Sie die Bereichsvariable selbst:</span><span class="sxs-lookup"><span data-stu-id="be4d5-143">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 <span data-ttu-id="be4d5-144">[!code-vb[VbLINQBasicOps&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="be4d5-144">[!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]</span></span>  
  
 <span data-ttu-id="be4d5-145">Wenn ein `Customer` Instanz ist ein großes Objekt, das viele Felder verfügt und Sie abrufen möchten lediglich den Namen, können Sie auswählen `cust.Name`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="be4d5-145">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="be4d5-146">Lokaler Typrückschluss erkennt, dass dadurch den Ergebnistyp aus einer Auflistung von `Customer` -Objekten, die eine Auflistung von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="be4d5-146">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 <span data-ttu-id="be4d5-147">[!code-vb[VbLINQBasicOps&5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="be4d5-147">[!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]</span></span>  
  
 <span data-ttu-id="be4d5-148">Um mehrere Felder aus der Datenquelle auswählen, haben Sie zwei Optionen:</span><span class="sxs-lookup"><span data-stu-id="be4d5-148">To select multiple fields from the data source, you have two choices:</span></span>  
  
-   <span data-ttu-id="be4d5-149">In der `Select` -Klausel, geben Sie die Felder, die im Ergebnis enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="be4d5-149">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="be4d5-150">Der Compiler definieren einen anonymen Typ, der diese Felder als Eigenschaften verfügt.</span><span class="sxs-lookup"><span data-stu-id="be4d5-150">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="be4d5-151">Weitere Informationen finden Sie unter [anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="be4d5-151">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="be4d5-152">Da die zurückgegebenen Elemente im folgenden Beispiel Instanzen eines anonymen Typs sind, verweisen nicht Sie auf den Typ anhand des Namens an anderer Stelle in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="be4d5-152">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="be4d5-153">Der vom Compiler festgelegte Name für den Typ enthält Zeichen, die in normalem Visual Basic-Code nicht gültig sind.</span><span class="sxs-lookup"><span data-stu-id="be4d5-153">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="be4d5-154">Im folgenden Beispiel werden die Elemente in der Auflistung, die von der Abfrage im zurückgegebenen `londonCusts4` sind Instanzen eines anonymen Typs</span><span class="sxs-lookup"><span data-stu-id="be4d5-154">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     <span data-ttu-id="be4d5-155">[!code-vb[VbLINQBasicOps&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="be4d5-155">[!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]</span></span>  
  
     <span data-ttu-id="be4d5-156">- oder - </span><span class="sxs-lookup"><span data-stu-id="be4d5-156">-or-</span></span>  
  
-   <span data-ttu-id="be4d5-157">Definieren Sie einen benannten Typ, der die Felder, die Sie verwenden möchten enthält, in das Ergebnis einschließen, erstellen und initialisieren Sie die Instanzen des Typs in der `Select` Klausel.</span><span class="sxs-lookup"><span data-stu-id="be4d5-157">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="be4d5-158">Verwenden Sie diese Option nur, wenn Sie einzelne Ergebnisse außerhalb der Auflistung verwendet, in der sie zurückgegeben werden, oder wenn Sie sie in Methodenaufrufe als Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="be4d5-158">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="be4d5-159">Der Typ des `londonCusts5` im folgenden Beispiel ist IEnumerable (Of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="be4d5-159">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     <span data-ttu-id="be4d5-160">[!code-vb[VbLINQBasicOps&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="be4d5-160">[!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]</span></span>  
  
     <span data-ttu-id="be4d5-161">[!code-vb[VbLINQBasicOps&#8;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="be4d5-161">[!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]</span></span>  
  
 <span data-ttu-id="be4d5-162">Weitere Informationen zur Verwendung der `Select` -Klausel in Visual Basic finden Sie unter [Select-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="be4d5-162">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="be4d5-163">Verknüpfen von Daten (Join und Group Join)</span><span class="sxs-lookup"><span data-stu-id="be4d5-163">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="be4d5-164">Sie können mehr als eine Datenquelle in Kombinieren der `From` -Klausel auf mehrere Weisen.</span><span class="sxs-lookup"><span data-stu-id="be4d5-164">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="be4d5-165">Im folgende Code wird beispielsweise verwendet zwei Datenquellen und implizit kombiniert Eigenschaften beide im Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="be4d5-165">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="be4d5-166">Die Abfrage wählt Studierende, deren Nachnamen mit einem Vokal beginnen.</span><span class="sxs-lookup"><span data-stu-id="be4d5-166">The query selects students whose last names start with a vowel.</span></span>  
  
 <span data-ttu-id="be4d5-167">[!code-vb[VbLINQBasicOps&#9;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="be4d5-167">[!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be4d5-168">Führen Sie diesen Code mit der erstellten Liste von Studierenden [Gewusst wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="be4d5-168">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="be4d5-169">Die `Join` -Schlüsselwort ist äquivalent zu einer `INNER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="be4d5-169">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="be4d5-170">Kombiniert zwei Sammlungen basierend auf übereinstimmenden Schlüsselwerten zwischen Elementen in beiden Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="be4d5-170">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="be4d5-171">Die Abfrage gibt alle oder einen Teil der Elemente der Auflistung, die übereinstimmende Schlüsselwerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="be4d5-171">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="be4d5-172">Im folgende Code wird z. B. die Aktion des vorherigen impliziten Joins dupliziert.</span><span class="sxs-lookup"><span data-stu-id="be4d5-172">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 <span data-ttu-id="be4d5-173">[!code-vb[VbLINQBasicOps&#10;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="be4d5-173">[!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]</span></span>  
  
 <span data-ttu-id="be4d5-174">`Group Join`Sammlungen in einer einzelnen hierarchischen Auflistung wie kombiniert eine `LEFT JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="be4d5-174">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="be4d5-175">Weitere Informationen finden Sie unter [Join-Klausel](../../../../visual-basic/language-reference/queries/join-clause.md) und [Group Join-Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="be4d5-175">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="be4d5-176">Gruppieren von Daten (Group By)</span><span class="sxs-lookup"><span data-stu-id="be4d5-176">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="be4d5-177">Sie können Hinzufügen einer `Group By` -Klausel, um die Elemente in einem Abfrageergebnis gemäß einem oder mehreren Feldern der Elemente zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="be4d5-177">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="be4d5-178">Im folgende Code werden z. B. Studierenden Klasse Jahr gruppiert.</span><span class="sxs-lookup"><span data-stu-id="be4d5-178">For example, the following code groups students by class year.</span></span>  
  
 <span data-ttu-id="be4d5-179">[!code-vb[VbLINQBasicOps&#11;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="be4d5-179">[!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]</span></span>  
  
 <span data-ttu-id="be4d5-180">Wenn Sie diesen Code mit der Liste der Schüler in erstellte ausführen [wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), die Ausgabe der `For Each` -Anweisung ist:</span><span class="sxs-lookup"><span data-stu-id="be4d5-180">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="be4d5-181">Jahr: Junior</span><span class="sxs-lookup"><span data-stu-id="be4d5-181">Year: Junior</span></span>  
  
 <span data-ttu-id="be4d5-182">Tucker, Michael</span><span class="sxs-lookup"><span data-stu-id="be4d5-182">Tucker, Michael</span></span>  
  
 <span data-ttu-id="be4d5-183">Garcia, Hugo</span><span class="sxs-lookup"><span data-stu-id="be4d5-183">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="be4d5-184">Garcia, Sarah</span><span class="sxs-lookup"><span data-stu-id="be4d5-184">Garcia, Debra</span></span>  
  
 <span data-ttu-id="be4d5-185">Tucker Lance</span><span class="sxs-lookup"><span data-stu-id="be4d5-185">Tucker, Lance</span></span>  
  
 <span data-ttu-id="be4d5-186">Jahr: Senior</span><span class="sxs-lookup"><span data-stu-id="be4d5-186">Year: Senior</span></span>  
  
 <span data-ttu-id="be4d5-187">Omelchenko Svetlana</span><span class="sxs-lookup"><span data-stu-id="be4d5-187">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="be4d5-188">Osada Michiko</span><span class="sxs-lookup"><span data-stu-id="be4d5-188">Osada, Michiko</span></span>  
  
 <span data-ttu-id="be4d5-189">Fakhouri Fadi</span><span class="sxs-lookup"><span data-stu-id="be4d5-189">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="be4d5-190">Feng Heiko</span><span class="sxs-lookup"><span data-stu-id="be4d5-190">Feng, Hanying</span></span>  
  
 <span data-ttu-id="be4d5-191">Adams, Thomas</span><span class="sxs-lookup"><span data-stu-id="be4d5-191">Adams, Terry</span></span>  
  
 <span data-ttu-id="be4d5-192">Jahr: neunte Klasse</span><span class="sxs-lookup"><span data-stu-id="be4d5-192">Year: Freshman</span></span>  
  
 <span data-ttu-id="be4d5-193">Mortensen Sven</span><span class="sxs-lookup"><span data-stu-id="be4d5-193">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="be4d5-194">Garcia, Cesar</span><span class="sxs-lookup"><span data-stu-id="be4d5-194">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="be4d5-195">Die Variante, die im folgenden Code gezeigt Jahrgänge sortiert und anschließend die Kursteilnehmer innerhalb jedes Jahres nach Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="be4d5-195">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 <span data-ttu-id="be4d5-196">[!code-vb[VbLINQBasicOps&#12;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="be4d5-196">[!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]</span></span>  
  
 <span data-ttu-id="be4d5-197">Weitere Informationen zu `Group By`, finden Sie unter [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="be4d5-197">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4d5-198">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be4d5-198">See Also</span></span>  
 <span data-ttu-id="be4d5-199"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="be4d5-199"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="be4d5-200"> [Erste Schritte mit LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="be4d5-200"> [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
<span data-ttu-id="be4d5-201"> [Abfragen](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="be4d5-201"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="be4d5-202"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="be4d5-202"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="be4d5-203"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="be4d5-203"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)</span></span>
