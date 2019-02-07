---
title: 'Problembehandlung: Dienstanwendung kann nicht installiert werden'
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
author: ghogen
ms.openlocfilehash: ecbaa3b2fb0e0fc85ed383385368617bf361f497
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289430"
---
# <a name="troubleshooting-service-application-wont-install"></a>Problembehandlung: Dienstanwendung kann nicht installiert werden
Wenn die Dienstanwendung nicht ordnungsgemäß installiert werden kann, stellen Sie sicher, dass die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft der Dienstklasse auf den Wert festgelegt ist, der im Installer für diesen Dienst angezeigt wird. Damit der Dienst ordnungsgemäß installiert werden kann, muss der Wert in beiden Instanzen identisch sein.  
  
> [!NOTE]
>  Feedback zum Installationsvorgang finden Sie auch in den Installationsprotokollen.  
  
 Sie sollten auch überprüfen, ob bereits ein anderer Dienst mit demselben Namen installiert wurde. Dienstnamen müssen eindeutig sein, damit die Installation erfolgreich abgeschlossen werden kann.  
  
## <a name="see-also"></a>Siehe auch
- [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
