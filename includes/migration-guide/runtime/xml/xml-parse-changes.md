---
ms.openlocfilehash: dfa8235fcfd868b80d3a610bddb492899519e289
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009051"
---
### <a name="xml-parsing-changes"></a>Änderungen an der XML-Analyse

| Name    | Wert   |
|:--------|:--------|
| Bereich   | Gering   |
| Version | 4.5.2   |
| Typ    | Laufzeit |

#### <a name="details"></a>Details

Aus Sicherheitsgründen wurden die folgenden Änderungen in den XML-Analyse-APIs eingeführt:

- <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=nameWithType> wird auf 10 Millionen festgelegt, wenn <xref:System.Xml.XmlReaderSettings> initialisiert wird.
- <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=nameWithType> ist standardmäßig auf `null` festgelegt.

> [!NOTE]
> <xref:System.Xml.XmlReaderSettings> wird von allen XML-Analysen verwendet. Diese Änderung unterstützt den <xref:System.Xml.XmlReader>-Fall, wirkt sich aber auch auf andere Szenarios aus.

#### <a name="suggestion"></a>Vorschlag

Sie können einen Wert in der Registrierung festlegen, um das vorherige Verhalten wiederherzustellen. Fügen Sie einen DWORD-Wert namens `EnableLegacyXmlSettings` zum Registrierungsschlüssel `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\XML` hinzu, und legen Sie den Wert auf `1` fest. Sie können den Registrierungswert stattdessen auch im HKEY_CURRENT_USER-Hive hinzufügen.

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName>
- <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=fullName>

Darüber hinaus ist jede direkt oder indirekt von <xref:System.Xml.XmlResolver> abhängige XML-API betroffen.

<!--

#### Affected APIs

- `P:System.Xml.XmlReaderSettings.MaxCharactersFromEntities`
- `P:System.Xml.XmlReaderSettings.XmlResolver`

-->
