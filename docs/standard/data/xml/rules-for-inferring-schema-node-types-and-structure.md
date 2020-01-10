---
title: Regeln für Rückschlussschemaknotentypen und Struktur
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d74ce896-717d-4871-8fd9-b070e2f53cb0
ms.openlocfilehash: 6d66384dea7018bcc3b2dd8fde96f4fa2653f8e8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710244"
---
# <a name="rules-for-inferring-schema-node-types-and-structure"></a>Regeln für Rückschlussschemaknotentypen und Struktur
In diesem Thema wird beschrieben, wie der Schemarückschlussprozess die in einem XML-Dokument auftretenden Knotentypen in eine XSD-Struktur (XML Schema Definition) übersetzt.  
  
## <a name="element-inference-rules"></a>Rückschlussregeln für Elemente  
 In diesem Abschnitt werden die Rückschlussregeln für Elementdeklarationen erläutert. Es existieren acht Strukturen zur Elementdeklaration, die hergeleitet werden können:  
  
1. Einfaches Element  
  
2. Leeres Element  
  
3. Leeres Element mit Attributen  
  
4. Element mit Attributen und einfachem Inhalt  
  
5. Element mit einer Sequenz von direkt untergeordneten Elementen  
  
6. Element mit einer Sequenz von direkt untergeordneten Elementen und Attributen  
  
7. Element mit einer Sequenz von Auswahlmöglichkeiten direkt untergeordneter Elemente  
  
8. Element mit einer Sequenz von Auswahlmöglichkeiten direkt untergeordneter Elemente und Attribute  
  
> [!NOTE]
> Alle `complexType`-Deklarationen werden als anonyme Typen hergeleitet. Das einzige globale hergeleitete Element ist das Stammelement. Alle anderen Elemente sind lokal.  
  
 Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
### <a name="simple-typed-element"></a>Element eines einfachen Typs  
 In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt. Das fett formatierte Element stellt das Schema dar, das für das Element eines einfachen Typs hergeleitet wird.  
  
 Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>text</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root" type="xs:string" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element"></a>Leeres Element  
 In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt. Das fett formatierte Element stellt das für das leere Element hergeleitete Schema dar.  
  
 Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element-with-attributes"></a>Leeres Element mit Attributen  
 In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt. Die fett formatierten Elemente stellen das für das leere Element mit Attributen hergeleitete Schema dar.  
  
 Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty attribute1="text"/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-attributes-and-simple-content"></a>Element mit Attributen und einfachem Inhalt  
 In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt. Die fett formatierten Elemente stellen das für ein Element mit Attributen und einfachem Inhalt hergeleitete Schema dar.  
  
 Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">value</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:simpleContent>`<br /><br /> `<xs:extension base="xs:string">`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:extension>`<br /><br /> `</xs:simpleContent>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements"></a>Element mit einer Sequenz von direkt untergeordneten Elementen  
 In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt. Die fett formatierten Elemente stellen das für ein Element mit einer Sequenz von direkt untergeordneten Elementen hergeleitete Schema dar.  
  
> [!NOTE]
> Ein Element wird auch wie eine Sequenz behandelt, wenn es nur über ein direkt untergeordnetes Element verfügt.  
  
 Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement" />`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements-and-attributes"></a>Element mit einer Sequenz von direkt untergeordneten Elementen und Attributen  
 In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt. Die fett formatierten Elemente stellen das für ein Element mit einer Sequenz von direkt untergeordneten Elementen und Attributen hergeleitete Schema dar.  
  
> [!NOTE]
> Ein Element wird auch wie eine Sequenz behandelt, wenn es nur über ein direkt untergeordnetes Element verfügt.  
  
 Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choices-of-child-elements"></a>Element mit einer Sequenz und Auswahlmöglichkeiten von direkt untergeordneten Elementen  
 In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt. Die fett formatierten Elemente stellen das für ein Element mit einer Sequenz und Auswahlmöglichkeiten von direkt untergeordneten Elementen hergeleitete Schema dar.  
  
