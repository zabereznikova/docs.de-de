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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c6dc444b8a4c19dbe486eb904e0f054e05f6fe6a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a><span data-ttu-id="a836c-102">Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards</span><span class="sxs-lookup"><span data-stu-id="a836c-102">Comparing ASP.NET Web Services to WCF Based on Purpose and Standards Used</span></span>
<span data-ttu-id="a836c-103">ASP.NET-Webdienste wurden zum Erstellen von Anwendungen entwickelt, die Nachrichten mit SOAP (Simple Object Access Protocol) über HTTP senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="a836c-103">ASP.NET Web services was developed for building applications that send and receive messages by using the Simple Object Access Protocol (SOAP) over HTTP.</span></span> <span data-ttu-id="a836c-104">Die Struktur der Nachrichten kann mit einem XML-Schema definiert werden, und zur einfacheren Serialisierung der Nachrichten an und von .NET-Framework-Objekten wird ein Tool bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a836c-104">The structure of the messages can be defined using an XML Schema, and a tool is provided to facilitate serializing the messages to and from .NET Framework objects.</span></span> <span data-ttu-id="a836c-105">Mit der Technologie können Metadaten zum Beschreiben von Webdiensten in WSDL (Web Services Description Language) automatisch generiert werden, und ein zweites Tool wird zum Generieren von Clients für Webdienste aus WSDL bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a836c-105">The technology can automatically generate metadata to describe Web services in the Web Services Description Language (WSDL), and a second tool is provided for generating clients for Web services from the WSDL.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a836c-106"> eignet sich zum Aktivieren von .NET Framework-Anwendungen für den Austausch von Nachrichten mit anderen Softwareeinheiten.</span><span class="sxs-lookup"><span data-stu-id="a836c-106"> is for enabling .NET Framework applications to exchange messages with other software entities.</span></span> <span data-ttu-id="a836c-107">SOAP wird standardmäßig verwendet, die Nachrichten können jedoch ein beliebiges Format aufweisen und mit jedem Transportprotokoll übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="a836c-107">SOAP is used by default, but the messages can be in any format, and conveyed by using any transport protocol.</span></span> <span data-ttu-id="a836c-108">Die Struktur der Nachrichten kann mit einem XML-Schema definiert werden, und zur einfacheren Serialisierung der Nachrichten an und von .NET-Framework-Objekten sind mehrere Optionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a836c-108">The structure of the messages can be defined using an XML Schema, and there are various options for serializing the messages to and from .NET Framework objects.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a836c-109"> kann automatisch Metadaten zum Beschreiben von Anwendungen generieren, die mit der Technologie in WSDL erstellt wurden. Außerdem wird ein Tool zum Generieren von Clients für diese Anwendungen aus WSDL bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a836c-109"> can automatically generate metadata to describe applications built using the technology in WSDL, and it also provides a tool for generating clients for those applications from the WSDL.</span></span>  
  
 <span data-ttu-id="a836c-110">Die von ASP.NET-Webdiensten unterstützten Standards werden dokumentiert [mithilfe von ASP.NET erstellten XML-Webdiensten](http://go.microsoft.com/fwlink/?LinkId=94872).</span><span class="sxs-lookup"><span data-stu-id="a836c-110">The standards supported by ASP.NET Web services are documented in [XML Web Services Created Using ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94872).</span></span> <span data-ttu-id="a836c-111">Die umfangreichere Liste der von unterstützten Standards [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aufgelisteten am [unterstützte Webdienstprotokolle vom sicherheitsbindungsarten Interoperabilitätsbindungen](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="a836c-111">The more extensive list of standards supported by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are listed at [Web Services Protocols Supported by System-Provided Interoperability Bindings](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a836c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a836c-112">See Also</span></span>  
 [<span data-ttu-id="a836c-113">Vergleichen von ASP.NET-Webdiensten mit WCF auf Grundlage der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="a836c-113">Comparing ASP.NET Web Services to WCF Based on Development</span></span>](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
