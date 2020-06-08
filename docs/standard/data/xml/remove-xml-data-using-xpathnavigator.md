---
title: Entfernen von XML-Daten mit "XPathNavigator"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 9f436bca-1b96-494b-a6d2-e102c7551752
ms.openlocfilehash: fa331757fac3f30ee86a24bbd0ee12b5f1031a4b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288666"
---
# <a name="remove-xml-data-using-xpathnavigator"></a><span data-ttu-id="1abac-102">Entfernen von XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="1abac-102">Remove XML Data using XPathNavigator</span></span>
<span data-ttu-id="1abac-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt eine Gruppe von Methoden bereit, mit denen Knoten und Werte aus einem XML-Dokument entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="1abac-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to remove nodes and values from an XML document.</span></span> <span data-ttu-id="1abac-104">Diese Methoden können nur dann verwendet werden, wenn das <xref:System.Xml.XPath.XPathNavigator>-Objekt bearbeitet werden kann, d. h. seine <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Eigenschaft muss `true` sein.</span><span class="sxs-lookup"><span data-stu-id="1abac-104">In order to use these methods, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be `true`.</span></span>  
  
 <span data-ttu-id="1abac-105"><xref:System.Xml.XPath.XPathNavigator>-Objekte, die ein XML-Dokument bearbeiten können, werden von der <xref:System.Xml.XmlDocument.CreateNavigator%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="1abac-105"><xref:System.Xml.XPath.XPathNavigator> objects that can edit an XML document are created by the <xref:System.Xml.XmlDocument.CreateNavigator%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="1abac-106"><xref:System.Xml.XPath.XPathNavigator>-Objekte, die von der <xref:System.Xml.XPath.XPathDocument>-Klasse erstellt werden, sind schreibgeschützt. Der Versuch, die Bearbeitungsmethoden eines <xref:System.Xml.XPath.XPathNavigator>-Objekts anzuwenden, das von einem <xref:System.Xml.XPath.XPathDocument>-Objekt erstellt wurde, führt zu einer <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="1abac-106"><xref:System.Xml.XPath.XPathNavigator> objects created by the <xref:System.Xml.XPath.XPathDocument> class are read-only and any attempt to use the editing methods of an <xref:System.Xml.XPath.XPathNavigator> object created by an <xref:System.Xml.XPath.XPathDocument> object results in a <xref:System.NotSupportedException>.</span></span>  
  
 <span data-ttu-id="1abac-107">Weitere Informationen zum Erstellen bearbeitbarer <xref:System.Xml.XPath.XPathNavigator>-Objekte finden Sie unter [Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).</span><span class="sxs-lookup"><span data-stu-id="1abac-107">For more information about creating editable <xref:System.Xml.XPath.XPathNavigator> objects, see [Reading XML Data using XPathDocument and XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).</span></span>  
  
## <a name="removing-nodes"></a><span data-ttu-id="1abac-108">Entfernen von Knoten</span><span class="sxs-lookup"><span data-stu-id="1abac-108">Removing Nodes</span></span>  
 <span data-ttu-id="1abac-109">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>-Methode zum Entfernen von Knoten aus einem XML-Dokument bereit.</span><span class="sxs-lookup"><span data-stu-id="1abac-109">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method to remove nodes from an XML document.</span></span>  
  
