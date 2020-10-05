---
title: 'Problembehandlung: Debuggen von Windows-Diensten'
description: Hier erfahren Sie mehr über die ersten Schritte beim Debuggen von Windows-Diensten. Beim Debuggen einer Windows-Dienstanwendung interagiert der Dienst mit dem Windows-Dienst-Manager.
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
ms.openlocfilehash: 5846692fa0d90a62dd569253abbd81aa63b5798d
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608893"
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="d124e-104">Problembehandlung: Debuggen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="d124e-104">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="d124e-105">Beim Debuggen einer Windows-Dienstanwendung interagiert der Dienst mit dem **Windows Service Manager**.</span><span class="sxs-lookup"><span data-stu-id="d124e-105">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="d124e-106">Der **Service Manager** startet den Dienst durch Aufrufen der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode und wartet dann 30 Sekunden auf die Rückgabe der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="d124e-106">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="d124e-107">Erfolgt in diesem Zeitraum keine Rückgabe durch die Methode, wird im Manager die Fehlermeldung angezeigt, dass der Dienst nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d124e-107">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="d124e-108">Wenn Sie die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode wie unter [Vorgehensweise: Debuggen von Windows-Dienstanwendungen](how-to-debug-windows-service-applications.md) beschrieben debuggen, müssen Sie diese 30 Sekunden beachten.</span><span class="sxs-lookup"><span data-stu-id="d124e-108">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="d124e-109">Wenn Sie in der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode einen Haltepunkt platzieren und der Durchlauf nicht innerhalb von 30 Sekunden abgeschlossen ist, wird der Dienst durch den Manager nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="d124e-109">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d124e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d124e-110">See also</span></span>

- [<span data-ttu-id="d124e-111">How to: Debuggen von Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="d124e-111">How to: Debug Windows Service Applications</span></span>](how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="d124e-112">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="d124e-112">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
