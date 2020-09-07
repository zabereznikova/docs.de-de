---
ms.openlocfilehash: b7b16e39fa5df9732fa769f2bcd3696dff3b2a49
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497336"
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
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)`

-->
