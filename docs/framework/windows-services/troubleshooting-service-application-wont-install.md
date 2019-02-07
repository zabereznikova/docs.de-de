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
# <a name="troubleshooting-service-application-wont-install"></a><span data-ttu-id="ece53-102">Problembehandlung: Dienstanwendung kann nicht installiert werden</span><span class="sxs-lookup"><span data-stu-id="ece53-102">Troubleshooting: Service Application Won't Install</span></span>
<span data-ttu-id="ece53-103">Wenn die Dienstanwendung nicht ordnungsgemäß installiert werden kann, stellen Sie sicher, dass die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft der Dienstklasse auf den Wert festgelegt ist, der im Installer für diesen Dienst angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ece53-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="ece53-104">Damit der Dienst ordnungsgemäß installiert werden kann, muss der Wert in beiden Instanzen identisch sein.</span><span class="sxs-lookup"><span data-stu-id="ece53-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ece53-105">Feedback zum Installationsvorgang finden Sie auch in den Installationsprotokollen.</span><span class="sxs-lookup"><span data-stu-id="ece53-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="ece53-106">Sie sollten auch überprüfen, ob bereits ein anderer Dienst mit demselben Namen installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ece53-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="ece53-107">Dienstnamen müssen eindeutig sein, damit die Installation erfolgreich abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ece53-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece53-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ece53-108">See also</span></span>
- [<span data-ttu-id="ece53-109">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="ece53-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
