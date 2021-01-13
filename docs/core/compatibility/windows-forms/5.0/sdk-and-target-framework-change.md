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
# <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a><span data-ttu-id="524e5-103">WinForms- und WPF-Apps verwenden Microsoft.NET.Sdk</span><span class="sxs-lookup"><span data-stu-id="524e5-103">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>

<span data-ttu-id="524e5-104">Windows Forms- und WPF-Apps (Windows Presentation Framework) verwenden jetzt das .NET SDK (`Microsoft.NET.Sdk`) anstelle des .NET Core SDK für WinForms- und WPF-Apps (`Microsoft.NET.Sdk.WindowsDesktop`).</span><span class="sxs-lookup"><span data-stu-id="524e5-104">Windows Forms and Windows Presentation Framework (WPF) apps now use the .NET SDK (`Microsoft.NET.Sdk`) instead of the .NET Core WinForms and WPF SDK (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span>

## <a name="change-description"></a><span data-ttu-id="524e5-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="524e5-105">Change description</span></span>

<span data-ttu-id="524e5-106">In vorherigen .NET Core-Versionen haben WinForms- und WPF-Apps ein separates [Projekt-SDK](../../../project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`) verwendet.</span><span class="sxs-lookup"><span data-stu-id="524e5-106">In previous .NET Core versions, WinForms and WPF apps used a separate [project SDK](../../../project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span> <span data-ttu-id="524e5-107">Ab .NET 5.0 wird das SDK für WinForms- und WPF-Apps mit dem .NET SDK (`Microsoft.NET.Sdk`) vereinheitlicht.</span><span class="sxs-lookup"><span data-stu-id="524e5-107">Starting in .NET 5.0, the WinForms and WPF SDK has been unified with the .NET SDK (`Microsoft.NET.Sdk`).</span></span> <span data-ttu-id="524e5-108">Außerdem ersetzt der neue [Zielframeworkmoniker (TFM)](../../../../standard/frameworks.md) `netcoreapp` und `netstandard` in .NET 5.</span><span class="sxs-lookup"><span data-stu-id="524e5-108">In addition, new [target framework monikers (TFM)](../../../../standard/frameworks.md) replace `netcoreapp` and `netstandard` in .NET 5.</span></span> <span data-ttu-id="524e5-109">Im folgenden Beispiel werden die Änderungen veranschaulicht, die für eine WPF-Projektdatei erforderlich sind, wenn Sie erneut auf .NET 5.0 oder höher abzielen.</span><span class="sxs-lookup"><span data-stu-id="524e5-109">The following example shows the changes you'd need to make for a WPF project file when retargeting to .NET 5.0 or later.</span></span>

<span data-ttu-id="524e5-110">In früheren .NET Core-Versionen:</span><span class="sxs-lookup"><span data-stu-id="524e5-110">In previous .NET Core versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="524e5-111">In .NET 5.0 und höher:</span><span class="sxs-lookup"><span data-stu-id="524e5-111">In .NET 5.0 and later versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

## <a name="version-introduced"></a><span data-ttu-id="524e5-112">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="524e5-112">Version introduced</span></span>

<span data-ttu-id="524e5-113">.NET SDK 5.0.100</span><span class="sxs-lookup"><span data-stu-id="524e5-113">.NET SDK 5.0.100</span></span>

## <a name="recommended-action"></a><span data-ttu-id="524e5-114">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="524e5-114">Recommended action</span></span>

<span data-ttu-id="524e5-115">In WPF- oder Windows Forms-Projektdateien:</span><span class="sxs-lookup"><span data-stu-id="524e5-115">In your WPF or Windows Forms project file:</span></span>

- <span data-ttu-id="524e5-116">Aktualisieren Sie das `Sdk`-Attribut auf `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="524e5-116">Update the `Sdk` attribute  to `Microsoft.NET.Sdk`.</span></span>
- <span data-ttu-id="524e5-117">Aktualisieren Sie die `TargetFramework`-Eigenschaft auf `net5.0-windows`.</span><span class="sxs-lookup"><span data-stu-id="524e5-117">Update the `TargetFramework` property to `net5.0-windows`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="524e5-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="524e5-118">Affected APIs</span></span>

<span data-ttu-id="524e5-119">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="524e5-119">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
