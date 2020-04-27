---
ms.openlocfilehash: 9544b65f31772d0f4cee918528a73171fec4de99
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021799"
---
### <a name="change-in-default-value-of-useshellexecute"></a>Änderung des Standardwerts von UseShellExecute

<xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> besitzt den Standardwert `false` für .NET Core. Für .NET Framework lautet der Standardwert `true`.

#### <a name="change-description"></a>Änderungsbeschreibung

<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> ermöglicht es Ihnen, eine Anwendung direkt zu starten, z. B. mit Code wie `Process.Start("mspaint.exe")`, der Paint startet. Außerdem können Sie eine zugehörige Anwendung indirekt starten, wenn <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> auf `true` festgelegt ist. Für .NET Framework lautet der Standardwert für <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> `true`. Dies bedeutet, dass Code wie `Process.Start("mytextfile.txt")` den Editor starten würde, wenn Sie *TXT*-Dateien diesem Editor zugeordnet haben. Um zu verhindern, dass eine App indirekt unter .NET Framework gestartet wird, müssen Sie <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> explizit auf `false` festlegen. Für .NET Core ist der Standardwert für <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> `false`. Dies bedeutet, dass zugehörige Anwendungen standardmäßig nicht gestartet werden, wenn Sie `Process.Start` aufrufen.

Diese Änderung wurde aus Leistungsgründen in .NET Core eingeführt. In der Regel wird <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> verwendet, um eine Anwendung direkt zu starten. Wenn Sie eine App direkt starten, muss die Windows-Shell nicht einbezogen werden, und die damit verbundenen Leistungskosten entfallen. Damit dieser Standardfall schneller wird, ändert .NET Core den Standardwert aus <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> in `false`. Wenn Sie ihn benötigen, können Sie wahlweise den langsameren Pfad verwenden.

#### <a name="version-introduced"></a>Eingeführt in Version

2.1

> [!NOTE]
> In früheren Versionen von .NET Core wurde `UseShellExecute` nicht für Windows implementiert.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Ihre App das alte Verhalten benötigt, rufen Sie <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> auf und legen dabei <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> auf `true` für das <xref:System.Diagnostics.ProcessStartInfo>-Objekt fest.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
