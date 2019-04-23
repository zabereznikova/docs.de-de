---
title: Der Name des vollständigen Betriebssystems konnte aufgrund eines internen Fehlers nicht abgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: ecbed5b59d36b1984c0b0ae161821ea99d28e090
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334639"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="4899a-102">Der Name des vollständigen Betriebssystems konnte aufgrund eines internen Fehlers nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4899a-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="4899a-103">Der Name des vollständigen Betriebssystems konnte aufgrund eines internen Fehlers nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4899a-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="4899a-104">Dies kann dadurch verursacht werden, dass WMI auf dem aktuellen Computer fehlt.</span><span class="sxs-lookup"><span data-stu-id="4899a-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="4899a-105">Beim Aufrufen der `My.Computer.Info.OSFullName` -Eigenschaft ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4899a-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="4899a-106">Eine mögliche Ursache für diesen Fehler ist, wenn WMI (Windows-Verwaltungsinstrumentation, Windows Management Instrumentation) auf dem aktuellen Computer nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4899a-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4899a-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4899a-107">To correct this error</span></span>  
  
1. <span data-ttu-id="4899a-108">Fügen Sie rund um den Aufruf der `Try...Catch` -Eigenschaft einen `My.Computer.Info.OSFullName` -Block hinzu.</span><span class="sxs-lookup"><span data-stu-id="4899a-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2. <span data-ttu-id="4899a-109">Weitere Informationen zu WMI und installieren Sie es, und suchen Sie nach "Windows Management Instrumentation Core".</span><span class="sxs-lookup"><span data-stu-id="4899a-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4899a-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4899a-110">See also</span></span>

- [<span data-ttu-id="4899a-111">My.Computer.Info.OSFullName</span><span class="sxs-lookup"><span data-stu-id="4899a-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="4899a-112">Behandeln und Auslösen von Ausnahmen in .NET</span><span class="sxs-lookup"><span data-stu-id="4899a-112">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="4899a-113">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4899a-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
