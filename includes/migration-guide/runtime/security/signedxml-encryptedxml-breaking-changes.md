---
ms.openlocfilehash: 5c8ea3565fbe599dd53a71ba8bd339704f7d7f8a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497352"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a>Breaking Changes bei SignedXml und EncryptedXml

#### <a name="details"></a>Details

In .NET Framework 4.6.2 führen geschlossene Sicherheitslücken in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> und <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> zu Änderungen des Laufzeitverhaltens. Ein auf ein Objekt angewendeter<ul><li>Wenn ein Dokument mehrere Elemente mit demselben <code>id</code>-Attribut enthält und eine Signatur auf eins dieser Elemente als Signaturstamm ausgerichtet ist, wird das Dokument als gültig markiert.</li><li>Dokumente, die nicht kanonische Transformationsalgorithmen für XPath in Verweisen verwenden, gelten jetzt als gültig.</li><li>Dokumente, die nicht kanonische Transformationsalgorithmen für XSLT in Verweisen verwenden, gelten jetzt als ungültig.</li><li>Programme können keine externen von Ressourcen getrennte Signaturen verwenden.</li></ul>

#### <a name="suggestion"></a>Vorschlag

Entwickler sollten die Verwendung von <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> und <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> sowie von von <xref:System.Security.Cryptography.Xml.Transform> abgeleiteten Typen prüfen, da ein Dokumentempfänger sie möglicherweise nicht verarbeiten kann.

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.6.2|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.Xml.Transform`
- `T:System.Security.Cryptography.Xml.XmlDsigXPathTransform`
- `T:System.Security.Cryptography.Xml.XmlDsigXsltTransform`

-->