### <a name="removing-a-node"></a><span data-ttu-id="1abac-110">Entfernen eines Knotens</span><span class="sxs-lookup"><span data-stu-id="1abac-110">Removing a Node</span></span>  
 <span data-ttu-id="1abac-111">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>-Methode bereit, mit der der aktuelle Knoten aus einem XML-Dokument gelöscht werden kann, auf dem sich gerade ein <xref:System.Xml.XPath.XPathNavigator>-Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="1abac-111">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method to delete the current node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on from an XML document.</span></span>  
  
 <span data-ttu-id="1abac-112">Nachdem ein Knoten mithilfe der <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>-Methode gelöscht wurde, kann vom Stamm eines <xref:System.Xml.XmlDocument>-Objekts aus nicht mehr darauf zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="1abac-112">After a node has been deleted using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method, it is no longer reachable from the root of the <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="1abac-113">Nachdem der Knoten gelöscht wurde, wird der <xref:System.Xml.XPath.XPathNavigator> auf dem übergeordneten Knoten des gelöschten Knotens positioniert.</span><span class="sxs-lookup"><span data-stu-id="1abac-113">After a node has been deleted, the <xref:System.Xml.XPath.XPathNavigator> is positioned on the parent node of the deleted node.</span></span>  
  
 <span data-ttu-id="1abac-114">Der Löschvorgang hat keine Auswirkungen auf die Position der <xref:System.Xml.XPath.XPathNavigator>-Objekte, die sich auf dem gelöschten Knoten befinden.</span><span class="sxs-lookup"><span data-stu-id="1abac-114">A delete operation doesn't affect the position of any <xref:System.Xml.XPath.XPathNavigator> object positioned on the deleted node.</span></span> <span data-ttu-id="1abac-115">Diese <xref:System.Xml.XPath.XPathNavigator>-Objekte sind insofern gültig, als sie innerhalb der gelöschten Unterstruktur verschoben werden können. Sie können jedoch nicht mit einer der regulären Knotensatz-Navigationsmethoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse in die Hauptknotenstruktur verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="1abac-115">These <xref:System.Xml.XPath.XPathNavigator> objects are valid in the sense that they can move within the deleted subtree, but cannot be moved to the main node tree using the regular node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1abac-116">Mithilfe der <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse können diese <xref:System.Xml.XPath.XPathNavigator>-Objekte zurück in die entsprechende Hauptknotenstruktur verschoben werden bzw. aus dieser in die gelöschte Unterstruktur verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="1abac-116">The <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class can be used to move these <xref:System.Xml.XPath.XPathNavigator> objects back into the main node tree, or from the main node tree to the deleted subtree.</span></span>  
  
 <span data-ttu-id="1abac-117">Im folgenden Beispiel wird das `price`-Element des ersten `book`-Elements der Datei `contosoBooks.xml` mithilfe der <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>-Methode gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1abac-117">In the following example, the `price` element of the first `book` element of the `contosoBooks.xml` file is deleted using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method.</span></span> <span data-ttu-id="1abac-118">Die Position des <xref:System.Xml.XPath.XPathNavigator>-Objekts, nachdem das `price`-Element im übergeordneten `book`-Element gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="1abac-118">The position of the <xref:System.Xml.XPath.XPathNavigator> object after the `price` element is deleted is on the parent `book` element.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.DeleteSelf()  
  
Console.WriteLine("Position after delete: {0}", navigator.Name)  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.DeleteSelf();  
  
Console.WriteLine("Position after delete: {0}", navigator.Name);  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="1abac-119">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="1abac-119">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-an-attribute-node"></a><span data-ttu-id="1abac-120">Entfernen eines Attributknotens</span><span class="sxs-lookup"><span data-stu-id="1abac-120">Removing an Attribute Node</span></span>  
 <span data-ttu-id="1abac-121">Attributknoten können mithilfe der <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>-Methode aus einem XML-Dokument entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="1abac-121">Attribute nodes are removed from an XML document using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method.</span></span>  
  
 <span data-ttu-id="1abac-122">Nachdem ein Attributknoten gelöscht wurde, kann nicht mehr von einem Stammknoten eines <xref:System.Xml.XmlDocument>-Objekts aus darauf zugegriffen werden, und das <xref:System.Xml.XPath.XPathNavigator>-Objekt wird auf dem übergeordneten Element positioniert.</span><span class="sxs-lookup"><span data-stu-id="1abac-122">After an attribute node has been deleted, it is no longer reachable from the root node of an <xref:System.Xml.XmlDocument> object and the <xref:System.Xml.XPath.XPathNavigator> object is positioned on the parent element.</span></span>  
  
