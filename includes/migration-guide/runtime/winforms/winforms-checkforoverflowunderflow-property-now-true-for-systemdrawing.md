---
ms.openlocfilehash: 68b0c4bb032b9744ef585eaef3d68e31afebee24
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497741"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="b3947-101">Die CheckForOverflowUnderflow-Eigenschaft von WinForm ist jetzt für System.Drawing auf TRUE festgelegt</span><span class="sxs-lookup"><span data-stu-id="b3947-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

#### <a name="details"></a><span data-ttu-id="b3947-102">Details</span><span class="sxs-lookup"><span data-stu-id="b3947-102">Details</span></span>

<span data-ttu-id="b3947-103">Die CheckForOverflowUnderflow-Eigenschaft für die Assembly „System.Drawing.dll“ ist auf TRUE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b3947-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b3947-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b3947-104">Suggestion</span></span>

<span data-ttu-id="b3947-105">Zuvor wurde das Ergebnis im Fall von Überläufen automatisch abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="b3947-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="b3947-106">Nun wird eine <xref:System.OverflowException?displayProperty=fullName>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b3947-106">Now an <xref:System.OverflowException?displayProperty=fullName> exception is thrown.</span></span>

| <span data-ttu-id="b3947-107">name</span><span class="sxs-lookup"><span data-stu-id="b3947-107">Name</span></span>    | <span data-ttu-id="b3947-108">Wert</span><span class="sxs-lookup"><span data-stu-id="b3947-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b3947-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="b3947-109">Scope</span></span>   |<span data-ttu-id="b3947-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b3947-110">Edge</span></span>|
|<span data-ttu-id="b3947-111">Version</span><span class="sxs-lookup"><span data-stu-id="b3947-111">Version</span></span>|<span data-ttu-id="b3947-112">4.5</span><span class="sxs-lookup"><span data-stu-id="b3947-112">4.5</span></span>|
|<span data-ttu-id="b3947-113">Typ</span><span class="sxs-lookup"><span data-stu-id="b3947-113">Type</span></span>|<span data-ttu-id="b3947-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b3947-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b3947-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b3947-115">Affected APIs</span></span>

<span data-ttu-id="b3947-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="b3947-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
