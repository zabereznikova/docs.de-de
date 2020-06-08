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
# <a name="schema-validation-using-xpathnavigator"></a>Schema-Validierung mithilfe von XPathNavigator
Mithilfe der <xref:System.Xml.XmlDocument>-Klasse haben Sie zwei Möglichkeiten, den XML-Inhalt eines <xref:System.Xml.XmlDocument>-Objekts zu validieren. Die erste Möglichkeit zum Validieren von XML-Inhalt besteht darin, ein validierendes <xref:System.Xml.XmlReader>-Objekt zu verwenden, und die zweite Möglichkeit besteht in der Verwendung der <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse. Mithilfe der <xref:System.Xml.XPath.XPathDocument>-Klasse können Sie eine schreibgeschützte Validierung von XML-Inhalt durchführen.  
  
## <a name="validating-xml-data"></a>Validieren von XML-Daten  
 In der Standardeinstellung validiert die <xref:System.Xml.XmlDocument>-Klasse ein XML-Dokument nicht mithilfe der DTD- oder XSD-Schemavalidierung (XML Schema Definition Language). Es wird nur überprüft, ob das XML-Dokument wohlgeformt ist.  
  
 Die erste Möglichkeit zum Validieren eines XML-Dokuments ist das Validieren des Dokuments mithilfe eines validierenden <xref:System.Xml.XmlDocument>-Objekts beim Laden in ein <xref:System.Xml.XmlReader>-Objekt. Die zweite Möglichkeit ist das Validieren eines zuvor nicht typisierten XML-Dokuments mithilfe der <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse. In beiden Fällen können Änderungen des validierten XML-Dokuments mithilfe der <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse erneut validiert werden.  
  
### <a name="validating-a-document-as-it-is-loaded"></a>Validieren eines Dokuments während des Ladevorgangs  
 Ein validierendes <xref:System.Xml.XmlReader>-Objekt wird durch das Übergeben eines <xref:System.Xml.XmlReaderSettings>-Objekts an die <xref:System.Xml.XmlReader.Create%2A>-Methode der <xref:System.Xml.XmlReader>-Klasse erstellt, die ein <xref:System.Xml.XmlReaderSettings>-Objekt als Parameter annimmt. Das als Parameter übergebene <xref:System.Xml.XmlReaderSettings>-Objekt verfügt über eine <xref:System.Xml.XmlReaderSettings.ValidationType%2A>-Eigenschaft, die auf `Schema` festgelegt ist, und über ein XML-Schema für das XML-Dokument, das in dem dessen <xref:System.Xml.XmlDocument>-Eigenschaft hinzugefügten <xref:System.Xml.XmlReaderSettings.Schemas%2A>-Objekt enthalten ist. Das validierende <xref:System.Xml.XmlReader>-Objekt wird dann zum Erstellen des <xref:System.Xml.XmlDocument>-Objekts verwendet.  
  
 Im folgenden Beispiel wird die `contosoBooks.xml`-Datei beim Laden in das <xref:System.Xml.XmlDocument>-Objekt validiert, indem das <xref:System.Xml.XmlDocument>-Objekt mithilfe eines validierenden <xref:System.Xml.XmlReader>-Objekts erstellt wird. Da das XML-Dokument entsprechend seines Schemas gültig ist, werden keine Schemavalidierungsfehler oder -warnungen generiert.  
  
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
  
 In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 In diesem Beispiel wird auch `contosoBooks.xsd` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 Im Beispiel oben wird eine <xref:System.Xml.Schema.XmlSchemaValidationException> ausgelöst, wenn <xref:System.Xml.XmlDocument.Load%2A> aufgerufen wird, falls ein Attribut oder Elementtyp nicht mit dem im Validierungsschema angegebenen zugehörigen Typ übereinstimmt. Wenn für den validierenden <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> ein <xref:System.Xml.XmlReader> festgelegt wurde, wird der <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> aufgerufen, sobald ein ungültiger Typ gefunden wird.  
  
 Greift der <xref:System.Xml.Schema.XmlSchemaException> auf ein Attribut oder Element zu, bei dem für <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>`invalid` angegeben ist, wird eine <xref:System.Xml.XPath.XPathNavigator> ausgelöst .  
  
 Um beim Zugriff auf Attribute oder Elemente mit dem <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> zu bestimmen, ob das jeweilige Attribut oder Element gültig ist, kann die <xref:System.Xml.XPath.XPathNavigator>-Eigenschaft verwendet werden.  
  
> [!NOTE]
> Wenn ein XML-Dokument in ein <xref:System.Xml.XmlDocument>-Objekt mit einem zugeordneten Schema geladen wird, das Standardwerte definiert, behandelt das <xref:System.Xml.XmlDocument>-Objekt diese Standardwerte, als wären diese im XML-Dokument enthalten. Das bedeutet, dass die <xref:System.Xml.XPath.XPathNavigator.IsEmptyElement%2A>-Eigenschaft immer `false` für ein Element zurückgibt, das vom Schema als Standard verwendet wird, auch wenn es im XML-Dokument als leeres Element geschrieben wurde.  
  
