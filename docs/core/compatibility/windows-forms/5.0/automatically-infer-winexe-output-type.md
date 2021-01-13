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
# <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a><span data-ttu-id="d894a-103">OutputType für WPF- und WinForms-Apps auf WinExe festgelegt</span><span class="sxs-lookup"><span data-stu-id="d894a-103">OutputType set to WinExe for WPF and WinForms apps</span></span>

<span data-ttu-id="d894a-104">`OutputType` wird für Windows Presentation Foundation- und Windows Forms-Apps automatisch auf `WinExe` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d894a-104">`OutputType` is automatically set to `WinExe` for Windows Presentation Foundation (WPF) and Windows Forms apps.</span></span> <span data-ttu-id="d894a-105">Wenn `OutputType` auf `WinExe` festgelegt ist, wird ein Konsolenfenster nicht geöffnet, sobald die App ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d894a-105">When `OutputType` is set to `WinExe`, a console window doesn't open when the app is executed.</span></span>

## <a name="change-description"></a><span data-ttu-id="d894a-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="d894a-106">Change description</span></span>

<span data-ttu-id="d894a-107">In früheren Versionen des .NET SDK wird der Wert verwendet, der in der Projektdatei für `OutputType` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d894a-107">In previous versions of the .NET SDK, the value that's specified for `OutputType` in the project file is used.</span></span> <span data-ttu-id="d894a-108">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d894a-108">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="d894a-109">Ab Version 5.0.100 des .NET SDK ist `OutputType` für WPF- und Windows Forms-Apps für alle Frameworkversionen, einschließlich des .NET Framework, automatisch auf `WinExe` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d894a-109">Starting in the 5.0.100 version of the .NET SDK, `OutputType` is automatically set to `WinExe` for WPF and Windows Forms apps that target any framework version, including .NET Framework.</span></span> <span data-ttu-id="d894a-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d894a-110">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

## <a name="reason-for-change"></a><span data-ttu-id="d894a-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="d894a-111">Reason for change</span></span>

<span data-ttu-id="d894a-112">Es wird angenommen, dass die meisten Benutzer nicht möchten, dass beim Ausführen einer Windows Presentation Foundation- oder Windows Forms-App ein Konsolenfenster geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="d894a-112">It's assumed that most users don't want a console window to open when a WPF or Windows Forms app is executed.</span></span> <span data-ttu-id="d894a-113">Darüber hinaus wird [jetzt, da diese Anwendungstypen das .NET SDK](sdk-and-target-framework-change.md) anstelle des Windows Desktop SDK verwenden, die richtige Standardeinstellung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d894a-113">In addition, [now that these application types use the .NET SDK](sdk-and-target-framework-change.md) instead of the Windows Desktop SDK, the correct default will be set.</span></span> <span data-ttu-id="d894a-114">Wenn darüber hinaus Unterstützung für iOS und Android hinzugefügt wird, wird es einfacher, mehrere Plattformen gleichzeitig als Ziel zu wählen, sofern alle den gleichen Ausgabetyp verwenden.</span><span class="sxs-lookup"><span data-stu-id="d894a-114">Further, when support for targeting iOS and Android is added, it will be easier to multi-target between multiple platforms if they all use the same output type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d894a-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d894a-115">Version introduced</span></span>

<span data-ttu-id="d894a-116">.NET 5.0.100</span><span class="sxs-lookup"><span data-stu-id="d894a-116">.NET 5.0.100</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d894a-117">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="d894a-117">Recommended action</span></span>

<span data-ttu-id="d894a-118">Ihrerseits müssen Sie nichts tun.</span><span class="sxs-lookup"><span data-stu-id="d894a-118">No action is required in your part.</span></span> <span data-ttu-id="d894a-119">Wenn Sie jedoch zum alten Verhalten zurückkehren möchten, legen Sie die Eigenschaft `DisableWinExeOutputInference` in Ihrer Projektdatei auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="d894a-119">However, if you want to revert to the old behavior, set the `DisableWinExeOutputInference` property to `true` in your project file.</span></span>

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

## <a name="affected-apis"></a><span data-ttu-id="d894a-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d894a-120">Affected APIs</span></span>

<span data-ttu-id="d894a-121">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="d894a-121">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
