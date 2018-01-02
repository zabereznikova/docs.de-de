---
title: "Der Name des vollständigen Betriebssystems konnte aufgrund eines internen Fehlers nicht abgerufen werden."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c67d47126718c3d90d853add61b7d06aaf84fc70
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="c4913-102">Der Name des vollständigen Betriebssystems konnte aufgrund eines internen Fehlers nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c4913-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="c4913-103">Der Name des vollständigen Betriebssystems konnte aufgrund eines internen Fehlers nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c4913-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="c4913-104">Dies kann dadurch verursacht werden, dass WMI auf dem aktuellen Computer fehlt.</span><span class="sxs-lookup"><span data-stu-id="c4913-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="c4913-105">Beim Aufrufen der `My.Computer.Info.OSFullName` -Eigenschaft ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c4913-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="c4913-106">Eine mögliche Ursache für diesen Fehler ist, wenn WMI (Windows-Verwaltungsinstrumentation, Windows Management Instrumentation) auf dem aktuellen Computer nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c4913-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c4913-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c4913-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="c4913-108">Fügen Sie rund um den Aufruf der `Try...Catch` -Eigenschaft einen `My.Computer.Info.OSFullName` -Block hinzu.</span><span class="sxs-lookup"><span data-stu-id="c4913-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2.  <span data-ttu-id="c4913-109">Weitere Informationen zu WMI und wie Sie sie installieren rufen Sie aus, und suchen Sie nach "Windows Management Instrumentation Core".</span><span class="sxs-lookup"><span data-stu-id="c4913-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4913-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4913-110">See Also</span></span>  
 [<span data-ttu-id="c4913-111">My.Computer.Info.OSFullName</span><span class="sxs-lookup"><span data-stu-id="c4913-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)  
 [<span data-ttu-id="c4913-112">Ausnahmen- und Fehlerbehandlung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c4913-112">Exception and Error Handling in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/3e351e73-cf23-40ab-8b60-05794160529e)  
 [<span data-ttu-id="c4913-113">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c4913-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
