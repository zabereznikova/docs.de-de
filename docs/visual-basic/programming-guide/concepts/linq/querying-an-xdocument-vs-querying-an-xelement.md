---
title: Vergleich zwischen dem Abfragen eines "XDocument" und dem Abfragen ein "XElement" (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2d111f84-0ded-4cde-8d93-5440557a726d
ms.openlocfilehash: 8d13276b6d66d0ec3768182df7b4324678174fae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54579844"
---
# <a name="querying-an-xdocument-vs-querying-an-xelement-visual-basic"></a><span data-ttu-id="79c95-102">Vergleich zwischen dem Abfragen eines "XDocument" und dem Abfragen ein "XElement" (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79c95-102">Querying an XDocument vs. Querying an XElement (Visual Basic)</span></span>
<span data-ttu-id="79c95-103">Das Schreiben von Abfragen für Dokumente, die über <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> geladen werden, unterscheidet sich geringfügig vom Schreiben von Abfragen für Dokumente, die über <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> geladen werden.</span><span class="sxs-lookup"><span data-stu-id="79c95-103">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="79c95-104">Vergleich zwischen "XDocument.Load" und "XElement.Load"</span><span class="sxs-lookup"><span data-stu-id="79c95-104">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="79c95-105">Beim Laden eines XML-Dokuments in ein <xref:System.Xml.Linq.XElement> über <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> enthält das <xref:System.Xml.Linq.XElement> am Stamm der XML-Struktur das Stammelement des geladenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="79c95-105">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="79c95-106">Wenn Sie jedoch dasselbe XML-Dokument über <xref:System.Xml.Linq.XDocument> in ein <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> laden, ist der Stamm der Struktur ein <xref:System.Xml.Linq.XDocument>-Knoten, und das Stammelement des geladenen Dokuments ist der einzige zulässige untergeordnete <xref:System.Xml.Linq.XElement>-Knoten des <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="79c95-106">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="79c95-107">Die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Achsen agieren relativ zum Stammknoten.</span><span class="sxs-lookup"><span data-stu-id="79c95-107">The [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="79c95-108">Dieses erstes Beispiel lädt eine XML-Struktur mit <xref:System.Xml.Linq.XElement.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="79c95-108">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="79c95-109">Anschließend fragt es die untergeordneten Elemente des Stamms der Struktur ab:</span><span class="sxs-lookup"><span data-stu-id="79c95-109">It then queries for the child elements of the root of the tree.</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XElement.Load")  
Console.WriteLine("----")  
Dim doc As XElement = XElement.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="79c95-110">Wie zu erwarten, erzeugt dieses Beispiel die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="79c95-110">As expected, this example produces the following output:</span></span>  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="79c95-111">Das folgende Beispiel entspricht dem vorhergehenden Beispiel, wobei hier die XML-Struktur nicht in ein <xref:System.Xml.Linq.XDocument>, sondern in ein <xref:System.Xml.Linq.XElement> geladen wird:</span><span class="sxs-lookup"><span data-stu-id="79c95-111">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="79c95-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="79c95-112">This example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="79c95-113">Dieselbe Abfrage hat also diesmal nicht die drei untergeordneten Knoten, sondern den einen `Root`-Knoten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="79c95-113">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="79c95-114">Ein Ansatz für den Umgang mit diesem Verhalten besteht darin, vor dem Zugreifen auf die Achsenmethoden die <xref:System.Xml.Linq.XDocument.Root%2A>-Eigenschaft zu verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="79c95-114">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Root.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="79c95-115">Diese Abfrage ist jetzt genauso schnell wie die Abfrage für die Struktur mit dem <xref:System.Xml.Linq.XElement> als Stammelement.</span><span class="sxs-lookup"><span data-stu-id="79c95-115">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="79c95-116">Das Beispiel führt zur folgenden Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="79c95-116">The example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a><span data-ttu-id="79c95-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79c95-117">See also</span></span>
- [<span data-ttu-id="79c95-118">Standardabfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79c95-118">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
