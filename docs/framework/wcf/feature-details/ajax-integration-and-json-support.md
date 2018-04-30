---
title: AJAX-Integration und JSON-Unterstützung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0d62da8cf67fb8f996f341018c39146b51e308c3
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="5f698-102">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="5f698-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="5f698-103">Da [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ASP.NET AJAX (Asynchronous JavaScript and XML) und das Datenformat JSON (JavaScript Object Notation) unterstützt, können [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste Vorgänge für AJAX-Clients verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="5f698-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to expose operations to AJAX clients.</span></span> <span data-ttu-id="5f698-104">AJAX-Clients sind Webseiten, die JavaScript-Code ausführen und über HTTP-Anforderungen auf diese [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5f698-104">AJAX clients are Web pages running JavaScript code and accessing these [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services using HTTP requests.</span></span> <span data-ttu-id="5f698-105">Die Themen in diesem Abschnitt enthalten Informationen über diese Unterstützung und ihre Implementierung.</span><span class="sxs-lookup"><span data-stu-id="5f698-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="5f698-106">Weitere Informationen zu ASP.NET AJAX und die Integration in ASP.NET 2.0 finden Sie unter [Übersicht über ASP.NET AJAX](http://go.microsoft.com/fwlink/?LinkId=96725).</span><span class="sxs-lookup"><span data-stu-id="5f698-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](http://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f698-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5f698-107">In This Section</span></span>  
 [<span data-ttu-id="5f698-108">Erstellen von WCF-Diensten für ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="5f698-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="5f698-109">Beschreibt, wie ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst für AJAX-Clients verfügbar gemacht werden kann, indem entweder über die Konfiguration oder mithilfe einer Diensthostfactory zur Erzeugung eines Dienstshosts, der den AJAX-Endpunkt automatisch konfiguriert, der entsprechende AJAX-Endpunkt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5f698-109">Describes how an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="5f698-110">Erstellen von WCF AJAX-Diensten ohne ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5f698-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="5f698-111">Beschreibt, wie ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst ohne ASP.NET erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5f698-111">Describes how to create an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="5f698-112">Unterstützung für JSON und andere Datenübertragungsformate</span><span class="sxs-lookup"><span data-stu-id="5f698-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="5f698-113">Beschreibt die Unterstützung des JSON-Formats, das in der Regel (statt XML) für den Nachrichtenaustausch mit ASP.NET AJAX-Diensten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5f698-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="5f698-114">Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste zu WCF</span><span class="sxs-lookup"><span data-stu-id="5f698-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="5f698-115">Beschreibt, wie ein AJAX-fähiger ASP.NET-Webdienst zu einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Webdienst migriert wird.</span><span class="sxs-lookup"><span data-stu-id="5f698-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f698-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f698-116">See Also</span></span>  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [<span data-ttu-id="5f698-117">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="5f698-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
