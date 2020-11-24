---
title: Zugreifen auf streng typisierte XML-Daten mit 'XPathNavigator'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 898e0f52-8a7c-4d1f-afcd-6ffb28b050b4
ms.openlocfilehash: fcf46a0716d79fd27cb06924bf74c119b8435147
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822827"
---
# <a name="accessing-strongly-typed-xml-data-using-xpathnavigator"></a>Zugreifen auf streng typisierte XML-Daten mit 'XPathNavigator'
Als Instanz des XPath 2.0-Datenmodells kann die <xref:System.Xml.XPath.XPathNavigator>-Klasse stark typisierte Daten enthalten, die den CLR-Typen (Common Language Runtime) zugeordnet werden. Gemäß des XPath 2.0-Datenmodells können nur Elemente und Attribute stark typisierte Daten enthalten. Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt Mechanismen zum Zugreifen auf Daten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt als stark typisierte Daten sowie Mechanismen zum Konvertieren von einem Datentyp in einen anderen bereit.  
  
## <a name="type-information-exposed-by-xpathnavigator"></a>Von XPathNavigator verfügbar gemachte Typinformationen  
 XML 1.0-Daten weisen im Allgemeinen keinen Typ auf, es sei denn, sie wurden mit einer DTD, einem XSD-Schema (XML Schema Definition Language) oder anderen Mechanismen verarbeitet. Es gibt verschiedene Kategorien von Typinformationen, die einem XML-Element oder XML-Attribut zugeordnet werden können.  
  
- Einfache CLR-Typen: Keine der XML-Schemasprachen unterstützt CLR-Typen (Common Language Runtime) direkt. Da das Anzeigen des Inhalts von einfachen Elementen und Attributen im am besten geeigneten CLR-Typ hilfreich ist, können alle einfachen Inhalte als <xref:System.String> mit allen hinzugefügten Schemainformationen typisiert werden, die den Inhalt möglicherweise einem besser geeigneten Typ anpassen, ohne dass Schemainformationen vorhanden sind. Mithilfe der <xref:System.Xml.XPath.XPathNavigator.ValueType%2A>-Eigenschaft können Sie den am besten geeigneten CLR-Typ des Inhalts von einfachen Elementen und Attributen ermitteln. Weitere Informationen zum Zuordnen von integrierten Schematypen zu CLR-Typen finden Sie unter [Typenunterstützung in den System.Xml-Klassen](type-support-in-the-system-xml-classes.md).  
  
- Liste der einfachen (CLR-)Typen: Ein Element oder Attribut mit einfachem Inhalt kann eine Liste mit Werten enthalten, die durch ein Leerzeichen voneinander getrennt sind. Die Werte werden von einem XML-Schema als ein "list type" angegeben. Wenn kein XML-Schema vorhanden ist, wird einfacher Inhalt als ein einzelner Textknoten behandelt. Wenn ein XML-Schema verfügbar ist, kann dieser einfache Inhalt als eine Serie von atomaren Werten verfügbar gemacht werden, die alle einen einfachen Typ aufweisen, der einer Auflistung von CLR-Objekten zugeordnet ist. Weitere Informationen zum Zuordnen von integrierten Schematypen zu CLR-Typen finden Sie unter [Typenunterstützung in den System.Xml-Klassen](type-support-in-the-system-xml-classes.md).  
  
- Typisierter Wert: Ein für ein Schema validiertes Attribut oder Element mit einem einfachen Typ weist einen typisierten Wert auf. Dieser Wert ist ein primitiver Typ, z. B. ein numerischer Typ, ein Zeichenfolgentyp oder ein Datentyp. Alle integrierten einfachen Typen in XSD können CLR-Typen zugeordnet werden, die Zugriff auf den Wert eines Knotens als einen besser geeigneten Typ anstatt nur als einen <xref:System.String> bereitstellen. Ein Element mit Attributen oder untergeordneten Elementen wird als komplexer Typ betrachtet. Der typisierte Wert eines komplexen Typs mit einfachem Inhalt (nur Textknoten als untergeordnete Elemente) ist der gleiche wie der Wert des einfachen Typs dieses Inhalts. Der typisierte Wert eines komplexen Typs mit komplexem Inhalt (ein oder mehr untergeordnete Elemente) ist der Zeichenfolgenwert der Verkettung aller untergeordneten Textknoten, die als ein <xref:System.String> zurückgegeben werden. Weitere Informationen zum Zuordnen von integrierten Schematypen zu CLR-Typen finden Sie unter [Typenunterstützung in den System.Xml-Klassen](type-support-in-the-system-xml-classes.md).  
  
