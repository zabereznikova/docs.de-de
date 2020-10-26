---
ms.openlocfilehash: 80d13609f1b02ae0ac875b2028e745670bb8f503
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050564"
---
### <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a>Der Wert von FrameworkDescription entspricht „.NET“ anstelle von „.NET Core“

<xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> gibt jetzt „.NET“ anstelle von „.NET Core“ zurück.

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen von .NET gibt <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> „.NET Core“ als Teil der Beschreibungszeichenfolge zurück, z. B. `.NET Core 3.1.1`.

Ab .NET 5.0 gibt <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> „.NET“ als Teil der Beschreibungszeichenfolge zurück, z. B. `.NET 5.0.0`.

#### <a name="reason-for-change"></a>Grund für die Änderung

Mit .NET 5 wird `netcoreapp` durch `net` als Zielframeworkmoniker ersetzt. Aus Konsistenzgründen wurde die Beschreibung des Frameworks ebenfalls aktualisiert. Die Änderung ist rein kosmetischer Natur, da der `FrameworkName` nur in der Eigenschaft <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> codiert wird.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Aktualisieren Sie jeglichen Code, mit dem in der von <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription> zurückgegebenen Zeichenfolge nach „.NET Core“ gesucht wird.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
