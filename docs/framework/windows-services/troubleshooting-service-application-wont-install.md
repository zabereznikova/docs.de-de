---
title: 'Problembehandlung: Dienstanwendung kann nicht installiert werden'
description: Führen Sie die Problembehandlung aus, wenn die Dienstanwendung nicht installiert wird. Stellen Sie sicher, dass die ServiceName-Eigenschaft für die Dienstklasse ordnungsgemäß festgelegt ist.
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
ms.openlocfilehash: d606adc7fddeb9f7e76a6974699c2455eda084b2
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608880"
---
# <a name="troubleshooting-service-application-wont-install"></a>Problembehandlung: Dienstanwendung kann nicht installiert werden
Wenn die Dienstanwendung nicht ordnungsgemäß installiert werden kann, stellen Sie sicher, dass die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft der Dienstklasse auf den Wert festgelegt ist, der im Installer für diesen Dienst angezeigt wird. Damit der Dienst ordnungsgemäß installiert werden kann, muss der Wert in beiden Instanzen identisch sein.  
  
> [!NOTE]
> Feedback zum Installationsvorgang finden Sie auch in den Installationsprotokollen.  
  
 Sie sollten auch überprüfen, ob bereits ein anderer Dienst mit demselben Namen installiert wurde. Dienstnamen müssen eindeutig sein, damit die Installation erfolgreich abgeschlossen werden kann.  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Windows-Dienstanwendungen](introduction-to-windows-service-applications.md)
