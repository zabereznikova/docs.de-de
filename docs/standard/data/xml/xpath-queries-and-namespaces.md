---
title: XPath-Abfragen und Namespaces
description: Erfahren Sie mehr über XPath-Abfragen und Namespaces. XPath-Abfragen kennen die Namespaces in einem XML-Dokument und können Namespacepräfixe zum Kennzeichnen von Element- und Attributnamen verwenden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ef6402be-2f8e-4be2-8d3e-a80891cdef8b
ms.openlocfilehash: a97ff5afef23c361b1f675d2f07f43b3bc5df299
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818387"
---
# <a name="xpath-queries-and-namespaces"></a><span data-ttu-id="bc9c5-104">XPath-Abfragen und Namespaces</span><span class="sxs-lookup"><span data-stu-id="bc9c5-104">XPath Queries and Namespaces</span></span>
<span data-ttu-id="bc9c5-105">XPath-Abfragen unterstützen Namespaces in einem XML-Dokument und können Namespacepräfixe zum Kennzeichnen von Element- und Attributnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-105">XPath queries are aware of namespaces in an XML document and can use namespace prefixes to qualify element and attribute names.</span></span> <span data-ttu-id="bc9c5-106">Durch das Kennzeichnen von Element- und Attributnamen mit einem Namespacepräfix wird die Anzahl der von einer XPath-Abfrage zurückgegebenen Knoten auf die Knoten beschränkt, die zu einem bestimmten Namespace gehören.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-106">Qualifying element and attribute names with a namespace prefix limits the nodes returned by an XPath query to only those nodes that belong to a specific namespace.</span></span>  
  
 <span data-ttu-id="bc9c5-107">Wenn z. B. das Präfix `books` dem Namespace `http://www.contoso.com/books` zugeordnet ist, wählt die folgende XPath-Abfrage `/books:books/books:book` nur die `book`-Elemente im Namespace `http://www.contoso.com/books` aus.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-107">For example if the prefix `books` maps to the namespace `http://www.contoso.com/books`, then the following XPath query `/books:books/books:book` selects only those `book` elements in the namespace `http://www.contoso.com/books`.</span></span>  
  
## <a name="the-xmlnamespacemanager"></a><span data-ttu-id="bc9c5-108">Der XmlNamespaceManager</span><span class="sxs-lookup"><span data-stu-id="bc9c5-108">The XmlNamespaceManager</span></span>  
 <span data-ttu-id="bc9c5-109">Um Namespaces in einer XPath-Abfrage zu verwenden, wird ein von der <xref:System.Xml.IXmlNamespaceResolver>-Schnittstelle abgeleitetes Objekt wie die <xref:System.Xml.XmlNamespaceManager>-Klasse mit dem Namespace-URI und -präfix erstellt, die in die XPath-Abfrage eingefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-109">To use namespaces in an XPath query, an object derived from the <xref:System.Xml.IXmlNamespaceResolver> interface like the <xref:System.Xml.XmlNamespaceManager> class is constructed with the namespace URI and prefix to include in the XPath query.</span></span>  
  
 <span data-ttu-id="bc9c5-110">Das <xref:System.Xml.XmlNamespaceManager>-Objekt kann in der Abfrage auf eine der folgenden Arten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="bc9c5-110">The <xref:System.Xml.XmlNamespaceManager> object may be used in the query in each of the following ways.</span></span>  
  
- <span data-ttu-id="bc9c5-111">Das <xref:System.Xml.XmlNamespaceManager>-Objekt wird mithilfe der <xref:System.Xml.XPath.XPathExpression>-Methode des <xref:System.Xml.XPath.XPathExpression.SetContext%2A>-Objekts einem vorhandenen <xref:System.Xml.XPath.XPathExpression>-Objekt zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-111">The <xref:System.Xml.XmlNamespaceManager> object is associated with an existing <xref:System.Xml.XPath.XPathExpression> object by using the <xref:System.Xml.XPath.XPathExpression.SetContext%2A> method of the <xref:System.Xml.XPath.XPathExpression> object.</span></span> <span data-ttu-id="bc9c5-112">Sie können auch mithilfe der statischen <xref:System.Xml.XPath.XPathExpression>-Methode ein neues <xref:System.Xml.XPath.XPathExpression.Compile%2A>-Objekt kompilieren, das eine den XPath-Ausdruck darstellende Zeichenfolge und ein <xref:System.Xml.XmlNamespaceManager>-Objekt als Parameter akzeptiert und ein neues <xref:System.Xml.XPath.XPathExpression>-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-112">You may also compile a new <xref:System.Xml.XPath.XPathExpression> object using the static <xref:System.Xml.XPath.XPathExpression.Compile%2A> method which takes a string representing the XPath expression and an <xref:System.Xml.XmlNamespaceManager> object as parameters and returns a new <xref:System.Xml.XPath.XPathExpression> object.</span></span>  
  
