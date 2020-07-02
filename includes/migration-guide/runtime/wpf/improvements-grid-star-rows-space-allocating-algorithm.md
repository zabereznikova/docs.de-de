---
ms.openlocfilehash: 62702de022656e45466a45f4150e518226a3fecc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621995"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="1696e-101">Verbesserungen für den Algorithmus zur Speicherplatzreservierung bei Grid-Sternzeilen</span><span class="sxs-lookup"><span data-stu-id="1696e-101">Improvements to Grid star-rows space allocating algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="1696e-102">Details</span><span class="sxs-lookup"><span data-stu-id="1696e-102">Details</span></span>

<span data-ttu-id="1696e-103">Es wurde ein Fehler im [Algorithmus zur Größenzuordnung ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) behoben, der in einem <xref:System.Windows.Controls.Grid> in .NET Framework 4.7 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1696e-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="1696e-104">Wenn ein Grid dieser Art mit <code>Height=&quot;Auto&quot;</code> leere Zeilen enthielt, wurden Zeilen gelegentlich an der falschen Position, möglicherweise sogar außerhalb des Grids angeordnet.</span><span class="sxs-lookup"><span data-stu-id="1696e-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1696e-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1696e-105">Suggestion</span></span>

<span data-ttu-id="1696e-106">Damit die Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.8 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1696e-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>

| <span data-ttu-id="1696e-107">name</span><span class="sxs-lookup"><span data-stu-id="1696e-107">Name</span></span>    | <span data-ttu-id="1696e-108">Wert</span><span class="sxs-lookup"><span data-stu-id="1696e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1696e-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="1696e-109">Scope</span></span>   |<span data-ttu-id="1696e-110">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="1696e-110">Major</span></span>|
|<span data-ttu-id="1696e-111">Version</span><span class="sxs-lookup"><span data-stu-id="1696e-111">Version</span></span>|<span data-ttu-id="1696e-112">4.8</span><span class="sxs-lookup"><span data-stu-id="1696e-112">4.8</span></span>|
|<span data-ttu-id="1696e-113">Typ</span><span class="sxs-lookup"><span data-stu-id="1696e-113">Type</span></span>|<span data-ttu-id="1696e-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1696e-114">Runtime</span></span>|
