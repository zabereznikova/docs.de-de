---
title: Kompilierte XPath-Ausdrücke
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e25dd95f-b64c-4d8b-a3a4-379e1aa0ad55
ms.openlocfilehash: 310d5eb01fff02d82ec3762d55ff14e5a6bcd621
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831012"
---
# <a name="compiled-xpath-expressions"></a><span data-ttu-id="7c086-102">Kompilierte XPath-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7c086-102">Compiled XPath Expressions</span></span>
<span data-ttu-id="7c086-103">Ein <xref:System.Xml.XPath.XPathExpression>-Objekt stellt eine kompilierte XPath-Abfrage dar, die entweder von der statischen <xref:System.Xml.XPath.XPathExpression.Compile%2A>-Methode der <xref:System.Xml.XPath.XPathExpression>-Klasse oder der <xref:System.Xml.XPath.XPathNavigator.Compile%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="7c086-103">An <xref:System.Xml.XPath.XPathExpression> object represents a compiled XPath query returned from either the static <xref:System.Xml.XPath.XPathExpression.Compile%2A> method of the <xref:System.Xml.XPath.XPathExpression> class or the <xref:System.Xml.XPath.XPathNavigator.Compile%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="the-xpathexpression-class"></a><span data-ttu-id="7c086-104">Die XPathExpression-Klasse</span><span class="sxs-lookup"><span data-stu-id="7c086-104">The XPathExpression Class</span></span>  
 <span data-ttu-id="7c086-105">Eine durch ein <xref:System.Xml.XPath.XPathExpression>-Objekt dargestellte kompilierte XPath-Abfrage ist nützlich, wenn dieselbe XPath-Abfrage mehrmals verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7c086-105">A compiled XPath query represented by an <xref:System.Xml.XPath.XPathExpression> object is useful if the same XPath query is being used more than once.</span></span>  
  
 <span data-ttu-id="7c086-106">Wenn z. B. die <xref:System.Xml.XPath.XPathNavigator.Select%2A>-Methode mehrmals ausgerufen wird, verwenden Sie die <xref:System.Xml.XPath.XPathExpression.Compile%2A>-Methode der <xref:System.Xml.XPath.XPathExpression>-Klasse oder die <xref:System.Xml.XPath.XPathNavigator.Compile%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse, um die XPath-Abfrage zu kompilieren und in einem <xref:System.Xml.XPath.XPathExpression>-Objekt zur Wiederverwendung und Leistungssteigerung zwischenzuspeichern, anstatt jedes Mal eine Zeichenfolge zu verwenden, die die XPath-Abfrage darstellt.</span><span class="sxs-lookup"><span data-stu-id="7c086-106">For example, when calling the <xref:System.Xml.XPath.XPathNavigator.Select%2A> method multiple times, instead of using a string representing the XPath query each time, use the <xref:System.Xml.XPath.XPathExpression.Compile%2A> method of the <xref:System.Xml.XPath.XPathExpression> class or the <xref:System.Xml.XPath.XPathNavigator.Compile%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class to compile and cache the XPath query in an <xref:System.Xml.XPath.XPathExpression> object for reuse and improved performance.</span></span>  
  
 <span data-ttu-id="7c086-107">Nach der Kompilierung kann das <xref:System.Xml.XPath.XPathExpression>-Objekt je nach dem Typ, der von der XPath-Abfrage zurückgegeben wird, als Eingabe für die folgenden Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="7c086-107">Once compiled, the <xref:System.Xml.XPath.XPathExpression> object may be used as input to the following <xref:System.Xml.XPath.XPathNavigator> class methods depending on the type returned from the XPath query.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.XPath.XPathNavigator.Matches%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 <span data-ttu-id="7c086-108">In der folgenden Tabelle werden alle XPath-Rückgabetypen des W3C sowie ihre Entsprechungen in Microsoft .NET Framework beschrieben. Außerdem wird erläutert, welche Methoden das <xref:System.Xml.XPath.XPathExpression>-Objekt auf der Basis des Rückgabetyps verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c086-108">The following table describes each of the W3C XPath return types, their Microsoft .NET Framework equivalencies, and what methods the <xref:System.Xml.XPath.XPathExpression> object may be used with based on its return type.</span></span>  
  
