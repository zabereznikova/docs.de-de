---
ms.openlocfilehash: 1f5bc43dcba15c28c179b23352558411f511c82f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235619"
---
### <a name="xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>Die DTD-Entitätserweiterung „XmlTextReader“ ist auf 10.000.000 Zeichen beschränkt

|   |   |
|---|---|
|Details|Die DTD-Entitätserweiterung ist jetzt auf 10.000.000 Zeichen beschränkt. Das Laden von XML-Dateien ohne DTD-Entitätserweiterung oder mit eingeschränkter DTD-Entitätserweiterung ist davon nicht betroffen. Dateien mit DTD-Entitäten, die auf mehr als 10.000.000 Zeichen erweitert werden, können nicht geladen werden und lösen nun eine Ausnahme aus.|
|Vorschlag|Wenn das Limit der DTD-Entitätserweiterung von 10.000.000 zu niedrig ist, kann der Wert mit der <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities>-Eigenschaft außer Kraft gesetzt werden. Eine <xref:System.Xml.XmlReaderSettings?displayProperty=name>-Klasse mit dem richtigen <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=name>-Wert kann an eine <code>XmlReader.Create</code>-Klasse übergeben werden, die <xref:System.Xml.XmlReaderSettings?displayProperty=name> akzeptiert (d.h. <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>).|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Xml.XmlTextReader?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNameTable)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader,System.Xml.XmlNameTable)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNameTable)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.Xml.XmlNameTable)?displayProperty=nameWithType></li></ul>|
