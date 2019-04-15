---
ms.openlocfilehash: 22f8e3bb1ba72379b3f5fc87a077e5fe57f89bf8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235217"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="4435b-101">NULL-Zusammenfügungswerte werden erst im nächsten Schritt angezeigt</span><span class="sxs-lookup"><span data-stu-id="4435b-101">Null coalescer values are not visible in debugger until one step later</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4435b-102">Details</span><span class="sxs-lookup"><span data-stu-id="4435b-102">Details</span></span>|<span data-ttu-id="4435b-103">Durch einen Fehler in .NET Framework 4.5 werden Werte, die über einen zusammenfügenden NULL-Vorgang festgelegt werden, nicht unmittelbar im Anschluss an die Zuweisung im Debugger angezeigt, wenn sie auf einer 64-Bit-Version des Frameworks ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4435b-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>|
|<span data-ttu-id="4435b-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="4435b-104">Suggestion</span></span>|<span data-ttu-id="4435b-105">Wenn Sie im Debugger einen zusätzlichen Schritt ausführen, wird der lokale Wert bzw. der Feldwert ohne Probleme aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="4435b-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="4435b-106">Dieses Problem wurde auch in .NET Framework 4.6 behoben und sollte nach einem Upgrade auf diese Version nicht mehr auftreten.</span><span class="sxs-lookup"><span data-stu-id="4435b-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>|
|<span data-ttu-id="4435b-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="4435b-107">Scope</span></span>|<span data-ttu-id="4435b-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4435b-108">Edge</span></span>|
|<span data-ttu-id="4435b-109">Version</span><span class="sxs-lookup"><span data-stu-id="4435b-109">Version</span></span>|<span data-ttu-id="4435b-110">4.5</span><span class="sxs-lookup"><span data-stu-id="4435b-110">4.5</span></span>|
|<span data-ttu-id="4435b-111">Typ</span><span class="sxs-lookup"><span data-stu-id="4435b-111">Type</span></span>|<span data-ttu-id="4435b-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="4435b-112">Runtime</span></span>|
