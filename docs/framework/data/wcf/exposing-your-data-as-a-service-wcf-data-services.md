---
title: Verfügbarmachen der Daten als Dienst (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
ms.openlocfilehash: 3c0763f21940831f401194356dc25b0d99c8d6f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765634"
---
# <a name="expose-your-data-as-a-service-wcf-data-services"></a>Verfügbarmachen der Daten als Dienst (WCF Data Services)

WCF Data Services-Integration mit Visual Studio können Sie zum Definieren von Diensten zum Verfügbarmachen von Daten als [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] -feeds. Erstellen eines Datendiensts, das einen OData-feed verfügbar macht, umfasst die folgenden grundlegenden Schritte:

1. **Definieren des Datenmodells.** WCF Data Services unterstützt systemintern Datenmodelle auf der Grundlage der [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md). Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen ein Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).

     WCF Data Services unterstützt außerdem Datenmodelle, die auf die common Language Runtime (CLR)-Objekte basieren, die eine Instanz von Zurückgeben der <xref:System.Linq.IQueryable%601> Schnittstelle. Dies ermöglicht es Ihnen, Datendienste bereitzustellen, die auf Listen, Arrays und Auflistungen in .NET Framework basieren. Zum Aktivieren von Erstellungs-, Aktualisierungs- und Löschvorgängen für diese Datenstrukturen müssen Sie außerdem die <xref:System.Data.Services.IUpdatable>-Schnittstelle implementieren. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines Datendiensts mit dem Reflektionsanbieter](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).

     Für einige erweiterte Szenarien umfasst die WCF Data Services eine Reihe von Anbietern, die Ihnen ermöglichen, ein Datenmodell auf Grundlage spät gebundener Datentypen zu definieren. Weitere Informationen finden Sie unter [Benutzerdefinierte Datendienstanbieter](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).

2. **Erstellen des Datendiensts.** Der einfachste Datendienst macht eine Klasse, die von der <xref:System.Data.Services.DataService%601> -Klasse erbt, mit einem Typ `T` verfügbar, bei dem es sich um den namespacequalifizierten Namen des Entitätscontainers handelt. Weitere Informationen finden Sie unter [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).

3. **Konfigurieren des Datendiensts.** In der Standardeinstellung deaktiviert WCF Data Services den Zugriff auf Ressourcen, die von einem Entitätscontainer verfügbar gemacht werden. Die <xref:System.Data.Services.DataServiceConfiguration> -Schnittstelle ermöglicht Ihnen das Konfigurieren des Zugriffs auf Ressourcen und Dienstvorgänge, das Angeben der unterstützten Version von OData und definieren anderer dienstweiter Verhalten, wie das batchverarbeitungsverhalten oder die maximale Anzahl von Entitäten, die zurückgegeben werden kann. in einer einzelnen Antwort. Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).

Ein Beispiel dafür, wie einen einfacher Datendienst erstellen, die auf der Northwind-Beispieldatenbank basiert, finden Sie unter [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).

## <a name="see-also"></a>Siehe auch

- [Erste Schritte](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
- [Übersicht](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)