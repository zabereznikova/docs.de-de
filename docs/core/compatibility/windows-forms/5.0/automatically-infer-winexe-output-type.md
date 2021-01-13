---
title: 'Breaking Change: OutputType für WPF- und WinForms-Apps auf WinExe festgelegt'
description: Hier erfahren Sie mehr über den Breaking Change im .NET SDK 5.0.100, durch den OutputType für Windows Forms-Apps automatisch auf WinExe festgelegt wird.
ms.date: 09/18/2020
ms.openlocfilehash: 0b56db57d5242f2fb001c4de339a7f696c088dfc
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633854"
---
# <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a>OutputType für WPF- und WinForms-Apps auf WinExe festgelegt

`OutputType` wird für Windows Presentation Foundation- und Windows Forms-Apps automatisch auf `WinExe` festgelegt. Wenn `OutputType` auf `WinExe` festgelegt ist, wird ein Konsolenfenster nicht geöffnet, sobald die App ausgeführt wird.

## <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen des .NET SDK wird der Wert verwendet, der in der Projektdatei für `OutputType` angegeben ist. Zum Beispiel:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Ab Version 5.0.100 des .NET SDK ist `OutputType` für WPF- und Windows Forms-Apps für alle Frameworkversionen, einschließlich des .NET Framework, automatisch auf `WinExe` festgelegt. Zum Beispiel:

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

## <a name="reason-for-change"></a>Grund für die Änderung

Es wird angenommen, dass die meisten Benutzer nicht möchten, dass beim Ausführen einer Windows Presentation Foundation- oder Windows Forms-App ein Konsolenfenster geöffnet wird. Darüber hinaus wird [jetzt, da diese Anwendungstypen das .NET SDK](sdk-and-target-framework-change.md) anstelle des Windows Desktop SDK verwenden, die richtige Standardeinstellung festgelegt. Wenn darüber hinaus Unterstützung für iOS und Android hinzugefügt wird, wird es einfacher, mehrere Plattformen gleichzeitig als Ziel zu wählen, sofern alle den gleichen Ausgabetyp verwenden.

## <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0.100

## <a name="recommended-action"></a>Empfohlene Maßnahme

Ihrerseits müssen Sie nichts tun. Wenn Sie jedoch zum alten Verhalten zurückkehren möchten, legen Sie die Eigenschaft `DisableWinExeOutputInference` in Ihrer Projektdatei auf `true` fest.

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

## <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
