---
ms.openlocfilehash: 92c03328414410d56a2ff5f445639757367b42c7
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420426"
---
### <a name="processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start"></a>Process.StartInfo löst InvalidOperationException für Prozesse aus, die Sie nicht gestartet haben

Das Lesen der <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType>-Eigenschaft für Prozesse, die Ihr Code nicht gestartet hat, löst eine <xref:System.InvalidOperationException> aus.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework wird beim Zugriff auf die <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType>-Eigenschaft für Prozesse, die Ihr Code nicht gestartet hat, ein Dummy-<xref:System.Diagnostics.ProcessStartInfo>-Objekt zurückgegeben. Das Dummyobjekt enthält Standardwerte für alle seine Eigenschaften außer <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables>.

Ab .NET Core 1.0 wird eine <xref:System.InvalidOperationException> ausgelöst, wenn Sie die <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType>-Eigenschaft für einen Prozess lesen, den Sie nicht gestartet haben (d. h. durch Aufrufen von <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>).

#### <a name="version-introduced"></a>Eingeführt in Version

1.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Greifen Sie nicht für Prozesse, die Ihr Code nicht gestartet hat, auf die <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType>-Eigenschaft zu. Lesen Sie diese Eigenschaft z. B. nicht für Prozesse, die von <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType> zurückgegeben werden.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.Process.StartInfo?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Process.StartInfo`

-->
