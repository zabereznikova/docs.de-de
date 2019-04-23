---
ms.openlocfilehash: 4892f75e4ae673d9d9cc7e9eeb6fb9b1a73f572e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804079"
---
### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a>RSACng lädt nun fehlerfrei RSA-Schlüssel, die nicht der Standardschlüsselgröße entsprechen

|   |   |
|---|---|
|Details|In .NET Framework-Versionen, die älter sind als Version 4.6.2, können Kunden, die keine Standardschlüsselgrößen für RSA-Zertifikate verwenden, auf diese Schlüssel nicht über die Erweiterungsmethoden <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> und <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> zugreifen.  Eine <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> wird mit der Meldung &quot;The requested key size is not supported&quot; (Die angeforderte Schlüsselgröße wird nicht unterstützt.) ausgelöst. Dieses Problem wurde in .NET Framework 4.6.2 behoben. Ebenso funktionieren <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> und <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> nun mit Schlüsselgrößen, die nicht der Standardgröße entsprechen, ohne dass eine <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> ausgelöst wird.|
|Vorschlag|Wenn eine Ausnahmebehandlungslogik auf dem vorherigen Verhalten basiert, durch das eine <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> ausgelöst wird, sobald eine von der Standardgröße abweichende Schlüsselgröße verwendet wird, kann das Entfernen der Logik sinnvoll sein.|
|Bereich|Microsoft Edge|
|Version|4.6.2|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li></ul>|
