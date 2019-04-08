---
ms.openlocfilehash: 2c54912e5c29b2ed8f4c8163550050e12e367263
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760645"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a>Breaking Changes bei SignedXml und EncryptedXml

|   |   |
|---|---|
|Details|In .NET Framework 4.6.2 führen geschlossene Sicherheitslücken in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=name> und <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=name> zu Änderungen des Laufzeitverhaltens. Ein auf ein Objekt angewendeter<ul><li>Wenn ein Dokument mehrere Elemente mit demselben <code>id</code>-Attribut enthält und eine Signatur auf eins dieser Elemente als Signaturstamm ausgerichtet ist, wird das Dokument als gültig markiert.</li><li>Dokumente, die nicht kanonische Transformationsalgorithmen für XPath in Verweisen verwenden, gelten jetzt als gültig.</li><li>Dokumente, die nicht kanonische Transformationsalgorithmen für XSLT in Verweisen verwenden, gelten jetzt als ungültig.</li><li>Programme können keine externen von Ressourcen getrennte Signaturen verwenden.</li></ul>|
|Vorschlag|Entwickler sollten die Verwendung von <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> und <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> sowie von von <xref:System.Security.Cryptography.Xml.Transform> abgeleiteten Typen prüfen, da ein Dokumentempfänger sie möglicherweise nicht verarbeiten kann.|
|Bereich|Gering|
|Version|4.6.2|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType></li></ul>|

