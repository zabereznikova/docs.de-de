---
title: Ändern von XML-Daten mit "XPathNavigator"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 03a7c5a1-b296-4af4-b209-043c958dc0a5
ms.openlocfilehash: 3b64bc8666274798ebaefc87ef3883fcec1ef6b1
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288835"
---
# <a name="modify-xml-data-using-xpathnavigator"></a>Ändern von XML-Daten mit "XPathNavigator"
Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt eine Gruppe von Methoden bereit, die zum Ändern von Knoten und Werten eines XML-Dokuments verwendet werden. Diese Methoden können nur dann verwendet werden, wenn das <xref:System.Xml.XPath.XPathNavigator>-Objekt bearbeitet werden kann, d. h. seine <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Eigenschaft muss `true` sein.  
  
 <xref:System.Xml.XPath.XPathNavigator>-Objekte, die ein XML-Dokument bearbeiten können, werden von der <xref:System.Xml.XmlDocument.CreateNavigator%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse erstellt. <xref:System.Xml.XPath.XPathNavigator>-Objekte, die von der <xref:System.Xml.XPath.XPathDocument>-Klasse erstellt werden, sind schreibgeschützt. Der Versuch, die Bearbeitungsmethoden eines <xref:System.Xml.XPath.XPathNavigator>-Objekts anzuwenden, das von einem <xref:System.Xml.XPath.XPathDocument>-Objekt erstellt wurde, führt zu einer <xref:System.NotSupportedException>.  
  
 Weitere Informationen zum Erstellen bearbeitbarer <xref:System.Xml.XPath.XPathNavigator>-Objekte finden Sie unter [Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).  
  
## <a name="modifying-nodes"></a>Ändern von Knoten  
 Ein einfaches Verfahren zum Ändern des Werts eines Knotens ist die Verwendung der <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode und der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse.  
  
 In der folgenden Tabelle ist die Wirkung dieser Methoden für verschiedene Knotentypen aufgeführt.  
  
|<xref:System.Xml.XPath.XPathNodeType>|Geänderte Daten|  
|---------------------------------------------------------------------------------------------------------------------------------------------|------------------|  
|<xref:System.Xml.XPath.XPathNodeType.Root>|Wird nicht unterstützt.|  
|<xref:System.Xml.XPath.XPathNodeType.Element>|Der Inhalt des Elements.|  
|<xref:System.Xml.XPath.XPathNodeType.Attribute>|Der Wert des Attributs.|  
|<xref:System.Xml.XPath.XPathNodeType.Text>|Der Textinhalt.|  
|<xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>|Der Inhalt mit Ausnahme des Ziels.|  
|<xref:System.Xml.XPath.XPathNodeType.Comment>|Der Inhalt des Kommentars.|  
|<xref:System.Xml.XPath.XPathNodeType.Namespace>|Nicht unterstützt.|  
  
> [!NOTE]
> Das Bearbeiten von <xref:System.Xml.XPath.XPathNodeType.Namespace>-Knoten oder des <xref:System.Xml.XPath.XPathNodeType.Root>-Knotens wird nicht unterstützt.  
  
 Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt ebenfalls eine Gruppe von Methoden zum Einfügen und Entfernen von Knoten bereit. Weitere Informationen zum Einfügen und Entfernen von Knoten aus einem XML-Dokument finden Sie in den Themen [Einfügen von XML-Daten mit XPathNavigator](insert-xml-data-using-xpathnavigator.md) und [Entfernen von XML-Daten mit XPathNavigator](remove-xml-data-using-xpathnavigator.md).  
  
### <a name="modifying-untyped-values"></a>Ändern von nicht typisierten Werten  
 Die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode fügt einfach den als Parameter übergebenen nicht typisierten `string`-Wert als Wert des Knotens ein, auf dem das <xref:System.Xml.XPath.XPathNavigator>-Objekt gerade positioniert ist. Der Wert wird ohne Typ bzw. (falls Schemainformationen verfügbar sind) ohne Prüfung der Gültigkeit des neuen Werts bezüglich des Knotentyps eingefügt.  
  
 Im folgenden Beispiel werden alle <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Elemente in der Datei `price` mit der `contosoBooks.xml`-Methode aktualisiert.  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="modifying-typed-values"></a>Ändern von typisierten Werten  
 Wenn der Typ ein einfacher W3C-XML-Schematyp ist, wird der neue mit der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode eingefügte Wert anhand aller Facets des einfachen Typs überprüft, bevor er festgelegt wird. Wenn der neue Wert bezüglich des Knotentyps nicht gültig ist (z. B. der Wert `-1` für ein Element vom Typ `xs:positiveInteger`), wird eine Ausnahme ausgelöst.  
  
 Im folgenden Beispiel wird versucht, den Wert des `price`-Elements des ersten `book`-Elements der Datei `contosoBooks.xml` in einen <xref:System.DateTime>-Wert zu ändern. Da der XML-Schematyp des `price`-Elements in den `xs:decimal`-Dateien als `contosoBooks.xsd` definiert ist, führt dies zu einer Ausnahme.  
  
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
  
 In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 In diesem Beispiel wird auch `contosoBooks.xsd` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
