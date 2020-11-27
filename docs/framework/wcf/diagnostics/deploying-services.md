---
title: Bereitstellen von Diensten
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 07bd2a3938f238336dc00fa2e0826a28a9363a4a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294806"
---
# <a name="deploying-services"></a><span data-ttu-id="40033-102">Bereitstellen von Diensten</span><span class="sxs-lookup"><span data-stu-id="40033-102">Deploying Services</span></span>

<span data-ttu-id="40033-103">In diesem Thema wird beschrieben, wie Sie eine Windows Communication Foundation (WCF)-Anwendung in einer Laufzeitumgebung bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="40033-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="40033-104">Auswählen der Hostumgebung für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="40033-104">Choosing the Hosting Environment for Your Application</span></span>  

 <span data-ttu-id="40033-105">WCF-Dienste können in jedem Windows-Prozess ausgeführt werden, der verwalteten Code unterstützt.</span><span class="sxs-lookup"><span data-stu-id="40033-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="40033-106">Zur Aktivierung muss der Dienst in einer Laufzeitumgebung gehostet werden, die ihn erstellt und seinen Kontext sowie seine Lebensdauer steuert.</span><span class="sxs-lookup"><span data-stu-id="40033-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="40033-107">Die Hostingoptionen umfassen eine breite Palette: von einfachen Konsolenanwendungen bis zu Serverumgebungen, wie einem Windows-Dienst oder Internetinformationsdienste (IIS), oder auch von Windows Activation Service (WAS) verwaltete Arbeitsprozesse.</span><span class="sxs-lookup"><span data-stu-id="40033-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="40033-108">Informationen zu den verschiedenen [Hostingoptionen](../hosting-services.md)für Ihre WCF-Anwendung finden Sie unter Hosting-Dienste.</span><span class="sxs-lookup"><span data-stu-id="40033-108">To review the different hosting options for your WCF application, see [Hosting Services](../hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40033-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40033-109">See also</span></span>

- [<span data-ttu-id="40033-110">Hosting</span><span class="sxs-lookup"><span data-stu-id="40033-110">Hosting</span></span>](../feature-details/hosting.md)
- [<span data-ttu-id="40033-111">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="40033-111">Hosting Services</span></span>](../hosting-services.md)
