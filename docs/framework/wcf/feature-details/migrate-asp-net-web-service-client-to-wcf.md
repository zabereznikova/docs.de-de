---
title: 'Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d77e07cca938b67f5b79416ac4d8fdef96739ed2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a><span data-ttu-id="c9c15-102">Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="c9c15-102">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="c9c15-103">Mit dem folgenden Verfahren werden die Schritte beschrieben, die durchgeführt werden müssen, um ASP.NET-Webdienst-Clientcode zu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="c9c15-103">The following procedure describes the broad steps that need to be followed to migrate ASP.NET Web Service client code to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="c9c15-104">Prozedur</span><span class="sxs-lookup"><span data-stu-id="c9c15-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a><span data-ttu-id="c9c15-105">So migrieren Sie ASP.NET-Webdienst-Clientcode zu WCF</span><span class="sxs-lookup"><span data-stu-id="c9c15-105">To migrate ASP.NET Web Service client code to WCF</span></span>  
  
1.  <span data-ttu-id="c9c15-106">Stellen Sie sicher, dass für den Client ein umfassender Satz an Tests vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c9c15-106">Ensure that a comprehensive set of tests exist for the client.</span></span>  
  
2.  <span data-ttu-id="c9c15-107">Verwenden Sie Visual Studio 2005, um ein Upgrade der Clientanwendung auf .NET 2.0 durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="c9c15-107">Use Visual Studio 2005 to upgrade the client application to .NET 2.0.</span></span> <span data-ttu-id="c9c15-108">Führen Sie die Tests aus.</span><span class="sxs-lookup"><span data-stu-id="c9c15-108">Run the set of tests.</span></span>  
  
3.  <span data-ttu-id="c9c15-109">Entfernen Sie ASP.NET-Clientcode aus dem Clientprojekt.</span><span class="sxs-lookup"><span data-stu-id="c9c15-109">Remove ASP.NET client code from the client project.</span></span> <span data-ttu-id="c9c15-110">Dieser Code wird mithilfe des WSDL.exe-Tools in Modulen generiert.</span><span class="sxs-lookup"><span data-stu-id="c9c15-110">That code is in modules generated using the WSDL.exe tool.</span></span>  
  
4.  <span data-ttu-id="c9c15-111">Generieren von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Clientcode der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c9c15-111">Generate [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client code using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="c9c15-112">Fügen Sie diesen Code zum Clientprojekt hinzu, und fügen Sie die Konfigurationsausgabe in die bestehende Konfigurationsdatei des Clients ein.</span><span class="sxs-lookup"><span data-stu-id="c9c15-112">Add that code to the client project and merge the configuration output into the client’s existing configuration file.</span></span>  
  
5.  <span data-ttu-id="c9c15-113">Kompilieren Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c9c15-113">Compile the application.</span></span> <span data-ttu-id="c9c15-114">Korrigieren Sie die Kompilierungsfehler, indem Sie Verweise auf ehemalige ASP.NET-Clienttypen durch Verweise auf die neuen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clienttypen ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c9c15-114">Repair the compilation errors by replacing references to the former ASP.NET client types with references to the new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client types.</span></span>  
  
6.  <span data-ttu-id="c9c15-115">Führen Sie die Tests aus.</span><span class="sxs-lookup"><span data-stu-id="c9c15-115">Run the set of tests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9c15-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9c15-116">See Also</span></span>  
 [<span data-ttu-id="c9c15-117">Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="c9c15-117">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