> [!NOTE]
> Das `maxOccurs`-Attribut des `xs:choice`-Elements wird im hergeleiteten Schema auf `"unbounded"` festgelegt.  
  
 Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choice-of-child-elements-and-attributes"></a>Element mit einer Sequenz und Auswahlmöglichkeit von direkt untergeordneten Elementen und Attributen  
 In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt. Die fett formatierten Elemente stellen das für ein Element mit einer Sequenz und Auswahlmöglichkeit von direkt untergeordneten Elementen und Attributen hergeleitete Schema dar.  
  
> [!NOTE]
> Das `maxOccurs`-Attribut des `xs:choice`-Elements wird im hergeleiteten Schema auf `"unbounded"` festgelegt.  
  
 Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="attribute-processing"></a>Verarbeitung von Attributen  
 Sobald eine neues Attribut in einem Knoten auftritt, wird es der hergeleiteten Definition des Knotens mit `use="required"` hinzugefügt. Wenn derselbe Knoten das nächste Mal in der Instanz gefunden wird, werden die Attribute der aktuellen Instanz mit den bereits hergeleiteten im Rückschlussprozess verglichen. Wenn einige der bereits hergeleiteten Attribute in der Instanz nicht vorhanden sind, wird der Attributdefinition `use="optional"` hinzugefügt. Neue Attribute werden vorhandenen Deklarationen mit `use="optional"` hinzugefügt.  
  
### <a name="occurrence-constraints"></a>Beschränkungen hinsichtlich des Vorkommens  
 Während des Schemarückschlussprozesses wird das `minOccurs`-Attribut und das `maxOccurs`-Attribut mit den Werten `"0"` oder `"1"` und `"1"` oder `"unbounded"` für hergeleitete Komponenten eines Schemas generiert. Die Werte `"1"` und `"unbounded"` werden nur verwendet, wenn die Werte `"0"` und `"1"` keine Validierung für das XML-Dokument durchführen können (wenn `MinOccurs="0"` ein Element beispielsweise nicht genau beschreibt, wird `minOccurs="1"` verwendet).  
  
### <a name="mixed-content"></a>Gemischter Inhalt  
 Wenn ein Element gemischte Inhalte (z. B. Text mit eingefügten Elementen) enthält, wird das `mixed="true"`-Attribut für die hergeleitete komplexe Typdefinition generiert.  
  
## <a name="other-node-type-inference-rules"></a>Rückschlussregeln für andere Knotentypen  
 In der folgenden Tabelle sind Rückschlussregeln für Verarbeitungsanweisungs-, Kommentar-, Entitätsverweis-, CDATA-, Dokumenttypen- und Namespaceknoten dargestellt.  
  
|Knotentyp|Übersetzung|  
|---------------|-----------------|  
|Verarbeitungsanweisung|Ignoriert.|  
|Anmerkungen|Ignoriert.|  
|Entitätsverweis|Die <xref:System.Xml.Schema.XmlSchemaInference>-Klasse behandelt keine Entitätsverweise. Wenn ein XML-Dokument Entitätsverweise enthält, müssen Sie einen Reader verwenden, der die Entitäten erweitert. Sie können beispielsweise eine <xref:System.Xml.XmlTextReader>-Klasse mit der <xref:System.Xml.XmlTextReader.EntityHandling%2A>-Eigenschaft übergeben, die auf den <xref:System.Xml.EntityHandling.ExpandEntities>-Member als Parameter festgelegt ist. Wenn Entitätsverweise auftreten und der Reader Entitäten nicht erweitert, wird eine Ausnahme ausgelöst.|  
|CDATA|Alle `<![CDATA[ … ]]`-Abschnitte in einem XML-Dokument werden als `xs:string` hergeleitet.|  
|Dokumenttyp|Ignoriert.|  
|-Namespaces|Ignoriert.|  
  
 Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Schema.XmlSchemaInference>
- [XML Schema Object Model (SOM) (XML-Schemaobjektmodell (SOM))](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)
- [Herleiten eines XML-Schemas](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)
- [Herleiten von Schemas aus XML-Dokumenten](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)
- [Regeln zum Herleiten einfacher Typen](../../../../docs/standard/data/xml/rules-for-inferring-simple-types.md)
