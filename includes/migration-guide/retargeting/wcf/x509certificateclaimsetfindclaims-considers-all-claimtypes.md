---
ms.openlocfilehash: abef47c64a7cfd99c5b50bf2100401a2d5fcc5c3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614495"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>X509CertificateClaimSet.FindClaims berücksichtigt alle claimTypes (Anspruchstypen)

#### <a name="details"></a>Details

Wenn in Apps, die auf .NET Framework 4.6.1 ausgerichtet sind, ein X509-Anspruchssatz über ein Zertifikat mit mehreren DNS-Einträge im SAN-Feld initialisiert wird, versucht die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName>-Methode, das claimType-Argument mit allen DNS-Einträgen abzugleichen. Bei Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, versucht die Methode <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName>, das claimType-Argument nur mit dem neuesten DNS-Eintrag abzugleichen.

#### <a name="suggestion"></a>Vorschlag

Diese Änderung wirkt sich nur auf Anwendungen aus, die auf .NET Framework 4.6.1 ausgerichtet sind. Diese Änderung kann mit dem [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation)-Kompatibilitätsschalter deaktiviert werden (oder bei Versionen vor 4.6.1 aktiviert werden).

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.6.1       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType>
