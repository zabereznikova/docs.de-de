---
title: Datendienstanbieter (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: a0160b1b-3d9c-4cc8-8391-cb0986a60a41
ms.openlocfilehash: dcca6023349148ac7f65f97028d876514ef31163
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91182834"
---
# <a name="data-services-providers-wcf-data-services"></a>Datendienstanbieter (WCF Data Services)

WCF Data Services unterstützt mehrere Anbieter Modelle zum verfügbar machen von Daten als Open Data Protocol-Feed (odata). Dieses Thema enthält Informationen, mit denen Sie den besten WCF Data Services Anbieter für Ihre Datenquelle auswählen können.  
  
## <a name="data-source-providers"></a>Datenquellenanbieter  

 WCF Data Services unterstützt die folgenden Anbieter zum Definieren des Datenmodells eines Daten Dienstanbietern.  
  
|Anbieter|Beschreibung|  
|--------------|-----------------|  
|Entity Framework-Anbieter|Dieser Anbieter ermöglicht Ihnen mithilfe von ADO.NET Entity Framework, relationale Daten durch das Definieren eines Datenmodells, das relationalen Daten zugeordnet wird, mit einem Datendienst zu verwenden. Die Datenquelle kann SQL Server oder eine beliebige andere Datenquelle mit Drittanbieterunterstützung für das Entity Framework sein. Sie sollten den Entity Framework-Anbieter verwenden, wenn Sie eine relationale Datenquelle wie eine SQL Server-Datenbank verwenden. Weitere Informationen finden Sie unter [Entity Framework-Anbieter](entity-framework-provider-wcf-data-services.md).|  
|Reflektionsanbieter|Dieser Anbieter ermöglicht es Ihnen, mithilfe von Reflektion ein auf vorhandenen Datenklassen, die als Instanzen der <xref:System.Linq.IQueryable%601>-Schnittstelle verfügbar gemacht werden können, basierendes Datenmodell zu definieren. Updates werden durch Implementieren der <xref:System.Data.Services.IUpdatable>-Schnittstelle aktiviert. Verwenden Sie diesen Anbieter, wenn Sie zur Laufzeit definierte statische Datenklassen verwenden, z. B. durch LINQ to SQL generierte oder durch ein typisiertes DataSet definierte Datenklassen. Weitere Informationen finden Sie unter [reflektionsanbieter](reflection-provider-wcf-data-services.md).|  
|Benutzerdefinierte Datendienstanbieter|WCF Data Services enthält eine Reihe von Anbietern, die es Ihnen ermöglichen, ein Datenmodell auf der Grundlage spät gebundener Datentypen dynamisch zu definieren. Sie sollten diese Schnittstellen implementieren, wenn die verfügbar gemachten Daten beim Entwurf der Anwendung nicht bekannt sind oder wenn die Entity Framework- oder Reflektionsanbieter nicht hinreichend sind. Weitere Informationen finden Sie unter [benutzerdefinierte Daten Dienstanbieter](custom-data-service-providers-wcf-data-services.md).|  
  
## <a name="other-data-service-providers"></a>Andere Datendienstanbieter  

 WCF Data Services verfügt über den folgenden zusätzlichen Daten Dienstanbieter, der die Leistung einer Datenquelle verbessert, die mit einem der anderen Anbieter definiert wurde.  
  
|Anbieter|Beschreibung|  
|--------------|-----------------|  
|Streaminganbieter|Dieser Anbieter ermöglicht es Ihnen, Binary Large Object Datentypen mithilfe WCF Data Services verfügbar zu machen. Ein Streaminganbieter wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServiceStreamProvider>-Schnittstelle erstellt. Dieser Anbieter kann zusammen mit einem beliebigen Datenquellenanbieter implementiert werden. Weitere Informationen finden Sie unter [streaminganbieter](streaming-provider-wcf-data-services.md).|  
  
## <a name="see-also"></a>Weitere Informationen

- [Definieren von WCF Data Services](defining-wcf-data-services.md)
- [Konfigurieren des Datendiensts](configuring-the-data-service-wcf-data-services.md)
- [Hosten des Datendiensts](hosting-the-data-service-wcf-data-services.md)
