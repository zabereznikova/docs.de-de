---
title: 'Problembehandlung: Debuggen von Windows-Diensten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: f38e65e93d4e6668795bf254573993d5100e2328
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="65755-102">Problembehandlung: Debuggen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="65755-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="65755-103">Beim Debuggen einer Windows-dienstanwendung, den Dienst und die **Windows Service Manager** interagieren.</span><span class="sxs-lookup"><span data-stu-id="65755-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="65755-104">Die **Service Manager** startet den Dienst durch Aufrufen der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode, und klicken Sie dann wartet 30 Sekunden für die <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="65755-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="65755-105">Wenn die Methode in diesem Zeitraum nicht zurückgegeben werden, wird der Manager ein Fehler angezeigt, dass der Dienst nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="65755-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="65755-106">Beim Debuggen der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> Methode wie beschrieben in [Vorgehensweise: Debuggen von Windows-Dienstanwendungen](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), Sie Bedenken Zeitraum von 30 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="65755-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="65755-107">Wenn Sie einen Haltepunkt in Einbinden der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> Methode und führen Sie nicht innerhalb von 30 Sekunden durchlaufen wird, der Manager wird den Dienst nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="65755-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65755-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65755-108">See Also</span></span>  
 [<span data-ttu-id="65755-109">Vorgehensweise: Debuggen von Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="65755-109">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [<span data-ttu-id="65755-110">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="65755-110">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
