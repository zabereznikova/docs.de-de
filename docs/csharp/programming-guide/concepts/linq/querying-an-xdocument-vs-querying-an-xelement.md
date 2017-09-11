---
title: "Vergleich zwischen dem Abfragen eines \"XDocument\" und dem Abfragen eines „XElement“ (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fa756d4adb1c361ef52e58bf6bdfd3bc2e31d13a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="querying-an-xdocument-vs-querying-an-xelement-c"></a><span data-ttu-id="34e6e-102">Vergleich zwischen dem Abfragen eines "XDocument" und dem Abfragen eines „XElement“ (C#)</span><span class="sxs-lookup"><span data-stu-id="34e6e-102">Querying an XDocument vs. Querying an XElement (C#)</span></span>
<span data-ttu-id="34e6e-103">Das Schreiben von Abfragen für Dokumente, die über <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> geladen werden, unterscheidet sich geringfügig vom Schreiben von Abfragen für Dokumente, die über <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> geladen werden.</span><span class="sxs-lookup"><span data-stu-id="34e6e-103">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="34e6e-104">Vergleich zwischen "XDocument.Load" und "XElement.Load"</span><span class="sxs-lookup"><span data-stu-id="34e6e-104">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="34e6e-105">Beim Laden eines XML-Dokuments in ein <xref:System.Xml.Linq.XElement> über <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> enthält das <xref:System.Xml.Linq.XElement> am Stamm der XML-Struktur das Stammelement des geladenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="34e6e-105">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="34e6e-106">Wenn Sie jedoch dasselbe XML-Dokument über <xref:System.Xml.Linq.XDocument> in ein <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> laden, ist der Stamm der Struktur ein <xref:System.Xml.Linq.XDocument>-Knoten, und das Stammelement des geladenen Dokuments ist der einzige zulässige untergeordnete <xref:System.Xml.Linq.XElement>-Knoten des <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="34e6e-106">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="34e6e-107">Die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Achsen agieren relativ zum Stammknoten.</span><span class="sxs-lookup"><span data-stu-id="34e6e-107">The [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="34e6e-108">Dieses erstes Beispiel lädt eine XML-Struktur mit <xref:System.Xml.Linq.XElement.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="34e6e-108">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="34e6e-109">Anschließend fragt es die untergeordneten Elemente des Stamms der Struktur ab:</span><span class="sxs-lookup"><span data-stu-id="34e6e-109">It then queries for the child elements of the root of the tree.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XElement.Load");  
Console.WriteLine("----");  
XElement doc = XElement.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="34e6e-110">Wie zu erwarten, erzeugt dieses Beispiel die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="34e6e-110">As expected, this example produces the following output:</span></span>  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="34e6e-111">Das folgende Beispiel entspricht dem vorhergehenden Beispiel, wobei hier die XML-Struktur nicht in ein <xref:System.Xml.Linq.XDocument>, sondern in ein <xref:System.Xml.Linq.XElement> geladen wird:</span><span class="sxs-lookup"><span data-stu-id="34e6e-111">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="34e6e-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="34e6e-112">This example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="34e6e-113">Dieselbe Abfrage hat also diesmal nicht die drei untergeordneten Knoten, sondern den einen `Root`-Knoten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="34e6e-113">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="34e6e-114">Ein Ansatz für den Umgang mit diesem Verhalten besteht darin, vor dem Zugreifen auf die Achsenmethoden die <xref:System.Xml.Linq.XDocument.Root%2A>-Eigenschaft zu verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="34e6e-114">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Root.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="34e6e-115">Diese Abfrage ist jetzt genauso schnell wie die Abfrage für die Struktur mit dem <xref:System.Xml.Linq.XElement> als Stammelement.</span><span class="sxs-lookup"><span data-stu-id="34e6e-115">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="34e6e-116">Das Beispiel führt zur folgenden Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="34e6e-116">The example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a><span data-ttu-id="34e6e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34e6e-117">See Also</span></span>  
 [<span data-ttu-id="34e6e-118">Basic Queries (LINQ to XML) (C#) (Standardabfragen (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="34e6e-118">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

