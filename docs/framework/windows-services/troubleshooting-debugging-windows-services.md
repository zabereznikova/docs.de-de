---
title: 'Problembehandlung: Debuggen von Windows-Diensten'
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
author: ghogen
manager: douge
ms.openlocfilehash: 77a0c19c2da2d1886beaf396650fa024fc1243a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510136"
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="32d31-102">Problembehandlung: Debuggen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="32d31-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="32d31-103">Beim Debuggen einer Windows-Dienstanwendung interagiert der Dienst mit dem **Windows Service Manager**.</span><span class="sxs-lookup"><span data-stu-id="32d31-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="32d31-104">Der **Service Manager** startet den Dienst durch Aufrufen der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode und wartet dann 30 Sekunden auf die Rückgabe der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="32d31-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="32d31-105">Erfolgt in diesem Zeitraum keine Rückgabe durch die Methode, wird im Manager die Fehlermeldung angezeigt, dass der Dienst nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="32d31-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="32d31-106">Beachten Sie diesen Zeitraum von 30 Sekunden, wenn Sie die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode wie unter [Vorgehensweise: Debuggen von Windows-Dienstanwendungen](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md) beschrieben debuggen möchten.</span><span class="sxs-lookup"><span data-stu-id="32d31-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="32d31-107">Wenn Sie in der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode einen Haltepunkt platzieren und der Durchlauf nicht innerhalb von 30 Sekunden abgeschlossen ist, wird der Dienst durch den Manager nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="32d31-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d31-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32d31-108">See Also</span></span>  
 [<span data-ttu-id="32d31-109">Vorgehensweise: Debuggen von Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="32d31-109">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [<span data-ttu-id="32d31-110">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="32d31-110">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
