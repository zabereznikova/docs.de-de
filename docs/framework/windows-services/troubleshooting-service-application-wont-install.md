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
ms.openlocfilehash: 82eb870761a7865385631cd9961ce99e0b0d3502
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="troubleshooting-service-application-won39t-install"></a><span data-ttu-id="73c6a-102">Problembehandlung: Dienst Anwendung gewonnen &#39; t installieren</span><span class="sxs-lookup"><span data-stu-id="73c6a-102">Troubleshooting: Service Application Won&#39;t Install</span></span>
<span data-ttu-id="73c6a-103">Wenn Ihr Service-Anwendung nicht ordnungsgemäß installiert wird, zu überprüfen, um sicherzustellen, dass die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> -Eigenschaft für die Dienstklasse auf denselben Wert festgelegt ist, wie in der Installer für diesen Dienst dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="73c6a-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="73c6a-104">Der Wert muss in beiden Instanzen nacheinander für Ihren Dienst ordnungsgemäß installiert sein.</span><span class="sxs-lookup"><span data-stu-id="73c6a-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73c6a-105">Sie können auch den Installationsprotokollen protokolliert, um Feedback zum während Installationsvorgangs erhalten betrachten.</span><span class="sxs-lookup"><span data-stu-id="73c6a-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="73c6a-106">Sie sollten auch überprüfen, um festzustellen, ob Sie einen anderen Dienst mit dem gleichen Namen bereits installiert haben.</span><span class="sxs-lookup"><span data-stu-id="73c6a-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="73c6a-107">Dienstnamen müssen eindeutig für die erfolgreiche Installation vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="73c6a-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73c6a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73c6a-108">See Also</span></span>  
 [<span data-ttu-id="73c6a-109">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="73c6a-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