- Schemasprachenspezifischer Typname: In den meisten Fällen werden die CLR-Typen, die als Nebeneffekt beim Übernehmen eines externen Schemas festgelegt werden, zum Bereitstellen des Zugriffs auf den Wert eines Knotens verwendet. In manchen Situationen ist es jedoch empfehlenswert, den Typ zu überprüfen, der einem bestimmten auf ein XML-Dokument angewendeten Schema zugeordnet ist. Zum Beispiel möchten Sie möglicherweise ein XML-Dokument durchsuchen und dabei alle Elemente extrahieren, die Inhalt vom Typ "PurchaseOrder" gemäß eines zugewiesenen Schemas aufweisen. Diese Typinformationen können nur durch Schemavalidierung festgelegt werden. Auf diese Informationen wird über die <xref:System.Xml.XPath.XPathNavigator.XmlType%2A>-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse zugegriffen. Weitere Informationen finden Sie im Abschnitt „Das Post-Schema-Validation-Infoset (PSVI)“ weiter unten.  
  
- Schemasprachenspezifische Typreflektion: In anderen Fällen sollten Sie nähere Informationen zum schemaspezifischen Typ abrufen, der auf ein XML-Dokument angewendet wird. Zum Beispiel möchten Sie eventuell beim Lesen einer XML-Datei die `maxOccurs`-Attribute aller gültigen Knoten im XML-Dokument extrahieren, um eine benutzerdefinierte Berechnung durchzuführen. Da diese Informationen nur durch Schemavalidierung festgelegt wird, wird darauf über die <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse zugegriffen. Weitere Informationen finden Sie im Abschnitt „Das Post-Schema-Validation-Infoset (PSVI)“ weiter unten.  
  
## <a name="xpathnavigator-typed-accessors"></a>Mit "XPathNavigator" typisierte Accessoren  
 Die folgenden Tabelle enthält die verschiedenen Eigenschaften und Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse, mit denen auf die Typinformationen eines Knotens zugegriffen werden kann.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.XmlType%2A>|Dieses Objekt enthält die XML-Schematypinformationen des Knotens, sofern dieser gültig ist.|  
|<xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>|Dieses Objekt enthält das Post-Schema-Validation-Infoset des Knotens, der nach der Validierung hinzugefügt wird. Darin sind die XML-Schematypinformationen sowie die Gültigkeitsinformationen eingeschlossen.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueType%2A>|Der CLR-Typ des typisierten Werts des Knotens.|  
|<xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>|Der Inhalt des Knotens als mindestens ein CLR-Wert, dessen Typ am ehesten dem XML-Schematyp des Knotens entspricht.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsBoolean%2A>|Der <xref:System.String>-Wert des aktuellen Knotens, gemäß der Umwandlungsregeln für XPath 2.0 für <xref:System.Boolean> in einen `xs:boolean`-Wert umgewandelt.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDateTime%2A>|Der <xref:System.String>-Wert des aktuellen Knotens, gemäß der Umwandlungsregeln für XPath 2.0 für <xref:System.DateTime> in einen `xs:datetime`-Wert umgewandelt.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>|Der <xref:System.String>-Wert des aktuellen Knotens, gemäß der Umwandlungsregeln für XPath 2.0 für <xref:System.Double> in einen `xsd:double`-Wert umgewandelt.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A>|Der <xref:System.String>-Wert des aktuellen Knotens, gemäß der Umwandlungsregeln für XPath 2.0 für <xref:System.Int32> in einen `xs:integer`-Wert umgewandelt.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A>|Der <xref:System.String>-Wert des aktuellen Knotens, gemäß der Umwandlungsregeln für XPath 2.0 für <xref:System.Int64> in einen `xs:integer`-Wert umgewandelt.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAs%2A>|Der Inhalt des Knotens, gemäß der Umwandlungsregeln für XPath 2.0 in den Zieltyp umgewandelt.|  
  
 Weitere Informationen zum Zuordnen von integrierten Schematypen zu CLR-Typen finden Sie unter [Typenunterstützung in den System.Xml-Klassen](type-support-in-the-system-xml-classes.md).  
  
## <a name="the-post-schema-validation-infoset-psvi"></a>Das Post-Schema-Validation-Infoset (PSVI)  
 Ein XML-Schemaprozessor akzeptiert ein XML-Infoset als Eingabe und konvertiert es in ein Post-Schema-Validation-Infoset (PSVI). Ein PSVI stellt das ursprüngliche Eingabe-XML-Infoset dar, dem neue Informationselemente hinzugefügt wurden. Vorhandenen Informationselementen wurden neue Eigenschaften hinzugefügt. Es gibt drei komplexe Klassen von Informationen, die dem XML-Infoset im PSVI hinzugefügt wurden und vom <xref:System.Xml.XPath.XPathNavigator> verfügbar gemacht werden.  
  
1. Validierungsergebnisse: Informationen dazu, ob ein Element oder ein Attribut erfolgreich validiert wurde. Diese werden von der <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse verfügbar gemacht.  
  
2. Standardinformationen: Angaben dazu, ob der Wert des Elements oder des Attributs über im Schema angegebene Standardwerte abgerufen wurde. Diese werden von der <xref:System.Xml.Schema.IXmlSchemaInfo.IsDefault%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse verfügbar gemacht.  
  
