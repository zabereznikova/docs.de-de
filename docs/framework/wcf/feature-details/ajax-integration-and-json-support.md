---
title: AJAX-Integration und JSON-Unterstützung
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: 3054c3c6faa8dfe621c706d8df031c23d497da0c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576511"
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="934a3-102">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="934a3-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="934a3-103">Die Windows Communication Foundation (WCF)-Unterstützung für ASP.NET Asynchronous JavaScript and XML (Ajax) und das JavaScript Object Notation JSON-Datenformat (JSON) ermöglichen es WCF-Diensten, Vorgänge für AJAX-Clients verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="934a3-103">The Windows Communication Foundation (WCF) support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow WCF services to expose operations to AJAX clients.</span></span> <span data-ttu-id="934a3-104">AJAX-Clients sind Webseiten, die JavaScript-Code ausführen und über HTTP-Anforderungen auf diese WCF-Dienste zugreifen.</span><span class="sxs-lookup"><span data-stu-id="934a3-104">AJAX clients are Web pages running JavaScript code and accessing these WCF services using HTTP requests.</span></span> <span data-ttu-id="934a3-105">Die Themen in diesem Abschnitt enthalten Informationen über diese Unterstützung und ihre Implementierung.</span><span class="sxs-lookup"><span data-stu-id="934a3-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="934a3-106">Weitere Informationen zu ASP.NET AJAX und der zugehörigen Integration in ASP.NET 2,0 finden Sie unter [ASP.NET AJAX Overview](https://docs.microsoft.com/previous-versions/aspnet/bb398874(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="934a3-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](https://docs.microsoft.com/previous-versions/aspnet/bb398874(v=vs.100)).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="934a3-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="934a3-107">In This Section</span></span>  
 [<span data-ttu-id="934a3-108">Erstellen von WCF-Diensten für ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="934a3-108">Creating WCF Services for ASP.NET AJAX</span></span>](creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="934a3-109">Beschreibt, wie ein WCF-Dienst für AJAX-Clients verfügbar gemacht werden kann, indem der entsprechende AJAX-Endpunkt entweder über die Konfiguration oder mithilfe einer Diensthostfactory für die Generierung eines Dienst Hosts, der den AJAX-Endpunkt automatisch konfiguriert, hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="934a3-109">Describes how a WCF service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="934a3-110">Erstellen von WCF AJAX-Diensten ohne ASP.NET</span><span class="sxs-lookup"><span data-stu-id="934a3-110">Creating WCF AJAX Services without ASP.NET</span></span>](creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="934a3-111">Beschreibt, wie ein WCF-Dienst ohne Verwendung von ASP.NET erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="934a3-111">Describes how to create a WCF service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="934a3-112">Unterstützung für JSON und andere Datenübertragungsformate</span><span class="sxs-lookup"><span data-stu-id="934a3-112">Support for JSON and Other Data Transfer Formats</span></span>](support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="934a3-113">Beschreibt die Unterstützung des JSON-Formats, das in der Regel (statt XML) für den Nachrichtenaustausch mit ASP.NET AJAX-Diensten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="934a3-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="934a3-114">Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF</span><span class="sxs-lookup"><span data-stu-id="934a3-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="934a3-115">Beschreibt, wie ein AJAX-fähiger ASP.NET-Webdienst zu einem WCF-Webdienst migriert wird.</span><span class="sxs-lookup"><span data-stu-id="934a3-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a WCF Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="934a3-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="934a3-116">See also</span></span>

- <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>
- [<span data-ttu-id="934a3-117">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="934a3-117">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
