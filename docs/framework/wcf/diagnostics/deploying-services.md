---
title: Bereitstellen von Diensten
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 2c3cd17b597fafcd02b9155089bc583fafbc9dea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085757"
---
# <a name="deploying-services"></a><span data-ttu-id="4d380-102">Bereitstellen von Diensten</span><span class="sxs-lookup"><span data-stu-id="4d380-102">Deploying Services</span></span>
<span data-ttu-id="4d380-103">In diesem Thema wird beschrieben, wie Sie eine Windows Communication Foundation (WCF)-Anwendung auf einer Laufzeitumgebung bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="4d380-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="4d380-104">Auswählen der Hostumgebung für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="4d380-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="4d380-105">WCF-Dienste sollen in jedem Windows-Prozess ausgeführt werden soll, Code unterstützt verwalteten.</span><span class="sxs-lookup"><span data-stu-id="4d380-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="4d380-106">Zur Aktivierung muss der Dienst in einer Laufzeitumgebung gehostet werden, die ihn erstellt und seinen Kontext sowie seine Lebensdauer steuert.</span><span class="sxs-lookup"><span data-stu-id="4d380-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="4d380-107">Die Hostingoptionen umfassen eine breite Palette: von einfachen Konsolenanwendungen bis zu Serverumgebungen, wie einem Windows-Dienst oder Internetinformationsdienste (IIS), oder auch von Windows Activation Service (WAS) verwaltete Arbeitsprozesse.</span><span class="sxs-lookup"><span data-stu-id="4d380-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="4d380-108">Die verschiedenen Hostingoptionen für Ihre WCF-Anwendung finden Sie unter [Hostingdienste](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="4d380-108">To review the different hosting options for your WCF application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d380-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d380-109">See also</span></span>

- [<span data-ttu-id="4d380-110">Hosting</span><span class="sxs-lookup"><span data-stu-id="4d380-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)
- [<span data-ttu-id="4d380-111">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="4d380-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
