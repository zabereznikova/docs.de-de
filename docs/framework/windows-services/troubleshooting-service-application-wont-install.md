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
manager: douge
ms.openlocfilehash: 1f3e5674f9a52627efdc24d6c70c0ab16dcdbbbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509659"
---
# <a name="troubleshooting-service-application-won39t-install"></a><span data-ttu-id="c8865-102">Problembehandlung: Dienstanwendung kann nicht installiert werden</span><span class="sxs-lookup"><span data-stu-id="c8865-102">Troubleshooting: Service Application Won&#39;t Install</span></span>
<span data-ttu-id="c8865-103">Wenn die Dienstanwendung nicht ordnungsgemäß installiert werden kann, stellen Sie sicher, dass die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft der Dienstklasse auf den Wert festgelegt ist, der im Installer für diesen Dienst angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c8865-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="c8865-104">Damit der Dienst ordnungsgemäß installiert werden kann, muss der Wert in beiden Instanzen identisch sein.</span><span class="sxs-lookup"><span data-stu-id="c8865-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8865-105">Feedback zum Installationsvorgang finden Sie auch in den Installationsprotokollen.</span><span class="sxs-lookup"><span data-stu-id="c8865-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="c8865-106">Sie sollten auch überprüfen, ob bereits ein anderer Dienst mit demselben Namen installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c8865-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="c8865-107">Dienstnamen müssen eindeutig sein, damit die Installation erfolgreich abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c8865-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8865-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8865-108">See Also</span></span>  
 [<span data-ttu-id="c8865-109">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="c8865-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
