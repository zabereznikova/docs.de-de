---
title: Bereitstellen von Diensten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e32570b381d6cab4326a13246dfe053b5032589
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-services"></a><span data-ttu-id="fe8d4-102">Bereitstellen von Diensten</span><span class="sxs-lookup"><span data-stu-id="fe8d4-102">Deploying Services</span></span>
<span data-ttu-id="fe8d4-103">In diesem Thema wird beschrieben, wie Sie eine [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Anwendung in einer Laufzeitumgebung bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="fe8d4-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="fe8d4-104">Auswählen der Hostumgebung für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="fe8d4-104">Choosing the Hosting Environment for Your Application</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="fe8d4-105">-Dienste können in jedem Windows-Prozess ausgeführt werden, der verwalteten Code unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fe8d4-105"> services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="fe8d4-106">Zur Aktivierung muss der Dienst in einer Laufzeitumgebung gehostet werden, die ihn erstellt und seinen Kontext sowie seine Lebensdauer steuert.</span><span class="sxs-lookup"><span data-stu-id="fe8d4-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="fe8d4-107">Die Hostingoptionen umfassen eine breite Palette: von einfachen Konsolenanwendungen bis zu Serverumgebungen, wie einem Windows-Dienst oder Internetinformationsdienste (IIS), oder auch von Windows Activation Service (WAS) verwaltete Arbeitsprozesse.</span><span class="sxs-lookup"><span data-stu-id="fe8d4-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="fe8d4-108">Überprüfen Sie die anderen Hostingoptionen für Ihre [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Anwendung finden Sie unter [Hostingdienste](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="fe8d4-108">To review the different hosting options for your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe8d4-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe8d4-109">See Also</span></span>  
 [<span data-ttu-id="fe8d4-110">Hosting</span><span class="sxs-lookup"><span data-stu-id="fe8d4-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="fe8d4-111">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="fe8d4-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
