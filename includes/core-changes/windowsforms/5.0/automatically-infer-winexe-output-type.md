---
ms.openlocfilehash: 54bee14f6de409550357194e905b6ee5d8ef8f18
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "90678997"
---
### <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a>OutputType für WPF- und WinForms-Apps auf WinExe festgelegt

`OutputType` wird für Windows Presentation Foundation- und Windows Forms-Apps automatisch auf `WinExe` festgelegt. Wenn `OutputType` auf `WinExe` festgelegt ist, wird ein Konsolenfenster nicht geöffnet, sobald die App ausgeführt wird.

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen von .NET wird der Wert verwendet, der in der Projektdatei für `OutputType` angegeben ist. Zum Beispiel:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Ab .NET 5.0 wird `OutputType` für Windows Presentation Foundation- und Windows Forms-Anwendungen automatisch auf `WinExe` festgelegt. Zum Beispiel:

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

#### <a name="reason-for-change"></a>Grund für die Änderung

Es wird angenommen, dass die meisten Benutzer nicht möchten, dass beim Ausführen einer Windows Presentation Foundation- oder Windows Forms-App ein Konsolenfenster geöffnet wird. Darüber hinaus wird [jetzt, da diese Anwendungstypen das .NET SDK](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) anstelle des Windows Desktop SDK verwenden, die richtige Standardeinstellung festgelegt. Wenn darüber hinaus Unterstützung für iOS und Android hinzugefügt wird, wird es einfacher, mehrere Plattformen gleichzeitig als Ziel zu wählen, sofern alle den gleichen Ausgabetyp verwenden.

#### <a name="version-introduced"></a>Eingeführt in Version

.NET Core 5.0 Preview 8

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Ihrerseits müssen Sie nichts tun. Wenn Sie jedoch zum alten Verhalten zurückkehren möchten, legen Sie die Eigenschaft `DisableWinExeOutputInference` in Ihrer Projektdatei auf `true` fest.

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

#### <a name="category"></a>Kategorie

- Windows Forms
- Windows Presentation Framework (WPF)

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
