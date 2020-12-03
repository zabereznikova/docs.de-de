---
title: 'Breaking Change: OutputType für WPF- und WinForms-Apps auf WinExe festgelegt'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, bei dem OutputType für Windows Forms-Apps automatisch auf WinExe festgelegt wird.
ms.date: 09/18/2020
ms.openlocfilehash: 072c5b11c8304eb540e176ce9747930789f28505
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759548"
---
# <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a><span data-ttu-id="bd2b0-103">OutputType für WPF- und WinForms-Apps auf WinExe festgelegt</span><span class="sxs-lookup"><span data-stu-id="bd2b0-103">OutputType set to WinExe for WPF and WinForms apps</span></span>

<span data-ttu-id="bd2b0-104">`OutputType` wird für Windows Presentation Foundation- und Windows Forms-Apps automatisch auf `WinExe` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bd2b0-104">`OutputType` is automatically set to `WinExe` for Windows Presentation Foundation (WPF) and Windows Forms apps.</span></span> <span data-ttu-id="bd2b0-105">Wenn `OutputType` auf `WinExe` festgelegt ist, wird ein Konsolenfenster nicht geöffnet, sobald die App ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bd2b0-105">When `OutputType` is set to `WinExe`, a console window doesn't open when the app is executed.</span></span>

## <a name="change-description"></a><span data-ttu-id="bd2b0-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="bd2b0-106">Change description</span></span>

<span data-ttu-id="bd2b0-107">In früheren Versionen von .NET wird der Wert verwendet, der in der Projektdatei für `OutputType` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="bd2b0-107">In previous versions of .NET, the value that's specified for `OutputType` in the project file is used.</span></span> <span data-ttu-id="bd2b0-108">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bd2b0-108">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="bd2b0-109">Ab .NET 5.0 wird `OutputType` für Windows Presentation Foundation- und Windows Forms-Anwendungen automatisch auf `WinExe` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bd2b0-109">Starting in .NET 5.0, `OutputType` is automatically set to `WinExe` for WPF and Windows Forms apps.</span></span> <span data-ttu-id="bd2b0-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bd2b0-110">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

## <a name="reason-for-change"></a><span data-ttu-id="bd2b0-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="bd2b0-111">Reason for change</span></span>

<span data-ttu-id="bd2b0-112">Es wird angenommen, dass die meisten Benutzer nicht möchten, dass beim Ausführen einer Windows Presentation Foundation- oder Windows Forms-App ein Konsolenfenster geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="bd2b0-112">It's assumed that most users don't want a console window to open when a WPF or Windows Forms app is executed.</span></span> <span data-ttu-id="bd2b0-113">Darüber hinaus wird [jetzt, da diese Anwendungstypen das .NET SDK](sdk-and-target-framework-change.md) anstelle des Windows Desktop SDK verwenden, die richtige Standardeinstellung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bd2b0-113">In addition, [now that these application types use the .NET SDK](sdk-and-target-framework-change.md) instead of the Windows Desktop SDK, the correct default will be set.</span></span> <span data-ttu-id="bd2b0-114">Wenn darüber hinaus Unterstützung für iOS und Android hinzugefügt wird, wird es einfacher, mehrere Plattformen gleichzeitig als Ziel zu wählen, sofern alle den gleichen Ausgabetyp verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd2b0-114">Further, when support for targeting iOS and Android is added, it will be easier to multi-target between multiple platforms if they all use the same output type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="bd2b0-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="bd2b0-115">Version introduced</span></span>

<span data-ttu-id="bd2b0-116">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="bd2b0-116">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="bd2b0-117">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="bd2b0-117">Recommended action</span></span>

<span data-ttu-id="bd2b0-118">Ihrerseits müssen Sie nichts tun.</span><span class="sxs-lookup"><span data-stu-id="bd2b0-118">No action is required in your part.</span></span> <span data-ttu-id="bd2b0-119">Wenn Sie jedoch zum alten Verhalten zurückkehren möchten, legen Sie die Eigenschaft `DisableWinExeOutputInference` in Ihrer Projektdatei auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="bd2b0-119">However, if you want to revert to the old behavior, set the `DisableWinExeOutputInference` property to `true` in your project file.</span></span>

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

## <a name="affected-apis"></a><span data-ttu-id="bd2b0-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="bd2b0-120">Affected APIs</span></span>

<span data-ttu-id="bd2b0-121">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="bd2b0-121">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
