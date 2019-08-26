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
ms.openlocfilehash: d04a0ddcef9ff7c31abd422f7f9fba34e804d2b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935411"
---
# <a name="troubleshooting-service-application-wont-install"></a>Problembehandlung: Dienstanwendung kann nicht installiert werden
Wenn die Dienstanwendung nicht ordnungsgemäß installiert werden kann, stellen Sie sicher, dass die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft der Dienstklasse auf den Wert festgelegt ist, der im Installer für diesen Dienst angezeigt wird. Damit der Dienst ordnungsgemäß installiert werden kann, muss der Wert in beiden Instanzen identisch sein.  
  
> [!NOTE]
> Feedback zum Installationsvorgang finden Sie auch in den Installationsprotokollen.  
  
 Sie sollten auch überprüfen, ob bereits ein anderer Dienst mit demselben Namen installiert wurde. Dienstnamen müssen eindeutig sein, damit die Installation erfolgreich abgeschlossen werden kann.  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
