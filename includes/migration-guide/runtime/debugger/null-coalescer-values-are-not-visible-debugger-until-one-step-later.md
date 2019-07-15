---
ms.openlocfilehash: c1a2d76b4e596acc395da6cefed008078e57a336
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858597"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="8b7ae-101">NULL-Zusammenfügungswerte werden erst im nächsten Schritt angezeigt</span><span class="sxs-lookup"><span data-stu-id="8b7ae-101">Null coalescer values are not visible in debugger until one step later</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8b7ae-102">Details</span><span class="sxs-lookup"><span data-stu-id="8b7ae-102">Details</span></span>|<span data-ttu-id="8b7ae-103">Durch einen Fehler in .NET Framework 4.5 werden Werte, die über einen zusammenfügenden NULL-Vorgang festgelegt werden, nicht unmittelbar im Anschluss an die Zuweisung im Debugger angezeigt, wenn sie auf einer 64-Bit-Version des Frameworks ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8b7ae-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>|
|<span data-ttu-id="8b7ae-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="8b7ae-104">Suggestion</span></span>|<span data-ttu-id="8b7ae-105">Wenn Sie im Debugger einen zusätzlichen Schritt ausführen, wird der lokale Wert bzw. der Feldwert ohne Probleme aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8b7ae-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="8b7ae-106">Dieses Problem wurde auch in .NET Framework 4.6 behoben und sollte nach einem Upgrade auf diese Version nicht mehr auftreten.</span><span class="sxs-lookup"><span data-stu-id="8b7ae-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>|
|<span data-ttu-id="8b7ae-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="8b7ae-107">Scope</span></span>|<span data-ttu-id="8b7ae-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8b7ae-108">Edge</span></span>|
|<span data-ttu-id="8b7ae-109">Version</span><span class="sxs-lookup"><span data-stu-id="8b7ae-109">Version</span></span>|<span data-ttu-id="8b7ae-110">4.5</span><span class="sxs-lookup"><span data-stu-id="8b7ae-110">4.5</span></span>|
|<span data-ttu-id="8b7ae-111">Typ</span><span class="sxs-lookup"><span data-stu-id="8b7ae-111">Type</span></span>|<span data-ttu-id="8b7ae-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="8b7ae-112">Runtime</span></span>|

