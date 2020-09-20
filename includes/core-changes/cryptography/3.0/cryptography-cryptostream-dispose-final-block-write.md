---
ms.openlocfilehash: 7766a59131fffe2b436c15a5ff58e67001be7941
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065101"
---
### <a name="cryptostreamdispose-transforms-final-block-only-when-writing"></a>CryptoStream.Dispose transformiert den abschließenden Block nur beim Schreiben

Die Methode <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType>, die verwendet wird, um `CryptoStream`-Vorgänge abzuschließen, versucht nicht mehr, den abschließenden Block beim Lesen zu transformieren.

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen von .NET konnte die Methode <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> eine Ausnahme auslösen, wenn ein Benutzer bei der Verwendung von <xref:System.Security.Cryptography.CryptoStream> im <xref:System.Security.Cryptography.CryptoStreamMode.Read>-Modus einen unvollständigen Lesevorgang durchführte (z. B. bei Verwendung von AES mit Auffüllung). Die Ausnahme wurde ausgelöst, da versucht wurde, den abschließenden Block zu transformieren, die Daten aber unvollständig waren.

Ab .NET Core 3.0 versucht <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> nicht mehr, den abschließenden Block beim Lesen zu transformieren, was unvollständige Lesevorgänge ermöglicht.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung ermöglicht unvollständige Lesevorgänge aus CryptoStream, wenn ein Netzwerkvorgang abgebrochen wird, ohne dass eine Ausnahme abgefangen werden muss.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Die meisten Apps sollten von dieser Änderung nicht betroffen sein.

Wenn Ihre Anwendung bisher bei unvollständigen Lesevorgängen eine Ausnahme abgefangen hat, können Sie diesen `catch`-Block löschen.
Wenn Ihre App das Transformieren des abschließenden Blocks in Hashingszenarios verwendet hat, müssen Sie möglicherweise sicherstellen, dass der gesamte Datenstrom gelesen wird, bevor er verworfen wird.

#### <a name="category"></a>Kategorie

Kryptografie

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.CryptoStream.Dispose`

-->
