---
ms.openlocfilehash: 8e0c934cd8c3cb8c08a526c7e145436db6ecf4a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "68237618"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="86882-101">Verbesserungen für den Algorithmus zur Speicherplatzreservierung bei Grid-Sternzeilen</span><span class="sxs-lookup"><span data-stu-id="86882-101">Improvements to Grid star-rows space allocating algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="86882-102">Details</span><span class="sxs-lookup"><span data-stu-id="86882-102">Details</span></span>|<span data-ttu-id="86882-103">Es wurde ein Fehler im [Algorithmus zur Größenzuordnung ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) behoben, der in einem <xref:System.Windows.Controls.Grid> in .NET Framework 4.7 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="86882-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="86882-104">Wenn ein Grid dieser Art mit <code>Height=&quot;Auto&quot;</code> leere Zeilen enthielt, wurden Zeilen gelegentlich an der falschen Position, möglicherweise sogar außerhalb des Grids angeordnet.</span><span class="sxs-lookup"><span data-stu-id="86882-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>|
|<span data-ttu-id="86882-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="86882-105">Suggestion</span></span>|<span data-ttu-id="86882-106">Damit die Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.8 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="86882-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>|
|<span data-ttu-id="86882-107">`Scope`</span><span class="sxs-lookup"><span data-stu-id="86882-107">Scope</span></span>|<span data-ttu-id="86882-108">Major</span><span class="sxs-lookup"><span data-stu-id="86882-108">Major</span></span>|
|<span data-ttu-id="86882-109">Version</span><span class="sxs-lookup"><span data-stu-id="86882-109">Version</span></span>|<span data-ttu-id="86882-110">4.8</span><span class="sxs-lookup"><span data-stu-id="86882-110">4.8</span></span>|
|<span data-ttu-id="86882-111">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="86882-111">Type</span></span>|<span data-ttu-id="86882-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="86882-112">Runtime</span></span>|
