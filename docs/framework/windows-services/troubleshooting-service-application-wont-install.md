---
title: 'Problembehandlung: Dienst Anwendung gewonnen &#39; t installieren'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 43c973d83d2d1b614cf0ce49ba8d4af24123b47e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-service-application-won39t-install"></a>Problembehandlung: Dienst Anwendung gewonnen &#39; t installieren
Wenn Ihr Service-Anwendung nicht ordnungsgemäß installiert wird, zu überprüfen, um sicherzustellen, dass die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> -Eigenschaft für die Dienstklasse auf denselben Wert festgelegt ist, wie in der Installer für diesen Dienst dargestellt wird. Der Wert muss in beiden Instanzen nacheinander für Ihren Dienst ordnungsgemäß installiert sein.  
  
> [!NOTE]
>  Sie können auch den Installationsprotokollen protokolliert, um Feedback zum während Installationsvorgangs erhalten betrachten.  
  
 Sie sollten auch überprüfen, um festzustellen, ob Sie einen anderen Dienst mit dem gleichen Namen bereits installiert haben. Dienstnamen müssen eindeutig für die erfolgreiche Installation vorhanden sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
