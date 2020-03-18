---
ms.openlocfilehash: 68da7216890da1819a994161507355a0b5ea1f9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857512"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a>Breaking Changes bei SignedXml und EncryptedXml

|   |   |
|---|---|
|Details|In .NET Framework 4.6.2 führen geschlossene Sicherheitslücken in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=name> und <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=name> zu Änderungen des Laufzeitverhaltens. Ein auf ein Objekt angewendeter<ul><li>Wenn ein Dokument mehrere Elemente mit demselben <code>id</code>-Attribut enthält und eine Signatur auf eins dieser Elemente als Signaturstamm ausgerichtet ist, wird das Dokument als gültig markiert.</li><li>Dokumente, die nicht kanonische Transformationsalgorithmen für XPath in Verweisen verwenden, gelten jetzt als gültig.</li><li>Dokumente, die nicht kanonische Transformationsalgorithmen für XSLT in Verweisen verwenden, gelten jetzt als ungültig.</li><li>Programme können keine externen von Ressourcen getrennte Signaturen verwenden.</li></ul>|
|Vorschlag|Entwickler sollten die Verwendung von <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> und <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> sowie von von <xref:System.Security.Cryptography.Xml.Transform> abgeleiteten Typen prüfen, da ein Dokumentempfänger sie möglicherweise nicht verarbeiten kann.|
|`Scope`|Nebenversion|
|Version|4.6.2|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType></li></ul>|
