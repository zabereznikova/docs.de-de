---
title: 'Problembehandlung: Service-Anwendung gewonnen&#39;t installieren'
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
manager: douge
ms.openlocfilehash: 1f3e5674f9a52627efdc24d6c70c0ab16dcdbbbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-service-application-won39t-install"></a>Problembehandlung: Service-Anwendung gewonnen&#39;t installieren
Wenn Ihr Service-Anwendung nicht ordnungsgemäß installiert wird, zu überprüfen, um sicherzustellen, dass die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> -Eigenschaft für die Dienstklasse auf denselben Wert festgelegt ist, wie in der Installer für diesen Dienst dargestellt wird. Der Wert muss in beiden Instanzen nacheinander für Ihren Dienst ordnungsgemäß installiert sein.  
  
> [!NOTE]
>  Sie können auch den Installationsprotokollen protokolliert, um Feedback zum während Installationsvorgangs erhalten betrachten.  
  
 Sie sollten auch überprüfen, um festzustellen, ob Sie einen anderen Dienst mit dem gleichen Namen bereits installiert haben. Dienstnamen müssen eindeutig für die erfolgreiche Installation vorhanden sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