|<span data-ttu-id="7c086-109">XPath-Rückgabetyp des W3C</span><span class="sxs-lookup"><span data-stu-id="7c086-109">W3C XPath Return Type</span></span>|<span data-ttu-id="7c086-110">Entsprechender .NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="7c086-110">.NET Framework Equivalent Type</span></span>|<span data-ttu-id="7c086-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c086-111">Description</span></span>|<span data-ttu-id="7c086-112">Methoden</span><span class="sxs-lookup"><span data-stu-id="7c086-112">Methods</span></span>|  
|---------------------------|------------------------------------|-----------------|-------------|  
|`Node set`|<xref:System.Xml.XPath.XPathNodeIterator>|<span data-ttu-id="7c086-113">Eine ungeordnete Auflistung von Knoten ohne Duplikate, die in der Reihenfolge der Dokumente erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7c086-113">An unordered collection of nodes without duplicates created in document order.</span></span>|<span data-ttu-id="7c086-114"><xref:System.Xml.XPath.XPathNavigator.Select%2A> oder <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A></span><span class="sxs-lookup"><span data-stu-id="7c086-114"><xref:System.Xml.XPath.XPathNavigator.Select%2A> or <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A></span></span>|  
|`Boolean`|<xref:System.Boolean>|<span data-ttu-id="7c086-115">Ein `true`-Wert oder ein `false`-Wert.</span><span class="sxs-lookup"><span data-stu-id="7c086-115">A `true` or `false` value.</span></span>|<span data-ttu-id="7c086-116"><xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> oder</span><span class="sxs-lookup"><span data-stu-id="7c086-116"><xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> or</span></span><br /><br /> <xref:System.Xml.XPath.XPathNavigator.Matches%2A>|  
|`Number`|<xref:System.Double>|<span data-ttu-id="7c086-117">Eine Gleitkommazahl.</span><span class="sxs-lookup"><span data-stu-id="7c086-117">A floating-point number.</span></span>|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
|`String`|<xref:System.String>|<span data-ttu-id="7c086-118">Eine Folge von UCS-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="7c086-118">A sequence of UCS characters.</span></span>|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
  
> [!NOTE]
> <span data-ttu-id="7c086-119">Die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode akzeptiert einen XPath-Ausdruck als Parameter.</span><span class="sxs-lookup"><span data-stu-id="7c086-119">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method accepts an XPath expression as its parameter.</span></span> <span data-ttu-id="7c086-120">Die <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>-Methode gibt ein <xref:System.Xml.XPath.XPathNavigator>-Objekt zurück, nicht einen der XPath-Rückgabetypen des W3C.</span><span class="sxs-lookup"><span data-stu-id="7c086-120">The <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> method returns an <xref:System.Xml.XPath.XPathNavigator> object, not one of the W3C XPath return types.</span></span>  
  
### <a name="the-returntype-property"></a><span data-ttu-id="7c086-121">Die ReturnType-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7c086-121">The ReturnType Property</span></span>  
 <span data-ttu-id="7c086-122">Nachdem eine XPath-Abfrage in ein <xref:System.Xml.XPath.XPathExpression>-Objekt kompiliert wurde, können Sie mithilfe der <xref:System.Xml.XPath.XPathExpression.ReturnType%2A>-Eigenschaft des <xref:System.Xml.XPath.XPathExpression>-Objekts bestimmen, was die XPath-Abfrage zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7c086-122">After an XPath query has been compiled into an <xref:System.Xml.XPath.XPathExpression> object, you can use the <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> property of the <xref:System.Xml.XPath.XPathExpression> object to determine what the XPath query returns.</span></span>  
  
 <span data-ttu-id="7c086-123">Die <xref:System.Xml.XPath.XPathExpression.ReturnType%2A>-Eigenschaft gibt einen der folgenden <xref:System.Xml.XPath.XPathResultType>-Enumerationswerte zurück, die die XPath-Rückgabetypen des W3C darstellen:</span><span class="sxs-lookup"><span data-stu-id="7c086-123">The <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> property returns one of the following <xref:System.Xml.XPath.XPathResultType> enumeration values representing the W3C XPath return types.</span></span>  
  
- <xref:System.Xml.XPath.XPathResultType.Any>  
  
- <xref:System.Xml.XPath.XPathResultType.Boolean>  
  
- <xref:System.Xml.XPath.XPathResultType.Error>  
  
- <xref:System.Xml.XPath.XPathResultType.Navigator>  
  
- <xref:System.Xml.XPath.XPathResultType.NodeSet>  
  
- <xref:System.Xml.XPath.XPathResultType.Number>  
  
- <xref:System.Xml.XPath.XPathResultType.String>  
  
 <span data-ttu-id="7c086-124">Im folgenden Beispiel werden mithilfe des <xref:System.Xml.XPath.XPathExpression>-Objekts eine Zahl und eine Knotengruppe aus der Datei `books.xml` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7c086-124">The following example uses the <xref:System.Xml.XPath.XPathExpression> object to return a number and a node set from the `books.xml` file.</span></span> <span data-ttu-id="7c086-125">Die <xref:System.Xml.XPath.XPathExpression.ReturnType%2A>-Eigenschaft aller <xref:System.Xml.XPath.XPathExpression>-Objekte sowie die Ergebnisse der <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode und der <xref:System.Xml.XPath.XPathNavigator.Select%2A>-Methode werden in die Konsole geschrieben.</span><span class="sxs-lookup"><span data-stu-id="7c086-125">The <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> property of each <xref:System.Xml.XPath.XPathExpression> object as well as the results from the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> and <xref:System.Xml.XPath.XPathNavigator.Select%2A> methods are written to the console.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Returns a number.  
Dim query1 As XPathExpression = navigator.Compile("bookstore/book/price/text()*10")  
Console.WriteLine(query1.ReturnType)  
  
