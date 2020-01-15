---
title: Pushbasierte Validierung mit „XmlSchemaValidator“
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 911d4460-dd91-4958-85b2-2ca3299f9ec6
ms.openlocfilehash: 6a0cc110c2b8bcd97b9f5c16a344db5a63046353
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709802"
---
# <a name="xmlschemavalidator-push-based-validation"></a>Pushbasierte Validierung mit „XmlSchemaValidator“

Die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse stellt eine effiziente leistungsstarke Methode zum Validieren von XML-Daten anhand von XML-Schemata in einem Push-Verfahren bereit. Zum Beispiel ermöglicht Ihnen die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse das direkte Validieren eines XML-Infosets, ohne es als XML-Dokument serialisieren zu müssen, und das anschließende erneute Analysieren des XML-Infosets mithilfe eines validierenden XML-Readers.

Die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse kann in erweiterten Szenarios verwendet werden, z. B. beim Erstellen von Validierungs-Engines für benutzerdefinierte XML-Datenquellen oder als eine Möglichkeit zum Erstellen eines validierenden XML-Writers.

Im folgenden Beispiel wird mithilfe der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse die `contosoBooks.xml`-Datei anhand des `contosoBooks.xsd`-Schemas validiert. Im Beispiel wird mit der <xref:System.Xml.Serialization.XmlSerializer>-Klasse die `contosoBooks.xml`-Datei deserialisiert, und der Wert der Knoten wird an die Methoden der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse übergeben.

> [!NOTE]
> Dieses Beispiel wird in allen Abschnitten dieses Themas verwendet.

