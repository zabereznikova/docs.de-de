---
title: Statisch kompilierte Abfragen (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 3f4825c7-c3b0-48da-ba4e-8e97fb2a2f34
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 83d6e37a00477cedc4a5a4c520ad79ff764d5ff7
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---
# <a name="statically-compiled-queries-linq-to-xml-visual-basic"></a><span data-ttu-id="d5cdd-102">Statisch kompilierte Abfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5cdd-102">Statically Compiled Queries (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="d5cdd-103">Eine der wichtigsten Leistungsvorteile von LINQ to XML, im Gegensatz zur <xref:System.Xml.XmlDocument>, sind Abfragen in LINQ to XML statisch kompiliert wird, während die XPath-Abfragen zur Laufzeit interpretiert werden müssen.</xref:System.Xml.XmlDocument></span><span class="sxs-lookup"><span data-stu-id="d5cdd-103">One of the most important performance benefits LINQ to XML, as opposed to <xref:System.Xml.XmlDocument>, is that queries in LINQ to XML are statically compiled, whereas XPath queries must be interpreted at run time.</span></span> <span data-ttu-id="d5cdd-104">Diese Funktion ist in LINQ to XML integriert, sodass Sie keine zusätzlichen Schritte ausführen müssen, um diesen Vorteil zu nutzen. Es ist jedoch hilfreich, den Unterschied zu verstehen, wenn Sie eine Auswahl zwischen den beiden Technologien treffen.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-104">This feature is built in to LINQ to XML, so you do not have to perform extra steps to take advantage of it, but it is helpful to understand the distinction when choosing between the two technologies.</span></span> <span data-ttu-id="d5cdd-105">In diesem Thema wird der Unterschied erklärt.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-105">This topic explains the difference.</span></span>  
  
## <a name="statically-compiled-queries-vs-xpath"></a><span data-ttu-id="d5cdd-106">Statisch kompilierte Abfragen und XPath</span><span class="sxs-lookup"><span data-stu-id="d5cdd-106">Statically Compiled Queries vs. XPath</span></span>  
 <span data-ttu-id="d5cdd-107">Im folgenden Beispiel wird gezeigt, wie Sie die Nachfolgerelemente mit einem bestimmten Namen und mit einem Attribut mit einem bestimmten Wert abrufen können.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-107">The following example shows how to get the descendant elements with a specified name, and with an attribute with a specified value.</span></span>  
  
 <span data-ttu-id="d5cdd-108">Hier folgt der entsprechende XPath-Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="d5cdd-108">The following is the equivalent XPath expression:</span></span>  
  
```  
//Address[@Type='Shipping']  
```  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 = From el In po.Descendants("Address")  
            Where el.@Type = "Shipping"  
  
For Each el In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="d5cdd-109">Der Abfrageausdruck in diesem Beispiel wird vom Compiler in eine methodenbasierte Abfragesyntax umgeschrieben.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-109">The query expression in this example is re-written by the compiler to method-based query syntax.</span></span> <span data-ttu-id="d5cdd-110">Das folgende in methodenbasierter Abfragesyntax geschriebene Beispiel führt zum selben Ergebnis wie das vorherige Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d5cdd-110">The following example, which is written in method-based query syntax, produces the same results as the previous one:</span></span>  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 As IEnumerable(Of XElement) = po.Descendants("Address").Where(Function(el) el.@Type = "Shipping")  
  
For Each el In list1  
    Console.WriteLine(el)  
Next   
```  
  
 <span data-ttu-id="d5cdd-111">Die <xref:System.Linq.Enumerable.Where%2A>Methode ist eine Erweiterungsmethode.</xref:System.Linq.Enumerable.Where%2A></span><span class="sxs-lookup"><span data-stu-id="d5cdd-111">The <xref:System.Linq.Enumerable.Where%2A> method is an extension method.</span></span> <span data-ttu-id="d5cdd-112">Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="d5cdd-112">For more information, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="d5cdd-113">Da <xref:System.Linq.Enumerable.Where%2A>ist eine Erweiterungsmethode, die obige Abfrage kompiliert, als wäre es wie folgt geschrieben:</xref:System.Linq.Enumerable.Where%2A></span><span class="sxs-lookup"><span data-stu-id="d5cdd-113">Because <xref:System.Linq.Enumerable.Where%2A> is an extension method, the query above is compiled as though it were written as follows:</span></span>  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")  
  
For Each el In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="d5cdd-114">Dieses Beispiel führt zu genau den gleichen Ergebnissen wie die beiden vorherigen Beispiele.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-114">This example produces exactly the same results as the previous two examples.</span></span> <span data-ttu-id="d5cdd-115">Dies veranschaulicht die Tatsache, dass Abfragen tatsächlich zu statisch verknüpften Methodenaufrufen kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-115">This illustrates the fact that queries are effectively compiled into statically linked method calls.</span></span> <span data-ttu-id="d5cdd-116">Hierdurch wird, gemeinsam mit der verzögerten Ausführungssemantik von Iteratoren, die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-116">This, combined with the deferred execution semantics of iterators, improves performance.</span></span> <span data-ttu-id="d5cdd-117">Weitere Informationen zu der verzögerten Ausführungssemantik von Iteratoren, finden Sie unter [verzögerte Ausführung und verzögerte Auswertung in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d5cdd-117">For more information about the deferred execution semantics of iterators, see [Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5cdd-118">Diese Beispiele sind für den Code repräsentativ, der möglicherweise vom Compiler geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-118">These examples are representative of the code that the compiler might write.</span></span> <span data-ttu-id="d5cdd-119">Die tatsächliche Implementierung kann in Details von diesen Beispielen abweichen, die Leistung wird jedoch weitgehend mit der dieser Beispiele übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-119">The actual implementation might differ slightly from these examples, but the performance will be the same or similar to these examples.</span></span>  
  
## <a name="executing-xpath-expressions-with-xmldocument"></a><span data-ttu-id="d5cdd-120">Ausführen von XPath-Ausdrücken mit XmlDocument</span><span class="sxs-lookup"><span data-stu-id="d5cdd-120">Executing XPath Expressions with XmlDocument</span></span>  
 <span data-ttu-id="d5cdd-121">Im folgenden Beispiel wird <xref:System.Xml.XmlDocument>um dieselben Ergebnisse wie in den vorherigen Beispielen:</xref:System.Xml.XmlDocument></span><span class="sxs-lookup"><span data-stu-id="d5cdd-121">The following example uses <xref:System.Xml.XmlDocument> to accomplish the same results as the previous examples:</span></span>  
  
```vb  
Dim reader = Xml.XmlReader.Create("PurchaseOrders.xml")  
Dim doc As New Xml.XmlDocument()  
doc.Load(reader)  
Dim nl As Xml.XmlNodeList = doc.SelectNodes(".//Address[@Type='Shipping']")  
For Each n As Xml.XmlNode In nl  
    Console.WriteLine(n.OuterXml)  
Next  
reader.Close()  
```  
  
 <span data-ttu-id="d5cdd-122">Diese Abfrage gibt dieselbe Ausgabe wie die Beispiele mit LINQ to XML zurück. der einzige Unterschied ist, dass LINQ to XML das gedruckte XML zieht, während <xref:System.Xml.XmlDocument>nicht.</xref:System.Xml.XmlDocument></span><span class="sxs-lookup"><span data-stu-id="d5cdd-122">This query returns the same output as the examples that use LINQ to XML; the only difference is that LINQ to XML indents the printed XML, whereas <xref:System.Xml.XmlDocument> does not.</span></span>  
  
 <span data-ttu-id="d5cdd-123">Allerdings die <xref:System.Xml.XmlDocument>Ansatz in der Regel ist nicht so gut wie LINQ to XML, da die <xref:System.Xml.XmlNode.SelectNodes%2A>Methode führen die folgenden intern jedes Mal, wenn sie aufgerufen wird:</xref:System.Xml.XmlNode.SelectNodes%2A> </xref:System.Xml.XmlDocument></span><span class="sxs-lookup"><span data-stu-id="d5cdd-123">However, the <xref:System.Xml.XmlDocument> approach generally does not perform as well as LINQ to XML, because the <xref:System.Xml.XmlNode.SelectNodes%2A> method must do the following internally every time it is called:</span></span>  
  
-   <span data-ttu-id="d5cdd-124">Analysieren der Zeichenfolge, die den XPath-Ausdruck enthält, und Zerlegen der Zeichenfolge in Token.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-124">It parses the string that contains the XPath expression, breaking the string into tokens.</span></span>  
  
-   <span data-ttu-id="d5cdd-125">Überprüfen der Token, um sicherzustellen, dass der XPath-Ausdruck gültig ist.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-125">It validates the tokens to make sure that the XPath expression is valid.</span></span>  
  
-   <span data-ttu-id="d5cdd-126">Übersetzen des Ausdrucks in eine interne Ausdrucksstruktur.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-126">It translates the expression into an internal expression tree.</span></span>  
  
-   <span data-ttu-id="d5cdd-127">Durchlaufen der Knoten und entsprechendes Auswählen der Knoten für das Resultset auf Grundlage der Ausdrucksauswertung.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-127">It iterates through the nodes, appropriately selecting the nodes for the result set based on the evaluation of the expression.</span></span>  
  
 <span data-ttu-id="d5cdd-128">Dies sind bedeutend mehr Arbeitsschritte als bei einer entsprechenden LINQ to XML-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-128">This is significantly more than the work done by the corresponding LINQ to XML query.</span></span> <span data-ttu-id="d5cdd-129">Die genauen Leistungsunterschiede variiert für verschiedene Arten von Abfragen, aber im Allgemeinen LINQ to XML-Abfragen jedoch weniger Arbeitsschritte und daher besser als das Auswerten von XPath-Ausdrücken mit <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument> ausführen.</span><span class="sxs-lookup"><span data-stu-id="d5cdd-129">The specific performance difference varies for different types of queries, but in general LINQ to XML queries do less work, and therefore perform better, than evaluating XPath expressions using <xref:System.Xml.XmlDocument>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5cdd-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5cdd-130">See Also</span></span>  
 [<span data-ttu-id="d5cdd-131">Leistung (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5cdd-131">Performance (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)

