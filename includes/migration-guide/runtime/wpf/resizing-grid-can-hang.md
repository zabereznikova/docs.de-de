---
ms.openlocfilehash: 8dc1b4d94d01813a8124d1340b50fa78a9b157f8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497427"
---
### <a name="resizing-a-grid-can-hang"></a><span data-ttu-id="a74ee-101">Die Änderung der Größe eines Rasters kann zu einem Absturz führen</span><span class="sxs-lookup"><span data-stu-id="a74ee-101">Resizing a Grid can hang</span></span>

#### <a name="details"></a><span data-ttu-id="a74ee-102">Details</span><span class="sxs-lookup"><span data-stu-id="a74ee-102">Details</span></span>

<span data-ttu-id="a74ee-103">Beim Anpassen des Layouts eines <code>T:System.Windows.Controls.Grid</code>-Rasters kann in den folgenden Situationen eine Endlosschleife entstehen:</span><span class="sxs-lookup"><span data-stu-id="a74ee-103">An infinite loop can occur during layout of a <code>T:System.Windows.Controls.Grid</code> under the following circumstances:</span></span><ul><li><span data-ttu-id="a74ee-104">Die Zeilendefinitionen enthalten zwei \*-Zeilen, die jeweils einen MinHeight- und einen MaxHeight-Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="a74ee-104">Row definitions contain two \*-rows, both declaring a MinHeight and a MaxHeight.</span></span></li><li><span data-ttu-id="a74ee-105">Der Inhalt der \*-Zeilen übersteigt den MaxHeight-Wert nicht</span><span class="sxs-lookup"><span data-stu-id="a74ee-105">Content of the \*-rows doesn't exceed the corresponding MaxHeight</span></span></li><li><span data-ttu-id="a74ee-106">Die verfügbare Höhe des Rasters liegt unterhalb des ersten MinHeight-Werts (dies gilt auch für sämtliche anderen festgelegten oder automatisch generierten Zeilen)</span><span class="sxs-lookup"><span data-stu-id="a74ee-106">The Grid's available height is exceeded by the first MinHeight (plus any other fixed or Auto rows)</span></span></li><li><span data-ttu-id="a74ee-107">Die App ist auf .NET Framework 4.7 ausgelegt oder aktiviert den Zuweisungsalgorithmus der Version 4.7, indem sie die Einstellung <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code> festlegt.</span><span class="sxs-lookup"><span data-stu-id="a74ee-107">The app targets .NET Framework 4.7, or opts in to the 4.7 allocation algorithm by setting <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code></span></span></li></ul><span data-ttu-id="a74ee-108">Eine Endlosschleife würde auch entstehen, wenn es mehr als zwei Zeilen oder Spalten gäbe.</span><span class="sxs-lookup"><span data-stu-id="a74ee-108">The loop would also happen with more than two rows, or in the analogous case for columns.</span></span> <span data-ttu-id="a74ee-109">Dieses Problem wurde in .NET Framework 4.7.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="a74ee-109">The issue is fixed in .NET Framework 4.7.1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a74ee-110">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a74ee-110">Suggestion</span></span>

<span data-ttu-id="a74ee-111">Upgrade auf .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="a74ee-111">Upgrade to .NET Framework 4.7.1.</span></span>  <span data-ttu-id="a74ee-112">Wenn Sie hingegen den .NET 4.7-Zuweisungsalgorithmus nicht benötigen, können Sie auch die folgenden Konfigurationseinstellungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="a74ee-112">Alternatively, if you don't need the 4.7 allocation algorithm you can use the following configuration setting:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="a74ee-113">Name</span><span class="sxs-lookup"><span data-stu-id="a74ee-113">Name</span></span>    | <span data-ttu-id="a74ee-114">Wert</span><span class="sxs-lookup"><span data-stu-id="a74ee-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a74ee-115">Bereich</span><span class="sxs-lookup"><span data-stu-id="a74ee-115">Scope</span></span>   |<span data-ttu-id="a74ee-116">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a74ee-116">Edge</span></span>|
|<span data-ttu-id="a74ee-117">Version</span><span class="sxs-lookup"><span data-stu-id="a74ee-117">Version</span></span>|<span data-ttu-id="a74ee-118">4.7</span><span class="sxs-lookup"><span data-stu-id="a74ee-118">4.7</span></span>|
|<span data-ttu-id="a74ee-119">Typ</span><span class="sxs-lookup"><span data-stu-id="a74ee-119">Type</span></span>|<span data-ttu-id="a74ee-120">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a74ee-120">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a74ee-121">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a74ee-121">Affected APIs</span></span>

<span data-ttu-id="a74ee-122">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="a74ee-122">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
