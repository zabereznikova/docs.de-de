---
ms.openlocfilehash: fa5cf2280cdd9535962568a6272d047d261eeba5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621209"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a>RSACng.VerifyHash gibt nun FALSE für alle Überprüfungsfehler zurück

#### <a name="details"></a>Details

Ab .NET Framework 4.6.2 gibt diese Methode **FALSE** zurück, wenn die Signatur selbst ein ungültiges Format aufweist. Sie gibt nun für jeden Überprüfungsfehler FALSE zurück. In .NET Framework 4.6 und 4.6.1 löst diese Methode die Ausnahme <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> aus, wenn die Signatur selbst falsch formatiert ist.

#### <a name="suggestion"></a>Vorschlag

Jeder Code, dessen Ausführung von der Behandlung der <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>-Ausnahme abhängt, sollte stattdessen ausgeführt werden, wenn ein Validierungsfehler auftritt und die Methode **FALSE** zurückgibt.

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.6.2|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
