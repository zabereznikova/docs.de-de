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
ms.openlocfilehash: cdffb3a8ce9c5119a0a17a8bc7e6ca78276423f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745674"
---
# <a name="troubleshooting-debugging-windows-services"></a>Problembehandlung: Debuggen von Windows-Diensten
Beim Debuggen einer Windows-Dienstanwendung interagiert der Dienst mit dem **Windows Service Manager**. Der **Service Manager** startet den Dienst durch Aufrufen der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode und wartet dann 30 Sekunden auf die Rückgabe der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode. Erfolgt in diesem Zeitraum keine Rückgabe durch die Methode, wird im Manager die Fehlermeldung angezeigt, dass der Dienst nicht gestartet werden kann.  
  
 Wenn Sie die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode wie unter [Vorgehensweise: Debuggen von Windows-Dienstanwendungen](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md) beschrieben debuggen, müssen Sie diese 30 Sekunden beachten. Wenn Sie in der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode einen Haltepunkt platzieren und der Durchlauf nicht innerhalb von 30 Sekunden abgeschlossen ist, wird der Dienst durch den Manager nicht gestartet.  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Debuggen von Windows-Dienstanwendungen](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