3. Typanmerkungen: Verweise auf Schemakomponenten, die möglicherweise Typdefinitionen oder Element- und Attributdeklarationen sind. Die <xref:System.Xml.XPath.XPathNavigator.XmlType%2A>-Eigenschaft von <xref:System.Xml.XPath.XPathNavigator> enthält die bestimmten Typinformationen des Knotens, sofern dieser gültig ist. Wenn die Gültigkeit eines Knotens unbekannt ist, das heißt, er wurde überprüft und anschließend bearbeitet. dann wird die <xref:System.Xml.XPath.XPathNavigator.XmlType%2A>-Eigenschaft auf `null` festgelegt, wobei die Typinformationen jedoch weiterhin in den verschiedenen Eigenschaften der <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse verfügbar sind.  
  
 Im folgenden Beispiel wird das Verwenden der Informationen im Post-Schema-Validation-Infoset veranschaulicht, die von <xref:System.Xml.XPath.XPathNavigator> verfügbar gemacht wurden.  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("books.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("published", "http://www.contoso.com/books")  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name)  
Console.WriteLine(navigator.SchemaInfo.Validity)  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("books.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("published", "http://www.contoso.com/books");  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name);  
Console.WriteLine(navigator.SchemaInfo.Validity);  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs);  
```  
  
 In diesem Beispiel wird die Datei `books.xml` als Eingabe verwendet.  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 In diesem Beispiel wird auch das `books.xsd`-Schema als Eingabe verwendet.  
  
```xml  
<xs:schema xmlns="http://www.contoso.com/books"
attributeFormDefault="unqualified" elementFormDefault="qualified"
targetNamespace="http://www.contoso.com/books"
xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:simpleType name="publishedType">  
        <xs:restriction base="xs:date">  
            <xs:minInclusive value="2003-01-01" />  
            <xs:maxInclusive value="2003-12-31" />  
        </xs:restriction>  
    </xs:simpleType>  
    <xs:complexType name="bookType">  
        <xs:sequence>  
            <xs:element name="title" type="xs:string"/>  
            <xs:element name="price" type="xs:decimal"/>  
            <xs:element name="published" type="publishedType"/>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="booksType">  
        <xs:sequence>  
            <xs:element name="book" type="bookType" />  
        </xs:sequence>  
    </xs:complexType>  
    <xs:element name="books" type="booksType" />  
</xs:schema>  
```  
  
## <a name="obtain-typed-values-using-valueas-properties"></a>Abrufen von typisierten Werten mithilfe von ValueAs-Eigenschaften  
 Der typisierte Wert eines Knotens kann durch Zugreifen auf die <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>-Eigenschaft von <xref:System.Xml.XPath.XPathNavigator> abgerufen werden. In bestimmten Fällen soll der typisierte Wert eines Knotens möglicherweise in einen anderen Typ konvertiert werden. Ein häufig verwendetes Beispiel ist das Abrufen eines numerischen Werts aus einem XML-Knoten. Betrachten Sie z. B. das folgende nicht validierte und nicht typisierte XML-Dokument.  
  
```xml  
<books>  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 Wenn <xref:System.Xml.XPath.XPathNavigator> auf dem `price`-Element positioniert wird, ist die <xref:System.Xml.XPath.XPathNavigator.XmlType%2A>-Eigenschaft `null`, die <xref:System.Xml.XPath.XPathNavigator.ValueType%2A>-Eigenschaft ist <xref:System.String> und die <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>-Eigenschaft entspricht der Zeichenfolge `10.00`.  
  
 Es ist jedoch trotzdem möglich, den Wert mithilfe der Methoden und Eigenschaften <xref:System.Xml.XPath.XPathItem.ValueAs%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A> und <xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A> als einen numerischen Wert zu extrahieren. Im folgenden Beispiel wird das Durchführen einer solchen Umwandlung mithilfe der <xref:System.Xml.XPath.XPathItem.ValueAs%2A>-Methode veranschaulicht.  
  
```vb  
Dim document As New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "")  
navigator.MoveToChild("book", "")  
navigator.MoveToChild("price", "")  
  
Dim price = navigator.ValueAs(GetType(Decimal))  
Dim discount As Decimal = 0.2  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * discount))  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "");  
navigator.MoveToChild("book", "");  
navigator.MoveToChild("price", "");  
  
Decimal price = (decimal)navigator.ValueAs(typeof(decimal));  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * (decimal)0.20));  
```  
  
 Weitere Informationen zum Zuordnen von integrierten Schematypen zu CLR-Typen finden Sie unter [Typenunterstützung in den System.Xml-Klassen](type-support-in-the-system-xml-classes.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Type Support in the System.Xml Classes (Typenunterstützung in den System.Xml-Klassen)](type-support-in-the-system-xml-classes.md)
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](process-xml-data-using-the-xpath-data-model.md)
- [Navigieren in Knotengruppen mit XPathNavigator](node-set-navigation-using-xpathnavigator.md)
- [Das Navigieren durch Attribut- und Namespaceknoten mit XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [Extrahieren von XML-Daten mit XPathNavigator](extract-xml-data-using-xpathnavigator.md)
