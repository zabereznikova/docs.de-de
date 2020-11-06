---
ms.openlocfilehash: 2599e1f65720c25695f1fb5cfa39cabb842efc1d
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888612"
---
### <a name="default-feedbacksize-value-for-instances-created-by-tripledescreate-changed"></a>Der Standardwert für FeedbackSize für mit TripleDES.Create erstellte Instanzen wurde geändert

Der Standardwert für die <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=nameWithType>-Eigenschaft in der von <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> zurückgegebenen <xref:System.Security.Cryptography.TripleDES>-Instanz wurde von 64 in 8 geändert, um die Migration vom .NET Framework zu vereinfachen. Diese Eigenschaft wird nur verwendet, wenn für die <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode>-Eigenschaft <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType> gilt, es sei denn, sie wird direkt im aufrufenden Code verwendet.

Unterstützung für den <xref:System.Security.Cryptography.CipherMode.CFB>-Modus steht für .NET seit dem 5.0 RC1-Release zur Verfügung. Nur .NET 5.0 RC1 und .NET 5.0 RC2-Anwendungen sollten also von dieser Änderung betroffen sein.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Core und vorherigen Vorabversionen von .NET 5.0 weist `TripleDES.Create().FeedbackSize` einen Standardwert von 64 auf. Ab der RTM-Version von .NET 5.0 weist `TripleDES.Create().FeedbackSize` einen Standardwert von 8 auf.

#### <a name="reason-for-change"></a>Grund für die Änderung

Im .NET Framework legt die <xref:System.Security.Cryptography.TripleDES>-Basisklasse für <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> einen Standardwert von 64 fest, die <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>-Klasse überschreibt den Standardwert jedoch durch 8. Als die <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>-Eigenschaft in der Version 2.0 von .NET Core eingeführt wurde, wurde dieses Verhalten beibehalten. Im .NET Framework gibt <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> jedoch eine Instanz von <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> zurück. Der Standardwert der Algorithmusfactory ist also 8. Für .NET Core und .NET 5 und höher gibt die Algorithmusfactory eine nicht öffentliche Implementierung zurück, die bis jetzt einen Standardwert von 64 aufwies.

Das Ändern des <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>-Werts der <xref:System.Security.Cryptography.TripleDES>-Implementierungsklasse in 8 ermöglicht es, dass Anwendungen, die für das .NET Framework geschrieben wurden, in dem der Verschlüsselungsmodus auf <xref:System.Security.Cryptography.CipherMode.CFB> festgelegt war, die die <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>-Eigenschaft jedoch nicht explizit zuwiesen, in .NET 5 weiterhin funktionieren.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 RTM

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Anwendungen, die Daten in den RC1- oder RC2-Versionen von .NET 5.0 verschlüsseln oder entschlüsseln, tun dies auch bei CFB64, wenn die folgenden Bedingungen erfüllt sind:

- Eine <xref:System.Security.Cryptography.TripleDES>-Instanz von <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> ist vorhanden.
- Der Standardwert für <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> wird verwendet.
- Die <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode>-Eigenschaft ist auf <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType> festgelegt.

Wenn dieses Verhalten beibehalten werden soll, weisen Sie die <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>-Eigenschaft `64` zu.

Nicht für alle `TripleDES`-Implementierungen wird derselbe Standardwert für <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> verwendet. Wenn Sie den <xref:System.Security.Cryptography.CipherMode.CFB>-Verschlüsselungsmodus für <xref:System.Security.Cryptography.TripleDES>-Instanzen verwenden, sollten Sie den <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>-Eigenschaftswert immer explizit zuweisen.

```csharp
TripleDES cipher = TripleDES.Create();
cipher.Mode = CipherMode.CFB;
// Explicitly set the FeedbackSize for CFB to control between CFB8 and CFB64.
cipher.FeedbackSize = 8;
```

#### <a name="category"></a>Kategorie

- Kryptografie

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.TripleDES.Create`
- `P:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize`

-->
