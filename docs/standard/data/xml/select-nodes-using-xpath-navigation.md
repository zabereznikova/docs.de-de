---
title: Auswählen von Knoten mithilfe der XPath-Navigation
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 8e4450dc-56b3-472b-b467-32f5694f83ad
ms.openlocfilehash: 58f1487486c2802a2c64b51afcecb01c76dd291a
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155606"
---
# <a name="select-nodes-using-xpath-navigation"></a><span data-ttu-id="227a7-102">Auswählen von Knoten mithilfe der XPath-Navigation</span><span class="sxs-lookup"><span data-stu-id="227a7-102">Select Nodes Using XPath Navigation</span></span>
<span data-ttu-id="227a7-103">Das XML-DOM (Document Object Model) enthält Methoden, die Ihnen ermöglichen, mithilfe der XPath-Navigation (XML Path Language) Informationen im DOM abzufragen.</span><span class="sxs-lookup"><span data-stu-id="227a7-103">The XML Document Object Model (DOM) contains methods that allow you to use XML Path Language (XPath) navigation to query information in the DOM.</span></span> <span data-ttu-id="227a7-104">Mit XPath können Sie einen bestimmten einzelnen Knoten oder alle Knoten suchen, die bestimmte Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="227a7-104">You can use XPath to find a single, specific node or to find all nodes that match some criteria.</span></span>  
  
## <a name="xpath-select-methods"></a><span data-ttu-id="227a7-105">XPath-Auswahlmethoden</span><span class="sxs-lookup"><span data-stu-id="227a7-105">XPath Select Methods</span></span>  
 <span data-ttu-id="227a7-106">Die DOM-Klassen stellen zwei Methoden für die XPath-Auswahl bereit: die <xref:System.Xml.XmlNode.SelectSingleNode%2A>-Methode und die <xref:System.Xml.XmlNode.SelectNodes%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="227a7-106">The DOM classes provide two methods for XPath selection: the <xref:System.Xml.XmlNode.SelectSingleNode%2A> method and the <xref:System.Xml.XmlNode.SelectNodes%2A> method.</span></span> <span data-ttu-id="227a7-107">Die <xref:System.Xml.XmlNode.SelectSingleNode%2A>-Methode gibt den ersten Knoten zurück, der die Auswahlkriterien erfüllt.</span><span class="sxs-lookup"><span data-stu-id="227a7-107">The <xref:System.Xml.XmlNode.SelectSingleNode%2A> method returns the first node that matches the selection criteria.</span></span> <span data-ttu-id="227a7-108">Die <xref:System.Xml.XmlNode.SelectNodes%2A>-Methode gibt eine <xref:System.Xml.XmlNodeList> zurück, die die übereinstimmenden Knoten enthält.</span><span class="sxs-lookup"><span data-stu-id="227a7-108">The <xref:System.Xml.XmlNode.SelectNodes%2A> method returns an <xref:System.Xml.XmlNodeList> that contains the matching nodes.</span></span>  
  
 <span data-ttu-id="227a7-109">Im folgenden Beispiel wird mit der <xref:System.Xml.XmlNode.SelectSingleNode%2A>-Methode der erste `book`-Knoten ausgewählt, bei dem der Nachname des Autors den angegebenen Kriterien entspricht.</span><span class="sxs-lookup"><span data-stu-id="227a7-109">The following example uses the <xref:System.Xml.XmlNode.SelectSingleNode%2A> method to select the first `book` node in which the author's last name meets the specified criteria.</span></span> <span data-ttu-id="227a7-110">Die Datei bookstore.xml (die am Ende dieses Themas zur Verfügung gestellt wird) wird als Eingabedatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="227a7-110">The bookstore.xml file (which is provided at the end of this topic) is used as the input file.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select and display the first node in which the author's
