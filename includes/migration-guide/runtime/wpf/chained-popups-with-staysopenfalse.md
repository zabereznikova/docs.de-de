---
ms.openlocfilehash: 7bf5f7e8a49acc2918dd0d68a1c54a5c277091b0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497668"
---
### <a name="chained-popups-with-staysopenfalse"></a><span data-ttu-id="35b99-101">Verkettete Popups mit „StaysOpen=FALSE“</span><span class="sxs-lookup"><span data-stu-id="35b99-101">Chained Popups with StaysOpen=False</span></span>

#### <a name="details"></a><span data-ttu-id="35b99-102">Details</span><span class="sxs-lookup"><span data-stu-id="35b99-102">Details</span></span>

<span data-ttu-id="35b99-103">Ein Popup mit „StaysOpen=FALSE“ sollte geschlossen werden, wenn Sie außerhalb des Popups klicken.</span><span class="sxs-lookup"><span data-stu-id="35b99-103">A Popup with StaysOpen=False is supposed to close when you click outside the Popup.</span></span> <span data-ttu-id="35b99-104">Wenn zwei oder mehr Popups verkettet sind (d.h. ein Popup enthält ein anderes), treten viele Probleme auf, unter anderem folgende:</span><span class="sxs-lookup"><span data-stu-id="35b99-104">When two or more such Popups are chained (i.e. one contains another), there were many problems, including:</span></span><ul><li><span data-ttu-id="35b99-105">Öffnen Sie zwei Ebenen. Klicken Sie außerhalb von P2, aber innerhalb von P1.</span><span class="sxs-lookup"><span data-stu-id="35b99-105">Open two levels, click outside P2 but inside P1.</span></span>  <span data-ttu-id="35b99-106">Es geschieht nichts.</span><span class="sxs-lookup"><span data-stu-id="35b99-106">Nothing happens.</span></span></li><li><span data-ttu-id="35b99-107">Öffnen Sie zwei Ebenen. Klicken Sie außerhalb von P1.</span><span class="sxs-lookup"><span data-stu-id="35b99-107">Open two levels, click outside P1.</span></span>  <span data-ttu-id="35b99-108">Beide Popups werden geschlossen.</span><span class="sxs-lookup"><span data-stu-id="35b99-108">Both popups close.</span></span></li><li><span data-ttu-id="35b99-109">Öffnen und schließen Sie zwei Ebenen.</span><span class="sxs-lookup"><span data-stu-id="35b99-109">Open and close two levels.</span></span>  <span data-ttu-id="35b99-110">Versuchen Sie dann, P2 erneut zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="35b99-110">Then try to open P2 again.</span></span>  <span data-ttu-id="35b99-111">Es geschieht nichts.</span><span class="sxs-lookup"><span data-stu-id="35b99-111">Nothing happens.</span></span></li><li><span data-ttu-id="35b99-112">Versuchen Sie, drei Ebenen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="35b99-112">Try to open three levels.</span></span>  <span data-ttu-id="35b99-113">Dies ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="35b99-113">You can't.</span></span>  <span data-ttu-id="35b99-114">(Je nachdem, wo Sie klicken, geschieht entweder nichts oder die ersten zwei Ebenen werden geschlossen.) Diese Fälle (und andere Varianten) funktionieren nun wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="35b99-114">(Either nothing happens or the first two levels close, depending on where you click.) These cases (and other variants) now work as expected.</span></span></li></ul>

| <span data-ttu-id="35b99-115">name</span><span class="sxs-lookup"><span data-stu-id="35b99-115">Name</span></span>    | <span data-ttu-id="35b99-116">Wert</span><span class="sxs-lookup"><span data-stu-id="35b99-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="35b99-117">Bereich</span><span class="sxs-lookup"><span data-stu-id="35b99-117">Scope</span></span>   |<span data-ttu-id="35b99-118">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="35b99-118">Edge</span></span>|
|<span data-ttu-id="35b99-119">Version</span><span class="sxs-lookup"><span data-stu-id="35b99-119">Version</span></span>|<span data-ttu-id="35b99-120">4.7.1</span><span class="sxs-lookup"><span data-stu-id="35b99-120">4.7.1</span></span>|
|<span data-ttu-id="35b99-121">Typ</span><span class="sxs-lookup"><span data-stu-id="35b99-121">Type</span></span>|<span data-ttu-id="35b99-122">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="35b99-122">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="35b99-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="35b99-123">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.Popup.StaysOpen`

-->
