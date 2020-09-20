---
ms.openlocfilehash: 975e331ad3e7bd7e0e8f49b62795c6acc7031ca9
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656337"
---
### <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a><span data-ttu-id="8225d-101">WinForms- und WPF-Apps verwenden Microsoft.NET.Sdk</span><span class="sxs-lookup"><span data-stu-id="8225d-101">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>

<span data-ttu-id="8225d-102">Windows Forms- und WPF-Apps (Windows Presentation Framework) verwenden jetzt das .NET SDK (`Microsoft.NET.Sdk`) anstelle des .NET Core SDK für WinForms- und WPF-Apps (`Microsoft.NET.Sdk.WindowsDesktop`).</span><span class="sxs-lookup"><span data-stu-id="8225d-102">Windows Forms and Windows Presentation Framework (WPF) apps now use the .NET SDK (`Microsoft.NET.Sdk`) instead of the .NET Core WinForms and WPF SDK (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span>

#### <a name="change-description"></a><span data-ttu-id="8225d-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="8225d-103">Change description</span></span>

<span data-ttu-id="8225d-104">In vorherigen .NET Core-Versionen haben WinForms- und WPF-Apps ein separates [Projekt-SDK](../../../../docs/core/project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`) verwendet.</span><span class="sxs-lookup"><span data-stu-id="8225d-104">In previous .NET Core versions, WinForms and WPF apps used a separate [project SDK](../../../../docs/core/project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span> <span data-ttu-id="8225d-105">Ab .NET 5.0 wird das SDK für WinForms- und WPF-Apps mit dem .NET SDK (`Microsoft.NET.Sdk`) vereinheitlicht.</span><span class="sxs-lookup"><span data-stu-id="8225d-105">Starting in .NET 5.0, the WinForms and WPF SDK has been unified with the .NET SDK (`Microsoft.NET.Sdk`).</span></span> <span data-ttu-id="8225d-106">Außerdem ersetzt der neue [Zielframeworkmoniker (TFM)](../../../../docs/standard/frameworks.md) `netcoreapp` und `netstandard` in .NET 5.</span><span class="sxs-lookup"><span data-stu-id="8225d-106">In addition, new [target framework monikers (TFM)](../../../../docs/standard/frameworks.md) replace `netcoreapp` and `netstandard` in .NET 5.</span></span> <span data-ttu-id="8225d-107">Im folgenden Beispiel werden die Änderungen veranschaulicht, die für eine WPF-Projektdatei erforderlich sind, wenn Sie erneut auf .NET 5.0 oder höher abzielen.</span><span class="sxs-lookup"><span data-stu-id="8225d-107">The following example shows the changes you'd need to make for a WPF project file when retargeting to .NET 5.0 or later.</span></span>

<span data-ttu-id="8225d-108">In früheren .NET Core-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8225d-108">In previous .NET Core versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="8225d-109">In .NET 5.0 und höher:</span><span class="sxs-lookup"><span data-stu-id="8225d-109">In .NET 5.0 and later versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

#### <a name="version-introduced"></a><span data-ttu-id="8225d-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="8225d-110">Version introduced</span></span>

<span data-ttu-id="8225d-111">.NET Core 5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="8225d-111">.NET 5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8225d-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="8225d-112">Recommended action</span></span>

<span data-ttu-id="8225d-113">In WPF- oder Windows Forms-Projektdateien:</span><span class="sxs-lookup"><span data-stu-id="8225d-113">In your WPF or Windows Forms project file:</span></span>

- <span data-ttu-id="8225d-114">Aktualisieren Sie das `Sdk`-Attribut auf `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="8225d-114">Update the `Sdk` attribute  to `Microsoft.NET.Sdk`.</span></span>
- <span data-ttu-id="8225d-115">Aktualisieren Sie die `TargetFramework`-Eigenschaft auf `net5.0-windows`.</span><span class="sxs-lookup"><span data-stu-id="8225d-115">Update the `TargetFramework` property to `net5.0-windows`.</span></span>

#### <a name="category"></a><span data-ttu-id="8225d-116">Kategorie</span><span class="sxs-lookup"><span data-stu-id="8225d-116">Category</span></span>

- <span data-ttu-id="8225d-117">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8225d-117">Windows Forms</span></span>
- <span data-ttu-id="8225d-118">Windows Presentation Framework (WPF)</span><span class="sxs-lookup"><span data-stu-id="8225d-118">Windows Presentation Framework (WPF)</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8225d-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="8225d-119">Affected APIs</span></span>

<span data-ttu-id="8225d-120">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="8225d-120">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
