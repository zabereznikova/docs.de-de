---
title: Datentransformationen mit LINQ (C#)
description: Informationen zur Verwendung von LINQ-Abfragen in C# für die Transformation von Daten Sie können mithilfe der SELECT-Klausel durch Sortieren und Gruppieren die Sequenz ändern und neue Typen erstellen.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: 2fb4166b9dbcecebf06b9dc3a780b02751dd4dc7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159149"
---
# <a name="data-transformations-with-linq-c"></a><span data-ttu-id="17001-104">Datentransformationen mit LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="17001-104">Data Transformations with LINQ (C#)</span></span>

<span data-ttu-id="17001-105">Bei Language Integrated Query (LINQ) geht es nicht nur um das Abrufen von Daten.</span><span class="sxs-lookup"><span data-stu-id="17001-105">Language-Integrated Query (LINQ) is not only about retrieving data.</span></span> <span data-ttu-id="17001-106">Es ist auch ein leistungsstarkes Tool zur Datentransformation.</span><span class="sxs-lookup"><span data-stu-id="17001-106">It is also a powerful tool for transforming data.</span></span> <span data-ttu-id="17001-107">Mithilfe einer LINQ-Abfrage können Sie eine Quellsequenz als Eingabe verwenden und sie auf viele Arten zum Erstellen einer neuen Ausgabesequenz ändern.</span><span class="sxs-lookup"><span data-stu-id="17001-107">By using a LINQ query, you can use a source sequence as input and modify it in many ways to create a new output sequence.</span></span> <span data-ttu-id="17001-108">Sie können die Sequenz selbst durch Sortieren und Gruppieren ändern, ohne die Elemente zu ändern.</span><span class="sxs-lookup"><span data-stu-id="17001-108">You can modify the sequence itself without modifying the elements themselves by sorting and grouping.</span></span> <span data-ttu-id="17001-109">Aber das vielleicht leistungsstärkste Feature von LINQ-Abfragen ist die Fähigkeit, neue Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="17001-109">But perhaps the most powerful feature of LINQ queries is the ability to create new types.</span></span> <span data-ttu-id="17001-110">Dies erfolgt in der [select](../../../language-reference/keywords/select-clause.md)-Klausel.</span><span class="sxs-lookup"><span data-stu-id="17001-110">This is accomplished in the [select](../../../language-reference/keywords/select-clause.md) clause.</span></span> <span data-ttu-id="17001-111">Sie können z. B. folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="17001-111">For example, you can perform the following tasks:</span></span>  
  
- <span data-ttu-id="17001-112">Führen Sie mehrere Eingabesequenzen in einer einzelnen Ausgabesequenz, die einen neuen Typ hat, zusammen.</span><span class="sxs-lookup"><span data-stu-id="17001-112">Merge multiple input sequences into a single output sequence that has a new type.</span></span>  
  
- <span data-ttu-id="17001-113">Erstellen Sie Ausgabesequenzen, deren Elemente aus nur einer oder mehreren Eigenschaften jedes Elements in der Quellsequenz bestehen.</span><span class="sxs-lookup"><span data-stu-id="17001-113">Create output sequences whose elements consist of only one or several properties of each element in the source sequence.</span></span>  
  
- <span data-ttu-id="17001-114">Erstellen Sie Ausgabesequenzen, deren Elemente aus Ergebnissen der Vorgänge für die Quelldaten bestehen.</span><span class="sxs-lookup"><span data-stu-id="17001-114">Create output sequences whose elements consist of the results of operations performed on the source data.</span></span>  
  
- <span data-ttu-id="17001-115">Erstellen Sie Ausgabesequenzen in einem anderen Format.</span><span class="sxs-lookup"><span data-stu-id="17001-115">Create output sequences in a different format.</span></span> <span data-ttu-id="17001-116">Beispielsweise können Sie Daten aus SQL-Zeilen oder Textdateien in XML umwandeln.</span><span class="sxs-lookup"><span data-stu-id="17001-116">For example, you can transform data from SQL rows or text files into XML.</span></span>  
  
 <span data-ttu-id="17001-117">Dies sind nur einige Beispiele.</span><span class="sxs-lookup"><span data-stu-id="17001-117">These are just several examples.</span></span> <span data-ttu-id="17001-118">Natürlich können diese Transformationen auf verschiedene Weise in der gleichen Abfrage kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="17001-118">Of course, these transformations can be combined in various ways in the same query.</span></span> <span data-ttu-id="17001-119">Darüber hinaus kann die Ausgabesequenz einer Abfrage als Eingabesequenz für eine neue Abfrage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="17001-119">Furthermore, the output sequence of one query can be used as the input sequence for a new query.</span></span>  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a><span data-ttu-id="17001-120">Verknüpfen mehrerer Eingaben in eine Ausgabesequenz</span><span class="sxs-lookup"><span data-stu-id="17001-120">Joining Multiple Inputs into One Output Sequence</span></span>  

 <span data-ttu-id="17001-121">Sie können eine LINQ-Abfrage verwenden, um eine Ausgabesequenz zu erstellen, die Elemente von mehr als einer Eingabesequenz enthält.</span><span class="sxs-lookup"><span data-stu-id="17001-121">You can use a LINQ query to create an output sequence that contains elements from more than one input sequence.</span></span> <span data-ttu-id="17001-122">Im folgenden Beispiel wird gezeigt, wie zwei Datenstrukturen im Arbeitsspeicher kombiniert werden können, aber die gleichen Prinzipien können angewendet werden, um Daten von XML- oder SQL- oder DataSet-Quellen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="17001-122">The following example shows how to combine two in-memory data structures, but the same principles can be applied to combine data from XML or SQL or DataSet sources.</span></span> <span data-ttu-id="17001-123">Nehmen Sie die beiden folgenden Klassentypen an:</span><span class="sxs-lookup"><span data-stu-id="17001-123">Assume the following two class types:</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 <span data-ttu-id="17001-124">Das folgende Beispiel gibt die Abfrage an:</span><span class="sxs-lookup"><span data-stu-id="17001-124">The following example shows the query:</span></span>  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 <span data-ttu-id="17001-125">Weitere Informationen finden Sie unter [join-Klausel](../../../language-reference/keywords/join-clause.md) und [select-Klausel](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="17001-125">For more information, see [join clause](../../../language-reference/keywords/join-clause.md) and [select clause](../../../language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="selecting-a-subset-of-each-source-element"></a><span data-ttu-id="17001-126">Auswählen einer Teilmenge jedes Quellelements</span><span class="sxs-lookup"><span data-stu-id="17001-126">Selecting a Subset of each Source Element</span></span>  

 <span data-ttu-id="17001-127">Es gibt zwei Hauptmethoden, eine Teilmenge jedes Elements in der Quellsequenz auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="17001-127">There are two primary ways to select a subset of each element in the source sequence:</span></span>  
  
1. <span data-ttu-id="17001-128">Um nur einen Member des Quellelements auszuwählen, verwenden Sie die Punktoperation.</span><span class="sxs-lookup"><span data-stu-id="17001-128">To select just one member of the source element, use the dot operation.</span></span> <span data-ttu-id="17001-129">Im folgenden Beispiel wird angenommen, dass ein `Customer`-Objekt verschiedene öffentliche Eigenschaften enthält, einschließlich der Zeichenfolge `City`.</span><span class="sxs-lookup"><span data-stu-id="17001-129">In the following example, assume that a `Customer` object contains several public properties including a string named `City`.</span></span> <span data-ttu-id="17001-130">Bei der Ausführung erzeugt diese Abfrage eine Ausgabesequenz von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="17001-130">When executed, this query will produce an output sequence of strings.</span></span>  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. <span data-ttu-id="17001-131">Zum Erstellen von Elementen, die mehr als eine Eigenschaft aus dem Quellelement enthalten, können Sie einen Objektinitialisierer mit einem benannten Objekt oder einen anonymen Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="17001-131">To create elements that contain more than one property from the source element, you can use an object initializer with either a named object or an anonymous type.</span></span> <span data-ttu-id="17001-132">Das folgende Beispiel zeigt die Verwendung eines anonymen Typs zum Kapseln zweier Eigenschaften von jedem `Customer`-Element:</span><span class="sxs-lookup"><span data-stu-id="17001-132">The following example shows the use of an anonymous type to encapsulate two properties from each `Customer` element:</span></span>  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 <span data-ttu-id="17001-133">Weitere Informationen finden Sie unter [Objekt- und Auflistungsinitialisierer](../../classes-and-structs/object-and-collection-initializers.md) und [Anonyme Typen](../../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="17001-133">For more information, see [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md) and [Anonymous Types](../../classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="transforming-in-memory-objects-into-xml"></a><span data-ttu-id="17001-134">Transformieren von Objekten im Speicher in XML</span><span class="sxs-lookup"><span data-stu-id="17001-134">Transforming in-Memory Objects into XML</span></span>  

 <span data-ttu-id="17001-135">LINQ-Abfragen machen es einfacher, Daten zwischen Datenstrukturen im Speicher, SQL-Datenbanken, ADO.NET-Datasets und XML-Streams oder XML-Dokumenten zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="17001-135">LINQ queries make it easy to transform data between in-memory data structures, SQL databases, ADO.NET Datasets and XML streams or documents.</span></span> <span data-ttu-id="17001-136">Im folgenden Beispiel werden Objekte in einer Datenstruktur im Arbeitsspeicher in XML-Elemente transformiert.</span><span class="sxs-lookup"><span data-stu-id="17001-136">The following example transforms objects in an in-memory data structure into XML elements.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 <span data-ttu-id="17001-137">Der Code erzeugt die folgende XML-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="17001-137">The code produces the following XML output:</span></span>  
  
```xml  
<Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 <span data-ttu-id="17001-138">Weitere Informationen finden Sie unter [Erstellen von XML-Strukturen in C# (LINQ to XML)](../../../../standard/linq/create-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="17001-138">For more information, see [Creating XML Trees in C# (LINQ to XML)](../../../../standard/linq/create-xml-trees.md).</span></span>  
  
## <a name="performing-operations-on-source-elements"></a><span data-ttu-id="17001-139">Ausführen von Operationen für Quellelemente</span><span class="sxs-lookup"><span data-stu-id="17001-139">Performing Operations on Source Elements</span></span>  

 <span data-ttu-id="17001-140">Eine Ausgabesequenz enthält möglicherweise keine Elemente oder Elementeigenschaften aus der Quellsequenz.</span><span class="sxs-lookup"><span data-stu-id="17001-140">An output sequence might not contain any elements or element properties from the source sequence.</span></span> <span data-ttu-id="17001-141">Die Ausgabe kann möglicherweise stattdessen eine Sequenz von Werten enthalten, die durch Verwendung der Quellelemente als Eingabeargumente berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="17001-141">The output might instead be a sequence of values that is computed by using the source elements as input arguments.</span></span>

 <span data-ttu-id="17001-142">Die folgende Abfrage übernimmt eine Zahlensequenz, die die Radien der Kreise darstellt, den Bereich für jeden Radius berechnet und eine Ausgabesequenz zurückgibt, die Zeichenfolgen enthält, die mit dem berechneten Bereich formatiert sind.</span><span class="sxs-lookup"><span data-stu-id="17001-142">The following query will take a sequence of numbers that represent radii of circles, calculate the area for each radius, and return an output sequence containing strings formatted with the calculated area.</span></span>

 <span data-ttu-id="17001-143">Jede Zeichenfolge für die Ausgabesequenz wird mithilfe der [Zeichenfolgeninterpolation](../../../language-reference/tokens/interpolated.md) formatiert.</span><span class="sxs-lookup"><span data-stu-id="17001-143">Each string for the output sequence will be formatted using [string interpolation](../../../language-reference/tokens/interpolated.md).</span></span> <span data-ttu-id="17001-144">Eine interpolierte Zeichenfolge enthält `$` vor dem öffnenden Anführungszeichen der Zeichenfolge, und Vorgänge können in geschweiften Klammern innerhalb der interpolierten Zeichenfolge durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="17001-144">An interpolated string will have a `$` in front of the string's opening quotation mark, and operations can be performed within curly braces placed inside the interpolated string.</span></span> <span data-ttu-id="17001-145">Nachdem diese Vorgänge ausgeführt wurden, werden die Ergebnisse verkettet.</span><span class="sxs-lookup"><span data-stu-id="17001-145">Once those operations are performed, the results will be concatenated.</span></span>
  
> [!NOTE]
> <span data-ttu-id="17001-146">Aufrufen von Methoden in Abfrageausdrücken wird nicht unterstützt, wenn die Abfrage in eine andere Domäne übersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="17001-146">Calling methods in query expressions is not supported if the query will be translated into some other domain.</span></span> <span data-ttu-id="17001-147">Sie können beispielsweise keine normale C#-Methode in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] aufrufen, da SQL Server über keinen Kontext dafür verfügt.</span><span class="sxs-lookup"><span data-stu-id="17001-147">For example, you cannot call an ordinary C# method in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] because SQL Server has no context for it.</span></span> <span data-ttu-id="17001-148">Sie können jedoch gespeicherte Prozeduren Methoden zuordnen und diese aufrufen.</span><span class="sxs-lookup"><span data-stu-id="17001-148">However, you can map stored procedures to methods and call those.</span></span> <span data-ttu-id="17001-149">Weitere Informationen finden Sie unter [Gespeicherte Prozeduren](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="17001-149">For more information, see [Stored Procedures](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="17001-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17001-150">See also</span></span>

- [<span data-ttu-id="17001-151">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="17001-151">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="17001-152">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="17001-152">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="17001-153">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="17001-153">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)
- [<span data-ttu-id="17001-154">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="17001-154">LINQ to XML (C#)</span></span>](../../../../standard/linq/linq-xml-overview.md)
- [<span data-ttu-id="17001-155">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="17001-155">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="17001-156">select-Klausel</span><span class="sxs-lookup"><span data-stu-id="17001-156">select clause</span></span>](../../../language-reference/keywords/select-clause.md)
