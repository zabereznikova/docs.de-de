---
title: Validieren eines XML-Dokuments im Dokumentobjektmodell
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 2c61c920-d0f8-4c72-bfcc-6524570f3060
ms.openlocfilehash: 93686ddf1afff76926e77acdbf5aa58e93d6cb77
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710036"
---
# <a name="validating-an-xml-document-in-the-dom"></a>Validieren eines XML-Dokuments im Dokumentobjektmodell

Die Klasse <xref:System.Xml.XmlDocument> validiert das XML-Dokument im DOM (Dokumentobjektmodell) standardmäßig nicht anhand eines XSD-Schemas (XML Schema Definition Language) oder einer DTD (Document Type Definition). Das XML-Dokument wird nur validiert, damit es wohlgeformt ist.

Wenn Sie das XML-Dokument im DOM validieren möchten, können Sie es beim Laden in das DOM validieren, indem Sie einen schemavalidierenden <xref:System.Xml.XmlReader> an die <xref:System.Xml.XmlDocument.Load%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse übergeben, oder Sie validieren ein zuvor nicht validiertes XML-Dokument im DOM mithilfe der <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse.

## <a name="validating-an-xml-document-as-it-is-loaded-into-the-dom"></a>Validieren eines XML-Dokuments beim Laden in das Dokumentobjektmodell

Die <xref:System.Xml.XmlDocument>-Klasse validiert die XML-Daten beim Laden in das DOM, wenn ein validierender <xref:System.Xml.XmlReader> an die <xref:System.Xml.XmlDocument.Load%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse übergeben wird.

Nach erfolgreicher Validierung werden Schemastandards angewendet, Textwerte bei Bedarf in atomare Werte konvertiert und Typinformationen validierten Informationselementen zugeordnet. Daher werden zuvor nicht typisierte XML-Daten durch typisierte XML-Daten ersetzt.

### <a name="creating-an-xml-schema-validating-xmlreader"></a>Erstellen eines "XmlReader" zum Validieren von XML-Schemata

Wenn Sie einen <xref:System.Xml.XmlReader> zum Validieren von XML-Schemata erstellen möchten, führen Sie folgende Schritte aus:

1. Erstellen Sie eine neue <xref:System.Xml.XmlReaderSettings>-Instanz.

2. Fügen Sie der <xref:System.Xml.XmlReaderSettings.Schemas%2A>-Eigenschaft der <xref:System.Xml.XmlReaderSettings>-Instanz ein XML-Schema hinzu.

3. Geben Sie `Schema` als den <xref:System.Xml.XmlReaderSettings.ValidationType%2A> an.

4. Geben Sie optional <xref:System.Xml.XmlReaderSettings.ValidationFlags%2A> und einen <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> an, um während der Schemavalidierung auftretende Fehler und Warnungen zu behandeln.

5. Übergeben Sie abschließend das <xref:System.Xml.XmlReaderSettings>-Objekt zusammen mit dem XML-Dokument an die <xref:System.Xml.XmlReader.Create%2A>-Methode der <xref:System.Xml.XmlReader>-Klasse. Dabei wird ein schemavalidierender <xref:System.Xml.XmlReader> erstellt.

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel validiert ein schemavalidierender <xref:System.Xml.XmlReader> die in das DOM geladenen XML-Daten. Es werden ungültige Änderungen am XML-Dokument vorgenommen, und das Dokument wird anschließend erneut validiert, was zu Schemavalidierungsfehlern führt. Abschließend wird einer der Fehler korrigiert, und anschließend werden Teile des XML-Dokuments teilweise validiert.

