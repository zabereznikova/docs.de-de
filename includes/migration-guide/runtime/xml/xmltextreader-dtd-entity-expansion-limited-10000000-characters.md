---
ms.openlocfilehash: fdec6671cbf2dae0d72dfaec07f162058b38cf9d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620508"
---
### <a name="xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>Die DTD-Entitätserweiterung „XmlTextReader“ ist auf 10.000.000 Zeichen beschränkt

#### <a name="details"></a>Details

Die DTD-Entitätserweiterung ist jetzt auf 10.000.000 Zeichen beschränkt. Das Laden von XML-Dateien ohne DTD-Entitätserweiterung oder mit eingeschränkter DTD-Entitätserweiterung ist davon nicht betroffen. Dateien mit DTD-Entitäten, die auf mehr als 10.000.000 Zeichen erweitert werden, können nicht geladen werden und lösen nun eine Ausnahme aus.

#### <a name="suggestion"></a>Vorschlag

Wenn das Limit der DTD-Entitätserweiterung von 10.000.000 zu niedrig ist, kann der Wert mit der <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities>-Eigenschaft außer Kraft gesetzt werden. Eine <xref:System.Xml.XmlReaderSettings?displayProperty=fullName>-Klasse mit dem richtigen <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName>-Wert kann an eine <code>XmlReader.Create</code>-Klasse übergeben werden, die <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> akzeptiert (d.h. <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>).

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Xml.XmlTextReader?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.Xml.XmlNameTable)></li></ul>|
