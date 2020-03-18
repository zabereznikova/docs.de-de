---
ms.openlocfilehash: 0dfc87201b9b31cd9d936f2c965c7d0ca0140cab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858522"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>„X509Certificate2.ToString(Boolean)“ wird jetzt nicht mehr ausgelöst, wenn .NET das Zertifikat nicht verarbeiten kann

|   |   |
|---|---|
|Details|Zuvor wurde diese Methode in .NET Framework 4.5.2 ausgelöst, wenn <code>true</code> für den ausführlichen Parameter übergeben wurde und Zertifikate installiert waren, die von .NET Framework nicht unterstützt wurden. Nun wird die Methode erfolgreich ausgeführt und gibt eine gültige Zeichenfolge zurück, die die Teile des Zertifikats auslässt, auf die nicht zugegriffen werden kann.|
|Vorschlag|Jeder von <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> abhängige Code sollte aktualisiert werden, um zu erwarten, dass die zurückgegebene Zeichenfolge einige Zertifikatsdaten in einigen Fällen ausschließt (z.B. den öffentlichen Schlüssel, den privaten Schlüssel und die Erweiterungen), in denen zuvor die API ausgelöst worden wäre.|
|`Scope`|Edge|
|Version|4.6|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|
