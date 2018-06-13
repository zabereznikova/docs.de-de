---
title: Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards
ms.date: 03/30/2017
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
ms.openlocfilehash: 60f2e9ccbfd5dbf205f3ed570ece1d4169f21e3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488311"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards
ASP.NET-Webdienste wurden zum Erstellen von Anwendungen entwickelt, die Nachrichten mit SOAP (Simple Object Access Protocol) über HTTP senden und empfangen. Die Struktur der Nachrichten kann mit einem XML-Schema definiert werden, und zur einfacheren Serialisierung der Nachrichten an und von .NET-Framework-Objekten wird ein Tool bereitgestellt. Mit der Technologie können Metadaten zum Beschreiben von Webdiensten in WSDL (Web Services Description Language) automatisch generiert werden, und ein zweites Tool wird zum Generieren von Clients für Webdienste aus WSDL bereitgestellt.  
  
 WCF eignet sich zum Aktivieren von .NET Framework-Anwendungen für den Austausch von Nachrichten mit anderen Softwareeinheiten. SOAP wird standardmäßig verwendet, die Nachrichten können jedoch ein beliebiges Format aufweisen und mit jedem Transportprotokoll übermittelt werden. Die Struktur der Nachrichten kann mit einem XML-Schema definiert werden, und zur einfacheren Serialisierung der Nachrichten an und von .NET-Framework-Objekten sind mehrere Optionen verfügbar. WCF kann automatisch Metadaten zum Beschreiben von Anwendungen, die mit der Technologie in WSDL erstellt wurden, und bietet auch ein Tool zum Generieren von Clients für diese Anwendungen aus WSDL.  
  
 Die von ASP.NET-Webdiensten unterstützten Standards werden dokumentiert [mithilfe von ASP.NET erstellten XML-Webdiensten](http://go.microsoft.com/fwlink/?LinkId=94872). Die umfangreichere Liste der von WCF unterstützten Standards werden am aufgeführten [unterstützte Webdienstprotokolle vom sicherheitsbindungsarten Interoperabilitätsbindungen](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Vergleichen von ASP.NET-Webdiensten mit WCF auf Grundlage der Entwicklung](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
