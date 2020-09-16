---
title: Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards
ms.date: 03/30/2017
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
ms.openlocfilehash: 1bd3a23d90680568bb2f909dec7902f967895495
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556667"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards
ASP.NET-Webdienste wurden zum Erstellen von Anwendungen entwickelt, die Nachrichten mit SOAP (Simple Object Access Protocol) über HTTP senden und empfangen. Die Struktur der Nachrichten kann mit einem XML-Schema definiert werden, und zur einfacheren Serialisierung der Nachrichten an und von .NET-Framework-Objekten wird ein Tool bereitgestellt. Mit der Technologie können Metadaten zum Beschreiben von Webdiensten in WSDL (Web Services Description Language) automatisch generiert werden, und ein zweites Tool wird zum Generieren von Clients für Webdienste aus WSDL bereitgestellt.  
  
 WCF dient zum Aktivieren von .NET Framework Anwendungen zum Austauschen von Nachrichten mit anderen Software Entitäten. SOAP wird standardmäßig verwendet, die Nachrichten können jedoch ein beliebiges Format aufweisen und mit jedem Transportprotokoll übermittelt werden. Die Struktur der Nachrichten kann mit einem XML-Schema definiert werden, und zur einfacheren Serialisierung der Nachrichten an und von .NET-Framework-Objekten sind mehrere Optionen verfügbar. WCF kann automatisch Metadaten generieren, um Anwendungen zu beschreiben, die mit der Technologie in WSDL erstellt wurden, und bietet außerdem ein Tool zum Generieren von Clients für diese Anwendungen aus der WSDL.  
  
 Die von ASP.NET-Webdiensten unterstützten Standards sind in den [Vorteilen von XML-Webdiensten dokumentiert, die mithilfe von ASP.NET erstellt wurden](/previous-versions/dotnet/netframework-4.0/0859ebft(v=vs.100)). Die umfassendere Liste der von WCF unterstützten Standards ist unter [Webdienst Protokolle aufgeführt, die von vom System bereitgestellten Interoperabilitäts Bindungen unterstützt](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)werden.  
  
## <a name="see-also"></a>Siehe auch

- [Vergleichen von ASP.NET-Webdiensten mit WCF auf Grundlage der Entwicklung](comparing-aspnet-web-services-to-wcf-based-on-development.md)
