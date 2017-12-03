---
title: Steuern des automatischen Starts des WCF-Diensthosts
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 60c7e2ddd4d4d57b675f2c12f8c5f567e8d23020
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="44d84-102">Steuern des automatischen Starts des WCF-Diensthosts</span><span class="sxs-lookup"><span data-stu-id="44d84-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="44d84-103">Sie haben die Möglichkeit zum Steuern der Autostartfunktion des [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Diensthosts (WcfSvcHost.exe) für ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Bibliotheksprojekt beim Debuggen eines anderen Projekts in der gleichen [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Projektmappe (bei Projektmappen mit mehreren Projekten).</span><span class="sxs-lookup"><span data-stu-id="44d84-103">You can control the auto-launching capability of [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Host (WcfSvcHost.exe) for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Library project, when you debug another project in the same [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="44d84-104">Dazu, mit der Maustaste die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienstprojekt in **Projektmappen-Explorer**, wählen Sie **Eigenschaften**, und klicken Sie auf **WCF Optionen** Registerkarte. Die **starten WCF-Diensthost beim Debuggen eines anderen Projekts in derselben Projektmappe** Kontrollkästchen ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="44d84-104">To do so, right-click the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="44d84-105">Deaktivieren Sie dieses Kontrollkästchen, wenn der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost für dieses bestimmte Projekt beim Debuggen eines anderen Projekts in der gleichen Projektmappe nicht gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="44d84-105">You can clear the box so that [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="44d84-106">Dieses Verhalten wirkt sich weder auf das F5-Debugging noch auf die Funktionen zum Hinzufügen von Dienstverweisen für dieses Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="44d84-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="44d84-107">Diese Option steht für die folgenden Projekte zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="44d84-107">This option is available to the following projects:</span></span>  
  
-   <span data-ttu-id="44d84-108">Bibliotheksprojekt für [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst</span><span class="sxs-lookup"><span data-stu-id="44d84-108">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Library Project.</span></span>  
  
-   <span data-ttu-id="44d84-109">Bibliotheksprojekt für sequenziellen Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="44d84-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="44d84-110">Bibliotheksprojekt für Statuscomputerworkflowdienst</span><span class="sxs-lookup"><span data-stu-id="44d84-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="44d84-111">Bibliotheksprojekt für Syndication-Dienst</span><span class="sxs-lookup"><span data-stu-id="44d84-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44d84-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44d84-112">See Also</span></span>  
 [<span data-ttu-id="44d84-113">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="44d84-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
