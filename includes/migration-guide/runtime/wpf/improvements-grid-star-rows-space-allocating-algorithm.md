---
ms.openlocfilehash: 415eb1960c20fb662469e126560d6f366309eb0d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496495"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="89774-101">Verbesserungen für den Algorithmus zur Speicherplatzreservierung bei Grid-Sternzeilen</span><span class="sxs-lookup"><span data-stu-id="89774-101">Improvements to Grid star-rows space allocating algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="89774-102">Details</span><span class="sxs-lookup"><span data-stu-id="89774-102">Details</span></span>

<span data-ttu-id="89774-103">Es wurde ein Fehler im [Algorithmus zur Größenzuordnung ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) behoben, der in einem <xref:System.Windows.Controls.Grid> in .NET Framework 4.7 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="89774-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="89774-104">Wenn ein Grid dieser Art mit <code>Height=&quot;Auto&quot;</code> leere Zeilen enthielt, wurden Zeilen gelegentlich an der falschen Position, möglicherweise sogar außerhalb des Grids angeordnet.</span><span class="sxs-lookup"><span data-stu-id="89774-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="89774-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="89774-105">Suggestion</span></span>

<span data-ttu-id="89774-106">Damit die Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.8 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="89774-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>

| <span data-ttu-id="89774-107">name</span><span class="sxs-lookup"><span data-stu-id="89774-107">Name</span></span>    | <span data-ttu-id="89774-108">Wert</span><span class="sxs-lookup"><span data-stu-id="89774-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="89774-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="89774-109">Scope</span></span>   |<span data-ttu-id="89774-110">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="89774-110">Major</span></span>|
|<span data-ttu-id="89774-111">Version</span><span class="sxs-lookup"><span data-stu-id="89774-111">Version</span></span>|<span data-ttu-id="89774-112">4.8</span><span class="sxs-lookup"><span data-stu-id="89774-112">4.8</span></span>|
|<span data-ttu-id="89774-113">Typ</span><span class="sxs-lookup"><span data-stu-id="89774-113">Type</span></span>|<span data-ttu-id="89774-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="89774-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="89774-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="89774-115">Affected APIs</span></span>

<span data-ttu-id="89774-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="89774-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
