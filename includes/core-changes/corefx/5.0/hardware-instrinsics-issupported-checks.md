---
ms.openlocfilehash: bba9659b92e5aabc276c585929c99898316036c5
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359133"
---
### <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a>Hardwareintrinsische IsSupported-Überprüfungen können für geschachtelte Typen abweichen

Bei der Überprüfung von `<Isa>.X64.IsSupported`, wobei `<Isa>` auf die Klassen im Namespace <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> verweist, kann das Ergebnis jetzt von früheren .NET-Versionen abweichen.

> [!TIP]
> *ISA* steht für Industriestandardarchitektur.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen machten einige der hardwareintrinsischen <xref:System.Runtime.Intrinsics.X86>-Typen wie <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType> keine geschachtelte `X64`-Klasse verfügbar. Für diese Typen wurde der Aufruf von `<Isa>.X64.IsSupported` in eine `IsSupported`-Eigenschaft in einer geschachtelten `X64`-Klasse aufgelöst, der die Klasse `<Isa>` übergeordnet ist. Das bedeutete, dass die Eigenschaft `true` zurückgeben konnte, auch wenn `<Isa>.IsSupported` `false` zurückgibt.

In .NET 5.0 und höher machen alle <xref:System.Runtime.Intrinsics.X86>-Typen eine geschachtelte `X64`-Klasse verfügbar, die Unterstützung entsprechend meldet. Dadurch wird sichergestellt, dass die allgemeine Hierarchie korrekt erhalten bleibt. Wenn `<Isa>.X64.IsSupported` `true` entspricht, kann zudem angenommen werden, dass `<Isa>.IsSupported` `true` entspricht.

#### <a name="reason-for-change"></a>Grund für die Änderung

Wenn `<Isa>.X64.IsSupported` `true` entspricht, ist beabsichtigt, dass für `<Isa>.IsSupported` `true` impliziert werden kann. Aufgrund der Funktionsweise der Memberauflösung in C# führten Klassen ohne geschachtelte `X64`-Klasse in Situationen, in denen das nicht der Fall war, zu Fehlern im Benutzercode.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Passen Sie Code mit Überprüfungen auf `IsSupported` ggf. an, damit die richtige ISA überprüft wird.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->
