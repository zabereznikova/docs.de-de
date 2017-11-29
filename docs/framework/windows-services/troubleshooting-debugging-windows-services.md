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
ms.openlocfilehash: 51c28f6e9b6fa2974fb9861716b2c9fc2a38fe1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-debugging-windows-services"></a>Problembehandlung: Debuggen von Windows-Diensten
Beim Debuggen einer Windows-dienstanwendung, den Dienst und die **Windows Service Manager** interagieren. Die **Service Manager** startet den Dienst durch Aufrufen der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode, und klicken Sie dann wartet 30 Sekunden für die <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode zurückgegeben. Wenn die Methode in diesem Zeitraum nicht zurückgegeben werden, wird der Manager ein Fehler angezeigt, dass der Dienst nicht gestartet werden kann.  
  
 Beim Debuggen der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> Methode wie beschrieben in [Vorgehensweise: Debuggen von Windows-Dienstanwendungen](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), Sie Bedenken Zeitraum von 30 Sekunden. Wenn Sie einen Haltepunkt in Einbinden der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> Methode und führen Sie nicht innerhalb von 30 Sekunden durchlaufen wird, der Manager wird den Dienst nicht gestartet.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Debuggen von Windows-Dienstanwendungen](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
