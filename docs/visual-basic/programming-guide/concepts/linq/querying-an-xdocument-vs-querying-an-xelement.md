---
title: Vergleich zwischen dem Abfragen eines &quot;XDocument&quot; und dem Abfragen ein &quot;XElement&quot; (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 2d111f84-0ded-4cde-8d93-5440557a726d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 93f0f7f50ad305540a6afef2374d4b948de48705
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="querying-an-xdocument-vs-querying-an-xelement-visual-basic"></a><span data-ttu-id="5635a-102">Vergleich zwischen dem Abfragen eines "XDocument" und dem Abfragen ein "XElement" (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5635a-102">Querying an XDocument vs. Querying an XElement (Visual Basic)</span></span>
<span data-ttu-id="5635a-103">Wenn Sie ein Dokument über <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, werden Sie feststellen, dass Sie etwas anders als beim Laden über <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.</xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> Abfragen schreiben müssen,</xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> laden</span><span class="sxs-lookup"><span data-stu-id="5635a-103">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="5635a-104">Vergleich zwischen "XDocument.Load" und "XElement.Load"</span><span class="sxs-lookup"><span data-stu-id="5635a-104">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="5635a-105">Beim Laden eines XML-Dokuments in ein <xref:System.Xml.Linq.XElement>über <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, die <xref:System.Xml.Linq.XElement>am Stamm der XML-Struktur das Stammelement des geladenen Dokuments enthält.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="5635a-105">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="5635a-106">Allerdings laden Wenn Sie dasselbe XML-Dokument in eine <xref:System.Xml.Linq.XDocument>über <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>den Stamm der Struktur ist ein <xref:System.Xml.Linq.XDocument>Knoten, und das Stammelement des geladenen Dokuments ist der einen zulässigen untergeordneten <xref:System.Xml.Linq.XElement>Knoten des <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="5635a-106">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="5635a-107">Die [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Achsen agieren relativ zum Stammknoten.</span><span class="sxs-lookup"><span data-stu-id="5635a-107">The [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="5635a-108">Dieses erstes Beispiel lädt eine XML-Struktur mithilfe von <xref:System.Xml.Linq.XElement.Load%2A>.</xref:System.Xml.Linq.XElement.Load%2A></span><span class="sxs-lookup"><span data-stu-id="5635a-108">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="5635a-109">Anschließend fragt es die untergeordneten Elemente des Stamms der Struktur ab:</span><span class="sxs-lookup"><span data-stu-id="5635a-109">It then queries for the child elements of the root of the tree.</span></span>  
  
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
  
 <span data-ttu-id="5635a-110">Wie zu erwarten, erzeugt dieses Beispiel die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="5635a-110">As expected, this example produces the following output:</span></span>  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="5635a-111">Im folgende Beispiel wird der gleiche wie der oben mit der Ausnahme, dass die XML-Struktur in eine <xref:System.Xml.Linq.XDocument>anstelle einer <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> geladen wird</span><span class="sxs-lookup"><span data-stu-id="5635a-111">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
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
  
 <span data-ttu-id="5635a-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="5635a-112">This example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="5635a-113">Dieselbe Abfrage hat also diesmal nicht die drei untergeordneten Knoten, sondern den einen `Root`-Knoten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5635a-113">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="5635a-114">Ein Ansatz für den Umgang mit diesem Verhalten ist die Verwendung der <xref:System.Xml.Linq.XDocument.Root%2A>Eigenschaft vor dem Zugriff auf die Achsenmethoden wie folgt:</xref:System.Xml.Linq.XDocument.Root%2A></span><span class="sxs-lookup"><span data-stu-id="5635a-114">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
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
  
 <span data-ttu-id="5635a-115">Diese Abfrage führt jetzt in der gleichen Weise wie die Abfrage für die Struktur als Stamm <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="5635a-115">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="5635a-116">Das Beispiel führt zur folgenden Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="5635a-116">The example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5635a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5635a-117">See Also</span></span>  
 [<span data-ttu-id="5635a-118">Standardabfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5635a-118">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
