---
ms.openlocfilehash: fc315faef750d93d914104dd568078aa3fc430d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887774"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a>RSACng.VerifyHash gibt nun FALSE für alle Überprüfungsfehler zurück

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6.2 gibt diese Methode **FALSE** zurück, wenn die Signatur selbst ein ungültiges Format aufweist. Sie gibt nun für jeden Überprüfungsfehler FALSE zurück. In .NET Framework 4.6 und 4.6.1 löst diese Methode die Ausnahme <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> aus, wenn die Signatur selbst falsch formatiert ist.|
|Vorschlag|Jeder Code, dessen Ausführung von der Behandlung der <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>-Ausnahme abhängt, sollte stattdessen ausgeführt werden, wenn ein Validierungsfehler auftritt und die Methode **FALSE** zurückgibt.|
|`Scope`|Nebenversion|
|Version|4.6.2|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
