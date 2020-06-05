---
title: Statisch kompilierte Abfragen (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 3f4825c7-c3b0-48da-ba4e-8e97fb2a2f34
ms.openlocfilehash: f020c1ed8627df8c8386a059f0cea372e8df363e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406767"
---
# <a name="statically-compiled-queries-linq-to-xml-visual-basic"></a><span data-ttu-id="4f480-102">Statisch kompilierte Abfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f480-102">Statically Compiled Queries (LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="4f480-103">Einer der wichtigsten Leistungsvorteile von LINQ to XML (im Unterschied zu <xref:System.Xml.XmlDocument>) besteht darin, dass Abfragen in LINQ to XML statisch kompiliert werden. XPath-Abfragen müssen dagegen zur Laufzeit interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="4f480-103">One of the most important performance benefits LINQ to XML, as opposed to <xref:System.Xml.XmlDocument>, is that queries in LINQ to XML are statically compiled, whereas XPath queries must be interpreted at run time.</span></span> <span data-ttu-id="4f480-104">Diese Funktion ist in LINQ to XML integriert, sodass Sie keine zusätzlichen Schritte ausführen müssen, um diesen Vorteil zu nutzen. Es ist jedoch hilfreich, den Unterschied zu verstehen, wenn Sie eine Auswahl zwischen den beiden Technologien treffen.</span><span class="sxs-lookup"><span data-stu-id="4f480-104">This feature is built in to LINQ to XML, so you do not have to perform extra steps to take advantage of it, but it is helpful to understand the distinction when choosing between the two technologies.</span></span> <span data-ttu-id="4f480-105">In diesem Thema wird der Unterschied erklärt.</span><span class="sxs-lookup"><span data-stu-id="4f480-105">This topic explains the difference.</span></span>

## <a name="statically-compiled-queries-vs-xpath"></a><span data-ttu-id="4f480-106">Statisch kompilierte Abfragen im Vergleich zu XPath</span><span class="sxs-lookup"><span data-stu-id="4f480-106">Statically Compiled Queries vs. XPath</span></span>

<span data-ttu-id="4f480-107">Im folgenden Beispiel wird gezeigt, wie Sie die Nachfolgerelemente mit einem bestimmten Namen und mit einem Attribut mit einem bestimmten Wert abrufen können.</span><span class="sxs-lookup"><span data-stu-id="4f480-107">The following example shows how to get the descendant elements with a specified name, and with an attribute with a specified value.</span></span>

<span data-ttu-id="4f480-108">Hier folgt der entsprechende XPath-Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="4f480-108">The following is the equivalent XPath expression:</span></span>

```vb
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

<span data-ttu-id="4f480-109">Der Abfrageausdruck in diesem Beispiel wird vom Compiler in eine methodenbasierte Abfragesyntax umgeschrieben.</span><span class="sxs-lookup"><span data-stu-id="4f480-109">The query expression in this example is re-written by the compiler to method-based query syntax.</span></span> <span data-ttu-id="4f480-110">Das folgende in methodenbasierter Abfragesyntax geschriebene Beispiel führt zum selben Ergebnis wie das vorherige Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4f480-110">The following example, which is written in method-based query syntax, produces the same results as the previous one:</span></span>

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 As IEnumerable(Of XElement) = po.Descendants("Address").Where(Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="4f480-111">Die <xref:System.Linq.Enumerable.Where%2A>-Methode ist eine Erweiterungsmethode.</span><span class="sxs-lookup"><span data-stu-id="4f480-111">The <xref:System.Linq.Enumerable.Where%2A> method is an extension method.</span></span> <span data-ttu-id="4f480-112">Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="4f480-112">For more information, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="4f480-113">Da <xref:System.Linq.Enumerable.Where%2A> eine Erweiterungsmethode ist, wird die obige Abfrage kompiliert, als wäre sie wie folgt geschrieben:</span><span class="sxs-lookup"><span data-stu-id="4f480-113">Because <xref:System.Linq.Enumerable.Where%2A> is an extension method, the query above is compiled as though it were written as follows:</span></span>

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="4f480-114">Dieses Beispiel führt zu genau den gleichen Ergebnissen wie die beiden vorherigen Beispiele.</span><span class="sxs-lookup"><span data-stu-id="4f480-114">This example produces exactly the same results as the previous two examples.</span></span> <span data-ttu-id="4f480-115">Dies veranschaulicht die Tatsache, dass Abfragen tatsächlich zu statisch verknüpften Methodenaufrufen kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="4f480-115">This illustrates the fact that queries are effectively compiled into statically linked method calls.</span></span> <span data-ttu-id="4f480-116">Hierdurch wird, gemeinsam mit der verzögerten Ausführungssemantik von Iteratoren, die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="4f480-116">This, combined with the deferred execution semantics of iterators, improves performance.</span></span> <span data-ttu-id="4f480-117">Weitere Informationen zur verzögerten Ausführungs Semantik von Iteratoren finden Sie unter [verzögerte Ausführung und verzögerte Auswertung in LINQ to XML (Visual Basic)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4f480-117">For more information about the deferred execution semantics of iterators, see [Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4f480-118">Diese Beispiele sind für den Code repräsentativ, der möglicherweise vom Compiler geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="4f480-118">These examples are representative of the code that the compiler might write.</span></span> <span data-ttu-id="4f480-119">Die tatsächliche Implementierung kann in Details von diesen Beispielen abweichen, die Leistung wird jedoch weitgehend mit der dieser Beispiele übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="4f480-119">The actual implementation might differ slightly from these examples, but the performance will be the same or similar to these examples.</span></span>

## <a name="executing-xpath-expressions-with-xmldocument"></a><span data-ttu-id="4f480-120">Ausführen von XPath-Ausdrücken mit XmlDocument</span><span class="sxs-lookup"><span data-stu-id="4f480-120">Executing XPath Expressions with XmlDocument</span></span>

<span data-ttu-id="4f480-121">Im folgenden Beispiel erhalten Sie mit <xref:System.Xml.XmlDocument> dieselben Ergebnisse wie in den vorherigen Beispielen:</span><span class="sxs-lookup"><span data-stu-id="4f480-121">The following example uses <xref:System.Xml.XmlDocument> to accomplish the same results as the previous examples:</span></span>

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

<span data-ttu-id="4f480-122">Diese Abfrage gibt dieselbe Ausgabe wie die Beispiele mit LINQ to XML zurück. Der einzige Unterschied ist, dass LINQ to XML das gedruckte XML im Gegensatz zu <xref:System.Xml.XmlDocument> einrückt.</span><span class="sxs-lookup"><span data-stu-id="4f480-122">This query returns the same output as the examples that use LINQ to XML; the only difference is that LINQ to XML indents the printed XML, whereas <xref:System.Xml.XmlDocument> does not.</span></span>

<span data-ttu-id="4f480-123">Der <xref:System.Xml.XmlDocument>-Ansatz bietet in der Regel nicht die Leistung von LINQ to XML, da die <xref:System.Xml.XmlNode.SelectNodes%2A>-Methode bei jedem Aufruf intern die folgenden Schritte ausführen muss:</span><span class="sxs-lookup"><span data-stu-id="4f480-123">However, the <xref:System.Xml.XmlDocument> approach generally does not perform as well as LINQ to XML, because the <xref:System.Xml.XmlNode.SelectNodes%2A> method must do the following internally every time it is called:</span></span>

- <span data-ttu-id="4f480-124">Analysieren der Zeichenfolge, die den XPath-Ausdruck enthält, und Zerlegen der Zeichenfolge in Token.</span><span class="sxs-lookup"><span data-stu-id="4f480-124">It parses the string that contains the XPath expression, breaking the string into tokens.</span></span>

- <span data-ttu-id="4f480-125">Überprüfen der Token, um sicherzustellen, dass der XPath-Ausdruck gültig ist.</span><span class="sxs-lookup"><span data-stu-id="4f480-125">It validates the tokens to make sure that the XPath expression is valid.</span></span>

- <span data-ttu-id="4f480-126">Übersetzen des Ausdrucks in eine interne Ausdrucksstruktur.</span><span class="sxs-lookup"><span data-stu-id="4f480-126">It translates the expression into an internal expression tree.</span></span>

- <span data-ttu-id="4f480-127">Durchlaufen der Knoten und entsprechendes Auswählen der Knoten für das Resultset auf Grundlage der Ausdrucksauswertung.</span><span class="sxs-lookup"><span data-stu-id="4f480-127">It iterates through the nodes, appropriately selecting the nodes for the result set based on the evaluation of the expression.</span></span>

<span data-ttu-id="4f480-128">Dies sind bedeutend mehr Arbeitsschritte als bei einer entsprechenden LINQ to XML-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="4f480-128">This is significantly more than the work done by the corresponding LINQ to XML query.</span></span> <span data-ttu-id="4f480-129">Die genauen Leistungsunterschiede variieren je nach Abfragetyp, in der Regel müssen LINQ to XML-Abfragen jedoch weniger Arbeitsschritte ausführen und bieten daher eine bessere Leistung als das Auswerten von XPath-Ausdrücken mit <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="4f480-129">The specific performance difference varies for different types of queries, but in general LINQ to XML queries do less work, and therefore perform better, than evaluating XPath expressions using <xref:System.Xml.XmlDocument>.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f480-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f480-130">See also</span></span>

- [<span data-ttu-id="4f480-131">Leistung (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f480-131">Performance (LINQ to XML) (Visual Basic)</span></span>](performance-linq-to-xml.md)
