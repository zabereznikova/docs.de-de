---
title: Bereitstellen von Diensten
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 684b781c568518cfb321d8021e4f7062e855e6aa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798142"
---
# <a name="deploying-services"></a><span data-ttu-id="78516-102">Bereitstellen von Diensten</span><span class="sxs-lookup"><span data-stu-id="78516-102">Deploying Services</span></span>
<span data-ttu-id="78516-103">In diesem Thema wird beschrieben, wie Sie eine Windows Communication Foundation (WCF)-Anwendung in einer Laufzeitumgebung bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="78516-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="78516-104">Auswählen der Hostumgebung für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="78516-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="78516-105">WCF-Dienste können in jedem Windows-Prozess ausgeführt werden, der verwalteten Code unterstützt.</span><span class="sxs-lookup"><span data-stu-id="78516-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="78516-106">Zur Aktivierung muss der Dienst in einer Laufzeitumgebung gehostet werden, die ihn erstellt und seinen Kontext sowie seine Lebensdauer steuert.</span><span class="sxs-lookup"><span data-stu-id="78516-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="78516-107">Die Hostingoptionen umfassen eine breite Palette: von einfachen Konsolenanwendungen bis zu Serverumgebungen, wie einem Windows-Dienst oder Internetinformationsdienste (IIS), oder auch von Windows Activation Service (WAS) verwaltete Arbeitsprozesse.</span><span class="sxs-lookup"><span data-stu-id="78516-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="78516-108">Informationen zu den verschiedenen [Hostingoptionen](../hosting-services.md)für Ihre WCF-Anwendung finden Sie unter Hosting-Dienste.</span><span class="sxs-lookup"><span data-stu-id="78516-108">To review the different hosting options for your WCF application, see [Hosting Services](../hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78516-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78516-109">See also</span></span>

- [<span data-ttu-id="78516-110">Hosting</span><span class="sxs-lookup"><span data-stu-id="78516-110">Hosting</span></span>](../feature-details/hosting.md)
- [<span data-ttu-id="78516-111">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="78516-111">Hosting Services</span></span>](../hosting-services.md)
