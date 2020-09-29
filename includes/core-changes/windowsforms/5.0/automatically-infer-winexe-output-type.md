---
ms.openlocfilehash: 54bee14f6de409550357194e905b6ee5d8ef8f18
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "90678997"
---
### <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a><span data-ttu-id="b1f7b-101">OutputType für WPF- und WinForms-Apps auf WinExe festgelegt</span><span class="sxs-lookup"><span data-stu-id="b1f7b-101">OutputType set to WinExe for WPF and WinForms apps</span></span>

<span data-ttu-id="b1f7b-102">`OutputType` wird für Windows Presentation Foundation- und Windows Forms-Apps automatisch auf `WinExe` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b1f7b-102">`OutputType` is automatically set to `WinExe` for Windows Presentation Foundation (WPF) and Windows Forms apps.</span></span> <span data-ttu-id="b1f7b-103">Wenn `OutputType` auf `WinExe` festgelegt ist, wird ein Konsolenfenster nicht geöffnet, sobald die App ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b1f7b-103">When `OutputType` is set to `WinExe`, a console window doesn't open when the app is executed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b1f7b-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="b1f7b-104">Change description</span></span>

<span data-ttu-id="b1f7b-105">In früheren Versionen von .NET wird der Wert verwendet, der in der Projektdatei für `OutputType` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="b1f7b-105">In previous versions of .NET, the value that's specified for `OutputType` in the project file is used.</span></span> <span data-ttu-id="b1f7b-106">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b1f7b-106">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="b1f7b-107">Ab .NET 5.0 wird `OutputType` für Windows Presentation Foundation- und Windows Forms-Anwendungen automatisch auf `WinExe` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b1f7b-107">Starting in .NET 5.0, `OutputType` is automatically set to `WinExe` for WPF and Windows Forms apps.</span></span> <span data-ttu-id="b1f7b-108">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b1f7b-108">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

#### <a name="reason-for-change"></a><span data-ttu-id="b1f7b-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="b1f7b-109">Reason for change</span></span>

<span data-ttu-id="b1f7b-110">Es wird angenommen, dass die meisten Benutzer nicht möchten, dass beim Ausführen einer Windows Presentation Foundation- oder Windows Forms-App ein Konsolenfenster geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="b1f7b-110">It's assumed that most users don't want a console window to open when a WPF or Windows Forms app is executed.</span></span> <span data-ttu-id="b1f7b-111">Darüber hinaus wird [jetzt, da diese Anwendungstypen das .NET SDK](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) anstelle des Windows Desktop SDK verwenden, die richtige Standardeinstellung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b1f7b-111">In addition, [now that these application types use the .NET SDK](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) instead of the Windows Desktop SDK, the correct default will be set.</span></span> <span data-ttu-id="b1f7b-112">Wenn darüber hinaus Unterstützung für iOS und Android hinzugefügt wird, wird es einfacher, mehrere Plattformen gleichzeitig als Ziel zu wählen, sofern alle den gleichen Ausgabetyp verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1f7b-112">Further, when support for targeting iOS and Android is added, it will be easier to multi-target between multiple platforms if they all use the same output type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b1f7b-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="b1f7b-113">Version introduced</span></span>

<span data-ttu-id="b1f7b-114">.NET Core 5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="b1f7b-114">.NET 5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b1f7b-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="b1f7b-115">Recommended action</span></span>

<span data-ttu-id="b1f7b-116">Ihrerseits müssen Sie nichts tun.</span><span class="sxs-lookup"><span data-stu-id="b1f7b-116">No action is required in your part.</span></span> <span data-ttu-id="b1f7b-117">Wenn Sie jedoch zum alten Verhalten zurückkehren möchten, legen Sie die Eigenschaft `DisableWinExeOutputInference` in Ihrer Projektdatei auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="b1f7b-117">However, if you want to revert to the old behavior, set the `DisableWinExeOutputInference` property to `true` in your project file.</span></span>

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

#### <a name="category"></a><span data-ttu-id="b1f7b-118">Kategorie</span><span class="sxs-lookup"><span data-stu-id="b1f7b-118">Category</span></span>

- <span data-ttu-id="b1f7b-119">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1f7b-119">Windows Forms</span></span>
- <span data-ttu-id="b1f7b-120">Windows Presentation Framework (WPF)</span><span class="sxs-lookup"><span data-stu-id="b1f7b-120">Windows Presentation Framework (WPF)</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b1f7b-121">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b1f7b-121">Affected APIs</span></span>

<span data-ttu-id="b1f7b-122">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="b1f7b-122">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
