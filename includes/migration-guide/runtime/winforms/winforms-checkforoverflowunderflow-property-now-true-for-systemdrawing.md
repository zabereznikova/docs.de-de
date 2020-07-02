---
ms.openlocfilehash: 4cd06fd02fadbaa9f74e40f850e688ee883454ed
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620447"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="2a58f-101">Die CheckForOverflowUnderflow-Eigenschaft von WinForm ist jetzt für System.Drawing auf TRUE festgelegt</span><span class="sxs-lookup"><span data-stu-id="2a58f-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

#### <a name="details"></a><span data-ttu-id="2a58f-102">Details</span><span class="sxs-lookup"><span data-stu-id="2a58f-102">Details</span></span>

<span data-ttu-id="2a58f-103">Die CheckForOverflowUnderflow-Eigenschaft für die Assembly „System.Drawing.dll“ ist auf TRUE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2a58f-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2a58f-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2a58f-104">Suggestion</span></span>

<span data-ttu-id="2a58f-105">Zuvor wurde das Ergebnis im Fall von Überläufen automatisch abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="2a58f-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="2a58f-106">Nun wird eine <xref:System.OverflowException?displayProperty=fullName>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="2a58f-106">Now an <xref:System.OverflowException?displayProperty=fullName> exception is thrown.</span></span>

| <span data-ttu-id="2a58f-107">name</span><span class="sxs-lookup"><span data-stu-id="2a58f-107">Name</span></span>    | <span data-ttu-id="2a58f-108">Wert</span><span class="sxs-lookup"><span data-stu-id="2a58f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2a58f-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="2a58f-109">Scope</span></span>   |<span data-ttu-id="2a58f-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2a58f-110">Edge</span></span>|
|<span data-ttu-id="2a58f-111">Version</span><span class="sxs-lookup"><span data-stu-id="2a58f-111">Version</span></span>|<span data-ttu-id="2a58f-112">4.5</span><span class="sxs-lookup"><span data-stu-id="2a58f-112">4.5</span></span>|
|<span data-ttu-id="2a58f-113">Typ</span><span class="sxs-lookup"><span data-stu-id="2a58f-113">Type</span></span>|<span data-ttu-id="2a58f-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2a58f-114">Runtime</span></span>|
