---
ms.openlocfilehash: 51208762cea2a5688c5d43e5d444d4e014e5f0b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621318"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>„X509Certificate2.ToString(Boolean)“ wird jetzt nicht mehr ausgelöst, wenn .NET das Zertifikat nicht verarbeiten kann

#### <a name="details"></a>Details

Zuvor wurde diese Methode in .NET Framework 4.5.2 ausgelöst, wenn <code>true</code> für den ausführlichen Parameter übergeben wurde und Zertifikate installiert waren, die von .NET Framework nicht unterstützt wurden. Nun wird die Methode erfolgreich ausgeführt und gibt eine gültige Zeichenfolge zurück, die die Teile des Zertifikats auslässt, auf die nicht zugegriffen werden kann.

#### <a name="suggestion"></a>Vorschlag

Jeder von <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> abhängige Code sollte aktualisiert werden, um zu erwarten, dass die zurückgegebene Zeichenfolge einige Zertifikatsdaten in einigen Fällen ausschließt (z.B. den öffentlichen Schlüssel, den privaten Schlüssel und die Erweiterungen), in denen zuvor die API ausgelöst worden wäre.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.6|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|