### <a name="validating-a-document-using-the-validate-method"></a>Validieren eines Dokuments mithilfe der Validate-Methode  
 Die <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse validiert das in einem <xref:System.Xml.XmlDocument>-Objekt enthaltene XML-Dokument anhand des in der <xref:System.Xml.XmlDocument>-Eigenschaft des <xref:System.Xml.XmlDocument.Schemas%2A>-Objekts angegebenen Schemas und führt den Zuwachs des Infosets durch. Dadurch wird ein zuvor nicht typisiertes XML-Dokument im <xref:System.Xml.XmlDocument>-Objekt durch ein typisiertes Dokument ersetzt.  
  
 Das <xref:System.Xml.XmlDocument>-Objekt meldet Schemavalidierungsfehler und -warnungen mithilfe des <xref:System.Xml.Schema.ValidationEventHandler>-Delegaten, der als Parameter an die <xref:System.Xml.XmlDocument.Validate%2A>-Methode übergeben wird.  
  
 Im folgenden Beispiel wird die im `contosoBooks.xml`-Objekt enthaltene <xref:System.Xml.XmlDocument>-Datei anhand des `contosoBooks.xsd`-Schemas validiert, das in der <xref:System.Xml.XmlDocument>-Eigenschaft des <xref:System.Xml.XmlDocument.Schemas%2A>-Objekts enthalten ist.  
  
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
  
 In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 In diesem Beispiel wird auch `contosoBooks.xsd` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
### <a name="validating-modifications"></a>Validierungsänderungen  
 Nachdem an einem XML-Dokument Änderungen vorgenommen wurden, können Sie die Änderungen anhand des Schemas des XML-Dokuments mithilfe der <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse validieren.  
  
 Im folgenden Beispiel wird die `contosoBooks.xml`-Datei beim Laden in das <xref:System.Xml.XmlDocument>-Objekt validiert, indem das <xref:System.Xml.XmlDocument>-Objekt mithilfe eines validierenden <xref:System.Xml.XmlReader>-Objekts erstellt wird. Das XML-Dokument ist erfolgreich validiert, wenn es ohne Eintreten von Schemavalidierungsfehlern oder -warnungen geladen werden kann. Im Beispiel werden dann zwei Änderungen am XML-Dokument vorgenommen, die gemäß des `contosoBooks.xsd`-Schemas ungültig sind. Bei der ersten Änderung wird ein ungültiges untergeordnetes Element eingefügt, wodurch ein Schemavalidierungsfehler eintritt. Bei der zweiten Änderung wird der Wert einer typisierten Knotens auf einen Wert festgelegt, der gemäß des Typs des Knotens ungültig ist, wodurch eine Ausnahme ausgelöst wird.  
  
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
  
 In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 In diesem Beispiel wird auch `contosoBooks.xsd` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 In dem Beispiel oben werden zwei Änderungen an dem XML-Dokument vorgenommen, das im <xref:System.Xml.XmlDocument>-Objekt enthalten ist. Beim Laden des XML-Dokuments wären alle festgestellten Schemavalidierungsfehler von der Methode des Ereignishandlers für die Validierung behandelt und auf der Konsole ausgegeben worden.  
  
 In diesem Beispiel sind die Validierungsfehler nach dem Laden des XML-Dokuments eingetreten und wurden mithilfe der <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse gefunden.  
  
 Änderungen, die mithilfe der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse vorgenommen wurden, hatten eine <xref:System.InvalidCastException> zur Folge, da der neue Wert gemäß des Schematyps des Knotens ungültig war.  
  
 Weitere Informationen zum Ändern von Werten mithilfe der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode finden Sie unter dem Thema [Ändern von XML-Daten mit XPathNavigator](modify-xml-data-using-xpathnavigator.md).  
  
### <a name="read-only-validation"></a>Schreibgeschützte Validierung  
 Die <xref:System.Xml.XPath.XPathDocument>-Klasse ist eine schreibgeschützte Darstellung eines XML-Dokuments im Speicher. Sowohl die <xref:System.Xml.XPath.XPathDocument>-Klasse als auch die <xref:System.Xml.XmlDocument>-Klasse erstellen <xref:System.Xml.XPath.XPathNavigator>-Objekte zum Navigieren und zum Bearbeiten von XML-Dokumenten. Da die <xref:System.Xml.XPath.XPathDocument>-Klasse schreibgeschützt ist, können von <xref:System.Xml.XPath.XPathNavigator>-Objekten zurückgegebene <xref:System.Xml.XPath.XPathDocument>-Objekte das im <xref:System.Xml.XPath.XPathDocument>-Objekt enthaltene XML-Dokument nicht bearbeiten.  
  
 Bei der Validierung können Sie ein <xref:System.Xml.XPath.XPathDocument>-Objekt auf die gleiche Weise erstellen, wie ein <xref:System.Xml.XmlDocument>-Objekt mithilfe eines validierenden <xref:System.Xml.XmlReader>-Objekts erstellt wird, wie bereits in diesem Thema erläutert. Das <xref:System.Xml.XPath.XPathDocument>-Objekt validiert das XML-Dokument beim Ladevorgang. Da die XML-Daten jedoch im <xref:System.Xml.XPath.XPathDocument>-Objekt nicht bearbeitet werden können, können Sie das XML-Dokument nicht erneut validieren.  
  
 Weitere Informationen zu schreibgeschützten und bearbeitbaren <xref:System.Xml.XPath.XPathNavigator>-Objekten finden Sie in dem Thema [Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](process-xml-data-using-the-xpath-data-model.md)
- [Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md)
- [Auswählen, Auswerten und Zuordnen von XML-Daten mithilfe von XPathNavigator](selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
- [Zugreifen auf XML-Daten mit XPathNavigator](accessing-xml-data-using-xpathnavigator.md)
- [Bearbeiten von XML-Daten mit XPathNavigator](editing-xml-data-using-xpathnavigator.md)