#### <a name="the-effects-of-editing-strongly-typed-xml-data"></a>Die Auswirkungen der Änderung von stark typisierten XML-Daten  
 Die <xref:System.Xml.XPath.XPathNavigator>-Klasse verwendet das W3C-XML-Schema als Grundlage für die Beschreibung von stark typisiertem XML. Zu Elementen und Attributen können auf der Grundlage der Validierung mit einem W3C-XML-Schemadokument Typinformationen angemerkt werden. Elemente, die andere Elemente oder Attribute enthalten können, werden als komplexe Typen bezeichnet. Elemente, die nur Inhalt in Form von Text enthalten können, werden als einfache Typen bezeichnet.  
  
> [!NOTE]
> Attribute können nur einfache Typen haben.  
  
 Ein Element oder Attribut kann als Schema-gültig betrachtet werden, wenn es alle spezifischen Regeln der Typdefinition genügt. Ein Element mit dem einfachen Typ `xs:int` ist nur dann gültig, wenn es einen numerischen Wert zwischen -2147483648 und 2147483647 enthält. Bei komplexen Typen hängt die Schema-Gültigkeit der Elemente von der Schema-Gültigkeit der untergeordneten Elemente und Attribute ab. Wenn ein Element bezüglich einer komplexen Typdefinition gültig ist, dann sind auch alle untergeordneten Elemente und Attribute bezüglich deren Definitionen gültig. Wenn auch nur ein einziges untergeordnetes Element oder Attribut bezüglich seiner Typdefinition ungültig ist oder wenn die Gültigkeit nicht bekannt ist, ist das Element entweder ungültig, oder die Gültigkeit ist unbekannt.  
  
 Da die Gültigkeit eines Elements von der Gültigkeit seiner untergeordneten Elemente und Attribute abhängt, führen Änderungen dazu, dass sich die Gültigkeit des Elements ändert, wenn es vorher gültig war. Insbesondere wird die Gültigkeit eines Elements unbekannt, wenn untergeordnete Elemente oder Attribute des Elements eingefügt, aktualisiert oder gelöscht werden. Dies wird durch Festlegen der <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>-Eigenschaft des Elements auf <xref:System.Xml.Schema.XmlSchemaValidity.NotKnown> dargestellt. Darüber hinaus setzt sich diese Auswirkung rekursiv aufwärts innerhalb des XML-Dokuments fort, da die Gültigkeit des übergeordneten Elements (und des diesem Element übergeordneten Elements usw.) eines Elements ebenfalls unbekannt wird.  
  
 Weitere Informationen über Schemavalidierung und die <xref:System.Xml.XPath.XPathNavigator>-Klasse finden Sie unter [Schemaüberprüfung mit XPathNavigator](schema-validation-using-xpathnavigator.md).  
  
### <a name="modifying-attributes"></a>Ändern von Attributen  
 Mit der <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode und der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode können nicht typisierte und typisierte Attributknoten sowie die anderen im Abschnitt "Ändern von Knoten" aufgeführten Knotentypen geändert werden.  
  
 Im fogenden Beispiel wird der Wert des `genre`-Attributs des ersten `book`-Elements der Datei `books.xml` geändert.  
  
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
  
 Weitere Informationen über die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode finden Sie in den Abschnitten "Ändern von nicht typisierten Werten" und "Ändern von typisierten Werten".  
  
## <a name="innerxml-and-outerxml-properties"></a>Die Eigenschaften "InnerXml" und "OuterXml"  
 Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse ändern das XML-Markup der Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist.  
  
 Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft ändert das XML-Markup der untergeordneten Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, mit den analysierten Inhalten des angegebenen XML-`string`. Ebenso ändert die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft das XML-Markup der untergeordneten Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, sowie den aktuellen Knoten selbst.  
  
 Im folgenden Beispiel wird mit der <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft der Wert des `price`-Elements geändert und in das erste `discount`-Element der Datei `book` ein neues `contosoBooks.xml`-Attribut eingefügt.  
  
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
  
 In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
## <a name="modifying-namespace-nodes"></a>Ändern von Namespaceknoten  
 Im DOM (Document Object Model) werden Namespacedeklarationen wie normale Attribute behandelt, die eingefügt, aktualisiert und gelöscht werden können. Die <xref:System.Xml.XPath.XPathNavigator>-Klasse lässt derartige Operationen auf Namespaceknoten nicht zu, da eine Änderung des Werts eines Namespaceknotens die Identität der Elemente innerhalb des Gültigkeitsbereichs des Namespaceknotens ändern kann. Dies wird im folgenden Beispiel veranschaulicht.  
  
