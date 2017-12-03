---
title: Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f3fec18cb93486dfe9d2b09582ad263d19b00617
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a><span data-ttu-id="c7966-102">Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards</span><span class="sxs-lookup"><span data-stu-id="c7966-102">Comparing ASP.NET Web Services to WCF Based on Purpose and Standards Used</span></span>
<span data-ttu-id="c7966-103">ASP.NET-Webdienste wurden zum Erstellen von Anwendungen entwickelt, die Nachrichten mit SOAP (Simple Object Access Protocol) über HTTP senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="c7966-103">ASP.NET Web services was developed for building applications that send and receive messages by using the Simple Object Access Protocol (SOAP) over HTTP.</span></span> <span data-ttu-id="c7966-104">Die Struktur der Nachrichten kann mit einem XML-Schema definiert werden, und zur einfacheren Serialisierung der Nachrichten an und von .NET-Framework-Objekten wird ein Tool bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c7966-104">The structure of the messages can be defined using an XML Schema, and a tool is provided to facilitate serializing the messages to and from .NET Framework objects.</span></span> <span data-ttu-id="c7966-105">Mit der Technologie können Metadaten zum Beschreiben von Webdiensten in WSDL (Web Services Description Language) automatisch generiert werden, und ein zweites Tool wird zum Generieren von Clients für Webdienste aus WSDL bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c7966-105">The technology can automatically generate metadata to describe Web services in the Web Services Description Language (WSDL), and a second tool is provided for generating clients for Web services from the WSDL.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c7966-106"> eignet sich zum Aktivieren von .NET Framework-Anwendungen für den Austausch von Nachrichten mit anderen Softwareeinheiten.</span><span class="sxs-lookup"><span data-stu-id="c7966-106"> is for enabling .NET Framework applications to exchange messages with other software entities.</span></span> <span data-ttu-id="c7966-107">SOAP wird standardmäßig verwendet, die Nachrichten können jedoch ein beliebiges Format aufweisen und mit jedem Transportprotokoll übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="c7966-107">SOAP is used by default, but the messages can be in any format, and conveyed by using any transport protocol.</span></span> <span data-ttu-id="c7966-108">Die Struktur der Nachrichten kann mit einem XML-Schema definiert werden, und zur einfacheren Serialisierung der Nachrichten an und von .NET-Framework-Objekten sind mehrere Optionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7966-108">The structure of the messages can be defined using an XML Schema, and there are various options for serializing the messages to and from .NET Framework objects.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c7966-109"> kann automatisch Metadaten zum Beschreiben von Anwendungen generieren, die mit der Technologie in WSDL erstellt wurden. Außerdem wird ein Tool zum Generieren von Clients für diese Anwendungen aus WSDL bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c7966-109"> can automatically generate metadata to describe applications built using the technology in WSDL, and it also provides a tool for generating clients for those applications from the WSDL.</span></span>  
  
 <span data-ttu-id="c7966-110">Die von ASP.NET-Webdiensten unterstützten Standards werden dokumentiert [mithilfe von ASP.NET erstellten XML-Webdiensten](http://go.microsoft.com/fwlink/?LinkId=94872).</span><span class="sxs-lookup"><span data-stu-id="c7966-110">The standards supported by ASP.NET Web services are documented in [XML Web Services Created Using ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94872).</span></span> <span data-ttu-id="c7966-111">Die umfangreichere Liste der von unterstützten Standards [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aufgelisteten am [unterstützte Webdienstprotokolle vom sicherheitsbindungsarten Interoperabilitätsbindungen](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="c7966-111">The more extensive list of standards supported by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are listed at [Web Services Protocols Supported by System-Provided Interoperability Bindings](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7966-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7966-112">See Also</span></span>  
 [<span data-ttu-id="c7966-113">Vergleichen von ASP.NET-Webdiensten mit WCF auf Grundlage der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="c7966-113">Comparing ASP.NET Web Services to WCF Based on Development</span></span>](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
