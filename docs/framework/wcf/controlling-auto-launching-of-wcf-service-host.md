---
title: Steuern des automatischen Starts des WCF-Diensthosts
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5bb6356ba4698cad00d443fdb80b1a45d35e2175
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="cbad4-102">Steuern des automatischen Starts des WCF-Diensthosts</span><span class="sxs-lookup"><span data-stu-id="cbad4-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="cbad4-103">Sie können steuern, die Autostartfunktion des [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] -Diensthost (WcfSvcHost.exe) für eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienst-Bibliotheksprojekt beim Debuggen von einem anderen Projekt in der gleichen Visual Studio-Projektmappe, die mehrere Projekte enthält.</span><span class="sxs-lookup"><span data-stu-id="cbad4-103">You can control the auto-launching capability of [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Host (WcfSvcHost.exe) for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="cbad4-104">Dazu, mit der Maustaste die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienstprojekt in **Projektmappen-Explorer**, wählen Sie **Eigenschaften**, und klicken Sie auf **WCF Optionen** Registerkarte. Die **starten WCF-Diensthost beim Debuggen eines anderen Projekts in derselben Projektmappe** Kontrollkästchen ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cbad4-104">To do so, right-click the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="cbad4-105">Deaktivieren Sie dieses Kontrollkästchen, wenn der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost für dieses bestimmte Projekt beim Debuggen eines anderen Projekts in der gleichen Projektmappe nicht gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cbad4-105">You can clear the box so that [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="cbad4-106">Dieses Verhalten wirkt sich weder auf das F5-Debugging noch auf die Funktionen zum Hinzufügen von Dienstverweisen für dieses Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="cbad4-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="cbad4-107">Diese Option steht für die folgenden Projekte zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="cbad4-107">This option is available to the following projects:</span></span>  
  
-   <span data-ttu-id="cbad4-108">Bibliotheksprojekt für [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst</span><span class="sxs-lookup"><span data-stu-id="cbad4-108">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Library Project.</span></span>  
  
-   <span data-ttu-id="cbad4-109">Bibliotheksprojekt für sequenziellen Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="cbad4-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="cbad4-110">Bibliotheksprojekt für Statuscomputerworkflowdienst</span><span class="sxs-lookup"><span data-stu-id="cbad4-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="cbad4-111">Bibliotheksprojekt für Syndication-Dienst</span><span class="sxs-lookup"><span data-stu-id="cbad4-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbad4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbad4-112">See Also</span></span>  
 [<span data-ttu-id="cbad4-113">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="cbad4-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
