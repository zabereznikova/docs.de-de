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
# <a name="troubleshooting-service-application-won39t-install"></a><span data-ttu-id="974a9-102">Problembehandlung: Dienst Anwendung gewonnen &#39; t installieren</span><span class="sxs-lookup"><span data-stu-id="974a9-102">Troubleshooting: Service Application Won&#39;t Install</span></span>
<span data-ttu-id="974a9-103">Wenn Ihr Service-Anwendung nicht ordnungsgemäß installiert wird, zu überprüfen, um sicherzustellen, dass die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> -Eigenschaft für die Dienstklasse auf denselben Wert festgelegt ist, wie in der Installer für diesen Dienst dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="974a9-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="974a9-104">Der Wert muss in beiden Instanzen nacheinander für Ihren Dienst ordnungsgemäß installiert sein.</span><span class="sxs-lookup"><span data-stu-id="974a9-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="974a9-105">Sie können auch den Installationsprotokollen protokolliert, um Feedback zum während Installationsvorgangs erhalten betrachten.</span><span class="sxs-lookup"><span data-stu-id="974a9-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="974a9-106">Sie sollten auch überprüfen, um festzustellen, ob Sie einen anderen Dienst mit dem gleichen Namen bereits installiert haben.</span><span class="sxs-lookup"><span data-stu-id="974a9-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="974a9-107">Dienstnamen müssen eindeutig für die erfolgreiche Installation vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="974a9-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="974a9-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="974a9-108">See Also</span></span>  
 [<span data-ttu-id="974a9-109">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="974a9-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
