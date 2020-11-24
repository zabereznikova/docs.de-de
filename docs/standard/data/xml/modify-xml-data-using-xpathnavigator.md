---
title: Ändern von XML-Daten mit "XPathNavigator"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 03a7c5a1-b296-4af4-b209-043c958dc0a5
ms.openlocfilehash: 79bb23b77557a5a10f021e2167c9fa8ae3ee044a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830193"
---
# <a name="modify-xml-data-using-xpathnavigator"></a><span data-ttu-id="e2976-102">Ändern von XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="e2976-102">Modify XML Data using XPathNavigator</span></span>
<span data-ttu-id="e2976-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt eine Gruppe von Methoden bereit, die zum Ändern von Knoten und Werten eines XML-Dokuments verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2976-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to modify nodes and values in an XML document.</span></span> <span data-ttu-id="e2976-104">Diese Methoden können nur dann verwendet werden, wenn das <xref:System.Xml.XPath.XPathNavigator>-Objekt bearbeitet werden kann, d. h. seine <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Eigenschaft muss `true` sein.</span><span class="sxs-lookup"><span data-stu-id="e2976-104">In order to use these methods, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be `true`.</span></span>  
  
 <span data-ttu-id="e2976-105"><xref:System.Xml.XPath.XPathNavigator>-Objekte, die ein XML-Dokument bearbeiten können, werden von der <xref:System.Xml.XmlDocument.CreateNavigator%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="e2976-105"><xref:System.Xml.XPath.XPathNavigator> objects that can edit an XML document are created by the <xref:System.Xml.XmlDocument.CreateNavigator%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="e2976-106"><xref:System.Xml.XPath.XPathNavigator>-Objekte, die von der <xref:System.Xml.XPath.XPathDocument>-Klasse erstellt werden, sind schreibgeschützt. Der Versuch, die Bearbeitungsmethoden eines <xref:System.Xml.XPath.XPathNavigator>-Objekts anzuwenden, das von einem <xref:System.Xml.XPath.XPathDocument>-Objekt erstellt wurde, führt zu einer <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="e2976-106"><xref:System.Xml.XPath.XPathNavigator> objects created by the <xref:System.Xml.XPath.XPathDocument> class are read-only and any attempt to use the editing methods of an <xref:System.Xml.XPath.XPathNavigator> object created by an <xref:System.Xml.XPath.XPathDocument> object result in a <xref:System.NotSupportedException>.</span></span>  
  
 <span data-ttu-id="e2976-107">Weitere Informationen zum Erstellen bearbeitbarer <xref:System.Xml.XPath.XPathNavigator>-Objekte finden Sie unter [Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).</span><span class="sxs-lookup"><span data-stu-id="e2976-107">For more information about creating editable <xref:System.Xml.XPath.XPathNavigator> objects, see [Reading XML Data using XPathDocument and XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).</span></span>  
  
## <a name="modifying-nodes"></a><span data-ttu-id="e2976-108">Ändern von Knoten</span><span class="sxs-lookup"><span data-stu-id="e2976-108">Modifying Nodes</span></span>  
 <span data-ttu-id="e2976-109">Ein einfaches Verfahren zum Ändern des Werts eines Knotens ist die Verwendung der <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode und der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="e2976-109">A simple technique for changing the value of a node is to use the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 <span data-ttu-id="e2976-110">In der folgenden Tabelle ist die Wirkung dieser Methoden für verschiedene Knotentypen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e2976-110">The following table lists the effects of these methods on different node types.</span></span>  
  
