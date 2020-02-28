---
ms.openlocfilehash: 9583d868ee01117d7bd6e465e7d89a734489d1a8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449217"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a>Der boolesche Parameter von SignedCms.ComputeSignature wird beachtet

In .NET Core wird der boolesche Parameter `silent` der Methode <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> beachtet. Eine PIN-Eingabeaufforderung wird nicht angezeigt, wenn dieser Parameter auf `true` festgelegt ist.

#### <a name="change-description"></a>Änderungsbeschreibung

Im .NET Framework wird der Parameter `silent` der Methode <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> ignoriert. Es wird stets eine PIN-Eingabeaufforderung angezeigt, wenn der Anbieter dies verlangt. In .NET Core wird der Parameter `silent` beachtet. Wenn er auf `true` festgelegt ist, wird keinesfalls eine PIN-Eingabeaufforderung angezeigt, selbst wenn dies vom Anbieter verlangt wird.

Unterstützung für CMS/PKCS #7-Nachrichten wurde in .NET Core 2.1 eingeführt.

#### <a name="version-introduced"></a>Eingeführt in Version

2.1

#### <a name="recommended-action"></a>Empfohlene Aktion

Um sicherzustellen, dass bei Bedarf eine PIN-Eingabeaufforderung angezeigt wird, sollten Desktopanwendungen <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> aufrufen und den booleschen Parameter auf `false` festlegen. Das resultierende Verhalten ist das gleiche wie bei .NET Framework, und zwar unabhängig davon, ob der Kontext „silent“ dort deaktiviert ist.

### <a name="category"></a>Kategorie

Kryptografie

### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
