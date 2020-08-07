---
title: Statisch kompilierte Abfragen (LINQ to XML) (C#)
description: Erfahren Sie mehr über statisch kompilierte Abfragen in LINQ to XML in C# und darüber, wie diese sich von XPath-Abfragen unterscheiden, die zur Laufzeit interpretiert werden müssen.
ms.date: 07/20/2015
ms.assetid: 3bf558fe-0705-479d-86d4-00188f5fcf9c
ms.openlocfilehash: cd2e6a6507311d5fc17215a22c70bd0449292b6f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302307"
---
# <a name="statically-compiled-queries-linq-to-xml-c"></a><span data-ttu-id="e8452-103">Statisch kompilierte Abfragen (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e8452-103">Statically Compiled Queries (LINQ to XML) (C#)</span></span>
<span data-ttu-id="e8452-104">Einer der wichtigsten Leistungsvorteile von LINQ to XML (im Unterschied zu <xref:System.Xml.XmlDocument>) besteht darin, dass Abfragen in LINQ to XML statisch kompiliert werden. XPath-Abfragen müssen dagegen zur Laufzeit interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="e8452-104">One of the most important performance benefits LINQ to XML, as opposed to <xref:System.Xml.XmlDocument>, is that queries in LINQ to XML are statically compiled, whereas XPath queries must be interpreted at run time.</span></span> <span data-ttu-id="e8452-105">Diese Funktion ist in LINQ to XML integriert, sodass Sie keine zusätzlichen Schritte ausführen müssen, um diesen Vorteil zu nutzen. Es ist jedoch hilfreich, den Unterschied zu verstehen, wenn Sie eine Auswahl zwischen den beiden Technologien treffen.</span><span class="sxs-lookup"><span data-stu-id="e8452-105">This feature is built in to LINQ to XML, so you do not have to perform extra steps to take advantage of it, but it is helpful to understand the distinction when choosing between the two technologies.</span></span> <span data-ttu-id="e8452-106">In diesem Thema wird der Unterschied erklärt.</span><span class="sxs-lookup"><span data-stu-id="e8452-106">This topic explains the difference.</span></span>  
  
## <a name="statically-compiled-queries-vs-xpath"></a><span data-ttu-id="e8452-107">Statisch kompilierte Abfragen und XPath</span><span class="sxs-lookup"><span data-stu-id="e8452-107">Statically Compiled Queries vs. XPath</span></span>  
 <span data-ttu-id="e8452-108">Im folgenden Beispiel wird gezeigt, wie Sie die Nachfolgerelemente mit einem bestimmten Namen und mit einem Attribut mit einem bestimmten Wert abrufen können.</span><span class="sxs-lookup"><span data-stu-id="e8452-108">The following example shows how to get the descendant elements with a specified name, and with an attribute with a specified value.</span></span>  
  
 <span data-ttu-id="e8452-109">Im Folgenden finden Sie den entsprechenden XPath-Ausdruck: `//Address[@Type='Shipping']`</span><span class="sxs-lookup"><span data-stu-id="e8452-109">The following is the equivalent XPath expression: `//Address[@Type='Shipping']`</span></span>
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    from el in po.Descendants("Address")  
    where (string)el.Attribute("Type") == "Shipping"  
    select el;  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="e8452-110">Der Abfrageausdruck in diesem Beispiel wird vom Compiler in eine methodenbasierte Abfragesyntax umgeschrieben.</span><span class="sxs-lookup"><span data-stu-id="e8452-110">The query expression in this example is re-written by the compiler to method-based query syntax.</span></span> <span data-ttu-id="e8452-111">Das folgende in methodenbasierter Abfragesyntax geschriebene Beispiel führt zum selben Ergebnis wie das vorherige Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8452-111">The following example, which is written in method-based query syntax, produces the same results as the previous one:</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    po  
    .Descendants("Address")  
    .Where(el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="e8452-112">Die <xref:System.Linq.Enumerable.Where%2A>-Methode ist eine Erweiterungsmethode.</span><span class="sxs-lookup"><span data-stu-id="e8452-112">The <xref:System.Linq.Enumerable.Where%2A> method is an extension method.</span></span> <span data-ttu-id="e8452-113">Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="e8452-113">For more information, see [Extension Methods](../../classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="e8452-114">Da <xref:System.Linq.Enumerable.Where%2A> eine Erweiterungsmethode ist, wird die obige Abfrage kompiliert, als wäre sie wie folgt geschrieben:</span><span class="sxs-lookup"><span data-stu-id="e8452-114">Because <xref:System.Linq.Enumerable.Where%2A> is an extension method, the query above is compiled as though it were written as follows:</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    System.Linq.Enumerable.Where(  
        po.Descendants("Address"),  
        el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="e8452-115">Dieses Beispiel führt zu genau den gleichen Ergebnissen wie die beiden vorherigen Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8452-115">This example produces exactly the same results as the previous two examples.</span></span> <span data-ttu-id="e8452-116">Dies veranschaulicht die Tatsache, dass Abfragen tatsächlich zu statisch verknüpften Methodenaufrufen kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="e8452-116">This illustrates the fact that queries are effectively compiled into statically linked method calls.</span></span> <span data-ttu-id="e8452-117">Hierdurch wird, gemeinsam mit der verzögerten Ausführungssemantik von Iteratoren, die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="e8452-117">This, combined with the deferred execution semantics of iterators, improves performance.</span></span> <span data-ttu-id="e8452-118">Weitere Informationen zu der verzögerten Ausführungssemantik von Iteratoren finden Sie unter [Verzögerte Ausführung und Auswertung in LINQ to XML (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e8452-118">For more information about the deferred execution semantics of iterators, see [Deferred Execution and Lazy Evaluation in LINQ to XML (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8452-119">Diese Beispiele sind für den Code repräsentativ, der möglicherweise vom Compiler geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="e8452-119">These examples are representative of the code that the compiler might write.</span></span> <span data-ttu-id="e8452-120">Die tatsächliche Implementierung kann in Details von diesen Beispielen abweichen, die Leistung wird jedoch weitgehend mit der dieser Beispiele übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e8452-120">The actual implementation might differ slightly from these examples, but the performance will be the same or similar to these examples.</span></span>  
  
## <a name="executing-xpath-expressions-with-xmldocument"></a><span data-ttu-id="e8452-121">Ausführen von XPath-Ausdrücken mit XmlDocument</span><span class="sxs-lookup"><span data-stu-id="e8452-121">Executing XPath Expressions with XmlDocument</span></span>  
 <span data-ttu-id="e8452-122">Im folgenden Beispiel erhalten Sie mit <xref:System.Xml.XmlDocument> dieselben Ergebnisse wie in den vorherigen Beispielen:</span><span class="sxs-lookup"><span data-stu-id="e8452-122">The following example uses <xref:System.Xml.XmlDocument> to accomplish the same results as the previous examples:</span></span>  
  
```csharp  
XmlReader reader = XmlReader.Create("PurchaseOrders.xml");  
XmlDocument doc = new XmlDocument();  
doc.Load(reader);  
XmlNodeList nl = doc.SelectNodes(".//Address[@Type='Shipping']");  
foreach (XmlNode n in nl)  
    Console.WriteLine(n.OuterXml);  
reader.Close();  
```  
  
 <span data-ttu-id="e8452-123">Diese Abfrage gibt dieselbe Ausgabe wie die Beispiele mit LINQ to XML zurück. Der einzige Unterschied ist, dass LINQ to XML das gedruckte XML im Gegensatz zu <xref:System.Xml.XmlDocument> einrückt.</span><span class="sxs-lookup"><span data-stu-id="e8452-123">This query returns the same output as the examples that use LINQ to XML; the only difference is that LINQ to XML indents the printed XML, whereas <xref:System.Xml.XmlDocument> does not.</span></span>  
  
 <span data-ttu-id="e8452-124">Der <xref:System.Xml.XmlDocument>-Ansatz bietet in der Regel nicht die Leistung von LINQ to XML, da die <xref:System.Xml.XmlNode.SelectNodes%2A>-Methode bei jedem Aufruf intern die folgenden Schritte ausführen muss:</span><span class="sxs-lookup"><span data-stu-id="e8452-124">However, the <xref:System.Xml.XmlDocument> approach generally does not perform as well as LINQ to XML, because the <xref:System.Xml.XmlNode.SelectNodes%2A> method must do the following internally every time it is called:</span></span>  
  
- <span data-ttu-id="e8452-125">Analysieren der Zeichenfolge, die den XPath-Ausdruck enthält, und Zerlegen der Zeichenfolge in Token.</span><span class="sxs-lookup"><span data-stu-id="e8452-125">It parses the string that contains the XPath expression, breaking the string into tokens.</span></span>  
  
- <span data-ttu-id="e8452-126">Überprüfen der Token, um sicherzustellen, dass der XPath-Ausdruck gültig ist.</span><span class="sxs-lookup"><span data-stu-id="e8452-126">It validates the tokens to make sure that the XPath expression is valid.</span></span>  
  
- <span data-ttu-id="e8452-127">Übersetzen des Ausdrucks in eine interne Ausdrucksstruktur.</span><span class="sxs-lookup"><span data-stu-id="e8452-127">It translates the expression into an internal expression tree.</span></span>  
  
- <span data-ttu-id="e8452-128">Durchlaufen der Knoten und entsprechendes Auswählen der Knoten für das Resultset auf Grundlage der Ausdrucksauswertung.</span><span class="sxs-lookup"><span data-stu-id="e8452-128">It iterates through the nodes, appropriately selecting the nodes for the result set based on the evaluation of the expression.</span></span>  
  
 <span data-ttu-id="e8452-129">Dies sind bedeutend mehr Arbeitsschritte als bei einer entsprechenden LINQ to XML-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="e8452-129">This is significantly more than the work done by the corresponding LINQ to XML query.</span></span> <span data-ttu-id="e8452-130">Die genauen Leistungsunterschiede variieren je nach Abfragetyp, in der Regel müssen LINQ to XML-Abfragen jedoch weniger Arbeitsschritte ausführen und bieten daher eine bessere Leistung als das Auswerten von XPath-Ausdrücken mit <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="e8452-130">The specific performance difference varies for different types of queries, but in general LINQ to XML queries do less work, and therefore perform better, than evaluating XPath expressions using <xref:System.Xml.XmlDocument>.</span></span>  