[!code-cpp[XmlDocumentValidation.Load#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlDocumentValidation.Load/CPP/XmlDocumentValidationExample.cpp#1)]
[!code-csharp[XmlDocumentValidation.Load#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlDocumentValidation.Load/CS/XmlDocumentValidationExample.cs#1)]
[!code-vb[XmlDocumentValidation.Load#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlDocumentValidation.Load/VB/XmlDocumentValidationExample.vb#1)]

In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.

[!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]

In diesem Beispiel wird auch die Datei `contosoBooks.xsd` als Eingabe verwendet.

[!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]

Beachten Sie Folgendes, wenn Sie XML-Daten beim Laden in das DOM validieren.

- Im vorangehenden Beispiel wird der <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> immer aufgerufen, sobald ein ungültiger Typ erkannt wird. Wenn im validierenden <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> kein <xref:System.Xml.XmlReader> festgelegt ist, wird beim Aufrufen von <xref:System.Xml.Schema.XmlSchemaValidationException> eine <xref:System.Xml.XmlDocument.Load%2A> ausgelöst, wenn ein Attribut- oder Elementtyp nicht mit dem entsprechenden Typ übereinstimmt, der im validierenden Schema angegeben ist.

- Wenn ein XML-Dokument in ein <xref:System.Xml.XmlDocument>-Objekt mit einem zugeordneten Schema geladen wird, das Standardwerte definiert, behandelt das <xref:System.Xml.XmlDocument>-Objekt diese Standardwerte, als wären diese im XML-Dokument enthalten. Das bedeutet, dass die <xref:System.Xml.XmlReader.IsEmptyElement%2A>-Eigenschaft immer den Wert `false` für ein Element zurückgibt, das als Standardwert aus dem Schema entnommen wurde. Es wird auch im XML-Dokument als leeres Element geschrieben.

## <a name="validating-an-xml-document-in-the-dom"></a>Validieren eines XML-Dokuments im Dokumentobjektmodell

Die <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse validiert die in das DOM geladenen XML-Daten anhand der Schemata in der <xref:System.Xml.XmlDocument>-Eigenschaft des <xref:System.Xml.XmlDocument.Schemas%2A>-Objekts. Nach erfolgreicher Validierung werden Schemastandards angewendet, Textwerte bei Bedarf in atomare Werte konvertiert und Typinformationen validierten Informationselementen zugeordnet. Daher werden zuvor nicht typisierte XML-Daten durch typisierte XML-Daten ersetzt.

Das folgende Beispiel ähnelt dem Beispiel unter "Validieren eines XML-Dokuments beim Laden in das Dokumentobjektmodell". In diesem Beispiel wird das XML-Dokument nicht beim Laden in das DOM validiert, sondern nachdem es mithilfe der <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse in das DOM geladen wurde. Die <xref:System.Xml.XmlDocument.Validate%2A>-Methode validiert das XML-Dokument anhand der in der <xref:System.Xml.XmlDocument.Schemas%2A>-Eigenschaft des <xref:System.Xml.XmlDocument> enthaltenen XML-Schemata. Anschließend werden am XML-Dokument ungültige Änderungen vorgenommen, und das Dokument wird dann erneut validiert, was zu Schemavalidierungsfehlern führt. Abschließend wird einer der Fehler korrigiert, und anschließend werden Teile des XML-Dokuments teilweise validiert.

[!code-csharp[XmlDocumentValidation.Validate#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlDocumentValidation.Validate/CS/XmlDocumentValidationExample.cs#1)]
[!code-vb[XmlDocumentValidation.Validate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlDocumentValidation.Validate/VB/XmlDocumentValidationExample.vb#1)]

In dem Beispiel werden die Dateien `contosoBooks.xml` und `contosoBooks.xsd`, auf die unter "Validieren eines XML-Dokuments beim Laden in das Dokumentobjektmodell" verwiesen wird, als Eingabe verwendet.

## <a name="handling-validation-errors-and-warnings"></a>Behandeln von Validierungsfehlern und Validierungswarnungen

Fehler bei der XML-Schema-Validierung werden gemeldet, wenn XML-Daten beim Laden in das DOM validiert werden. Ihnen werden alle Schemavalidierungsfehler mitgeteilt, die während der Validierung beim Laden oder während der Validierung eines zuvor nicht validierten XML-Dokuments auftreten.

Validierungsfehler werden vom <xref:System.Xml.Schema.ValidationEventHandler> behandelt. Wenn ein <xref:System.Xml.Schema.ValidationEventHandler> der <xref:System.Xml.XmlReaderSettings>-Instanz zugeordnet oder an die <xref:System.Xml.XmlDocument.Validate%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse übergeben wurde, behandelt der <xref:System.Xml.Schema.ValidationEventHandler> Schemavalidierungsfehler. Andernfalls wird beim Auftreten eines Schemavalidierungsfehlers eine <xref:System.Xml.Schema.XmlSchemaValidationException> ausgelöst.

> [!NOTE]
> Die XML-Daten werden trotz der Schemavalidierungsfehler in das DOM geladen, sofern der <xref:System.Xml.Schema.ValidationEventHandler> keine Ausnahme auslöst, um den Vorgang zu beenden.
>
> Schemavalidierungswarnungen werden nicht gemeldet, sofern kein <xref:System.Xml.Schema.XmlSchemaValidationFlags.ReportValidationWarnings>-Flag für das <xref:System.Xml.XmlReaderSettings>-Objekt angegeben wurde.

 Beispiele zur Erläuterung des <xref:System.Xml.Schema.ValidationEventHandler> finden Sie unter "Validieren eines XML-Dokuments beim Laden in das Dokumentobjektmodell" and "Validieren eines XML-Dokuments im Dokumentobjektmodell".

## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XmlReader>
- <xref:System.Xml.Schema.ValidationEventHandler>
- <xref:System.Xml.XmlReaderSettings>
- [Verarbeiten von XML-Daten mithilfe des DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)
- [Arbeiten mit XML-Schemata](../../../../docs/standard/data/xml/working-with-xml-schemas.md)
