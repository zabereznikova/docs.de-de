---
title: Benutzerdefinierte Datendienstanbieter (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
ms.openlocfilehash: f198de20a3fa788fb8d5f2dc4ebf799989814756
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184001"
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Benutzerdefinierte Datendienstanbieter (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] enthält eine Reihe von Anbietern, die Ihnen ermöglicht, ein Datenmodell auf Grundlage spät gebundener Datentypen zu definieren.  
  
|Anbieter|Beschreibung|  
|--------------|-----------------|  
|Metadatenanbieter|Dies ist der benutzerdefinierte Kerndatendienstanbieter, der es Ihnen ermöglicht, durch das Implementieren der <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>-Schnittstelle ein benutzerdefiniertes Datenmodell zur Laufzeit zu definieren.|  
|Abfrageanbieter|Dieser Anbieter ermöglicht es Ihnen, Abfragen an ein benutzerdefiniertes Datenmodell auszuführen, das mit der <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>-Schnittstelle definiert ist. Der Abfrageanbieter wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServiceQueryProvider>-Schnittstelle erstellt.|  
|Updateanbieter|Dieser Anbieter ermöglicht es Ihnen, Updates an in einem benutzerdefinierten Datendienstanbieter verfügbar gemachte Typen vorzunehmen und Parallelität zu verwalten. Ein Updateanbieter wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServiceUpdateProvider>-Schnittstelle erstellt.|  
|Paginganbieter|Dieser Anbieter wird mit dem benutzerdefinierten Datendienstanbieter verwendet, um servergesteuerte Pagingunterstützung zu aktivieren. Ein Paginganbieter für einen benutzerdefinierten Datendienst wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServicePagingProvider>-Schnittstelle erstellt.|  
|Streaminganbieter|Dieser Anbieter ermöglicht es Ihnen, Binary Large Object-Datentypen als Stream verfügbar zu machen. Ein Streaminganbieter wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServiceStreamProvider>-Schnittstelle erstellt. Der Streaminganbieter kann auch mit Entity Framework und Reflektionsdatenquellenanbietern verwendet werden. Weitere Informationen finden Sie unter [Streaminganbieter](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).|  
  
 Weitere Informationen finden Sie im Artikel [Benutzerdefinierte Datendienstanbieter](https://go.microsoft.com/fwlink/?LinkID=186850) und [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Anbietertoolkit im der [OData SDK](https://go.microsoft.com/fwlink/?LinkId=186069).  
  
## <a name="see-also"></a>Siehe auch

- [Datendienstanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [Entity Framework-Anbieter](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)
- [Reflektionsanbieter](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
