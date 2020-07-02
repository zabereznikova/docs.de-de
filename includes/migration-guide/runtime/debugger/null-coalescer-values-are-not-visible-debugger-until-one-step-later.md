---
ms.openlocfilehash: 907c4aa5573c392a68afad0a4d937eadcd556440
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620293"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="761ba-101">NULL-Zusammenfügungswerte werden erst im nächsten Schritt angezeigt</span><span class="sxs-lookup"><span data-stu-id="761ba-101">Null coalescer values are not visible in debugger until one step later</span></span>

#### <a name="details"></a><span data-ttu-id="761ba-102">Details</span><span class="sxs-lookup"><span data-stu-id="761ba-102">Details</span></span>

<span data-ttu-id="761ba-103">Durch einen Fehler in .NET Framework 4.5 werden Werte, die über einen zusammenfügenden NULL-Vorgang festgelegt werden, nicht unmittelbar im Anschluss an die Zuweisung im Debugger angezeigt, wenn sie auf einer 64-Bit-Version des Frameworks ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="761ba-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="761ba-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="761ba-104">Suggestion</span></span>

<span data-ttu-id="761ba-105">Wenn Sie im Debugger einen zusätzlichen Schritt ausführen, wird der lokale Wert bzw. der Feldwert ohne Probleme aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="761ba-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="761ba-106">Dieses Problem wurde auch in .NET Framework 4.6 behoben und sollte nach einem Upgrade auf diese Version nicht mehr auftreten.</span><span class="sxs-lookup"><span data-stu-id="761ba-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>

| <span data-ttu-id="761ba-107">name</span><span class="sxs-lookup"><span data-stu-id="761ba-107">Name</span></span>    | <span data-ttu-id="761ba-108">Wert</span><span class="sxs-lookup"><span data-stu-id="761ba-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="761ba-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="761ba-109">Scope</span></span>   |<span data-ttu-id="761ba-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="761ba-110">Edge</span></span>|
|<span data-ttu-id="761ba-111">Version</span><span class="sxs-lookup"><span data-stu-id="761ba-111">Version</span></span>|<span data-ttu-id="761ba-112">4.5</span><span class="sxs-lookup"><span data-stu-id="761ba-112">4.5</span></span>|
|<span data-ttu-id="761ba-113">Typ</span><span class="sxs-lookup"><span data-stu-id="761ba-113">Type</span></span>|<span data-ttu-id="761ba-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="761ba-114">Runtime</span></span>|
