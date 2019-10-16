---
title: Steuern des automatischen Starts des WCF-Diensthosts
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 7f21cd7ea600277461146387b962a89ea0a8472b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320629"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="c2134-102">Steuern des automatischen Starts des WCF-Diensthosts</span><span class="sxs-lookup"><span data-stu-id="c2134-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="c2134-103">Sie können die Funktion zum automatischen Starten von Windows Communication Foundation (WCF)-Dienst Hosts (WcfSvcHost. exe) für ein WCF-Dienst Bibliotheksprojekt steuern, wenn Sie ein anderes Projekt in derselben Visual Studio-Projekt Mappe Debuggen, die mehrere Projekte enthält.</span><span class="sxs-lookup"><span data-stu-id="c2134-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="c2134-104">Klicken Sie hierzu in **Projektmappen-Explorer**mit der rechten Maustaste auf das WCF-Dienstprojekt, wählen Sie **Eigenschaften**aus, und klicken Sie auf die Registerkarte **WCF-Optionen** . Das Kontrollkästchen **WCF-Dienst Host beim Debuggen eines anderen Projekts in derselben Projekt Mappe starten** ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c2134-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="c2134-105">Sie können das Kontrollkästchen deaktivieren, sodass der WCF-Dienst Host für dieses bestimmte Projekt nicht gestartet wird, wenn ein anderes Projekt in derselben Projekt Mappe deentschlbelt wird.</span><span class="sxs-lookup"><span data-stu-id="c2134-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="c2134-106">Dieses Verhalten wirkt sich weder auf das F5-Debugging noch auf die Funktionen zum Hinzufügen von Dienstverweisen für dieses Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="c2134-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="c2134-107">Diese Option steht für die folgenden Projekte zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="c2134-107">This option is available to the following projects:</span></span>  
  
- <span data-ttu-id="c2134-108">WCF-Dienst Bibliotheksprojekt.</span><span class="sxs-lookup"><span data-stu-id="c2134-108">WCF Service Library Project.</span></span>  
  
- <span data-ttu-id="c2134-109">Bibliotheksprojekt für sequenziellen Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="c2134-109">Sequential Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="c2134-110">Bibliotheksprojekt für Statuscomputerworkflowdienst</span><span class="sxs-lookup"><span data-stu-id="c2134-110">State Machine Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="c2134-111">Bibliotheksprojekt für Syndication-Dienst</span><span class="sxs-lookup"><span data-stu-id="c2134-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2134-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2134-112">See also</span></span>

- [<span data-ttu-id="c2134-113">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="c2134-113">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