#### <a name="default-attributes"></a><span data-ttu-id="1abac-123">Standardattribute</span><span class="sxs-lookup"><span data-stu-id="1abac-123">Default Attributes</span></span>  
 <span data-ttu-id="1abac-124">Unabhängig davon, mit welcher Methode Attribute entfernt wurden, bestehen spezielle Einschränkungen für das Entfernen von Standardattributen in der DTD oder im XML-Schema des XML-Dokuments.</span><span class="sxs-lookup"><span data-stu-id="1abac-124">Regardless of the method used to remove attributes, there are special limitations on removing attributes that are defined as default attributes in the DTD or XML Schema for the XML document.</span></span> <span data-ttu-id="1abac-125">Standardattribute können nicht entfernt werden, wenn nicht das zugehörige Element ebenfalls entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="1abac-125">Default attributes cannot be removed unless the element they belong to is also removed.</span></span> <span data-ttu-id="1abac-126">Standardattribute sind immer für Elemente vorhanden, für die Standardattribute deklariert wurden. Daher führt das Löschen eines Standardattributs dazu, dass ein Ersatzattribut in das Element eingefügt und der deklarierte Standardwert initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="1abac-126">Default attributes are always present for elements that have default attributes declared, and as a result, deleting a default attribute results in a replacement attribute being inserted into the element and initialized to the default value that was declared.</span></span>  
  
## <a name="removing-values"></a><span data-ttu-id="1abac-127">Entfernen von Werten</span><span class="sxs-lookup"><span data-stu-id="1abac-127">Removing Values</span></span>  
 <span data-ttu-id="1abac-128">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode zum Entfernen von nicht typisierten und typisierten Knoten aus einem XML-Dokument bereit.</span><span class="sxs-lookup"><span data-stu-id="1abac-128">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods to remove untyped and typed values from an XML document.</span></span>  
  
### <a name="removing-untyped-values"></a><span data-ttu-id="1abac-129">Entfernen nicht typisierter Werte</span><span class="sxs-lookup"><span data-stu-id="1abac-129">Removing Untyped Values</span></span>  
 <span data-ttu-id="1abac-130">Die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode fügt einfach den als Parameter übergebenen nicht typisierten `string`-Wert als Wert des Knotens ein, auf dem das <xref:System.Xml.XPath.XPathNavigator>-Objekt gerade positioniert ist.</span><span class="sxs-lookup"><span data-stu-id="1abac-130">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method simply inserts the untyped `string` value passed as a parameter as the value of the node the <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="1abac-131">Durch Übergeben einer leeren Zeichenfolge an die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode wird der Wert des aktuellen Knotens entfernt.</span><span class="sxs-lookup"><span data-stu-id="1abac-131">Passing an empty string to the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method removes the value of the current node.</span></span>  
  
 <span data-ttu-id="1abac-132">Im folgenden Beispiel wird der Wert des `price`-Elements des ersten `book`-Elements der Datei `contosoBooks.xml` mithilfe der <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode entfernt.</span><span class="sxs-lookup"><span data-stu-id="1abac-132">The following example removes the value of the `price` element of the first `book` element in the `contosoBooks.xml` file using the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetValue("")  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetValue("");  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="1abac-133">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="1abac-133">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-typed-values"></a><span data-ttu-id="1abac-134">Entfernen typisierter Werte</span><span class="sxs-lookup"><span data-stu-id="1abac-134">Removing Typed Values</span></span>  
 <span data-ttu-id="1abac-135">Wenn der Typ ein einfacher W3C-XML-Schematyp ist, wird der neue mit der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode eingefügte Wert anhand aller Facets des einfachen Typs überprüft, bevor er festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1abac-135">When the type of a node is a W3C XML Schema simple type, the new value inserted by the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method is checked against the facets of the simple type before the value is set.</span></span> <span data-ttu-id="1abac-136">Wenn der neue Wert bezüglich des Knotentyps nicht gültig ist (z. B. der Wert `-1` für ein Element vom Typ `xs:positiveInteger`), wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1abac-136">If the new value is not valid according to the type of the node (for example, setting a value of `-1` on an element whose type is `xs:positiveInteger`), it results in an exception.</span></span> <span data-ttu-id="1abac-137">Außerdem ist es nicht möglich, der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode `null` als Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="1abac-137">The <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method also cannot be passed `null` as a parameter.</span></span> <span data-ttu-id="1abac-138">Daher muss das Entfernen eines typisierten Werts in Übereinstimmung mit dem Schematyp des Knotens erfolgen.</span><span class="sxs-lookup"><span data-stu-id="1abac-138">As a result removing the value of a typed node must comply with the schema type of the node.</span></span>  
  
 <span data-ttu-id="1abac-139">Im folgenden Beispiel wird der Wert des `price`-Elements des ersten `book`-Elements der Datei `contosoBooks.xml` mithilfe der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode entfernt, indem der Wert auf `0` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1abac-139">The following example removes the value of the `price` element of the first `book` element in the `contosoBooks.xml` file using the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method by setting the value to `0`.</span></span> <span data-ttu-id="1abac-140">Der Wert des Knotens wird nicht entfernt, es wird jedoch der Buchpreis entsprechend seinem Datentyp `xs:decimal` entfernt.</span><span class="sxs-lookup"><span data-stu-id="1abac-140">The value of the node is not removed, but the price of the book has been removed according to its data type of `xs:decimal`.</span></span>  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetTypedValue(0)  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetTypedValue(0);  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
