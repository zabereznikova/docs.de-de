---
ms.openlocfilehash: 58cb3580c8701773452ae8338f036a94bbee80c5
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449396"
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

CoreFx

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
