---
title: Extrahieren von XML-Daten mit XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 095b0987-ee4b-4595-a160-da1c956ad576
ms.openlocfilehash: 627da3c8c45d007e677c4f92f4d5cd602d34ae84
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710855"
---
# <a name="extract-xml-data-using-xpathnavigator"></a><span data-ttu-id="67f0c-102">Extrahieren von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="67f0c-102">Extract XML Data Using XPathNavigator</span></span>
<span data-ttu-id="67f0c-103">Es gibt in Microsoft .NET Framework mehre Möglichkeiten zur Darstellung eines XML-Dokuments.</span><span class="sxs-lookup"><span data-stu-id="67f0c-103">There are several different ways to represent an XML document in the Microsoft .NET Framework.</span></span> <span data-ttu-id="67f0c-104">Es kann ein <xref:System.String> oder eine der Klassen <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, <xref:System.Xml.XmlDocument> oder <xref:System.Xml.XPath.XPathDocument> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="67f0c-104">This includes using a <xref:System.String>, or by using the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, <xref:System.Xml.XmlDocument>, or <xref:System.Xml.XPath.XPathDocument> classes.</span></span> <span data-ttu-id="67f0c-105">Um den Wechsel zwischen verschiedenen Darstellungen eines XML-Dokuments zu erleichtern, stellt die <xref:System.Xml.XPath.XPathNavigator>-Klasse eine Reihe von Methoden und Eigenschaften zum Extrahieren von XML als <xref:System.String>, als <xref:System.Xml.XmlReader>-Objekt oder als <xref:System.Xml.XmlWriter>-Objekt bereit.</span><span class="sxs-lookup"><span data-stu-id="67f0c-105">To facilitate moving between these different representations of an XML document, the <xref:System.Xml.XPath.XPathNavigator> class provides a number of methods and properties for extracting the XML as a <xref:System.String>, <xref:System.Xml.XmlReader> object or <xref:System.Xml.XmlWriter> object.</span></span>  
  