|<xref:System.Xml.XPath.XPathNodeType>|<span data-ttu-id="e2976-111">Geänderte Daten</span><span class="sxs-lookup"><span data-stu-id="e2976-111">Data Changed</span></span>|  
|---------------------------------------------------------------------------------------------------------------------------------------------|------------------|  
|<xref:System.Xml.XPath.XPathNodeType.Root>|<span data-ttu-id="e2976-112">Wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e2976-112">Not supported.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Element>|<span data-ttu-id="e2976-113">Der Inhalt des Elements.</span><span class="sxs-lookup"><span data-stu-id="e2976-113">The content of the element.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Attribute>|<span data-ttu-id="e2976-114">Der Wert des Attributs.</span><span class="sxs-lookup"><span data-stu-id="e2976-114">The value of the attribute.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Text>|<span data-ttu-id="e2976-115">Der Textinhalt.</span><span class="sxs-lookup"><span data-stu-id="e2976-115">The text content.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>|<span data-ttu-id="e2976-116">Der Inhalt mit Ausnahme des Ziels.</span><span class="sxs-lookup"><span data-stu-id="e2976-116">The content, excluding the target.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Comment>|<span data-ttu-id="e2976-117">Der Inhalt des Kommentars.</span><span class="sxs-lookup"><span data-stu-id="e2976-117">The content of the comment.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Namespace>|<span data-ttu-id="e2976-118">Nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e2976-118">Not Supported.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="e2976-119">Das Bearbeiten von <xref:System.Xml.XPath.XPathNodeType.Namespace>-Knoten oder des <xref:System.Xml.XPath.XPathNodeType.Root>-Knotens wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e2976-119">Editing <xref:System.Xml.XPath.XPathNodeType.Namespace> nodes or the <xref:System.Xml.XPath.XPathNodeType.Root> node is not supported.</span></span>  
  
 <span data-ttu-id="e2976-120">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt ebenfalls eine Gruppe von Methoden zum Einfügen und Entfernen von Knoten bereit.</span><span class="sxs-lookup"><span data-stu-id="e2976-120">The <xref:System.Xml.XPath.XPathNavigator> class also provides a set of methods used to insert and remove nodes.</span></span> <span data-ttu-id="e2976-121">Weitere Informationen zum Einfügen und Entfernen von Knoten aus einem XML-Dokument finden Sie in den Themen [Einfügen von XML-Daten mit XPathNavigator](insert-xml-data-using-xpathnavigator.md) und [Entfernen von XML-Daten mit XPathNavigator](remove-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="e2976-121">For more information about inserting and removing nodes from an XML document, see the [Insert XML Data using XPathNavigator](insert-xml-data-using-xpathnavigator.md) and [Remove XML Data using XPathNavigator](remove-xml-data-using-xpathnavigator.md) topics.</span></span>  
  
### <a name="modifying-untyped-values"></a><span data-ttu-id="e2976-122">Ändern von nicht typisierten Werten</span><span class="sxs-lookup"><span data-stu-id="e2976-122">Modifying Untyped Values</span></span>  
 <span data-ttu-id="e2976-123">Die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode fügt einfach den als Parameter übergebenen nicht typisierten `string`-Wert als Wert des Knotens ein, auf dem das <xref:System.Xml.XPath.XPathNavigator>-Objekt gerade positioniert ist.</span><span class="sxs-lookup"><span data-stu-id="e2976-123">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method simply inserts the untyped `string` value passed as a parameter as the value of the node the <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="e2976-124">Der Wert wird ohne Typ bzw. (falls Schemainformationen verfügbar sind) ohne Prüfung der Gültigkeit des neuen Werts bezüglich des Knotentyps eingefügt.</span><span class="sxs-lookup"><span data-stu-id="e2976-124">The value is inserted without any type or without verifying that the new value is valid according to the type of the node if schema information is available.</span></span>  
  
 <span data-ttu-id="e2976-125">Im folgenden Beispiel werden alle <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Elemente in der Datei `price` mit der `contosoBooks.xml`-Methode aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e2976-125">In the following example, the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method is used to update all `price` elements in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 <span data-ttu-id="e2976-126">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2976-126">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="modifying-typed-values"></a><span data-ttu-id="e2976-127">Ändern von typisierten Werten</span><span class="sxs-lookup"><span data-stu-id="e2976-127">Modifying Typed Values</span></span>  
 <span data-ttu-id="e2976-128">Wenn der Typ ein einfacher W3C-XML-Schematyp ist, wird der neue mit der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode eingefügte Wert anhand aller Facets des einfachen Typs überprüft, bevor er festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e2976-128">When the type of a node is a W3C XML Schema simple type, the new value inserted by the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method is checked against the facets of the simple type before the value is set.</span></span> <span data-ttu-id="e2976-129">Wenn der neue Wert bezüglich des Knotentyps nicht gültig ist (z. B. der Wert `-1` für ein Element vom Typ `xs:positiveInteger`), wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e2976-129">If the new value is not valid according to the type of the node (for example, setting a value of `-1` on an element whose type is `xs:positiveInteger`), it results in an exception.</span></span>  
  
 <span data-ttu-id="e2976-130">Im folgenden Beispiel wird versucht, den Wert des `price`-Elements des ersten `book`-Elements der Datei `contosoBooks.xml` in einen <xref:System.DateTime>-Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e2976-130">The following example attempts to change the value of the `price` element of the first `book` element in the `contosoBooks.xml` file to a <xref:System.DateTime> value.</span></span> <span data-ttu-id="e2976-131">Da der XML-Schematyp des `price`-Elements in den `xs:decimal`-Dateien als `contosoBooks.xsd` definiert ist, führt dies zu einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="e2976-131">Because the XML Schema type of the `price` element is defined as `xs:decimal` in the `contosoBooks.xsd` files, this results in an exception.</span></span>  
  
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
  
navigator.SetTypedValue(DateTime.Now)  
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
  
navigator.SetTypedValue(DateTime.Now);  
```  
  
 <span data-ttu-id="e2976-132">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2976-132">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="e2976-133">In diesem Beispiel wird auch `contosoBooks.xsd` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2976-133">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
#### <a name="the-effects-of-editing-strongly-typed-xml-data"></a><span data-ttu-id="e2976-134">Die Auswirkungen der Änderung von stark typisierten XML-Daten</span><span class="sxs-lookup"><span data-stu-id="e2976-134">The Effects of Editing Strongly Typed XML Data</span></span>  
 <span data-ttu-id="e2976-135">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse verwendet das W3C-XML-Schema als Grundlage für die Beschreibung von stark typisiertem XML.</span><span class="sxs-lookup"><span data-stu-id="e2976-135">The <xref:System.Xml.XPath.XPathNavigator> class uses the W3C XML Schema as a basis for describing strongly typed XML.</span></span> <span data-ttu-id="e2976-136">Zu Elementen und Attributen können auf der Grundlage der Validierung mit einem W3C-XML-Schemadokument Typinformationen angemerkt werden.</span><span class="sxs-lookup"><span data-stu-id="e2976-136">Elements and attributes can be annotated with type information based on validation against a W3C XML Schema document.</span></span> <span data-ttu-id="e2976-137">Elemente, die andere Elemente oder Attribute enthalten können, werden als komplexe Typen bezeichnet. Elemente, die nur Inhalt in Form von Text enthalten können, werden als einfache Typen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e2976-137">Elements that can contain other elements or attributes are called complex types, while those that can only contain textual content are called simple types.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2976-138">Attribute können nur einfache Typen haben.</span><span class="sxs-lookup"><span data-stu-id="e2976-138">Attributes can only have simple types.</span></span>  
  
 <span data-ttu-id="e2976-139">Ein Element oder Attribut kann als Schema-gültig betrachtet werden, wenn es alle spezifischen Regeln der Typdefinition genügt.</span><span class="sxs-lookup"><span data-stu-id="e2976-139">An element or attribute can be considered to be schema-valid if it conforms to all the rules specific to its type definition.</span></span> <span data-ttu-id="e2976-140">Ein Element mit dem einfachen Typ `xs:int` ist nur dann gültig, wenn es einen numerischen Wert zwischen -2147483648 und 2147483647 enthält.</span><span class="sxs-lookup"><span data-stu-id="e2976-140">An element that has the simple type `xs:int` has to contain a numeric value between -2147483648 and 2147483647 to be schema-valid.</span></span> <span data-ttu-id="e2976-141">Bei komplexen Typen hängt die Schema-Gültigkeit der Elemente von der Schema-Gültigkeit der untergeordneten Elemente und Attribute ab.</span><span class="sxs-lookup"><span data-stu-id="e2976-141">For complex types, the schema-validity of the element is dependent on the schema-validity of its child elements and attributes.</span></span> <span data-ttu-id="e2976-142">Wenn ein Element bezüglich einer komplexen Typdefinition gültig ist, dann sind auch alle untergeordneten Elemente und Attribute bezüglich deren Definitionen gültig.</span><span class="sxs-lookup"><span data-stu-id="e2976-142">Thus if an element is valid against its complex type definition, all its child elements and attributes are valid against their type definitions.</span></span> <span data-ttu-id="e2976-143">Wenn auch nur ein einziges untergeordnetes Element oder Attribut bezüglich seiner Typdefinition ungültig ist oder wenn die Gültigkeit nicht bekannt ist, ist das Element entweder ungültig, oder die Gültigkeit ist unbekannt.</span><span class="sxs-lookup"><span data-stu-id="e2976-143">Similarly, if even one of the child elements or attributes of an element is invalid against its type definition, or has an unknown validity, the element is also either invalid or of unknown validity.</span></span>  
  
 <span data-ttu-id="e2976-144">Da die Gültigkeit eines Elements von der Gültigkeit seiner untergeordneten Elemente und Attribute abhängt, führen Änderungen dazu, dass sich die Gültigkeit des Elements ändert, wenn es vorher gültig war.</span><span class="sxs-lookup"><span data-stu-id="e2976-144">Given that the validity of an element is dependent on the validity of its child elements and attributes, modifications to either result in altering the validity of the element if it was previously valid.</span></span> <span data-ttu-id="e2976-145">Insbesondere wird die Gültigkeit eines Elements unbekannt, wenn untergeordnete Elemente oder Attribute des Elements eingefügt, aktualisiert oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e2976-145">Specifically, if the child elements or attributes of an element are inserted, updated, or deleted, then the validity of the element becomes unknown.</span></span> <span data-ttu-id="e2976-146">Dies wird durch Festlegen der <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>-Eigenschaft des Elements auf <xref:System.Xml.Schema.XmlSchemaValidity.NotKnown> dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e2976-146">This is represented by the <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> property of the element's <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property being set to <xref:System.Xml.Schema.XmlSchemaValidity.NotKnown>.</span></span> <span data-ttu-id="e2976-147">Darüber hinaus setzt sich diese Auswirkung rekursiv aufwärts innerhalb des XML-Dokuments fort, da die Gültigkeit des übergeordneten Elements (und des diesem Element übergeordneten Elements usw.) eines Elements ebenfalls unbekannt wird.</span><span class="sxs-lookup"><span data-stu-id="e2976-147">Furthermore, this effect cascades upwards recursively across the XML document, because the validity of the element's parent element (and its parent element, and so on) also becomes unknown.</span></span>  
  
 <span data-ttu-id="e2976-148">Weitere Informationen über Schemavalidierung und die <xref:System.Xml.XPath.XPathNavigator>-Klasse finden Sie unter [Schemaüberprüfung mit XPathNavigator](schema-validation-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="e2976-148">For more information about schema validation and the <xref:System.Xml.XPath.XPathNavigator> class, see [Schema Validation using XPathNavigator](schema-validation-using-xpathnavigator.md).</span></span>  
  
### <a name="modifying-attributes"></a><span data-ttu-id="e2976-149">Ändern von Attributen</span><span class="sxs-lookup"><span data-stu-id="e2976-149">Modifying Attributes</span></span>  
 <span data-ttu-id="e2976-150">Mit der <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode und der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode können nicht typisierte und typisierte Attributknoten sowie die anderen im Abschnitt "Ändern von Knoten" aufgeführten Knotentypen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e2976-150">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods can be used to modify untyped and typed attribute nodes as well as the other node types listed in the "Modifying Nodes" section.</span></span>  
  
 <span data-ttu-id="e2976-151">Im fogenden Beispiel wird der Wert des `genre`-Attributs des ersten `book`-Elements der Datei `books.xml` geändert.</span><span class="sxs-lookup"><span data-stu-id="e2976-151">The following example changes the value of the `genre` attribute of the first `book` element in the `books.xml` file.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", String.Empty)  
navigator.MoveToChild("book", String.Empty)  
navigator.MoveToAttribute("genre", String.Empty)  
  
navigator.SetValue("non-fiction")  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", String.Empty);  
navigator.MoveToChild("book", String.Empty);  
navigator.MoveToAttribute("genre", String.Empty);  
  
navigator.SetValue("non-fiction");  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="e2976-152">Weitere Informationen über die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode finden Sie in den Abschnitten "Ändern von nicht typisierten Werten" und "Ändern von typisierten Werten".</span><span class="sxs-lookup"><span data-stu-id="e2976-152">For more information about the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods, see the "Modifying Untyped Values" and "Modifying Typed Values" sections.</span></span>  
  
## <a name="innerxml-and-outerxml-properties"></a><span data-ttu-id="e2976-153">Die Eigenschaften "InnerXml" und "OuterXml"</span><span class="sxs-lookup"><span data-stu-id="e2976-153">InnerXml and OuterXml Properties</span></span>  
 <span data-ttu-id="e2976-154">Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse ändern das XML-Markup der Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist.</span><span class="sxs-lookup"><span data-stu-id="e2976-154">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class change the XML markup of the nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="e2976-155">Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft ändert das XML-Markup der untergeordneten Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, mit den analysierten Inhalten des angegebenen XML-`string`.</span><span class="sxs-lookup"><span data-stu-id="e2976-155">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on with the parsed contents of the given XML `string`.</span></span> <span data-ttu-id="e2976-156">Ebenso ändert die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft das XML-Markup der untergeordneten Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, sowie den aktuellen Knoten selbst.</span><span class="sxs-lookup"><span data-stu-id="e2976-156">Similarly, the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on as well as the current node itself.</span></span>  
  
 <span data-ttu-id="e2976-157">Im folgenden Beispiel wird mit der <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft der Wert des `price`-Elements geändert und in das erste `discount`-Element der Datei `book` ein neues `contosoBooks.xml`-Attribut eingefügt.</span><span class="sxs-lookup"><span data-stu-id="e2976-157">The following example uses the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property to modify the value of the `price` element and insert a new `discount` attribute on the first `book` element in the `contosoBooks.xml` file.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml");  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.OuterXml = "<price discount=\"0\">10.99</price>"  
  
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
  
navigator.OuterXml = "<price discount=\"0\">10.99</price>";  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="e2976-158">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2976-158">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
## <a name="modifying-namespace-nodes"></a><span data-ttu-id="e2976-159">Ändern von Namespaceknoten</span><span class="sxs-lookup"><span data-stu-id="e2976-159">Modifying Namespace Nodes</span></span>  
 <span data-ttu-id="e2976-160">Im DOM (Document Object Model) werden Namespacedeklarationen wie normale Attribute behandelt, die eingefügt, aktualisiert und gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="e2976-160">In the Document Object Model (DOM), namespace declarations are treated as if they are regular attributes that can be inserted, updated and deleted.</span></span> <span data-ttu-id="e2976-161">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse lässt derartige Operationen auf Namespaceknoten nicht zu, da eine Änderung des Werts eines Namespaceknotens die Identität der Elemente innerhalb des Gültigkeitsbereichs des Namespaceknotens ändern kann. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e2976-161">The <xref:System.Xml.XPath.XPathNavigator> class does not allow such operations on namespace nodes because altering the value of a namespace node can change the identity of the elements and attributes within the scope of the namespace node as illustrated in the following example.</span></span>  
  
```xml  
<root xmlns="http://www.contoso.com">  
    <child />  
</root>  
```  
  
 <span data-ttu-id="e2976-162">Wenn das obige XML-Beispiel wie folgt geändert wird, wird dadurch jedes Element des Dokuments umbenannt, da sich der Wert des Namespace-URI aller Elemente ändert.</span><span class="sxs-lookup"><span data-stu-id="e2976-162">If the XML example above is changed in the following way, this effectively renames every element in the document because the value of each element's namespace URI is changed.</span></span>  
  
```xml  
<root xmlns="urn:contoso.com">  
    <child />  
</root>  
```  
  
 <span data-ttu-id="e2976-163">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse lässt das Einfügen von Namespaceknoten zu, wenn kein Konflikt innerhalb des Gültigkeitsbereichs, in den sie eingefügt werden, besteht.</span><span class="sxs-lookup"><span data-stu-id="e2976-163">Inserting namespace nodes that do not conflict with namespace declarations at the scope that they are inserted in is allowed by the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="e2976-164">In diesem Fall befinden sich die Namespacedeklarationen nicht in niedrigeren Gültigkeitsbereichen des XML-Dokuments und führen daher nicht zu einer Umbenennung. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e2976-164">In this case, the namespace declarations are not declared at lower scopes in the XML document and does not result in renaming as illustrated in the following example.</span></span>  
  
```xml  
<root xmlns:a="http://www.contoso.com">  
    <parent>  
        <a:child />  
    </parent>  
</root>  
```  
  
 <span data-ttu-id="e2976-165">Wenn das obige XML-Beispiel wie folgt geändert wird, werden die Namespacedeklarationen richtig innerhalb des XML-Dokuments unterhalb des Gültigkeitsbereichs der anderen Namespacedeklaration weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="e2976-165">If the XML example above is changed in the following way, the namespace declarations are correctly propagated across the XML document below the scope of the other namespace declaration.</span></span>  
  
```xml  
<root xmlns:a="http://www.contoso.com">  
    <parent a:parent-id="1234" xmlns:a="http://www.contoso.com/parent-id">  
        <a:child xmlns:a="http://www.contoso.com/" />  
    </parent>  
</root>  
```  
  
 <span data-ttu-id="e2976-166">Im obigen XML-Beispiel wird das Attribut `a:parent-id` im `parent`-Element im `http://www.contoso.com/parent-id`-Namespace eingefügt.</span><span class="sxs-lookup"><span data-stu-id="e2976-166">In the XML example above, the attribute `a:parent-id` is inserted on the `parent` element in the `http://www.contoso.com/parent-id` namespace.</span></span> <span data-ttu-id="e2976-167">Die <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>-Methode wird zum Einfügen des Attributs bei Positionierung auf dem `parent`-Element verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2976-167">The <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> method is used to insert the attribute while positioned on the `parent` element.</span></span> <span data-ttu-id="e2976-168">Die `http://www.contoso.com`-Namespacedeklaration wird von der <xref:System.Xml.XPath.XPathNavigator>-Klasse automatisch eingefügt, damit die Konsistenz mit dem restlichen XML-Dokument erhalten bleibt.</span><span class="sxs-lookup"><span data-stu-id="e2976-168">The `http://www.contoso.com` namespace declaration is automatically inserted by the <xref:System.Xml.XPath.XPathNavigator> class to preserve the consistency of the rest of the XML document.</span></span>  
  
## <a name="modifying-entity-reference-nodes"></a><span data-ttu-id="e2976-169">Ändern von Entitätsverweisknoten</span><span class="sxs-lookup"><span data-stu-id="e2976-169">Modifying Entity Reference Nodes</span></span>  
 <span data-ttu-id="e2976-170">Entitätsverweisknoten in einem <xref:System.Xml.XmlDocument>-Objekt sind schreibgeschützt und können weder mit der <xref:System.Xml.XPath.XPathNavigator>-Klasse noch mit der <xref:System.Xml.XmlNode>-Klasse geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e2976-170">Entity reference nodes in an <xref:System.Xml.XmlDocument> object are read-only and cannot be edited using either the <xref:System.Xml.XPath.XPathNavigator> or <xref:System.Xml.XmlNode> classes.</span></span> <span data-ttu-id="e2976-171">Ein Versuch, einen Entitätsverweisknoten zu ändern, führt zu einer <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="e2976-171">Any attempt to modify an entity reference node results in an <xref:System.InvalidOperationException>.</span></span>  
  
## <a name="modifying-xsinil-nodes"></a><span data-ttu-id="e2976-172">Ändern von xsi:nil-Knoten</span><span class="sxs-lookup"><span data-stu-id="e2976-172">Modifying xsi:nil Nodes</span></span>  
 <span data-ttu-id="e2976-173">Die XML-Schemaempfehlung des W3C führt das Konzept des "nillable"-Elements ein.</span><span class="sxs-lookup"><span data-stu-id="e2976-173">The W3C XML Schema recommendation introduces the concept of an element being nillable.</span></span> <span data-ttu-id="e2976-174">Wenn ein Element "nillable" ist, kann das Element gültig sein, ohne einen Inhalt zu haben.</span><span class="sxs-lookup"><span data-stu-id="e2976-174">When an element is nillable, it is possible for the element to have no content and still be valid.</span></span> <span data-ttu-id="e2976-175">Das Konzept eines "nillable"-Elements entspricht dem Konzept eines Objekts, das `null` ist.</span><span class="sxs-lookup"><span data-stu-id="e2976-175">The concept of an element being nillable is similar to the concept of an object being `null`.</span></span> <span data-ttu-id="e2976-176">Das Hauptunterschied besteht darin, dass auf ein `null`-Objekt keinerlei Zugriff möglich ist, während ein `xsi:nil`-Element zwar keinen Inhalt (untergeordnete Elemente oder Text) hat, aber Eigenschaften (z. B. Attribute) aufweist, auf die zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e2976-176">The main difference is that a `null` object cannot be accessed in any way, while an `xsi:nil` element still has properties such as attributes that can be accessed, but has no content (child elements or text).</span></span> <span data-ttu-id="e2976-177">Wenn ein Element eines XML-Dokuments ein `xsi:nil`-Attribut mit dem Wert `true` hat, bedeutet dies, dass das Element keinen Inhalt hat.</span><span class="sxs-lookup"><span data-stu-id="e2976-177">The existence of the `xsi:nil` attribute with a value of `true` on an element in an XML document is used to indicate that an element has no content.</span></span>  
  
 <span data-ttu-id="e2976-178">Wenn einem gültigen Element, dessen <xref:System.Xml.XPath.XPathNavigator>-Attribut den Wert `xsi:nil` hat, mittels eines `true`-Objekts Inhalt hinzugefügt wird, wird der Wert des `xsi:nil`-Attributs auf `false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e2976-178">If an <xref:System.Xml.XPath.XPathNavigator> object is used to add content to a valid element with an `xsi:nil` attribute with a value of `true`, the value of its `xsi:nil` attribute is set to `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2976-179">Wenn der Inhalt eines Elements, dessen `xsi:nil`-Attribut den Wert `false` hat, gelöscht wird, wird der Wert des Attributs nicht auf `true` geändert.</span><span class="sxs-lookup"><span data-stu-id="e2976-179">If the content of an element with an `xsi:nil` attribute set to `false` is deleted, the value of the attribute is not changed to `true`.</span></span>  
  
## <a name="saving-an-xml-document"></a><span data-ttu-id="e2976-180">Speichern eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="e2976-180">Saving an XML Document</span></span>  
 <span data-ttu-id="e2976-181">Änderungen eines <xref:System.Xml.XmlDocument>-Objekts, die von den in diesem Thema beschriebenen Bearbeitungsmethoden vorgenommen wurden, werden mit den Methoden der <xref:System.Xml.XmlDocument>-Klasse gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e2976-181">Saving changes made to an <xref:System.Xml.XmlDocument> object as the result of the editing methods described in this topic is performed using the methods of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="e2976-182">Weitere Informationen zum Speichern der an einem <xref:System.Xml.XmlDocument>-Objekt vorgenommenen Änderungen finden Sie unter [Speichern und Ausgeben eines Dokuments](saving-and-writing-a-document.md).</span><span class="sxs-lookup"><span data-stu-id="e2976-182">For more information about saving changes made to an <xref:System.Xml.XmlDocument> object, see [Saving and Writing a Document](saving-and-writing-a-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2976-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2976-183">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="e2976-184">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="e2976-184">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="e2976-185">Einfügen von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="e2976-185">Insert XML Data using XPathNavigator</span></span>](insert-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="e2976-186">Entfernen von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="e2976-186">Remove XML Data using XPathNavigator</span></span>](remove-xml-data-using-xpathnavigator.md)
