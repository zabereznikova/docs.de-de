---
ms.openlocfilehash: d4e60f2a59980263916718ebcc71cc359952c031
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497257"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a><span data-ttu-id="950cc-101">Die WPF-Rechtschreibprüfungs-API schlägt auf unerwartete Weise fehl</span><span class="sxs-lookup"><span data-stu-id="950cc-101">WPF Spell Checking fails in unexpected ways</span></span>

#### <a name="details"></a><span data-ttu-id="950cc-102">Details</span><span class="sxs-lookup"><span data-stu-id="950cc-102">Details</span></span>

<span data-ttu-id="950cc-103">Dies umfasst eine Reihe von Problemen mit der WPF-Rechtschreibprüfungs-API:</span><span class="sxs-lookup"><span data-stu-id="950cc-103">This includes a number of WPF Spell Checker issues:</span></span><ul><li><span data-ttu-id="950cc-104">Die WPF-Rechtschreibprüfungs-API löst manchmal <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName> aus</span><span class="sxs-lookup"><span data-stu-id="950cc-104">WPF Spell Checker sometimes throws <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName></span></span></li><li><span data-ttu-id="950cc-105">Die WPF-Rechtschreibprüfungs-API schlägt mit der Ausnahme <xref:System.UnauthorizedAccessException> fehl, wenn Anwendungen mit der Einstellung „Als anderer Benutzer ausführen“ gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="950cc-105">WPF Spell Checker fails with <xref:System.UnauthorizedAccessException> when applications are launched using 'run as different user'</span></span></li><li><span data-ttu-id="950cc-106">Die WPF-Rechtschreibprüfungs-API erkennt fälschlicherweise Rechtschreibfehler in zusammengesetzten deutschen Wörtern wie „Hausnummer“.</span><span class="sxs-lookup"><span data-stu-id="950cc-106">WPF Spell Checker incorrectly identifies spelling errors in compound words like 'Hausnummer' in German.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="950cc-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="950cc-107">Suggestion</span></span>

<span data-ttu-id="950cc-108">Problem 1: wurde in .NET Framework 4.6.2 behoben. Problem 2: Die WPF-Rechtschreibprüfungs-API wird nicht mehr unterstützt, wenn Anwendungen mit der Einstellung „Als anderer Benutzer ausführen“ gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="950cc-108">Issue #1 - This has been fixed in .NET Framework 4.6.2 Issue #2 - WPF Spell Checker is no longer supported when applications are launched using 'run as different user'.</span></span> <span data-ttu-id="950cc-109">Ab .NET Framework 4.6.2 stürzen Anwendungen, die auf diese Weise gestartet werden, nicht mehr unerwartet ab. Stattdessen wird nur die Rechtschreibprüfungs-API im Hintergrund deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="950cc-109">Starting .NET Framework 4.6.2, applications launched in this manner will no longer crash unexpectedly - instead the Spell Checker will be silently disabled.</span></span> <span data-ttu-id="950cc-110">Problem 3: wurde in .NET Framework 4.6.2 behoben.</span><span class="sxs-lookup"><span data-stu-id="950cc-110">Issue #3 - This has been fixed in .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="950cc-111">name</span><span class="sxs-lookup"><span data-stu-id="950cc-111">Name</span></span>    | <span data-ttu-id="950cc-112">Wert</span><span class="sxs-lookup"><span data-stu-id="950cc-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="950cc-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="950cc-113">Scope</span></span>   |<span data-ttu-id="950cc-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="950cc-114">Edge</span></span>|
|<span data-ttu-id="950cc-115">Version</span><span class="sxs-lookup"><span data-stu-id="950cc-115">Version</span></span>|<span data-ttu-id="950cc-116">4.6.1</span><span class="sxs-lookup"><span data-stu-id="950cc-116">4.6.1</span></span>|
|<span data-ttu-id="950cc-117">Typ</span><span class="sxs-lookup"><span data-stu-id="950cc-117">Type</span></span>|<span data-ttu-id="950cc-118">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="950cc-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="950cc-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="950cc-119">Affected APIs</span></span>

<span data-ttu-id="950cc-120">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="950cc-120">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
