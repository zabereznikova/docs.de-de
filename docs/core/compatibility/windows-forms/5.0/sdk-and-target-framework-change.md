---
title: 'Breaking Change: WinForms- und WPF-Apps verwenden Microsoft.NET.Sdk'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den Windows Forms- und Windows Presentation Framework-Apps (WPF) jetzt das .NET SDK anstelle des .NET Core SDK für WinForms und WPF verwenden.
ms.date: 09/18/2020
ms.openlocfilehash: 5eafed03fbf034f6a6457217a8527a877214e239
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633818"
---
# <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a>WinForms- und WPF-Apps verwenden Microsoft.NET.Sdk

Windows Forms- und WPF-Apps (Windows Presentation Framework) verwenden jetzt das .NET SDK (`Microsoft.NET.Sdk`) anstelle des .NET Core SDK für WinForms- und WPF-Apps (`Microsoft.NET.Sdk.WindowsDesktop`).

## <a name="change-description"></a>Änderungsbeschreibung

In vorherigen .NET Core-Versionen haben WinForms- und WPF-Apps ein separates [Projekt-SDK](../../../project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`) verwendet. Ab .NET 5.0 wird das SDK für WinForms- und WPF-Apps mit dem .NET SDK (`Microsoft.NET.Sdk`) vereinheitlicht. Außerdem ersetzt der neue [Zielframeworkmoniker (TFM)](../../../../standard/frameworks.md) `netcoreapp` und `netstandard` in .NET 5. Im folgenden Beispiel werden die Änderungen veranschaulicht, die für eine WPF-Projektdatei erforderlich sind, wenn Sie erneut auf .NET 5.0 oder höher abzielen.

In früheren .NET Core-Versionen:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

In .NET 5.0 und höher:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

## <a name="version-introduced"></a>Eingeführt in Version

.NET SDK 5.0.100

## <a name="recommended-action"></a>Empfohlene Maßnahme

In WPF- oder Windows Forms-Projektdateien:

- Aktualisieren Sie das `Sdk`-Attribut auf `Microsoft.NET.Sdk`.
- Aktualisieren Sie die `TargetFramework`-Eigenschaft auf `net5.0-windows`.

## <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
