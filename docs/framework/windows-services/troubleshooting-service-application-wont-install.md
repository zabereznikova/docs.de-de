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
author: ghogen
ms.openlocfilehash: 4a57fb6975a6ded48abf7c8fd7eacec16e4f94d8
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925526"
---
# <a name="troubleshooting-service-application-wont-install"></a><span data-ttu-id="f00c3-104">Problembehandlung: Dienstanwendung kann nicht installiert werden</span><span class="sxs-lookup"><span data-stu-id="f00c3-104">Troubleshooting: Service Application Won't Install</span></span>
<span data-ttu-id="f00c3-105">Wenn die Dienstanwendung nicht ordnungsgemäß installiert werden kann, stellen Sie sicher, dass die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft der Dienstklasse auf den Wert festgelegt ist, der im Installer für diesen Dienst angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f00c3-105">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="f00c3-106">Damit der Dienst ordnungsgemäß installiert werden kann, muss der Wert in beiden Instanzen identisch sein.</span><span class="sxs-lookup"><span data-stu-id="f00c3-106">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f00c3-107">Feedback zum Installationsvorgang finden Sie auch in den Installationsprotokollen.</span><span class="sxs-lookup"><span data-stu-id="f00c3-107">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="f00c3-108">Sie sollten auch überprüfen, ob bereits ein anderer Dienst mit demselben Namen installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f00c3-108">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="f00c3-109">Dienstnamen müssen eindeutig sein, damit die Installation erfolgreich abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f00c3-109">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f00c3-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f00c3-110">See also</span></span>

- [<span data-ttu-id="f00c3-111">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="f00c3-111">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