Dim number As Double = CType(navigator.Evaluate(query1), Double)  
Console.WriteLine(number)  
  
' Returns a node set.  
Dim query2 As XPathExpression = navigator.Compile("bookstore/book/price")  
Console.WriteLine(query2.ReturnType)  
  
Dim nodes As XPathNodeIterator = navigator.Select(query2)  
nodes.MoveNext()  
Console.WriteLine(nodes.Current.Value)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Returns a number.  
XPathExpression query1 = navigator.Compile("bookstore/book/price/text()*10");  
Console.WriteLine(query1.ReturnType);  
  
Double number = (Double)navigator.Evaluate(query1);  
Console.WriteLine(number);  
  
// Returns a node set.  
XPathExpression query2 = navigator.Compile("bookstore/book/price");  
Console.WriteLine(query2.ReturnType);  
  
XPathNodeIterator nodes = navigator.Select(query2);  
nodes.MoveNext();  
Console.WriteLine(nodes.Current.Value);  
```  
  
 <span data-ttu-id="7c086-126">In diesem Beispiel wird die Datei `books.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c086-126">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="higher-performance-xpath-expressions"></a><span data-ttu-id="7c086-127">Leistungsfähigere XPath-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7c086-127">Higher Performance XPath Expressions</span></span>  
 <span data-ttu-id="7c086-128">Wenn Sie eine bessere Leistung erreichen möchten, verwenden Sie in Ihren Abfragen einen möglichst spezifischen XPath-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="7c086-128">For better performance, use the most specific XPath expression possible in your queries.</span></span> <span data-ttu-id="7c086-129">Wenn z. B. der `book`-Knoten ein untergeordneter Knoten des `bookstore`-Knotens ist, und der `bookstore`-Knoten ist das oberste Element in einem XML-Dokument, ist die Verwendung des XPath-Ausdrucks `/bookstore/book` schneller als die Verwendung von `//book`.</span><span class="sxs-lookup"><span data-stu-id="7c086-129">For example, if the `book` node is a child node of the `bookstore` node and the `bookstore` node is the top-most element in an XML document, using the XPath expression `/bookstore/book` is faster than using `//book`.</span></span> <span data-ttu-id="7c086-130">Der XPath-Ausdruck `//book` durchsucht alle Knoten in der XML-Struktur nach übereinstimmenden Knoten.</span><span class="sxs-lookup"><span data-stu-id="7c086-130">The `//book` XPath expression will scan every node in the XML tree to identify matching nodes.</span></span>  
  
 <span data-ttu-id="7c086-131">Darüber hinaus kann die Verwendung der von der <xref:System.Xml.XPath.XPathNavigator>-Klasse bereitgestellten Methoden zur Knotensatznavigation zur Leistungssteigerung der Auswahlmethoden führen, die von der <xref:System.Xml.XPath.XPathNavigator>-Klasse für Fälle mit einfachen Auswahlkriterien bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7c086-131">Additionally, using the node set navigation methods supplied by the <xref:System.Xml.XPath.XPathNavigator> class may result in improved performance over the selection methods supplied by the <xref:System.Xml.XPath.XPathNavigator> class in cases where your selection criteria are simple.</span></span> <span data-ttu-id="7c086-132">Wenn Sie z. B. den ersten untergeordneten Knoten des aktuellen Knotens auswählen müssen, ist es schneller, die <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>-Methode zu verwenden, als den XPath-Ausdruck `child::*[1]` und die <xref:System.Xml.XPath.XPathNavigator.Select%2A>-Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c086-132">For example, if you need to select the first child of the current node, it is faster to use the <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A> method than to use the `child::*[1]` XPath expression and the <xref:System.Xml.XPath.XPathNavigator.Select%2A> method.</span></span>  
  
 <span data-ttu-id="7c086-133">Weitere Informationen zu den Methoden der Knotensatznavigation der <xref:System.Xml.XPath.XPathNavigator>-Klasse finden Sie unter [Navigieren in Knotengruppen mit XPathNavigator](node-set-navigation-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="7c086-133">For more information about the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class, see [Node Set Navigation Using XPathNavigator](node-set-navigation-using-xpathnavigator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c086-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c086-134">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="7c086-135">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="7c086-135">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="7c086-136">Auswählen von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7c086-136">Select XML Data Using XPathNavigator</span></span>](select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="7c086-137">Auswerten von XPath-Ausdrücken mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7c086-137">Evaluate XPath Expressions using XPathNavigator</span></span>](evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="7c086-138">Vergleich von Knoten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7c086-138">Matching Nodes using XPathNavigator</span></span>](matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="7c086-139">In XPath-Abfragen erkannte Knotentypen</span><span class="sxs-lookup"><span data-stu-id="7c086-139">Node Types Recognized with XPath Queries</span></span>](node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="7c086-140">XPath-Abfragen und Namespaces</span><span class="sxs-lookup"><span data-stu-id="7c086-140">XPath Queries and Namespaces</span></span>](xpath-queries-and-namespaces.md)
