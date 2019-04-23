---
ms.openlocfilehash: fe5dfa0b8866debd8a6091a264e251f2fd2e4dca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804046"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>X509CertificateClaimSet.FindClaims berücksichtigt alle claimTypes (Anspruchstypen)

|   |   |
|---|---|
|Details|Wenn in Apps, die auf .NET Framework 4.6.1 ausgerichtet sind, ein X509-Anspruchssatz über ein Zertifikat mit mehreren DNS-Einträge im SAN-Feld initialisiert wird, versucht die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name>-Methode, das claimType-Argument mit allen DNS-Einträgen abzugleichen. Bei Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, versucht die Methode <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name>, das claimType-Argument nur mit dem neuesten DNS-Eintrag abzugleichen.|
|Vorschlag|Diese Änderung wirkt sich nur auf Anwendungen aus, die auf .NET Framework 4.6.1 ausgerichtet sind. Diese Änderung kann mit dem [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation)-Kompatibilitätsschalter deaktiviert werden (oder bei Versionen vor 4.6.1 aktiviert werden).|
|Bereich|Gering|
|Version|4.6.1|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType></li></ul>|
