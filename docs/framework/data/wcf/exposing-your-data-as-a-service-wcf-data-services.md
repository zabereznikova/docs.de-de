---
title: Verfügbarmachen der Daten als Dienst (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
ms.openlocfilehash: 1dc1f0ec12c50c4c97b141a34b468e3367ead75e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780304"
---
# <a name="expose-your-data-as-a-service-wcf-data-services"></a>Verfügbar machen Ihrer Daten als Dienst (WCF Data Services)

WCF Data Services ist in Visual Studio integriert, damit Sie Dienste einfacher definieren können, um Ihre Daten als [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Feeds verfügbar zu machen. Das Erstellen eines Daten Dienes, der einen odata-Feed verfügbar macht, umfasst die folgenden grundlegenden Schritte:

1. **Definieren Sie das Datenmodell.** WCF Data Services systemeigene Unterstützung für Datenmodelle, die auf dem [ADO.NET-Entity Framework](../adonet/ef/index.md)basieren. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie einen Datendienst mithilfe einer ADO.NET-Entity Framework](create-a-data-service-using-an-adonet-ef-data-wcf.md)Datenquelle.

     WCF Data Services unterstützt auch Datenmodelle, die auf Common Language Runtime (CLR)-Objekten basieren, die eine Instanz <xref:System.Linq.IQueryable%601> der-Schnittstelle zurückgeben. Dies ermöglicht es Ihnen, Datendienste bereitzustellen, die auf Listen, Arrays und Auflistungen in .NET Framework basieren. Zum Aktivieren von Erstellungs-, Aktualisierungs- und Löschvorgängen für diese Datenstrukturen müssen Sie außerdem die <xref:System.Data.Services.IUpdatable>-Schnittstelle implementieren. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie einen Datendienst mithilfe des reflektionsanbieters](create-a-data-service-using-rp-wcf-data-services.md).

     Für erweiterte Szenarien umfasst WCF Data Services eine Reihe von Anbietern, die es Ihnen ermöglichen, ein Datenmodell auf der Grundlage spät gebundener Datentypen zu definieren. Weitere Informationen finden Sie unter [benutzerdefinierte Daten Dienstanbieter](custom-data-service-providers-wcf-data-services.md).

2. **Erstellen Sie den Datendienst.** Der einfachste Datendienst macht eine Klasse, die von der <xref:System.Data.Services.DataService%601> -Klasse erbt, mit einem Typ `T` verfügbar, bei dem es sich um den namespacequalifizierten Namen des Entitätscontainers handelt. Weitere Informationen finden Sie unter [Defining WCF Data Services](defining-wcf-data-services.md).

3. **Konfigurieren Sie den Datendienst.** Standardmäßig deaktiviert WCF Data Services den Zugriff auf Ressourcen, die von einem Entitätencontainer verfügbar gemacht werden. Die <xref:System.Data.Services.DataServiceConfiguration> -Schnittstelle ermöglicht Ihnen das Konfigurieren des Zugriffs auf Ressourcen und Dienst Vorgänge, das Angeben der unterstützten Version von odata und das definieren anderer Dienst weiter Verhalten, z. b. das Batch Verarbeitungs Verhalten oder die maximale Anzahl von Entitäten, die zurückgegeben werden können. in einer einzelnen Antwort. Weitere Informationen finden Sie unter [Konfigurieren des Daten Dienstanbieter](configuring-the-data-service-wcf-data-services.md).

Ein Beispiel für das Erstellen eines einfachen Daten Dienstanbieter, der auf der Northwind-Beispieldatenbank basiert, finden Sie unter [Schnellstart](quickstart-wcf-data-services.md).

## <a name="see-also"></a>Siehe auch

- [Erste Schritte](getting-started-with-wcf-data-services.md)
- [Übersicht](wcf-data-services-overview.md)
