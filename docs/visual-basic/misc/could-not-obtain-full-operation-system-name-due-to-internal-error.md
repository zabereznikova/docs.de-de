---
title: Der Name des vollständigen Betriebssystems konnte aufgrund eines internen Fehlers nicht abgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: f85ca5f7f325cb0dd2b8fc55d3f90f6abdfd4a7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33635076"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="5d9ce-102">Der Name des vollständigen Betriebssystems konnte aufgrund eines internen Fehlers nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5d9ce-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="5d9ce-103">Der Name des vollständigen Betriebssystems konnte aufgrund eines internen Fehlers nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5d9ce-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="5d9ce-104">Dies kann dadurch verursacht werden, dass WMI auf dem aktuellen Computer fehlt.</span><span class="sxs-lookup"><span data-stu-id="5d9ce-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="5d9ce-105">Beim Aufrufen der `My.Computer.Info.OSFullName` -Eigenschaft ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5d9ce-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="5d9ce-106">Eine mögliche Ursache für diesen Fehler ist, wenn WMI (Windows-Verwaltungsinstrumentation, Windows Management Instrumentation) auf dem aktuellen Computer nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5d9ce-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5d9ce-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5d9ce-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="5d9ce-108">Fügen Sie rund um den Aufruf der `Try...Catch` -Eigenschaft einen `My.Computer.Info.OSFullName` -Block hinzu.</span><span class="sxs-lookup"><span data-stu-id="5d9ce-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2.  <span data-ttu-id="5d9ce-109">Weitere Informationen zu WMI und wie Sie sie installieren rufen Sie aus, und suchen Sie nach "Windows Management Instrumentation Core".</span><span class="sxs-lookup"><span data-stu-id="5d9ce-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d9ce-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d9ce-110">See Also</span></span>  
 [<span data-ttu-id="5d9ce-111">My.Computer.Info.OSFullName</span><span class="sxs-lookup"><span data-stu-id="5d9ce-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)  
 [<span data-ttu-id="5d9ce-112">Ausnahmen- und Fehlerbehandlung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d9ce-112">Exception and Error Handling in Visual Basic</span></span>](http://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)  
 [<span data-ttu-id="5d9ce-113">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5d9ce-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
