---
title: Schema-Validierung mithilfe von XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 81fa0e41-d9c9-46f0-b22b-50da839c77f5
ms.openlocfilehash: f6e56616543bf7d2ad2e6be4d7bf7cbc50ba3a23
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84292006"
---
# <a name="schema-validation-using-xpathnavigator"></a><span data-ttu-id="83795-102">Schema-Validierung mithilfe von XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="83795-102">Schema Validation using XPathNavigator</span></span>
<span data-ttu-id="83795-103">Mithilfe der <xref:System.Xml.XmlDocument>-Klasse haben Sie zwei Möglichkeiten, den XML-Inhalt eines <xref:System.Xml.XmlDocument>-Objekts zu validieren.</span><span class="sxs-lookup"><span data-stu-id="83795-103">Using the <xref:System.Xml.XmlDocument> class, you can validate the XML content contained in an <xref:System.Xml.XmlDocument> object in two ways.</span></span> <span data-ttu-id="83795-104">Die erste Möglichkeit zum Validieren von XML-Inhalt besteht darin, ein validierendes <xref:System.Xml.XmlReader>-Objekt zu verwenden, und die zweite Möglichkeit besteht in der Verwendung der <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="83795-104">The first way is to validate the XML content using a validating <xref:System.Xml.XmlReader> object and the second way is to use the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="83795-105">Mithilfe der <xref:System.Xml.XPath.XPathDocument>-Klasse können Sie eine schreibgeschützte Validierung von XML-Inhalt durchführen.</span><span class="sxs-lookup"><span data-stu-id="83795-105">You can also perform read-only validation of XML content using the <xref:System.Xml.XPath.XPathDocument> class.</span></span>  
  