' last name is Kingsolver.  
Dim node As XmlNode = root.SelectSingleNode( _  
     "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr)  
Console.WriteLine(node.InnerXml)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select and display the first node in which the author's
// last name is Kingsolver.  
XmlNode node = root.SelectSingleNode(  
    "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr);  
Console.WriteLine(node.InnerXml);  
```  
  
 <span data-ttu-id="227a7-111">Im nächsten Beispiel werden mit der <xref:System.Xml.XmlNode.SelectNodes%2A>-Methode alle Buchknoten ausgewählt, bei denen der Preis größer ist als eine angegebene Summe.</span><span class="sxs-lookup"><span data-stu-id="227a7-111">The next example uses the <xref:System.Xml.XmlNode.SelectNodes%2A> method to select all the book nodes in which the price is greater than a specified amount.</span></span> <span data-ttu-id="227a7-112">Der Preis für jedes Buch in der ausgewählten Liste wird dann programmgesteuert um zehn Prozent reduziert.</span><span class="sxs-lookup"><span data-stu-id="227a7-112">The price for each book in the selected list is then programmatically reduced by ten percent.</span></span> <span data-ttu-id="227a7-113">Schließlich wird die aktualisierte Datei in die Konsole geschrieben.</span><span class="sxs-lookup"><span data-stu-id="227a7-113">Finally, the updated file is written to the console.</span></span> <span data-ttu-id="227a7-114">Die Datei bookstore.xml (die am Ende dieses Themas zur Verfügung gestellt wird) wird als Eingabedatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="227a7-114">The bookstore.xml file (which is provided at the end of this topic) is used as the input file.</span></span>  
  
```vb  
' Load the document and set the root element.  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select all nodes where the book price is greater than 10.00.  
Dim nodeList As XmlNodeList = root.SelectNodes( _  
     "descendant::bk:book[bk:price>10.00]", nsmgr)  
For Each book As XmlNode In nodeList  
     Dim price As Double  
     price = Math.Round(Convert.ToSingle( _  
          book.LastChild.InnerText) * 0.9, 2)  
     book.LastChild.InnerText = price.ToString()  
Next  
  
' Display the updated document.  
doc.Save(Console.Out)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select all nodes where the book price is greater than 10.00.  
XmlNodeList nodeList = root.SelectNodes(  
     "descendant::bk:book[bk:price>10.00]", nsmgr);  
foreach (XmlNode book in nodeList)  
{  
     // Discount prices by 10%.  
     double price;  
     price = Math.Round(Convert.ToSingle(  
          book.LastChild.InnerText) * 0.9, 2);  
     book.LastChild.InnerText = price.ToString();  
}  
  
// Display the updated document.  
doc.Save(Console.Out);  
```  
  
 <span data-ttu-id="227a7-115">In den Beispielen oben wird die XPath-Abfrage beim Dokumentelement begonnen.</span><span class="sxs-lookup"><span data-stu-id="227a7-115">The examples above start the XPath query at the document element.</span></span> <span data-ttu-id="227a7-116">Durch das Festlegen des Anfangspunkts für die XPath-Abfrage wird der Kontextknoten festgelegt, der den Anfangspunkt der XPath-Abfrage darstellt.</span><span class="sxs-lookup"><span data-stu-id="227a7-116">Setting the starting point for the XPath query sets the context node, which is the starting point for the XPath query.</span></span> <span data-ttu-id="227a7-117">Wenn Sie nicht beim Dokumentelement beginnen möchten, sondern bei seinem ersten untergeordneten Element, können Sie die select-Anweisung wie folgt schreiben:</span><span class="sxs-lookup"><span data-stu-id="227a7-117">If you do not want to start at the document element, but want to start from the first child of the document element, you can code the select statement as follows:</span></span>  
  
```vb  
doc.DocumentElement.FirstChild.SelectNodes(. . . )  
```  
  
```csharp  
this doc.DocumentElement.FirstChild.SelectNodes(. . .);  
```  
  
 <span data-ttu-id="227a7-118">Alle <xref:System.Xml.XmlNodeList>-Objekte werden mit dem zugrunde liegenden Dokument synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="227a7-118">All <xref:System.Xml.XmlNodeList> objects are synchronized with the underlying document.</span></span> <span data-ttu-id="227a7-119">Wenn Sie die Knotenliste durchlaufen und den Wert eines Knotens ändern, wird dieser Knoten daher auch in dem Dokument aktualisiert, aus dem er stammt.</span><span class="sxs-lookup"><span data-stu-id="227a7-119">Therefore, if you iterate through the node list and modify the value of a node, that node is also updated in the document it came from.</span></span> <span data-ttu-id="227a7-120">Beachten Sie, dass im vorhergehenden Beispiel auch das zugrunde liegende Dokument geändert wird, wenn ein Knoten in der ausgewählten <xref:System.Xml.XmlNodeList> geändert wird.</span><span class="sxs-lookup"><span data-stu-id="227a7-120">Notice in the previous example that when a node is modified in the selected <xref:System.Xml.XmlNodeList> the underlying document is also modified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="227a7-121">Wenn das zugrunde liegenden Dokument verändert wird, ist es empfehlenswert, die Auswahl erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="227a7-121">When the underlying document is modified, it is advisable to rerun the select.</span></span> <span data-ttu-id="227a7-122">Wenn die Änderung des Knoten dazu führen kann, dass der Knoten der Knotenliste hinzugefügt wird, wenn dies vorher nicht der Fall war, oder dass der Knoten aus der Knotenliste entfernt wird, kann nicht garantiert werden, dass die Knotenliste korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="227a7-122">If the node modified is one that could cause the node to be added to the node list when it was not previously, or would now cause it to be removed from the node list, there is no guarantee that the node list is now accurate.</span></span>  
  
## <a name="namespaces-in-xpath-expressions"></a><span data-ttu-id="227a7-123">Namespaces in XPath-Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="227a7-123">Namespaces in XPath Expressions</span></span>  
 <span data-ttu-id="227a7-124">XPath-Ausdrücke können Namespaces enthalten.</span><span class="sxs-lookup"><span data-stu-id="227a7-124">XPath expressions can include namespaces.</span></span> <span data-ttu-id="227a7-125">Namespace-Auflösung wird mithilfe von <xref:System.Xml.XmlNamespaceManager> unterstützt.</span><span class="sxs-lookup"><span data-stu-id="227a7-125">Namespace resolution is supported using the <xref:System.Xml.XmlNamespaceManager>.</span></span> <span data-ttu-id="227a7-126">Wenn der XPath-Ausdruck ein Präfix umfasst, muss das Paar aus Präfix- und Namespace-URI <xref:System.Xml.XmlNamespaceManager> hinzugefügt werden, und <xref:System.Xml.XmlNamespaceManager> wird an die <xref:System.Xml.XmlNode.SelectNodes%28System.String%2CSystem.Xml.XmlNamespaceManager%29>-Methode oder die <xref:System.Xml.XmlNode.SelectSingleNode%28System.String%2CSystem.Xml.XmlNamespaceManager%29>-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="227a7-126">If the XPath expression includes a prefix, the prefix and namespace URI pair must be added to the <xref:System.Xml.XmlNamespaceManager>, and the <xref:System.Xml.XmlNamespaceManager> is passed to the <xref:System.Xml.XmlNode.SelectNodes%28System.String%2CSystem.Xml.XmlNamespaceManager%29> or <xref:System.Xml.XmlNode.SelectSingleNode%28System.String%2CSystem.Xml.XmlNamespaceManager%29> method.</span></span> <span data-ttu-id="227a7-127">Beachten Sie, dass die oben aufgeführten Codebeispiele <xref:System.Xml.XmlNamespaceManager> verwenden, um den Namespace des Dokuments bookstore.xml aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="227a7-127">Notice that the code examples above use the <xref:System.Xml.XmlNamespaceManager> to resolve the namespace of the bookstore.xml document.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="227a7-128">Wenn der XPath-Ausdruck kein Präfix umfasst, wird davon ausgegangen, dass der Namespace-URI (Uniform Resource Identifier) der leere Namespace ist.</span><span class="sxs-lookup"><span data-stu-id="227a7-128">If the XPath expression does not include a prefix, it is assumed that the namespace Uniform Resource Identifier (URI) is the empty namespace.</span></span> <span data-ttu-id="227a7-129">Wenn die XML einen Standardnamespace umfasst, muss <xref:System.Xml.XmlNamespaceManager> trotzdem ein Präfix und Namespace-URI hinzugefügt werden. Andernfalls werden keine Knoten ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="227a7-129">If your XML includes a default namespace, you must still add a prefix and namespace URI to the <xref:System.Xml.XmlNamespaceManager>; otherwise, no nodes will be selected.</span></span>  
  
#### <a name="input-file"></a><span data-ttu-id="227a7-130">Eingabedatei</span><span class="sxs-lookup"><span data-stu-id="227a7-130">Input File</span></span>  
 <span data-ttu-id="227a7-131">Nachfolgend ist die Datei bookstore.xml aufgeführt, die für die Beispiele in diesem Thema als Eingabedatei verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="227a7-131">The following is the bookstore.xml file that is used as the input file in the examples in this topic:</span></span>  
  
```xml  
<?xml version='1.0'?>  
<bookstore xmlns="urn:newbooks-schema">  
  <book genre="novel" style="hardcover">  
    <title>The Handmaid's Tale</title>  
    <author>  
      <first-name>Margaret</first-name>  
      <last-name>Atwood</last-name>  
    </author>  
    <price>19.95</price>  
  </book>  
  <book genre="novel" style="other">  
    <title>The Poisonwood Bible</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>11.99</price>  
  </book>  
  <book genre="novel" style="paperback">  
    <title>The Bean Trees</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>5.99</price>  
  </book>  
</bookstore>  
```  
  
## <a name="see-also"></a><span data-ttu-id="227a7-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="227a7-132">See also</span></span>

- [<span data-ttu-id="227a7-133">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="227a7-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
