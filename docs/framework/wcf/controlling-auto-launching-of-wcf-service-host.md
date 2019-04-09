---
title: Steuern des automatischen Starts des WCF-Diensthosts
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 2fa060e567fba9bb5e6344b2c8fc67fb639ad0f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228496"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="66332-102">Steuern des automatischen Starts des WCF-Diensthosts</span><span class="sxs-lookup"><span data-stu-id="66332-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="66332-103">Sie können den automatischen Start-Funktion von Windows Communication Foundation (WCF)-Diensthost (WcfSvcHost.exe) für einen WCF-Dienstbibliotheksprojekt, steuern, beim Debuggen eines anderen Projekts in der gleichen Visual Studio-Projektmappe mit mehreren Projekten.</span><span class="sxs-lookup"><span data-stu-id="66332-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="66332-104">Dazu, mit der Maustaste in den WCF-Dienstprojekt **Projektmappen-Explorer**, wählen Sie **Eigenschaften**, und klicken Sie auf **WCF-Optionen** Registerkarte. Die **starten WCF-Diensthost beim Debuggen von einem anderen Projekt in der gleichen Projektmappe** Kontrollkästchen ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="66332-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="66332-105">Sie können das Kontrollkästchen deaktivieren, so, dass WCF-Diensthost für dieses bestimmte Projekt beim Debuggen eines anderen Projekts in der gleichen Projektmappe nicht gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="66332-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="66332-106">Dieses Verhalten wirkt sich weder auf das F5-Debugging noch auf die Funktionen zum Hinzufügen von Dienstverweisen für dieses Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="66332-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="66332-107">Diese Option steht für die folgenden Projekte zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="66332-107">This option is available to the following projects:</span></span>  
  
-   <span data-ttu-id="66332-108">WCF-Dienstbibliotheksprojekt.</span><span class="sxs-lookup"><span data-stu-id="66332-108">WCF Service Library Project.</span></span>  
  
-   <span data-ttu-id="66332-109">Bibliotheksprojekt für sequenziellen Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="66332-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="66332-110">Bibliotheksprojekt für Statuscomputerworkflowdienst</span><span class="sxs-lookup"><span data-stu-id="66332-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="66332-111">Bibliotheksprojekt für Syndication-Dienst</span><span class="sxs-lookup"><span data-stu-id="66332-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66332-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66332-112">See also</span></span>

- [<span data-ttu-id="66332-113">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="66332-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
