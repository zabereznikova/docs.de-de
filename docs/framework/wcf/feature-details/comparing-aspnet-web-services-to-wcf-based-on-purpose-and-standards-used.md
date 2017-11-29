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
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards
ASP.NET-Webdienste wurden zum Erstellen von Anwendungen entwickelt, die Nachrichten mit SOAP (Simple Object Access Protocol) über HTTP senden und empfangen. Die Struktur der Nachrichten kann mit einem XML-Schema definiert werden, und zur einfacheren Serialisierung der Nachrichten an und von .NET-Framework-Objekten wird ein Tool bereitgestellt. Mit der Technologie können Metadaten zum Beschreiben von Webdiensten in WSDL (Web Services Description Language) automatisch generiert werden, und ein zweites Tool wird zum Generieren von Clients für Webdienste aus WSDL bereitgestellt.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] eignet sich zum Aktivieren von .NET Framework-Anwendungen für den Austausch von Nachrichten mit anderen Softwareeinheiten. SOAP wird standardmäßig verwendet, die Nachrichten können jedoch ein beliebiges Format aufweisen und mit jedem Transportprotokoll übermittelt werden. Die Struktur der Nachrichten kann mit einem XML-Schema definiert werden, und zur einfacheren Serialisierung der Nachrichten an und von .NET-Framework-Objekten sind mehrere Optionen verfügbar. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann automatisch Metadaten zum Beschreiben von Anwendungen generieren, die mit der Technologie in WSDL erstellt wurden. Außerdem wird ein Tool zum Generieren von Clients für diese Anwendungen aus WSDL bereitgestellt.  
  
 Die von ASP.NET-Webdiensten unterstützten Standards werden dokumentiert [mithilfe von ASP.NET erstellten XML-Webdiensten](http://go.microsoft.com/fwlink/?LinkId=94872). Die umfangreichere Liste der von unterstützten Standards [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aufgelisteten am [unterstützte Webdienstprotokolle vom sicherheitsbindungsarten Interoperabilitätsbindungen](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Vergleichen von ASP.NET-Webdiensten mit WCF auf Grundlage der Entwicklung](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
