---
ms.openlocfilehash: c3114277445daaae988b41782721c443c1e780d1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497475"
---
### <a name="wpf-spawns-a-wisptisexe-process-which-can-freeze-the-mouse"></a><span data-ttu-id="a9948-101">WPF erzeugt einen „wiptis.exe“-Prozess, der die Maus sperren kann</span><span class="sxs-lookup"><span data-stu-id="a9948-101">WPF spawns a wisptis.exe process which can freeze the mouse</span></span>

#### <a name="details"></a><span data-ttu-id="a9948-102">Details</span><span class="sxs-lookup"><span data-stu-id="a9948-102">Details</span></span>

<span data-ttu-id="a9948-103">Mit Version 4.5.2 wurde ein Problem eingeführt, durch das <code>wisptis.exe</code> erzeugt wird. Hierdurch kann die Mauseingabe gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="a9948-103">An issue was introduced in 4.5.2 that causes <code>wisptis.exe</code> to be spawned that can freeze mouse input.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a9948-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a9948-104">Suggestion</span></span>

<span data-ttu-id="a9948-105">Eine Problembehebung steht in einem Service Release von .NET Framework 4.5.2 (Hotfixrollup 3026376) oder durch ein Upgrade auf .NET Framework 4.6 zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a9948-105">A fix for this issue is available in a servicing release of the .NET Framework 4.5.2 (hotfix rollup 3026376), or by upgrading to the .NET Framework 4.6</span></span>

| <span data-ttu-id="a9948-106">name</span><span class="sxs-lookup"><span data-stu-id="a9948-106">Name</span></span>    | <span data-ttu-id="a9948-107">Wert</span><span class="sxs-lookup"><span data-stu-id="a9948-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a9948-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="a9948-108">Scope</span></span>   |<span data-ttu-id="a9948-109">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="a9948-109">Major</span></span>|
|<span data-ttu-id="a9948-110">Version</span><span class="sxs-lookup"><span data-stu-id="a9948-110">Version</span></span>|<span data-ttu-id="a9948-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="a9948-111">4.5.2</span></span>|
|<span data-ttu-id="a9948-112">Typ</span><span class="sxs-lookup"><span data-stu-id="a9948-112">Type</span></span>|<span data-ttu-id="a9948-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a9948-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a9948-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a9948-114">Affected APIs</span></span>

<span data-ttu-id="a9948-115">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="a9948-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
