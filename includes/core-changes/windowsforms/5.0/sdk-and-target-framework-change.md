---
ms.openlocfilehash: 975e331ad3e7bd7e0e8f49b62795c6acc7031ca9
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656337"
---
### <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a>WinForms- und WPF-Apps verwenden Microsoft.NET.Sdk

Windows Forms- und WPF-Apps (Windows Presentation Framework) verwenden jetzt das .NET SDK (`Microsoft.NET.Sdk`) anstelle des .NET Core SDK für WinForms- und WPF-Apps (`Microsoft.NET.Sdk.WindowsDesktop`).

#### <a name="change-description"></a>Änderungsbeschreibung

In vorherigen .NET Core-Versionen haben WinForms- und WPF-Apps ein separates [Projekt-SDK](../../../../docs/core/project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`) verwendet. Ab .NET 5.0 wird das SDK für WinForms- und WPF-Apps mit dem .NET SDK (`Microsoft.NET.Sdk`) vereinheitlicht. Außerdem ersetzt der neue [Zielframeworkmoniker (TFM)](../../../../docs/standard/frameworks.md) `netcoreapp` und `netstandard` in .NET 5. Im folgenden Beispiel werden die Änderungen veranschaulicht, die für eine WPF-Projektdatei erforderlich sind, wenn Sie erneut auf .NET 5.0 oder höher abzielen.

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

#### <a name="version-introduced"></a>Eingeführt in Version

.NET Core 5.0 Preview 8

#### <a name="recommended-action"></a>Empfohlene Maßnahme

In WPF- oder Windows Forms-Projektdateien:

- Aktualisieren Sie das `Sdk`-Attribut auf `Microsoft.NET.Sdk`.
- Aktualisieren Sie die `TargetFramework`-Eigenschaft auf `net5.0-windows`.

#### <a name="category"></a>Kategorie

- Windows Forms
- Windows Presentation Framework (WPF)

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
