---
ms.openlocfilehash: fe5dfa0b8866debd8a6091a264e251f2fd2e4dca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234501"
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
