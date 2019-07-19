---
ms.openlocfilehash: 770e303ab261b97efb49a3e0865a015d8de33247
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802721"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="7b41b-101">Verbesserungen für den Algorithmus zur Speicherplatzreservierung bei Grid-Sternzeilen</span><span class="sxs-lookup"><span data-stu-id="7b41b-101">Improvements to Grid star-rows space allocating algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7b41b-102">Details</span><span class="sxs-lookup"><span data-stu-id="7b41b-102">Details</span></span>|<span data-ttu-id="7b41b-103">Es wurde ein Fehler im [Algorithmus zur Größenzuordnung ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) behoben, der in einem <xref:System.Windows.Controls.Grid> in .NET Framework 4.7 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7b41b-103">Fixed a bug in the [algorithm for allocating sizes to ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="7b41b-104">Wenn ein Grid dieser Art mit <code>Height=&quot;Auto&quot;</code> leere Zeilen enthielt, wurden Zeilen gelegentlich an der falschen Position, möglicherweise sogar außerhalb des Grids angeordnet.</span><span class="sxs-lookup"><span data-stu-id="7b41b-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>|
|<span data-ttu-id="7b41b-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="7b41b-105">Suggestion</span></span>|<span data-ttu-id="7b41b-106">Damit die Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.8 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7b41b-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>|
|<span data-ttu-id="7b41b-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="7b41b-107">Scope</span></span>|<span data-ttu-id="7b41b-108">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="7b41b-108">Major</span></span>|
|<span data-ttu-id="7b41b-109">Version</span><span class="sxs-lookup"><span data-stu-id="7b41b-109">Version</span></span>|<span data-ttu-id="7b41b-110">4.8</span><span class="sxs-lookup"><span data-stu-id="7b41b-110">4.8</span></span>|
|<span data-ttu-id="7b41b-111">Typ</span><span class="sxs-lookup"><span data-stu-id="7b41b-111">Type</span></span>|<span data-ttu-id="7b41b-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7b41b-112">Runtime</span></span>|