## <a name="namespace-nodes"></a><span data-ttu-id="1abac-141">Namespaceknoten</span><span class="sxs-lookup"><span data-stu-id="1abac-141">Namespace Nodes</span></span>  
 <span data-ttu-id="1abac-142">Namespaceknoten können nicht aus einem <xref:System.Xml.XmlDocument>-Objekt gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="1abac-142">Namespace nodes cannot be deleted from an <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="1abac-143">Beim Versuch, Namespaceknoten mithilfe der <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>-Methode zu löschen, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1abac-143">Attempts to delete namespace nodes using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method results in an exception.</span></span>  
  
## <a name="the-innerxml-and-outerxml-properties"></a><span data-ttu-id="1abac-144">Die Eigenschaften "InnerXml" und "OuterXml"</span><span class="sxs-lookup"><span data-stu-id="1abac-144">The InnerXml and OuterXml Properties</span></span>  
 <span data-ttu-id="1abac-145">Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse ändern das XML-Markup der Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist.</span><span class="sxs-lookup"><span data-stu-id="1abac-145">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class change the XML markup of the nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="1abac-146">Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft ändert das XML-Markup der untergeordneten Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, mit den analysierten Inhalten des angegebenen XML-`string`.</span><span class="sxs-lookup"><span data-stu-id="1abac-146">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on with the parsed contents of the given XML `string`.</span></span> <span data-ttu-id="1abac-147">Ebenso ändert die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft das XML-Markup der untergeordneten Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, sowie den aktuellen Knoten selbst.</span><span class="sxs-lookup"><span data-stu-id="1abac-147">Similarly, the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on as well as the current node itself.</span></span>  
  
 <span data-ttu-id="1abac-148">Neben den in diesem Thema beschriebenen Methoden können die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft zum Entfernen von Knoten und Werten aus einem XML-Dokument verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1abac-148">In addition to the methods described in this topic, the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties can be used to remove nodes and values from an XML document.</span></span> <span data-ttu-id="1abac-149">Weitere Informationen zum Verwenden der Eigenschaften <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> und <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> zum Ändern von Knoten finden Sie im Thema [Ändern von XML-Daten mit XPathNavigator](modify-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="1abac-149">For more information about using the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties to modify nodes, see the [Modify XML Data using XPathNavigator](modify-xml-data-using-xpathnavigator.md) topic.</span></span>  
  
## <a name="saving-an-xml-document"></a><span data-ttu-id="1abac-150">Speichern eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="1abac-150">Saving an XML Document</span></span>  
 <span data-ttu-id="1abac-151">Änderungen eines <xref:System.Xml.XmlDocument>-Objekts, die von den in diesem Thema beschriebenen Methoden vorgenommen wurden, werden mit den Methoden der <xref:System.Xml.XmlDocument>-Klasse gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1abac-151">Saving changes made to an <xref:System.Xml.XmlDocument> object as the result of the methods described in this topic is performed using the methods of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="1abac-152">Weitere Informationen zum Speichern der an einem <xref:System.Xml.XmlDocument>-Objekt vorgenommenen Änderungen finden Sie unter [Speichern und Ausgeben eines Dokuments](saving-and-writing-a-document.md).</span><span class="sxs-lookup"><span data-stu-id="1abac-152">For more information about saving changes made to an <xref:System.Xml.XmlDocument> object, see [Saving and Writing a Document](saving-and-writing-a-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1abac-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1abac-153">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="1abac-154">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="1abac-154">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="1abac-155">Einfügen von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="1abac-155">Insert XML Data using XPathNavigator</span></span>](insert-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="1abac-156">Ändern von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="1abac-156">Modify XML Data using XPathNavigator</span></span>](modify-xml-data-using-xpathnavigator.md)