## <a name="validating-xml-data"></a><span data-ttu-id="83795-106">Validieren von XML-Daten</span><span class="sxs-lookup"><span data-stu-id="83795-106">Validating XML Data</span></span>  
 <span data-ttu-id="83795-107">In der Standardeinstellung validiert die <xref:System.Xml.XmlDocument>-Klasse ein XML-Dokument nicht mithilfe der DTD- oder XSD-Schemavalidierung (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="83795-107">The <xref:System.Xml.XmlDocument> class does not validate an XML document using either DTD or XML schema definition language (XSD) schema validation by default.</span></span> <span data-ttu-id="83795-108">Es wird nur überprüft, ob das XML-Dokument wohlgeformt ist.</span><span class="sxs-lookup"><span data-stu-id="83795-108">It only verifies that the XML document is well formed.</span></span>  
  
 <span data-ttu-id="83795-109">Die erste Möglichkeit zum Validieren eines XML-Dokuments ist das Validieren des Dokuments mithilfe eines validierenden <xref:System.Xml.XmlDocument>-Objekts beim Laden in ein <xref:System.Xml.XmlReader>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="83795-109">The first way to validate an XML document is to validate the document as it is loaded into an <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="83795-110">Die zweite Möglichkeit ist das Validieren eines zuvor nicht typisierten XML-Dokuments mithilfe der <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="83795-110">The second way is to validate a previously untyped XML document using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="83795-111">In beiden Fällen können Änderungen des validierten XML-Dokuments mithilfe der <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse erneut validiert werden.</span><span class="sxs-lookup"><span data-stu-id="83795-111">In both cases, changes to the validated XML document can be revalidated using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span>  
  
### <a name="validating-a-document-as-it-is-loaded"></a><span data-ttu-id="83795-112">Validieren eines Dokuments während des Ladevorgangs</span><span class="sxs-lookup"><span data-stu-id="83795-112">Validating a Document as it is Loaded</span></span>  
 <span data-ttu-id="83795-113">Ein validierendes <xref:System.Xml.XmlReader>-Objekt wird durch das Übergeben eines <xref:System.Xml.XmlReaderSettings>-Objekts an die <xref:System.Xml.XmlReader.Create%2A>-Methode der <xref:System.Xml.XmlReader>-Klasse erstellt, die ein <xref:System.Xml.XmlReaderSettings>-Objekt als Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="83795-113">A validating <xref:System.Xml.XmlReader> object is created by passing an <xref:System.Xml.XmlReaderSettings> object to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class that takes an <xref:System.Xml.XmlReaderSettings> object as a parameter.</span></span> <span data-ttu-id="83795-114">Das als Parameter übergebene <xref:System.Xml.XmlReaderSettings>-Objekt verfügt über eine <xref:System.Xml.XmlReaderSettings.ValidationType%2A>-Eigenschaft, die auf `Schema` festgelegt ist, und über ein XML-Schema für das XML-Dokument, das in dem dessen <xref:System.Xml.XmlDocument>-Eigenschaft hinzugefügten <xref:System.Xml.XmlReaderSettings.Schemas%2A>-Objekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="83795-114">The <xref:System.Xml.XmlReaderSettings> object passed as a parameter has a <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property set to `Schema` and an XML Schema for the XML document contained in the <xref:System.Xml.XmlDocument> object added to its <xref:System.Xml.XmlReaderSettings.Schemas%2A> property.</span></span> <span data-ttu-id="83795-115">Das validierende <xref:System.Xml.XmlReader>-Objekt wird dann zum Erstellen des <xref:System.Xml.XmlDocument>-Objekts verwendet.</span><span class="sxs-lookup"><span data-stu-id="83795-115">The validating <xref:System.Xml.XmlReader> object is then used to create the <xref:System.Xml.XmlDocument> object.</span></span>  
  
 <span data-ttu-id="83795-116">Im folgenden Beispiel wird die `contosoBooks.xml`-Datei beim Laden in das <xref:System.Xml.XmlDocument>-Objekt validiert, indem das <xref:System.Xml.XmlDocument>-Objekt mithilfe eines validierenden <xref:System.Xml.XmlReader>-Objekts erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="83795-116">The following example validates the `contosoBooks.xml` file as it is loaded into the <xref:System.Xml.XmlDocument> object by creating the <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="83795-117">Da das XML-Dokument entsprechend seines Schemas gültig ist, werden keine Schemavalidierungsfehler oder -warnungen generiert.</span><span class="sxs-lookup"><span data-stu-id="83795-117">Because the XML document is valid according to its schema, no schema validation errors or warnings are generated.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidatingReaderExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Try  
            Dim settings As XmlReaderSettings = New XmlReaderSettings()  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
            settings.ValidationType = ValidationType.Schema  
  
            Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
            Dim document As XmlDocument = New XmlDocument()  
            document.Load(reader)  
            Dim navigator As XPathNavigator = document.CreateNavigator()  
  
        Catch e As Exception  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message)  
        End Try  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidatingReaderExample  
{  
    static void Main(string[] args)  
    {  
        try  
        {  
            XmlReaderSettings settings = new XmlReaderSettings();  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
            settings.ValidationType = ValidationType.Schema;  
  
            XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
            XmlDocument document = new XmlDocument();  
            document.Load(reader);  
            XPathNavigator navigator = document.CreateNavigator();  
        }  
        catch (Exception e)  
        {  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message);  
        }  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="83795-118">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="83795-118">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="83795-119">In diesem Beispiel wird auch `contosoBooks.xsd` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="83795-119">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 <span data-ttu-id="83795-120">Im Beispiel oben wird eine <xref:System.Xml.Schema.XmlSchemaValidationException> ausgelöst, wenn <xref:System.Xml.XmlDocument.Load%2A> aufgerufen wird, falls ein Attribut oder Elementtyp nicht mit dem im Validierungsschema angegebenen zugehörigen Typ übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="83795-120">In the above example, an <xref:System.Xml.Schema.XmlSchemaValidationException> will be thrown when <xref:System.Xml.XmlDocument.Load%2A> is called if any attribute or element type does not match the corresponding type specified in the validating schema.</span></span> <span data-ttu-id="83795-121">Wenn für den validierenden <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> ein <xref:System.Xml.XmlReader> festgelegt wurde, wird der <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> aufgerufen, sobald ein ungültiger Typ gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="83795-121">If a <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> is set on the validating <xref:System.Xml.XmlReader>, the <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> will get called whenever an invalid type is encountered.</span></span>  
  
 <span data-ttu-id="83795-122">Greift der <xref:System.Xml.Schema.XmlSchemaException> auf ein Attribut oder Element zu, bei dem für <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>`invalid` angegeben ist, wird eine <xref:System.Xml.XPath.XPathNavigator> ausgelöst .</span><span class="sxs-lookup"><span data-stu-id="83795-122">An <xref:System.Xml.Schema.XmlSchemaException> will be thrown when an attribute or element with <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> set to `invalid` is accessed by the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="83795-123">Um beim Zugriff auf Attribute oder Elemente mit dem <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> zu bestimmen, ob das jeweilige Attribut oder Element gültig ist, kann die <xref:System.Xml.XPath.XPathNavigator>-Eigenschaft verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="83795-123">The <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> property can be used to determine whether or not an individual attribute or element is valid when accessing attributes or elements with the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83795-124">Wenn ein XML-Dokument in ein <xref:System.Xml.XmlDocument>-Objekt mit einem zugeordneten Schema geladen wird, das Standardwerte definiert, behandelt das <xref:System.Xml.XmlDocument>-Objekt diese Standardwerte, als wären diese im XML-Dokument enthalten.</span><span class="sxs-lookup"><span data-stu-id="83795-124">When an XML document is loaded into an <xref:System.Xml.XmlDocument> object with an associated schema that defines default values, the <xref:System.Xml.XmlDocument> object treats these defaults as if they appeared in the XML document.</span></span> <span data-ttu-id="83795-125">Das bedeutet, dass die <xref:System.Xml.XPath.XPathNavigator.IsEmptyElement%2A>-Eigenschaft immer `false` für ein Element zurückgibt, das vom Schema als Standard verwendet wird, auch wenn es im XML-Dokument als leeres Element geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="83795-125">This means that the <xref:System.Xml.XPath.XPathNavigator.IsEmptyElement%2A> property  always returns `false` for an element that was defaulted from the schema, even if in the XML document it was written as an empty element.</span></span>  
  
### <a name="validating-a-document-using-the-validate-method"></a><span data-ttu-id="83795-126">Validieren eines Dokuments mithilfe der Validate-Methode</span><span class="sxs-lookup"><span data-stu-id="83795-126">Validating a Document using the Validate Method</span></span>  
 <span data-ttu-id="83795-127">Die <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse validiert das in einem <xref:System.Xml.XmlDocument>-Objekt enthaltene XML-Dokument anhand des in der <xref:System.Xml.XmlDocument>-Eigenschaft des <xref:System.Xml.XmlDocument.Schemas%2A>-Objekts angegebenen Schemas und führt den Zuwachs des Infosets durch.</span><span class="sxs-lookup"><span data-stu-id="83795-127">The <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class validates the XML document contained in an <xref:System.Xml.XmlDocument> object against the schemas specified in the <xref:System.Xml.XmlDocument> object's <xref:System.Xml.XmlDocument.Schemas%2A> property and performs infoset augmentation.</span></span> <span data-ttu-id="83795-128">Dadurch wird ein zuvor nicht typisiertes XML-Dokument im <xref:System.Xml.XmlDocument>-Objekt durch ein typisiertes Dokument ersetzt.</span><span class="sxs-lookup"><span data-stu-id="83795-128">The result is a previously untyped XML document in the <xref:System.Xml.XmlDocument> object replaced with a typed document.</span></span>  
  
 <span data-ttu-id="83795-129">Das <xref:System.Xml.XmlDocument>-Objekt meldet Schemavalidierungsfehler und -warnungen mithilfe des <xref:System.Xml.Schema.ValidationEventHandler>-Delegaten, der als Parameter an die <xref:System.Xml.XmlDocument.Validate%2A>-Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="83795-129">The <xref:System.Xml.XmlDocument> object reports schema validation errors and warnings using the <xref:System.Xml.Schema.ValidationEventHandler> delegate passed as a parameter to the <xref:System.Xml.XmlDocument.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="83795-130">Im folgenden Beispiel wird die im `contosoBooks.xml`-Objekt enthaltene <xref:System.Xml.XmlDocument>-Datei anhand des `contosoBooks.xsd`-Schemas validiert, das in der <xref:System.Xml.XmlDocument>-Eigenschaft des <xref:System.Xml.XmlDocument.Schemas%2A>-Objekts enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="83795-130">The following example validates the `contosoBooks.xml` file contained in the <xref:System.Xml.XmlDocument> object against the `contosoBooks.xsd` schema contained in the <xref:System.Xml.XmlDocument> object's <xref:System.Xml.XmlDocument.Schemas%2A> property.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidateExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Dim document As XmlDocument = New XmlDocument()  
        document.Load("contosoBooks.xml")  
        Dim navigator As XPathNavigator = document.CreateNavigator()  
  
        document.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
        Dim validation As ValidationEventHandler = New ValidationEventHandler(AddressOf SchemaValidationHandler)  
  
        document.Validate(validation)  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidateExample  
{  
    static void Main(string[] args)  
    {  
        XmlDocument document = new XmlDocument();  
        document.Load("contosoBooks.xml");  
        XPathNavigator navigator = document.CreateNavigator();  
  
        document.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
        ValidationEventHandler validation = new ValidationEventHandler(SchemaValidationHandler);  
  
        document.Validate(validation);  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="83795-131">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="83795-131">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="83795-132">In diesem Beispiel wird auch `contosoBooks.xsd` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="83795-132">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
### <a name="validating-modifications"></a><span data-ttu-id="83795-133">Validierungsänderungen</span><span class="sxs-lookup"><span data-stu-id="83795-133">Validating Modifications</span></span>  
 <span data-ttu-id="83795-134">Nachdem an einem XML-Dokument Änderungen vorgenommen wurden, können Sie die Änderungen anhand des Schemas des XML-Dokuments mithilfe der <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse validieren.</span><span class="sxs-lookup"><span data-stu-id="83795-134">After modifications are made to an XML document, you can validate the modifications against the schema for the XML document using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="83795-135">Im folgenden Beispiel wird die `contosoBooks.xml`-Datei beim Laden in das <xref:System.Xml.XmlDocument>-Objekt validiert, indem das <xref:System.Xml.XmlDocument>-Objekt mithilfe eines validierenden <xref:System.Xml.XmlReader>-Objekts erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="83795-135">The following example validates the `contosoBooks.xml` file as it is loaded into the <xref:System.Xml.XmlDocument> object by creating the <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="83795-136">Das XML-Dokument ist erfolgreich validiert, wenn es ohne Eintreten von Schemavalidierungsfehlern oder -warnungen geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="83795-136">The XML document is validated successfully as it is loaded without generating any schema validation errors or warnings.</span></span> <span data-ttu-id="83795-137">Im Beispiel werden dann zwei Änderungen am XML-Dokument vorgenommen, die gemäß des `contosoBooks.xsd`-Schemas ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="83795-137">The example then makes two modifications to the XML document that are invalid according to the `contosoBooks.xsd` schema.</span></span> <span data-ttu-id="83795-138">Bei der ersten Änderung wird ein ungültiges untergeordnetes Element eingefügt, wodurch ein Schemavalidierungsfehler eintritt. Bei der zweiten Änderung wird der Wert einer typisierten Knotens auf einen Wert festgelegt, der gemäß des Typs des Knotens ungültig ist, wodurch eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="83795-138">The first modification inserts an invalid child element resulting in a schema validation error, and the second modification sets the value of a typed node to a value that is invalid according to the type of the node resulting in an exception.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidatingReaderExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Try  
            Dim settings As XmlReaderSettings = New XmlReaderSettings()  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
            settings.ValidationType = ValidationType.Schema  
  
            Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
            Dim document As XmlDocument = New XmlDocument()  
            document.Load(reader)  
            Dim navigator As XPathNavigator = document.CreateNavigator()  
  
            Dim validation As ValidationEventHandler = New ValidationEventHandler(AddressOf SchemaValidationHandler)  
  
            navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
            navigator.MoveToChild("book", "http://www.contoso.com/books")  
            navigator.MoveToChild("author", "http://www.contoso.com/books")  
  
            navigator.AppendChild("<title>Book Title</title>")  
  
            document.Validate(validation)  
  
            navigator.MoveToParent()  
            navigator.MoveToChild("price", "http://www.contoso.com/books")  
            navigator.SetTypedValue(DateTime.Now)  
        Catch e As Exception  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message)  
        End Try  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidatingReaderExample  
{  
    static void Main(string[] args)  
    {  
        try  
        {  
            XmlReaderSettings settings = new XmlReaderSettings();  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
            settings.ValidationType = ValidationType.Schema;  
  
            XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
            XmlDocument document = new XmlDocument();  
            document.Load(reader);  
            XPathNavigator navigator = document.CreateNavigator();  
  
            ValidationEventHandler validation = new ValidationEventHandler(SchemaValidationHandler);  
  
            navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
            navigator.MoveToChild("book", "http://www.contoso.com/books");  
            navigator.MoveToChild("author", "http://www.contoso.com/books");  
  
            navigator.AppendChild("<title>Book Title</title>");  
  
            document.Validate(validation);  
  
            navigator.MoveToParent();  
            navigator.MoveToChild("price", "http://www.contoso.com/books");  
            navigator.SetTypedValue(DateTime.Now);  
        }  
        catch (Exception e)  
        {  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message);  
        }  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="83795-139">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="83795-139">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="83795-140">In diesem Beispiel wird auch `contosoBooks.xsd` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="83795-140">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 <span data-ttu-id="83795-141">In dem Beispiel oben werden zwei Änderungen an dem XML-Dokument vorgenommen, das im <xref:System.Xml.XmlDocument>-Objekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="83795-141">In the example above, two modifications are made to the XML document contained in the <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="83795-142">Beim Laden des XML-Dokuments wären alle festgestellten Schemavalidierungsfehler von der Methode des Ereignishandlers für die Validierung behandelt und auf der Konsole ausgegeben worden.</span><span class="sxs-lookup"><span data-stu-id="83795-142">As the XML document was loaded, any schema validation errors encountered would have been handled by the validation event handler method and written to the console.</span></span>  
  
 <span data-ttu-id="83795-143">In diesem Beispiel sind die Validierungsfehler nach dem Laden des XML-Dokuments eingetreten und wurden mithilfe der <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse gefunden.</span><span class="sxs-lookup"><span data-stu-id="83795-143">In this example, the validation errors were introduced after the XML document was loaded and were found using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="83795-144">Änderungen, die mithilfe der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse vorgenommen wurden, hatten eine <xref:System.InvalidCastException> zur Folge, da der neue Wert gemäß des Schematyps des Knotens ungültig war.</span><span class="sxs-lookup"><span data-stu-id="83795-144">Modifications made using the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class resulted in an <xref:System.InvalidCastException> because the new value was invalid according to the schema type of the node.</span></span>  
  
 <span data-ttu-id="83795-145">Weitere Informationen zum Ändern von Werten mithilfe der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode finden Sie unter dem Thema [Ändern von XML-Daten mit XPathNavigator](modify-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="83795-145">For more information about modifying values using the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method, see the [Modify XML Data using XPathNavigator](modify-xml-data-using-xpathnavigator.md) topic.</span></span>  
  
### <a name="read-only-validation"></a><span data-ttu-id="83795-146">Schreibgeschützte Validierung</span><span class="sxs-lookup"><span data-stu-id="83795-146">Read-Only Validation</span></span>  
 <span data-ttu-id="83795-147">Die <xref:System.Xml.XPath.XPathDocument>-Klasse ist eine schreibgeschützte Darstellung eines XML-Dokuments im Speicher.</span><span class="sxs-lookup"><span data-stu-id="83795-147">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory representation of an XML document.</span></span> <span data-ttu-id="83795-148">Sowohl die <xref:System.Xml.XPath.XPathDocument>-Klasse als auch die <xref:System.Xml.XmlDocument>-Klasse erstellen <xref:System.Xml.XPath.XPathNavigator>-Objekte zum Navigieren und zum Bearbeiten von XML-Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="83795-148">Both the <xref:System.Xml.XPath.XPathDocument> class and the <xref:System.Xml.XmlDocument> class create <xref:System.Xml.XPath.XPathNavigator> objects to navigate and edit XML documents.</span></span> <span data-ttu-id="83795-149">Da die <xref:System.Xml.XPath.XPathDocument>-Klasse schreibgeschützt ist, können von <xref:System.Xml.XPath.XPathNavigator>-Objekten zurückgegebene <xref:System.Xml.XPath.XPathDocument>-Objekte das im <xref:System.Xml.XPath.XPathDocument>-Objekt enthaltene XML-Dokument nicht bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="83795-149">Because the <xref:System.Xml.XPath.XPathDocument> class is a read-only class, <xref:System.Xml.XPath.XPathNavigator> object's returned from <xref:System.Xml.XPath.XPathDocument> objects cannot edit the XML document contained in the <xref:System.Xml.XPath.XPathDocument> object.</span></span>  
  
 <span data-ttu-id="83795-150">Bei der Validierung können Sie ein <xref:System.Xml.XPath.XPathDocument>-Objekt auf die gleiche Weise erstellen, wie ein <xref:System.Xml.XmlDocument>-Objekt mithilfe eines validierenden <xref:System.Xml.XmlReader>-Objekts erstellt wird, wie bereits in diesem Thema erläutert.</span><span class="sxs-lookup"><span data-stu-id="83795-150">In the case of validation, you can create an <xref:System.Xml.XPath.XPathDocument> object just like you create an <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object as described earlier in this topic.</span></span> <span data-ttu-id="83795-151">Das <xref:System.Xml.XPath.XPathDocument>-Objekt validiert das XML-Dokument beim Ladevorgang. Da die XML-Daten jedoch im <xref:System.Xml.XPath.XPathDocument>-Objekt nicht bearbeitet werden können, können Sie das XML-Dokument nicht erneut validieren.</span><span class="sxs-lookup"><span data-stu-id="83795-151">The <xref:System.Xml.XPath.XPathDocument> object validates the XML document as it is loaded, but because you cannot edit the XML data in the <xref:System.Xml.XPath.XPathDocument> object, you cannot revalidate the XML document.</span></span>  
  
 <span data-ttu-id="83795-152">Weitere Informationen zu schreibgeschützten und bearbeitbaren <xref:System.Xml.XPath.XPathNavigator>-Objekten finden Sie in dem Thema [Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).</span><span class="sxs-lookup"><span data-stu-id="83795-152">For more information about read-only and editable <xref:System.Xml.XPath.XPathNavigator> objects, see the [Reading XML Data using XPathDocument and XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83795-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83795-153">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="83795-154">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="83795-154">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="83795-155">Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument</span><span class="sxs-lookup"><span data-stu-id="83795-155">Reading XML Data using XPathDocument and XmlDocument</span></span>](reading-xml-data-using-xpathdocument-and-xmldocument.md)
- [<span data-ttu-id="83795-156">Auswählen, Auswerten und Zuordnen von XML-Daten mithilfe von XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="83795-156">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="83795-157">Zugreifen auf XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="83795-157">Accessing XML Data using XPathNavigator</span></span>](accessing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="83795-158">Bearbeiten von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="83795-158">Editing XML Data using XPathNavigator</span></span>](editing-xml-data-using-xpathnavigator.md)