## <a name="convert-an-xpathnavigator-to-a-string"></a><span data-ttu-id="67f0c-106">Konvertiert einen XPathNavigator in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="67f0c-106">Convert an XPathNavigator to a String</span></span>  
 <span data-ttu-id="67f0c-107">Die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse wird zum Abrufen des Markups des ganzen XML-Dokuments oder des Markups eines einzelnen Knotens und seiner untergeordneten Knoten verwendet.</span><span class="sxs-lookup"><span data-stu-id="67f0c-107">The <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class is used to get the markup of the entire XML document or just the markup of a single node and its child nodes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67f0c-108">Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft ruft das Markup der einem Knoten untergeordneten Knoten ab.</span><span class="sxs-lookup"><span data-stu-id="67f0c-108">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property gets the markup of just the child nodes of a node.</span></span>  
  
 <span data-ttu-id="67f0c-109">Im folgenden Codebeispiel wird das ganze in einem <xref:System.Xml.XPath.XPathNavigator>-Objekt enthaltene XML-Dokument sowohl als <xref:System.String> als auch als einzelner Knoten mit untergeordneten Knoten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="67f0c-109">The following code example shows how to save an entire XML document contained in an <xref:System.Xml.XPath.XPathNavigator> object as a <xref:System.String>, as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("input.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Save the entire input.xml document to a string.  
Dim xml As String = navigator.OuterXml  
  
' Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element)  
Dim root As String = navigator.OuterXml  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Save the entire input.xml document to a string.  
string xml = navigator.OuterXml;  
  
// Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element);  
string root = navigator.OuterXml;  
```  
  
## <a name="convert-an-xpathnavigator-to-an-xmlreader"></a><span data-ttu-id="67f0c-110">Konvertiert von XPathNavigator in XmlReader</span><span class="sxs-lookup"><span data-stu-id="67f0c-110">Convert an XPathNavigator to an XmlReader</span></span>  
 <span data-ttu-id="67f0c-111">Mit der <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A>-Methode wird gesamte Inhalt eines XML-Dokuments oder nur ein einzelner Knoten und seine untergeordneten Knoten als Stream in ein <xref:System.Xml.XmlReader>-Objekt übertragen.</span><span class="sxs-lookup"><span data-stu-id="67f0c-111">The <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> method is used to stream the entire contents of an XML document or just a single node and its child nodes to an <xref:System.Xml.XmlReader> object.</span></span>  
  
 <span data-ttu-id="67f0c-112">Beim Erstellen des <xref:System.Xml.XmlReader>-Objekts aus dem aktuellen Knoten und den untergeordneten Knoten wird die <xref:System.Xml.XmlReader>-Eigenschaft des <xref:System.Xml.XmlReader.ReadState%2A>-Objekts auf <xref:System.Xml.ReadState.Initial> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="67f0c-112">When the <xref:System.Xml.XmlReader> object is created with the current node and its child nodes, the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.ReadState%2A> property is set to <xref:System.Xml.ReadState.Initial>.</span></span> <span data-ttu-id="67f0c-113">Beim ersten Aufruf der <xref:System.Xml.XmlReader>-Methode des <xref:System.Xml.XmlReader.Read%2A>-Objekts wird die Position des <xref:System.Xml.XmlReader> auf den aktuellen Knoten des <xref:System.Xml.XPath.XPathNavigator> verschoben.</span><span class="sxs-lookup"><span data-stu-id="67f0c-113">When the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.Read%2A> method is called for the first time, the <xref:System.Xml.XmlReader> is moved to the current node of the <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="67f0c-114">Das neue <xref:System.Xml.XmlReader>-Objekt setzt den Lesevorgang bis zum Ende der XML-Struktur fort.</span><span class="sxs-lookup"><span data-stu-id="67f0c-114">The new <xref:System.Xml.XmlReader> object continues to read until the end of the XML tree is reached.</span></span> <span data-ttu-id="67f0c-115">In diesem Fall gibt die <xref:System.Xml.XmlReader.Read%2A>-Methode `false` zurück und die <xref:System.Xml.XmlReader>-Eigenschaft des <xref:System.Xml.XmlReader.ReadState%2A>-Objekts wird auf <xref:System.Xml.ReadState.EndOfFile> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="67f0c-115">At this point, the <xref:System.Xml.XmlReader.Read%2A> method returns `false` and the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.ReadState%2A> property is set to <xref:System.Xml.ReadState.EndOfFile>.</span></span>  
  
 <span data-ttu-id="67f0c-116">Die Position des <xref:System.Xml.XPath.XPathNavigator>-Objekts wird durch das Erstellen oder das Verschieben des <xref:System.Xml.XmlReader>-Objekts nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="67f0c-116">The <xref:System.Xml.XPath.XPathNavigator> object's position is unchanged by the creation or movement of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="67f0c-117">Ein Aufruf der <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A>-Methode ist nur dann zulässig, wenn das Objekt auf einem Element oder auf dem Stammknoten positioniert ist.</span><span class="sxs-lookup"><span data-stu-id="67f0c-117">The <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> method is only valid when positioned on an element or root node.</span></span>  
  
 <span data-ttu-id="67f0c-118">Im folgenden Beispiel wird ein <xref:System.Xml.XmlReader>-Objekt erstellt, das das ganze XML-Dokument sowohl in einem <xref:System.Xml.XPath.XPathDocument>-Objekt als auch als einzelnen Knoten mit untergeordneten Knoten enthält.</span><span class="sxs-lookup"><span data-stu-id="67f0c-118">The following example shows how to get an <xref:System.Xml.XmlReader> object containing the entire XML document in an <xref:System.Xml.XPath.XPathDocument> object as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlReader.  
Dim xml As XmlReader = navigator.ReadSubtree()  
  
While xml.Read()  
    Console.WriteLine(xml.ReadInnerXml())  
End While  
  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlReader = navigator.ReadSubtree()  
  
While book.Read()  
    Console.WriteLine(book.ReadInnerXml())  
End While  
  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlReader.  
XmlReader xml = navigator.ReadSubtree();  
  
while (xml.Read())  
{  
    Console.WriteLine(xml.ReadInnerXml());  
}  
  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlReader book = navigator.ReadSubtree();  
  
while (book.Read())  
{  
    Console.WriteLine(book.ReadInnerXml());  
}  
  
book.Close();  
```  
  
 <span data-ttu-id="67f0c-119">In diesem Beispiel wird die Datei `books.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="67f0c-119">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
## <a name="converting-an-xpathnavigator-to-an-xmlwriter"></a><span data-ttu-id="67f0c-120">Konvertieren von XPathNavigator in XmlWriter</span><span class="sxs-lookup"><span data-stu-id="67f0c-120">Converting an XPathNavigator to an XmlWriter</span></span>  
 <span data-ttu-id="67f0c-121">Mit der <xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A>-Methode wird gesamte Inhalt eines XML-Dokuments oder nur ein einzelner Knoten und seine untergeordneten Knoten als Stream in ein <xref:System.Xml.XmlWriter>-Objekt übertragen.</span><span class="sxs-lookup"><span data-stu-id="67f0c-121">The <xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A> method is used to stream the entire contents of an XML document or just a single node and its child nodes to an <xref:System.Xml.XmlWriter> object.</span></span>  
  
 <span data-ttu-id="67f0c-122">Die Position des <xref:System.Xml.XPath.XPathNavigator>-Objekts wird durch das Erstellen des <xref:System.Xml.XmlWriter>-Objekts nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="67f0c-122">The <xref:System.Xml.XPath.XPathNavigator> object's position is unchanged by the creation of the <xref:System.Xml.XmlWriter> object.</span></span>  
  
 <span data-ttu-id="67f0c-123">Im folgenden Beispiel wird ein <xref:System.Xml.XmlWriter>-Objekt erstellt, das das ganze XML-Dokument sowohl in einem <xref:System.Xml.XPath.XPathDocument>-Objekt als auch als einzelnen Knoten mit untergeordneten Knoten enthält.</span><span class="sxs-lookup"><span data-stu-id="67f0c-123">The following example shows how to get an <xref:System.Xml.XmlWriter> object containing the entire XML document in an <xref:System.Xml.XPath.XPathDocument> object as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlWriter.  
Dim xml As XmlWriter = XmlWriter.Create("newbooks.xml")  
navigator.WriteSubtree(xml)  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlWriter = XmlWriter.Create("book.xml")  
navigator.WriteSubtree(book)  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlWriter.  
XmlWriter xml = XmlWriter.Create("newbooks.xml");  
navigator.WriteSubtree(xml);  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlWriter book = XmlWriter.Create("book.xml");  
navigator.WriteSubtree(book);  
book.Close();  
```  
  
 <span data-ttu-id="67f0c-124">In dem Beispiel wird die bereits erwähnte Datei `books.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="67f0c-124">The example takes the `books.xml` file found earlier in this topic as input.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67f0c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67f0c-125">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="67f0c-126">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="67f0c-126">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="67f0c-127">Navigieren in Knotengruppen mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="67f0c-127">Node Set Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="67f0c-128">Das Navigieren durch Attribut- und Namespaceknoten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="67f0c-128">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="67f0c-129">Zugreifen auf streng typisierte XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="67f0c-129">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