```xml  
<root xmlns="http://www.contoso.com">  
    <child />  
</root>  
```  
  
 Wenn das obige XML-Beispiel wie folgt geändert wird, wird dadurch jedes Element des Dokuments umbenannt, da sich der Wert des Namespace-URI aller Elemente ändert.  
  
```xml  
<root xmlns="urn:contoso.com">  
    <child />  
</root>  
```  
  
 Die <xref:System.Xml.XPath.XPathNavigator>-Klasse lässt das Einfügen von Namespaceknoten zu, wenn kein Konflikt innerhalb des Gültigkeitsbereichs, in den sie eingefügt werden, besteht. In diesem Fall befinden sich die Namespacedeklarationen nicht in niedrigeren Gültigkeitsbereichen des XML-Dokuments und führen daher nicht zu einer Umbenennung. Dies wird im folgenden Beispiel veranschaulicht.  
  
```xml  
<root xmlns:a="http://www.contoso.com">  
    <parent>  
        <a:child />  
    </parent>  
</root>  
```  
  
 Wenn das obige XML-Beispiel wie folgt geändert wird, werden die Namespacedeklarationen richtig innerhalb des XML-Dokuments unterhalb des Gültigkeitsbereichs der anderen Namespacedeklaration weitergegeben.  
  
```xml  
<root xmlns:a="http://www.contoso.com">  
    <parent a:parent-id="1234" xmlns:a="http://www.contoso.com/parent-id">  
        <a:child xmlns:a="http://www.contoso.com/" />  
    </parent>  
</root>  
```  
  
 Im obigen XML-Beispiel wird das Attribut `a:parent-id` im `parent`-Element im `http://www.contoso.com/parent-id`-Namespace eingefügt. Die <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>-Methode wird zum Einfügen des Attributs bei Positionierung auf dem `parent`-Element verwendet. Die `http://www.contoso.com`-Namespacedeklaration wird von der <xref:System.Xml.XPath.XPathNavigator>-Klasse automatisch eingefügt, damit die Konsistenz mit dem restlichen XML-Dokument erhalten bleibt.  
  
## <a name="modifying-entity-reference-nodes"></a>Ändern von Entitätsverweisknoten  
 Entitätsverweisknoten in einem <xref:System.Xml.XmlDocument>-Objekt sind schreibgeschützt und können weder mit der <xref:System.Xml.XPath.XPathNavigator>-Klasse noch mit der <xref:System.Xml.XmlNode>-Klasse geändert werden. Ein Versuch, einen Entitätsverweisknoten zu ändern, führt zu einer <xref:System.InvalidOperationException>.  
  
## <a name="modifying-xsinil-nodes"></a>Ändern von xsi:nil-Knoten  
 Die XML-Schemaempfehlung des W3C führt das Konzept des "nillable"-Elements ein. Wenn ein Element "nillable" ist, kann das Element gültig sein, ohne einen Inhalt zu haben. Das Konzept eines "nillable"-Elements entspricht dem Konzept eines Objekts, das `null` ist. Das Hauptunterschied besteht darin, dass auf ein `null`-Objekt keinerlei Zugriff möglich ist, während ein `xsi:nil`-Element zwar keinen Inhalt (untergeordnete Elemente oder Text) hat, aber Eigenschaften (z. B. Attribute) aufweist, auf die zugegriffen werden kann. Wenn ein Element eines XML-Dokuments ein `xsi:nil`-Attribut mit dem Wert `true` hat, bedeutet dies, dass das Element keinen Inhalt hat.  
  
 Wenn einem gültigen Element, dessen <xref:System.Xml.XPath.XPathNavigator>-Attribut den Wert `xsi:nil` hat, mittels eines `true`-Objekts Inhalt hinzugefügt wird, wird der Wert des `xsi:nil`-Attributs auf `false` festgelegt.  
  
> [!NOTE]
> Wenn der Inhalt eines Elements, dessen `xsi:nil`-Attribut den Wert `false` hat, gelöscht wird, wird der Wert des Attributs nicht auf `true` geändert.  
  
## <a name="saving-an-xml-document"></a>Speichern eines XML-Dokuments  
 Änderungen eines <xref:System.Xml.XmlDocument>-Objekts, die von den in diesem Thema beschriebenen Bearbeitungsmethoden vorgenommen wurden, werden mit den Methoden der <xref:System.Xml.XmlDocument>-Klasse gespeichert. Weitere Informationen zum Speichern der an einem <xref:System.Xml.XmlDocument>-Objekt vorgenommenen Änderungen finden Sie unter [Speichern und Ausgeben eines Dokuments](saving-and-writing-a-document.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](process-xml-data-using-the-xpath-data-model.md)
- [Einfügen von XML-Daten mit XPathNavigator](insert-xml-data-using-xpathnavigator.md)
- [Entfernen von XML-Daten mit XPathNavigator](remove-xml-data-using-xpathnavigator.md)
