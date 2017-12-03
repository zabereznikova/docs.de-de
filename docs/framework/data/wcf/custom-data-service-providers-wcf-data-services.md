---
title: Benutzerdefinierte Datendienstanbieter (WCF Data Services)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9a242f6f62435440660c81d6b9838250f3d253c0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Benutzerdefinierte Datendienstanbieter (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] umfasst eine Reihe von Anbietern, die es Ihnen ermöglicht, ein Datenmodell auf der Grundlage spät gebundener Datentypen zu definieren.  
  
|Anbieter|Beschreibung|  
|--------------|-----------------|  
|Metadatenanbieter|Dies ist der benutzerdefinierte Kerndatendienstanbieter, der es Ihnen ermöglicht, durch das Implementieren der <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>-Schnittstelle ein benutzerdefiniertes Datenmodell zur Laufzeit zu definieren.|  
|Abfrageanbieter|Dieser Anbieter ermöglicht es Ihnen, Abfragen an ein benutzerdefiniertes Datenmodell auszuführen, das mit der <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>-Schnittstelle definiert ist. Der Abfrageanbieter wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServiceQueryProvider>-Schnittstelle erstellt.|  
|Updateanbieter|Dieser Anbieter ermöglicht es Ihnen, Updates an in einem benutzerdefinierten Datendienstanbieter verfügbar gemachte Typen vorzunehmen und Parallelität zu verwalten. Ein Updateanbieter wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServiceUpdateProvider>-Schnittstelle erstellt.|  
|Paginganbieter|Dieser Anbieter wird mit dem benutzerdefinierten Datendienstanbieter verwendet, um servergesteuerte Pagingunterstützung zu aktivieren. Ein Paginganbieter für einen benutzerdefinierten Datendienst wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServicePagingProvider>-Schnittstelle erstellt.|  
|Streaminganbieter|Dieser Anbieter ermöglicht es Ihnen, Binary Large Object-Datentypen als Stream verfügbar zu machen. Ein Streaminganbieter wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServiceStreamProvider>-Schnittstelle erstellt. Der Streaminganbieter kann auch mit Entity Framework und Reflektionsdatenquellenanbietern verwendet werden. Weitere Informationen finden Sie unter [Streaming Provider](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).|  
  
 Weitere Informationen finden Sie im Artikel [Benutzerdefinierte Datendienstanbieter](http://go.microsoft.com/fwlink/?LinkID=186850) und [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Anbietertoolkit im die [OData SDK](http://go.microsoft.com/fwlink/?LinkId=186069).  
  
## <a name="see-also"></a>Siehe auch  
 [Datendienstanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Entity Framework-Anbieter](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
 [Reflektionsanbieter](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
