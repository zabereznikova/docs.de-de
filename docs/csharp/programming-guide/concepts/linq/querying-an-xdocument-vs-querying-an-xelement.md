---
title: Vergleich zwischen dem Abfragen eines "XDocument" und dem Abfragen eines „XElement“ (C#)
description: Lernen Sie die Unterschiede zwischen dem Abfragen von XDocument und XElement kennen. Sehen Sie sich Codebeispiele an, die diese Unterschiede veranschaulichen.
ms.date: 07/20/2015
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
ms.openlocfilehash: 0c81768f06148308a639f96f4041e464b24edd33
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87300318"
---
# <a name="querying-an-xdocument-vs-querying-an-xelement-c"></a><span data-ttu-id="095ef-104">Vergleich zwischen dem Abfragen eines "XDocument" und dem Abfragen eines „XElement“ (C#)</span><span class="sxs-lookup"><span data-stu-id="095ef-104">Querying an XDocument vs. Querying an XElement (C#)</span></span>
<span data-ttu-id="095ef-105">Das Schreiben von Abfragen für Dokumente, die über <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> geladen werden, unterscheidet sich geringfügig vom Schreiben von Abfragen für Dokumente, die über <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> geladen werden.</span><span class="sxs-lookup"><span data-stu-id="095ef-105">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="095ef-106">Vergleich zwischen "XDocument.Load" und "XElement.Load"</span><span class="sxs-lookup"><span data-stu-id="095ef-106">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="095ef-107">Beim Laden eines XML-Dokuments in ein <xref:System.Xml.Linq.XElement> über <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> enthält das <xref:System.Xml.Linq.XElement> am Stamm der XML-Struktur das Stammelement des geladenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="095ef-107">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="095ef-108">Wenn Sie jedoch dasselbe XML-Dokument über <xref:System.Xml.Linq.XDocument> in ein <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> laden, ist der Stamm der Struktur ein <xref:System.Xml.Linq.XDocument>-Knoten, und das Stammelement des geladenen Dokuments ist der einzige zulässige untergeordnete <xref:System.Xml.Linq.XElement>-Knoten des <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="095ef-108">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="095ef-109">Die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Achsen agieren relativ zum Stammknoten.</span><span class="sxs-lookup"><span data-stu-id="095ef-109">The [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="095ef-110">Dieses erstes Beispiel lädt eine XML-Struktur mit <xref:System.Xml.Linq.XElement.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="095ef-110">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="095ef-111">Anschließend fragt es die untergeordneten Elemente des Stamms der Struktur ab:</span><span class="sxs-lookup"><span data-stu-id="095ef-111">It then queries for the child elements of the root of the tree.</span></span>  
  
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
  
 <span data-ttu-id="095ef-112">Wie zu erwarten, erzeugt dieses Beispiel die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="095ef-112">As expected, this example produces the following output:</span></span>  
  
```output  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="095ef-113">Das folgende Beispiel entspricht dem vorhergehenden Beispiel, wobei hier die XML-Struktur nicht in ein <xref:System.Xml.Linq.XDocument>, sondern in ein <xref:System.Xml.Linq.XElement> geladen wird:</span><span class="sxs-lookup"><span data-stu-id="095ef-113">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
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
  
 <span data-ttu-id="095ef-114">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="095ef-114">This example produces the following output:</span></span>  
  
```output  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="095ef-115">Dieselbe Abfrage hat also diesmal nicht die drei untergeordneten Knoten, sondern den einen `Root`-Knoten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="095ef-115">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="095ef-116">Ein Ansatz für den Umgang mit diesem Verhalten besteht darin, vor dem Zugreifen auf die Achsenmethoden die <xref:System.Xml.Linq.XDocument.Root%2A>-Eigenschaft zu verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="095ef-116">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
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
  
 <span data-ttu-id="095ef-117">Diese Abfrage ist jetzt genauso schnell wie die Abfrage für die Struktur mit dem <xref:System.Xml.Linq.XElement> als Stammelement.</span><span class="sxs-lookup"><span data-stu-id="095ef-117">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="095ef-118">Das Beispiel führt zur folgenden Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="095ef-118">The example produces the following output:</span></span>  
  
```output  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  