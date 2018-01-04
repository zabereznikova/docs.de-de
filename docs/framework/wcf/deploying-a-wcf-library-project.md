---
title: Bereitstellen eines WCF-Bibliotheksprojekts
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbbbff1d88559f8ab35caa48fcb04ff1cd7bf015
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-a-wcf-library-project"></a><span data-ttu-id="fd8a4-102">Bereitstellen eines WCF-Bibliotheksprojekts</span><span class="sxs-lookup"><span data-stu-id="fd8a4-102">Deploying a WCF Library Project</span></span>
<span data-ttu-id="fd8a4-103">In diesem Thema wird beschrieben, wie Sie ein [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Dienstbibliotheksprojekt bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fd8a4-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Library Project.</span></span>  
  
## <a name="deploying-a-wcf-service-library"></a><span data-ttu-id="fd8a4-104">Bereitstellen einer WCF-Dienstbibliothek</span><span class="sxs-lookup"><span data-stu-id="fd8a4-104">Deploying a WCF Service Library</span></span>  
 <span data-ttu-id="fd8a4-105">Eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliothek ist eine Dynamic Link Library (DLL).</span><span class="sxs-lookup"><span data-stu-id="fd8a4-105">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library is a dynamic-link library (DLL).</span></span> <span data-ttu-id="fd8a4-106">Als solche kann sie nicht eigenständig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fd8a4-106">As such, it cannot be executed on its own.</span></span> <span data-ttu-id="fd8a4-107">Sie muss vielmehr in einer Hostumgebung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fd8a4-107">It needs to be deployed into a hosting environment.</span></span> <span data-ttu-id="fd8a4-108">Weitere Informationen zu diesem Vorgang finden Sie unter [Hosting und Verwenden von WCF-Webdiensten](http://go.microsoft.com/fwlink/?LinkId=99932).</span><span class="sxs-lookup"><span data-stu-id="fd8a4-108">For more information about this process, see [Hosting and Consuming WCF Services](http://go.microsoft.com/fwlink/?LinkId=99932).</span></span>  
  
 <span data-ttu-id="fd8a4-109">Eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliothek kann wie jeder andere [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fd8a4-109">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library can be deployed like any other [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="fd8a4-110">Beachten Sie jedoch, dass [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] die Konfiguration für DLLs nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fd8a4-110">However, be aware that [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] does not support configuration for DLLs.</span></span> <span data-ttu-id="fd8a4-111"><xref:System.Configuration> unterstützt eine Konfigurationsdatei pro Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="fd8a4-111"><xref:System.Configuration> supports one configuration file per app-domain.</span></span> <span data-ttu-id="fd8a4-112">Das [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliotheksprojekt umgeht diese Beschränkung, indem es während der Entwicklung die Datei app.config für die Bibliothek bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="fd8a4-112">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library project alleviates this limitation by providing an App.config file for the library during development.</span></span> <span data-ttu-id="fd8a4-113">Die Datei app.config wird nach der Bereitstellung jedoch nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="fd8a4-113">However, the App.config file is not recognized after deployment.</span></span>  
  
 <span data-ttu-id="fd8a4-114">Sie müssen den Konfigurationscode in die von der Hostumgebung erkannte Konfigurationsdatei ziehen.</span><span class="sxs-lookup"><span data-stu-id="fd8a4-114">You have to move your configuration code into the configuration file recognized by your hosting environment.</span></span> <span data-ttu-id="fd8a4-115">Für das Selbsthosting sollten Sie den Inhalt der Datei app.config in die Datei app.config der ausführbaren Hostingdatei kopieren.</span><span class="sxs-lookup"><span data-stu-id="fd8a4-115">For self-hosting, you should copy the contents of the App.config file into the App.config file of the hosting executable.</span></span> <span data-ttu-id="fd8a4-116">Wenn Sie IIS zum Hosten Ihres Diensts einsetzen, sollten Sie den Inhalt der Datei app.config in die Datei web.config des virtuellen Verzeichnisses kopieren.</span><span class="sxs-lookup"><span data-stu-id="fd8a4-116">If you use IIS to host your service, you should copy the contents of the App.config file into the Web.config file of the virtual directory.</span></span>
