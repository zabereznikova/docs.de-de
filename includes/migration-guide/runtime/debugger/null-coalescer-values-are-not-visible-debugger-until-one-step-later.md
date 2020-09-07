---
ms.openlocfilehash: af8de731ee93d0bfb01042d894f5730570dcdd78
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497137"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="45f9d-101">NULL-Zusammenfügungswerte werden erst im nächsten Schritt angezeigt</span><span class="sxs-lookup"><span data-stu-id="45f9d-101">Null coalescer values are not visible in debugger until one step later</span></span>

#### <a name="details"></a><span data-ttu-id="45f9d-102">Details</span><span class="sxs-lookup"><span data-stu-id="45f9d-102">Details</span></span>

<span data-ttu-id="45f9d-103">Durch einen Fehler in .NET Framework 4.5 werden Werte, die über einen zusammenfügenden NULL-Vorgang festgelegt werden, nicht unmittelbar im Anschluss an die Zuweisung im Debugger angezeigt, wenn sie auf einer 64-Bit-Version des Frameworks ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="45f9d-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="45f9d-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="45f9d-104">Suggestion</span></span>

<span data-ttu-id="45f9d-105">Wenn Sie im Debugger einen zusätzlichen Schritt ausführen, wird der lokale Wert bzw. der Feldwert ohne Probleme aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="45f9d-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="45f9d-106">Dieses Problem wurde auch in .NET Framework 4.6 behoben und sollte nach einem Upgrade auf diese Version nicht mehr auftreten.</span><span class="sxs-lookup"><span data-stu-id="45f9d-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>

| <span data-ttu-id="45f9d-107">name</span><span class="sxs-lookup"><span data-stu-id="45f9d-107">Name</span></span>    | <span data-ttu-id="45f9d-108">Wert</span><span class="sxs-lookup"><span data-stu-id="45f9d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="45f9d-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="45f9d-109">Scope</span></span>   |<span data-ttu-id="45f9d-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="45f9d-110">Edge</span></span>|
|<span data-ttu-id="45f9d-111">Version</span><span class="sxs-lookup"><span data-stu-id="45f9d-111">Version</span></span>|<span data-ttu-id="45f9d-112">4.5</span><span class="sxs-lookup"><span data-stu-id="45f9d-112">4.5</span></span>|
|<span data-ttu-id="45f9d-113">Typ</span><span class="sxs-lookup"><span data-stu-id="45f9d-113">Type</span></span>|<span data-ttu-id="45f9d-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="45f9d-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="45f9d-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="45f9d-115">Affected APIs</span></span>

<span data-ttu-id="45f9d-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="45f9d-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
