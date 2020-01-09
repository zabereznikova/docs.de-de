---
title: Benutzerdefinierte Datendienstanbieter (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
ms.openlocfilehash: a5041b04151a288f9c6c1a567dacec8da8c80a42
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346136"
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Benutzerdefinierte Datendienstanbieter (WCF Data Services)
WCF Data Services enthält eine Reihe von Anbietern, die es Ihnen ermöglichen, ein Datenmodell auf der Grundlage spät gebundener Datentypen zu definieren.  
  
|anbieter|Beschreibung|  
|--------------|-----------------|  
|Metadatenanbieter|Dies ist der benutzerdefinierte Kerndatendienstanbieter, der es Ihnen ermöglicht, durch das Implementieren der <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>-Schnittstelle ein benutzerdefiniertes Datenmodell zur Laufzeit zu definieren.|  
|Abfrageanbieter|Dieser Anbieter ermöglicht es Ihnen, Abfragen an ein benutzerdefiniertes Datenmodell auszuführen, das mit der <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>-Schnittstelle definiert ist. Der Abfrageanbieter wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServiceQueryProvider>-Schnittstelle erstellt.|  
|Updateanbieter|Dieser Anbieter ermöglicht es Ihnen, Updates an in einem benutzerdefinierten Datendienstanbieter verfügbar gemachte Typen vorzunehmen und Parallelität zu verwalten. Ein Updateanbieter wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServiceUpdateProvider>-Schnittstelle erstellt.|  
|Paginganbieter|Dieser Anbieter wird mit dem benutzerdefinierten Datendienstanbieter verwendet, um servergesteuerte Pagingunterstützung zu aktivieren. Ein Paginganbieter für einen benutzerdefinierten Datendienst wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServicePagingProvider>-Schnittstelle erstellt.|  
|Streaminganbieter|Dieser Anbieter ermöglicht es Ihnen, Binary Large Object-Datentypen als Stream verfügbar zu machen. Ein Streaminganbieter wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServiceStreamProvider>-Schnittstelle erstellt. Der Streaminganbieter kann auch mit Entity Framework und Reflektionsdatenquellenanbietern verwendet werden. Weitere Informationen finden Sie unter [streaminganbieter](streaming-provider-wcf-data-services.md).|  
  
## <a name="see-also"></a>Siehe auch

- [Datendienstanbieter](data-services-providers-wcf-data-services.md)
- [Entity Framework-Anbieter](entity-framework-provider-wcf-data-services.md)
- [Reflektionsanbieter](reflection-provider-wcf-data-services.md)