- <span data-ttu-id="bc9c5-113">Das <xref:System.Xml.XmlNamespaceManager>-Objekt selbst wird zusammen mit einer den XPath-Ausdruck darstellenden Zeichenfolge als Parameter an eine akzeptierende Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-113">The <xref:System.Xml.XmlNamespaceManager> object itself is passed as a parameter to an accepting <xref:System.Xml.XPath.XPathNavigator> class method along with a string representing the XPath expression.</span></span>  
  
 <span data-ttu-id="bc9c5-114">Im Folgenden finden Sie eine Auflistung der Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse, die ein von der <xref:System.Xml.IXmlNamespaceResolver>-Schnittstelle abgeleitetes Objekt als Parameter akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-114">The following are the methods of the <xref:System.Xml.XPath.XPathNavigator> class that accept an object derived from the <xref:System.Xml.IXmlNamespaceResolver> interface as a parameter.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
### <a name="the-default-namespace"></a><span data-ttu-id="bc9c5-115">Der Standardnamespace</span><span class="sxs-lookup"><span data-stu-id="bc9c5-115">The Default Namespace</span></span>  
 <span data-ttu-id="bc9c5-116">Im folgenden XML-Dokument wird der Standardnamespace mit einem leeren Präfix für die Deklaration des `http://www.contoso.com/books`-Namespaces verwendet.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-116">In the XML document that follows, the default namespace with an empty prefix is used to declare the `http://www.contoso.com/books` namespace.</span></span>  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <author>Author Name</author>  
        <price>5.50</price>  
    </book>  
</books>  
```  
  
 <span data-ttu-id="bc9c5-117">XPath behandelt das leere Präfix als `null`-Namespace.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-117">XPath treats the empty prefix as the `null` namespace.</span></span> <span data-ttu-id="bc9c5-118">Mit anderen Worten: In XPath-Abfragen können nur Präfixe verwendet werden, die Namespaces zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-118">In other words, only prefixes mapped to namespaces can be used in XPath queries.</span></span> <span data-ttu-id="bc9c5-119">Das bedeutet, dass Sie ein Präfix definieren müssen, wenn Sie einen Namespace in einem XML-Dokument abfragen möchten, auch wenn es sich um den Standardnamespace handelt.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-119">This means that if you want to query against a namespace in an XML document, even if it is the default namespace, you need to define a prefix for it.</span></span>  
  
 <span data-ttu-id="bc9c5-120">Ohne die Definition eines Präfixes für das obige XML-Dokument gibt z. B. die XPath-Abfrage `/books/book` kein Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-120">For example, without defining a prefix for the XML document above, the XPath query `/books/book` would not return any results.</span></span>  
  
 <span data-ttu-id="bc9c5-121">Ein Präfix muss gebunden sein, um Mehrdeutigkeit beim Abfragen von Dokumenten zu vermeiden, die einige Knoten außerhalb der Namespaces sowie einige Knoten in einem Standardnamespace enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-121">A prefix must be bound to prevent ambiguity when querying documents with some nodes not in a namespace, and some in a default namespace.</span></span>  
  
 <span data-ttu-id="bc9c5-122">Im folgenden Code wird ein Präfix für den Standardnamespace definiert, und alle `book`-Elemente aus dem `http://www.contoso.com/books`-Namespace werden ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="bc9c5-122">The following code defines a prefix for the default namespace and selects all the `book` elements from the `http://www.contoso.com/books` namespace.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim query As XPathExpression = navigator.Compile("/books:books/books:book")  
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(navigator.NameTable)  
manager.AddNamespace("books", "http://www.contoso.com/books")  
query.SetContext(manager)  
Dim nodes As XPathNodeIterator = navigator.Select(query)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathExpression query = navigator.Compile("/books:books/books:book");  
XmlNamespaceManager manager = new XmlNamespaceManager(navigator.NameTable);  
manager.AddNamespace("books", "http://www.contoso.com/books");  
query.SetContext(manager);  
XPathNodeIterator nodes = navigator.Select(query);  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc9c5-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc9c5-123">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="bc9c5-124">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="bc9c5-124">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="bc9c5-125">Auswählen von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="bc9c5-125">Select XML Data Using XPathNavigator</span></span>](select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="bc9c5-126">Auswerten von XPath-Ausdrücken mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="bc9c5-126">Evaluate XPath Expressions using XPathNavigator</span></span>](evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="bc9c5-127">Vergleich von Knoten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="bc9c5-127">Matching Nodes using XPathNavigator</span></span>](matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="bc9c5-128">In XPath-Abfragen erkannte Knotentypen</span><span class="sxs-lookup"><span data-stu-id="bc9c5-128">Node Types Recognized with XPath Queries</span></span>](node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="bc9c5-129">Kompilierte XPath-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="bc9c5-129">Compiled XPath Expressions</span></span>](compiled-xpath-expressions.md)