[!code-csharp[XmlSchemaValidatorExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaValidatorExamples/CS/XmlSchemaValidatorExamples.cs#1)]
[!code-vb[XmlSchemaValidatorExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaValidatorExamples/VB/XmlSchemaValidatorExamples.vb#1)]

In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.

[!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]

In diesem Beispiel wird auch `contosoBooks.xsd` als Eingabe verwendet.

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" targetNamespace="http://www.contoso.com/books" xmlns:xs="http://www.w3.org/2001/XMLSchema">
    <xs:element name="bookstore">
        <xs:complexType>
            <xs:sequence>
                <xs:element maxOccurs="unbounded" name="book">
                    <xs:complexType>
                        <xs:sequence>
                            <xs:element name="title" type="xs:string" />
                            <xs:element name="author">
                                <xs:complexType>
                                    <xs:sequence>
                                        <xs:element minOccurs="0" name="name" type="xs:string" />
                                        <xs:element minOccurs="0" name="first-name" type="xs:string" />
                                        <xs:element minOccurs="0" name="last-name" type="xs:string" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="price" type="xs:decimal" />
                        </xs:sequence>
                        <xs:attribute name="genre" type="xs:string" use="required" />
                        <xs:attribute name="publicationdate" type="xs:date" use="required" />
                        <xs:attribute name="ISBN" type="xs:string" use="required" />
                    </xs:complexType>
                </xs:element>
            </xs:sequence>
        </xs:complexType>
    </xs:element>
</xs:schema>
```

## <a name="validating-xml-data-using-xmlschemavalidator"></a>Validieren von XML-Daten mithilfe von "XmlSchemaValidator"

Um die Validierung eines XML-Infosets zu starten, müssen Sie zuerst eine neue Instanz der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse mithilfe des <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>-Konstruktors initialisieren.

Der <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>-Konstruktor nimmt die Objekte <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet> und <xref:System.Xml.XmlNamespaceManager> sowie den <xref:System.Xml.Schema.XmlSchemaValidationFlags>-Wert als Parameter an. Mit dem <xref:System.Xml.XmlNameTable>-Objekt werden bekannte Namespacezeichenfolgen, z. B. der Schemanamespace, der XML-Namespace usw., atomisiert und während der Validierung von einfachem Inhalt an die <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A>-Methode übergeben. Das <xref:System.Xml.Schema.XmlSchemaSet>-Objekt enthält die XML-Schemata, mit denen die XML-Infosets validiert werden. Mit dem <xref:System.Xml.XmlNamespaceManager>-Objekt werden während der Validierung gefundene Namespaces aufgelöst. Mit dem <xref:System.Xml.Schema.XmlSchemaValidationFlags>-Wert werden bestimmte Validierungsfunktionen deaktiviert.

Weitere Informationen zum <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>-Konstruktor finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.

### <a name="initializing-validation"></a>Initialisieren der Validierung

Nach dem Erstellen eines <xref:System.Xml.Schema.XmlSchemaValidator>-Objekts wird mit zwei überladenen <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methoden der Zustand des <xref:System.Xml.Schema.XmlSchemaValidator>-Objekts initialisiert. Nachfolgend sind die zwei <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methoden dargestellt.

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

Die Standard-<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>-Methode initialisiert ein <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt mit dessen Anfangszustand, und die überladene <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>-Methode, die ein <xref:System.Xml.Schema.XmlSchemaObject> als Parameter annimmt, initialisiert ein <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt mit dessen Anfangszustand zur teilweisen Validierung.

Beide <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methoden können nur unmittelbar nach dem Erstellen eines <xref:System.Xml.Schema.XmlSchemaValidator>-Objekts oder nach einem Aufruf von <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A> aufgerufen werden.

Ein Beispiel für die <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>-Methode finden Sie im Beispiel in der Einleitung. Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.

#### <a name="partial-validation"></a>Teilweise Validierung

Die <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>-Methode, die ein <xref:System.Xml.Schema.XmlSchemaObject> als Parameter annimmt, initialisiert ein <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt mit dessen anfänglichem Zustand zur teilweisen Validierung.

Im folgenden Beispiel wird ein <xref:System.Xml.Schema.XmlSchemaObject> mithilfe der <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>-Methode zur teilweisen Validierung initialisiert. Das `orderNumber`-Schemaelement wird durch Auswählen des Schemaelements durch <xref:System.Xml.XmlQualifiedName> in der <xref:System.Xml.Schema.XmlSchemaObjectTable>-Auflistung übergeben, die von der <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A>-Eigenschaft des <xref:System.Xml.Schema.XmlSchemaSet>-Objekts zurückgegeben wurde. Das <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt validiert dann dieses bestimmte Element.

```vb
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
schemaSet.Compile()
Dim nameTable As NameTable = New NameTable()
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)

Dim validator As XmlSchemaValidator = New XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None)
validator.Initialize(schemaSet.GlobalElements.Item(New XmlQualifiedName("orderNumber")))

validator.ValidateElement("orderNumber", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateText("123")
validator.ValidateEndElement(Nothing)
```

```csharp
XmlSchemaSet schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
schemaSet.Compile();
NameTable nameTable = new NameTable();
XmlNamespaceManager manager = new XmlNamespaceManager(nameTable);

XmlSchemaValidator validator = new XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize(schemaSet.GlobalElements[new XmlQualifiedName("orderNumber")]);

validator.ValidateElement("orderNumber", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateText("123");
validator.ValidateEndElement(null);
```

In diesem Beispiel wird das folgende XML-Schema als Eingabe verwendet.

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="orderNumber" type="xs:int" />
</xs:schema>
```

Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.

### <a name="adding-additional-schemas"></a>Hinzufügen von zusätzlichen Schemata

Mit der <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>-Methode der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse wird der Gruppe von Schemata, die während der Validierung verwendet werden, ein XML-Schema hinzugefügt. Mit der <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>-Methode können die Auswirkungen des Findens eines XML-Inlineschemas in dem XML-Infoset simuliert werden, das validiert wird.

> [!NOTE]
> Der Zielnamespace des <xref:System.Xml.Schema.XmlSchema>-Parameters darf nicht mit dem Namespace eines der Elemente oder Attribute übereinstimmen, die bereits vom <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt gefunden wurden.
>
> Wenn der <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType>-Wert nicht als Parameter an den <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>-Konstruktor übergeben wurde, hat die <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>-Methode keine Auswirkungen.

Das Ergebnis der <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>-Methode hängt von dem aktuellen XML-Knotenkontext ab, der validiert wird. Weitere Informationen zu Validierungskontexten finden Sie in diesem Thema im Abschnitt „Validierungskontext“.

Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.

### <a name="validating-elements-attributes-and-content"></a>Validieren von Elementen, Attributen und Inhalt

Die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse stellt verschiedene Methoden zum Validieren von Elementen, Attributen und Inhalt in einem XML-Infoset anhand von XML-Schemata bereit. In der folgenden Tabelle werden diese Methoden beschrieben.

|-Methode|Beschreibung|
|------------|-----------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|Validiert den Elementnamen im aktuellen Kontext.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|Validiert das Attribut im aktuellen Elementkontext oder anhand des <xref:System.Xml.Schema.XmlSchemaAttribute>-Objekts, das als Parameter an die <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methode übergeben wurde.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|Überprüft, ob alle erforderlichen Attribute im Elementkontext vorhanden sind, und bereitet das <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt auf das Validieren des untergeordneten Inhalts des Elements vor.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|Validiert, ob Text im aktuellen Elementkontext zulässig ist, und sammelt den Text zum Validieren, ob das aktuelle Element einfachen Inhalt aufweist.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|Validiert, ob Leerraum im aktuellen Elementkontext zulässig ist, und sammelt den Leerraum zum Validieren, ob das aktuelle Element einfachen Inhalt aufweist.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|Überprüft, ob der Textinhalt des Elements gemäß des Datentyps für Elemente mit einfachem Inhalt gültig ist und ob der Inhalt des aktuellen Elements für Elemente mit komplexem Inhalt vollständig ist.|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|Überspringt die Validierung des aktuellen Elementinhalts und bereitet das <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt zum Validieren des Inhalts im Kontext des übergeordneten Elements vor.|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|Beendet die Validierung und überprüft Identitätseinschränkungen für das gesamte XML-Dokument, wenn die <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints>-Validierungsoption festgelegt ist.|

> [!NOTE]
> Die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse verfügt über einen definierten Zustandsübergang, der die Abfolge und das Vorkommen von Aufrufen der Methoden erzwingt, die in der vorherigen Tabelle beschrieben wurden. Der bestimmte Zustandsübergang der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse wird im Abschnitt "Zustandsübergang von "XmlSchemaValidator"" dieses Themas beschrieben.

Ein Beispiel für Methoden zum Validieren von Elementen, Attributen und Inhalt eines XML-Infosets finden Sie im Beispiel des vorherigen Abschnitts. Weitere Informationen zu diesen Methoden finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.

#### <a name="validating-content-using-an-xmlvaluegetter"></a>Validieren von Inhalt mithilfe von "XmlValueGetter"

Mit <xref:System.Xml.Schema.XmlValueGetter>`delegate` kann der Wert von Attribut-, Text- oder Leerzeichenknoten als CLR-Typ (Common Language Runtime) übergeben werden, der mit dem XSD-Typ (XML Schema Definition Language) des Attribut-, Text- oder Leerzeichenknotens kompatibel ist. <xref:System.Xml.Schema.XmlValueGetter>`delegate` ist hilfreich, wenn der CLR-Wert eines Attribut-, Text- oder Leerzeichenknotens bereits verfügbar ist, und erspart die Kosten für die Konvertierung in `string` und die anschließende erneute Analyse zur Validierung.

Die Methoden <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> und <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> sind überladen und akzeptieren den Wert der Attribut-, Text- oder Leerraumknoten als `string` oder <xref:System.Xml.Schema.XmlValueGetter>`delegate`.

Die folgenden Methoden der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse akzeptieren einen <xref:System.Xml.Schema.XmlValueGetter>`delegate` als Parameter.

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>

Im Folgenden wird ein Beispiel für <xref:System.Xml.Schema.XmlValueGetter>`delegate` aus dem Beispiel für die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse in der Einleitung dargestellt. <xref:System.Xml.Schema.XmlValueGetter>`delegate` gibt den Wert eines Attributs als <xref:System.DateTime>-Objekt zurück. Zum Validieren dieses von <xref:System.DateTime> zurückgegebenen <xref:System.Xml.Schema.XmlValueGetter>-Objekts wird es zunächst vom <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt in den ValueType (ValueType ist die Standard-CLR-Zuordnung für den XSD-Typ) des Datentyps des Attributs konvertiert und dann werden Facets des konvertierten Werts überprüft.

```vb
Shared dateTimeGetterContent As Object

Shared Function DateTimeGetterHandle() As Object
    Return dateTimeGetterContent
End Function

Shared Function DateTimeGetter(dateTime As DateTime) As XmlValueGetter
    dateTimeGetterContent = dateTime
    Return New XmlValueGetter(AddressOf DateTimeGetterHandle)
End Function
```

```csharp
static object dateTimeGetterContent;

static object DateTimeGetterHandle()
{
    return dateTimeGetterContent;
}

static XmlValueGetter DateTimeGetter(DateTime dateTime)
{
    dateTimeGetterContent = dateTime;
    return new XmlValueGetter(dateTimeGetterHandle);
}
```

Ein vollständiges Beispiel für <xref:System.Xml.Schema.XmlValueGetter>`delegate` finden Sie im Beispiel in der Einleitung. Weitere Informationen zum <xref:System.Xml.Schema.XmlValueGetter>`delegate` finden Sie in der Referenzdokumentation zur <xref:System.Xml.Schema.XmlValueGetter>-Klasse und zur <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.

#### <a name="post-schema-validation-information"></a>Informationen zur Post-Schema-Validation

Die <xref:System.Xml.Schema.XmlSchemaInfo>-Klasse stellt einige der Informationen zur Post-Schema-Validation eines XML-Knotens dar, der von der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse validiert wird. Verschiedene Methoden der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse akzeptieren ein <xref:System.Xml.Schema.XmlSchemaInfo>-Objekt als einen optionalen (`null`) `out`-Parameter.

Bei einer erfolgreichen Validierung werden Eigenschaften des <xref:System.Xml.Schema.XmlSchemaInfo>-Objekts auf die Ergebnisse der Validierung festgelegt. Bei der erfolgreichen Validierung eines Attributs mithilfe der <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>-Methode werden z. B. die Eigenschaften <xref:System.Xml.Schema.XmlSchemaInfo>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A> und <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A> des <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A>-Objekts, sofern angegeben, auf die Ergebnisse der Validierung festgelegt.

Die folgenden Methoden der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse akzeptieren ein <xref:System.Xml.Schema.XmlSchemaInfo>-Objekt als out-Parameter.

- <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>

Ein vollständiges Beispiel für die <xref:System.Xml.Schema.XmlSchemaInfo>-Klasse finden Sie im Beispiel in der Einleitung. Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaInfo>-Klasse finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaInfo>-Klasse.

### <a name="retrieving-expected-particles-attributes-and-unspecified-default-attributes"></a>Abrufen von erwarteten Partikeln, Attributen und nicht angegebenen Standardattributen

Die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse stellt die Methoden <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> und <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> zum Abrufen der erwarteten Partikel, Attribute und nicht angegebenen Standardattribute im aktuellen Validierungskontext bereit.

#### <a name="retrieving-expected-particles"></a>Abrufen von erwarteten Partikeln

Die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode gibt ein Array von <xref:System.Xml.Schema.XmlSchemaParticle>-Objekten mit den erwarteten Partikeln im aktuellen Elementkontext zurück. Die gültigen Partikel, die von der <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode zurückgegeben werden können, sind Instanzen der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse und der <xref:System.Xml.Schema.XmlSchemaAny>-Klasse.

Wenn der Compositor für das Inhaltsmodell eine `xs:sequence` ist, wird nur der nächste Partikel in der Abfolge zurückgegeben. Wenn der Compositor für das Inhaltsmodell `xs:all` oder `xs:choice` ist, werden alle gültigen Partikel zurückgegeben, die im aktuellen Elementkontext folgen können.

> [!NOTE]
> Wenn die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode unmittelbar nach dem Aufrufen der <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methode aufgerufen wird, gibt die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode alle globalen Elemente zurück.

Im folgenden XSD-Schema (XML Schema Definition Language) und XML-Dokument entspricht z. B. nach dem Validieren des `book`-Elements das `book`-Element dem aktuellen Elementkontext. Die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode gibt ein Array mit einem einzelnen <xref:System.Xml.Schema.XmlSchemaElement>-Objekt zurück, das das `title`-Element darstellt. Wenn der Validierungskontext dem `title`-Element entspricht, gibt die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode ein leeres Array zurück. Wenn die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode aufgerufen wird, nachdem das `title`-Element validiert wurde und bevor das `description`-Element validiert wurde, gibt sie ein Array mit einem einzelnen <xref:System.Xml.Schema.XmlSchemaElement>-Objekt zurück, das das `description`-Element darstellt. Wenn die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode aufgerufen wird, nachdem das `description`-Element validiert wurde, gibt sie ein Array mit einem einzelnen <xref:System.Xml.Schema.XmlSchemaAny>-Objekt zurück, das den Platzhalter darstellt.

```vb
Dim reader As XmlReader =  XmlReader.Create("input.xml")

Dim schemaSet As New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
Dim manager As New XmlNamespaceManager(reader.NameTable)

Dim validator As New XmlSchemaValidator(reader.NameTable,schemaSet,manager,XmlSchemaValidationFlags.None)
validator.Initialize()

validator.ValidateElement("book", "", Nothing)

validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("title", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next
validator.ValidateEndElement(Nothing)

For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("description", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

For Each particle As XmlSchemaParticle In validator.GetExpectedParticles()
    Console.WriteLine(particle.GetType())
Next

validator.ValidateElement("namespace", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

validator.ValidateEndElement(Nothing)
```

```csharp
XmlReader reader = XmlReader.Create("input.xml");

var schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
var manager = new XmlNamespaceManager(reader.NameTable);

var validator = new XmlSchemaValidator(reader.NameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize();

validator.ValidateElement("book", "", null);

validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("title", "", null);
validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}
validator.ValidateEndElement(null);

foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("description", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

foreach (XmlSchemaParticle particle in validator.GetExpectedParticles())
{
    Console.WriteLine(particle.GetType());
}

validator.ValidateElement("namespace", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

validator.ValidateEndElement(null);
```

 Im Beispiel wird der folgende XML-Code als Eingabe angenommen:

```xml
<xs:schema xmlns:xs="http://www.w3c.org/2001/XMLSchema">
  <xs:element name="book">
    <xs:sequence>
      <xs:element name="title" type="xs:string" />
      <xs:element name="description" type="xs:string" />
      <xs:any processContent="lax" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:element>
</xs:schema>
```

Im Beispiel wird das folgende XSD-Schema als Eingabe angenommen:

```xml
<book>
  <title>My Book</title>
  <description>My Book's Description</description>
  <namespace>System.Xml.Schema</namespace>
</book>
```

> [!NOTE]
> Die Ergebnisse der Methoden <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> und <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse hängen vom aktuellen Kontext ab, der validiert wird. Weitere Informationen finden Sie in diesem Thema im Abschnitt „Validierungskontext“.

Ein Beispiel für die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode finden Sie im Beispiel in der Einleitung. Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.

#### <a name="retrieving-expected-attributes"></a>Abrufen von erwarteten Attributen

Die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode gibt ein Array von <xref:System.Xml.Schema.XmlSchemaAttribute>-Objekten mit den erwarteten Attributen im aktuellen Elementkontext zurück.

Im Beispiel in der Einleitung werden mit der <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode alle Attribute des `book`-Elements abgerufen.

Wenn Sie die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode unmittelbar nach der <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>-Methode aufrufen, werden alle Attribute zurückgegeben, die im XML-Dokument vorhanden sein können. Wenn Sie jedoch die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode nach einem oder mehreren Aufrufen der <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>-Methode aufrufen, werden die Attribute zurückgegeben, die bisher noch nicht für das aktuelle Element validiert wurden.

> [!NOTE]
> Die Ergebnisse der Methoden <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> und <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse hängen vom aktuellen Kontext ab, der validiert wird. Weitere Informationen finden Sie in diesem Thema im Abschnitt „Validierungskontext“.

Ein Beispiel für die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode finden Sie im Beispiel in der Einleitung. Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.

#### <a name="retrieving-unspecified-default-attributes"></a>Abrufen von nicht angegebenen Standardattributen

Die <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>-Methode füllt die angegebene <xref:System.Collections.ArrayList> mit den <xref:System.Xml.Schema.XmlSchemaAttribute>-Objekten für alle Attribute mit Standardwerten, die noch nicht mithilfe der <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>-Methode im Elementkontext validiert wurden. Die <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>-Methode muss nach einem Aufruf der <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>-Methode für alle Attribute im Elementkontext aufgerufen werden. Mit der <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>-Methode muss bestimmt werden, welche Standardattribute in das XML-Dokument eingefügt werden sollen, das validiert wird.

Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.

### <a name="handling-schema-validation-events"></a>Behandeln von Schemavalidierungsereignissen

Schemavalidierungswarnungen und -fehler, die während der Validierung gefunden wurden, werden vom <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler>-Ereignis der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse behandelt.

Schemavalidierungswarnungen weisen einen <xref:System.Xml.Schema.XmlSeverityType>-Wert von <xref:System.Xml.Schema.XmlSeverityType.Warning> auf, und Schemavalidierungsfehler weisen einen <xref:System.Xml.Schema.XmlSeverityType>-Wert von <xref:System.Xml.Schema.XmlSeverityType.Error> auf. Wenn kein <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> zugewiesen wurde, wird eine <xref:System.Xml.Schema.XmlSchemaValidationException> für alle Schemavalidierungsfehler mit einem <xref:System.Xml.Schema.XmlSeverityType>-Wert von <xref:System.Xml.Schema.XmlSeverityType.Error> ausgelöst. Für Schemavalidierungswarnungen mit einem <xref:System.Xml.Schema.XmlSchemaValidationException>-Wert von <xref:System.Xml.Schema.XmlSeverityType> wird jedoch keine <xref:System.Xml.Schema.XmlSeverityType.Warning> ausgelöst.

Das folgende Beispiel für einen <xref:System.Xml.Schema.ValidationEventHandler>, der Schemavalidierungswarnungen und -fehler während der Schemavalidierung empfängt, stammt aus dem Beispiel in der Einleitung.

```vb
Shared Sub SchemaValidationEventHandler(sender As Object, e As ValidationEventArgs)

    Select Case e.Severity
        Case XmlSeverityType.Error
            Console.WriteLine(vbCrLf & "Error: {0}", e.Message)
            Exit Sub
        Case XmlSeverityType.Warning
            Console.WriteLine(vbCrLf & "Warning: {0}", e.Message)
            Exit Sub
    End Select
End Sub
```

```csharp
static void SchemaValidationEventHandler(object sender, ValidationEventArgs e)
{
    switch (e.Severity)
    {
        case XmlSeverityType.Error:
            Console.WriteLine("\nError: {0}", e.Message);
            break;
        case XmlSeverityType.Warning:
            Console.WriteLine("\nWarning: {0}", e.Message);
            break;
    }
}
```

Ein vollständiges Beispiel von <xref:System.Xml.Schema.ValidationEventHandler> finden Sie im Beispiel in der Einleitung. Weitere Informationen finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaInfo>-Klasse.

## <a name="xmlschemavalidator-state-transition"></a>Zustandsübergänge von "XmlSchemaValidator"

Die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse verfügt über einen definierten Zustandsübergang, der die Abfolge und das Vorkommen von Aufrufen der Methoden erzwingt, mit denen Elemente, Attribute und Inhalt in einem XML-Infoset validiert werden.

In der folgenden Tabelle werden die Zustandsübergänge der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse und die Abfolge und das Vorkommen von Methodenaufrufen erläutert, die in den einzelnen Zuständen auftreten können.

|Phase|Übergang|
|-----------|----------------|
|Überprüfen|<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|
|TopLevel|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element|
|Element|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>* (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Inhalt\*)? <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;<br /><br /> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;<br /><br /> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Inhalt\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>&#124;|
|Inhalt|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element|

> [!NOTE]
> Von den einzelnen Methoden in der Tabelle oben wird eine <xref:System.InvalidOperationException> ausgelöst, wenn der Aufruf der Methode gemäß des aktuellen Zustands eines <xref:System.Xml.Schema.XmlSchemaValidator>-Objekts in der falschen Abfolge ausgeführt wurde.

In der Tabelle der Zustandsübergänge oben werden Satzzeichen verwendet, um die Methoden und andere Zustände zu beschreiben, die für jeden Zustand des Zustandübergangs der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse aufgerufen werden können. Die verwendeten Symbole entsprechen den Symbolen der XML-Richtlinien für DTD (Document Type Definition).

In der folgenden Tabelle wird beschrieben, welche Auswirkungen die Satzzeichen in der Tabelle der Zustandsübergänge oben auf die Methoden und andere Zustände haben, die für jeden Zustand im Zustandsübergang der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse aufgerufen werden können.

|Symbol|Beschreibung|
|------------|-----------------|
|&#124;|Entweder die Methode bzw. der Zustand vor oder die Methode bzw. der Zustand nach dem senkrechten Strich, kann aufgerufen werden.|
|?|Die Methode oder der Zustand nach dem Fragezeichen ist optional, es kann jedoch nur ein Aufruf der Methode bzw. des Zustands erfolgen.|
|*|Die Methode bzw. der Zustand nach dem Zeichen "*" ist optional und kann mehr als einmal aufgerufen werden.|

## <a name="validation-context"></a>Validierungskontext

Die Methoden der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse, mit denen Elemente, Attribute und Inhalt in einem XML-Infoset validiert werden, ändern den Validierungskontext eines <xref:System.Xml.Schema.XmlSchemaValidator>-Objekts. Die <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>-Methode überspringt die Validierung des aktuellen Elementinhalts und bereitet das <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt zum Validieren des Inhalts im Kontext des übergeordneten Elements vor. Dies entspricht dem Überspringen der Validierung aller untergeordneten Elemente des aktuellen Elements und dem anschließenden Aufrufen der <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>-Methode.

Die Ergebnisse der Methoden <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> und <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse hängen vom aktuellen Kontext ab, der validiert wird.

In der folgenden Tabelle werden die Ergebnisse der Aufrufe dieser Methoden nach dem Aufrufen einer der Methoden der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse erläutert, mit der Elemente, Attribute und Inhalt in einem XML-Infoset validiert werden.

|-Methode|GetExpectedParticles|GetExpectedAttributes|AddSchema|
|------------|--------------------------|---------------------------|---------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>|Wenn die <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Standardmethode aufgerufen wird, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> ein Array mit allen globalen Elementen zurück.<br /><br /> Wenn die überladene <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methode, die ein <xref:System.Xml.Schema.XmlSchemaObject> als Parameter annimmt, zum Initialisieren der teilweisen Validierung eines Elements aufgerufen wird, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> nur das Element zurück, mit dem das <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt initialisiert wurde.|Wenn die <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Standardmethode aufgerufen wird, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> ein leeres Array zurück.<br /><br /> Wenn die Überladung der <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methode, die ein <xref:System.Xml.Schema.XmlSchemaObject> als Parameter annimmt, zum Initialisieren der teilweisen Validierung eines Attributs aufgerufen wird, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> nur das Attribut zurück, mit dem das <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt initialisiert wurde.|Fügt dem <xref:System.Xml.Schema.XmlSchemaSet> des <xref:System.Xml.Schema.XmlSchemaValidator>-Objekts das Schema hinzu, wenn es keine Vorverarbeitungsfehler aufweist.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|Wenn das Kontextelement gültig ist, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> die Abfolge der Elemente zurück, die als untergeordnete Elemente des Kontextelements erwartet werden.<br /><br /> Wenn das Kontextelement ungültig ist, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> ein leeres Array zurück.|Wenn das Kontextelement gültig ist und <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> bisher nicht aufgerufen wurde, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> eine Liste aller im Kontextelement definierten Attribute zurück.<br /><br /> Wenn einige Attribute bereits validiert wurden, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> eine Liste der noch zu validierenden Attribute zurück.<br /><br /> Wenn das Kontextelement ungültig ist, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> ein leeres Array zurück.|Siehe oben.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|Wenn sich das Kontextattribut auf der obersten Ebene befindet, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> ein leeres Array zurück.<br /><br /> Andernfalls gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> die Abfolge der Elemente zurück, die als das erste untergeordnete Element des Kontextelements erwartet werden.|Wenn sich das Kontextattribut auf der obersten Ebene befindet, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> ein leeres Array zurück.<br /><br /> Andernfalls gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> die Liste der noch zu validierenden Attribute zurück.|Siehe oben.|
|<xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> gibt die Abfolge der Elemente zurück, die als das erste untergeordnete Element des Kontextelements erwartet werden.|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> gibt eine Liste der erforderlichen und optionalen Attribute zurück, die noch für das Kontextelement validiert werden müssen.|Siehe oben.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> gibt die Abfolge der Elemente zurück, die als das erste untergeordnete Element des Kontextelements erwartet werden.|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> gibt ein leeres Array zurück.|Siehe oben.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|Wenn <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> contentType des Kontextelements Mixed ist, gibt die Abfolge der Elemente zurück, die auf der nächsten Position erwartet werden.<br /><br /> Wenn contentType des Kontextelements TextOnly oder Empty ist, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> ein leeres Array zurück.<br /><br /> Wenn contentType des Kontextelements ElementOnly ist, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> die Abfolge der Elemente zurück, die auf der nächsten Position erwartet werden. Es ist jedoch bereits ein Validierungsfehler aufgetreten.|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> gibt die Liste der nicht validierten Attribute des Kontextelements zurück.|Siehe oben.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|Wenn sich der Kontextleerraum auf der obersten Ebene befindet, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> ein leeres Array zurück.<br /><br /> Andernfalls entspricht das Verhalten der <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode dem von <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.|Wenn sich der Kontextleerraum auf der obersten Ebene befindet, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> ein leeres Array zurück.<br /><br /> Andernfalls entspricht das Verhalten der <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode dem von <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.|Siehe oben.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> gibt die Abfolge der Elemente zurück, die nach dem Kontextelement erwartet werden (möglicherweise nebengeordnete Elemente).|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> gibt die Liste der nicht validierten Attribute des Kontextelements zurück.<br /><br /> Wenn das Kontextelement kein übergeordnetes Element aufweist, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> eine leere Liste zurück. (Das Kontextelement ist das übergeordnete Element des aktuellen Elements, für das <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> aufgerufen wurde.)|Siehe oben.|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|Wie in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.|Wie in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.|Siehe oben.|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|Gibt ein leeres Array zurück.|Gibt ein leeres Array zurück.|Siehe oben.|

> [!NOTE]
> Die von den verschiedenen Eigenschaften der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse zurückgegebenen Werte werden nicht durch das Aufrufen einer der Methoden in der oben stehenden Tabelle verändert.

## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Schema.XmlSchemaValidator>
