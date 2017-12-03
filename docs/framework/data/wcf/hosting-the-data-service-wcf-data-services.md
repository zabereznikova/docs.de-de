---
title: Hosting des Datendiensts (WCF Data Services)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7fa76c5672b4117c446aca145b7cf98dae7801d4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="hosting-the-data-service-wcf-data-services"></a>Hosting des Datendiensts (WCF Data Services)
Mithilfe von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], können Sie einen Dienst, die Daten als verfügbar macht erstellen eine [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed. Dieser Datendienst wird als Klasse definiert, die von <xref:System.Data.Services.DataService%601> erbt. Diese Klasse stellt die Funktionalität erforderlich, um Anforderungsnachrichten zu verarbeiten, Updates für die Datenquelle auszuführen und antwortmeldungen zu generieren, gemäß [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Allerdings kann kein Datendienst zu binden und ein Netzwerksocket eingehenden HTTP-Anforderungen gelauscht. Für diese erforderliche Funktion benötigt der Datendienst eine Hostingkomponente.  
  
 Der Datendiensthost führt die folgenden Aufgaben im Namen des Datendiensts aus:  
  
-   Lauscht auf Anforderungen und leitet diese an den Datendienst weiter.  
  
-   Erstellt für jede Anforderung eine Instanz des Datendiensts.  
  
-   Fordert an, dass der Datendienst die eingehende Anforderung verarbeitet.  
  
-   Sendet die Antwort im Namen des Datendiensts.  
  
 Zur Vereinfachung Hosten eines Datendiensts [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] dient, mit der Windows Communication Foundation (WCF) integriert. Der Datendienst stellt eine WCF-Standardimplementierung, die als in den Datendiensthost fungiert ein [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Anwendung. Daher können Sie einen Datendienst in einer der folgenden Methoden hosten:  
  
-   In einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendung.  
  
-   In einer verwalteten Anwendung, die selbst gehostete WCF-Dienste unterstützt.  
  
-   In einem anderen benutzerdefinierten Datendiensthost.  
  
## <a name="hosting-a-data-service-in-an-aspnet-application"></a>Hosten eines Datendiensts in einer ASP.NET-Anwendung  
 Bei Verwendung der **neues Element hinzufügen** Dialogfeld in Visual Studio zum Definieren eines Datendiensts in einer ASP.NET-Anwendung das Tool generiert zwei neue Dateien im Projekt. Die erste Datei verfügt über die `.svc`-Erweiterung und weist die WCF-Laufzeit an, wie der Datendienst instanziiert werden soll. Im folgenden ist ein Beispiel für diese Datei für die Northwind-beispieldatendienst erstellt, wenn Sie die [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md):  
  
```  
<%@ ServiceHost Language="C#"   
    Factory="System.Data.Services.DataServiceHostFactory,   
            System.Data.Services, Version=4.0.0.0,   
            Culture=neutral, PublicKeyToken=b77a5c561934e089"   
    Service="NorthwindService.Northwind" %>   
```  
  
 Diese Direktive weist die Anwendung an, den Diensthost für die benannte Datendienstklasse mithilfe der <xref:System.Data.Services.DataServiceHostFactory>-Klasse zu erstellen.  
  
 Die CodeBehind-Seite für die `.svc`-Datei enthält die Klasse, bei der es sich um die Implementierung des Datendiensts selbst handelt und die für den Northwind-Beispieldatendienst folgendermaßen definiert wird:  
  
 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
 Da sich ein Datendienst wie ein WCF-Dienst verhält, wird der Datendienst in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] integriert und folgt dem WCF-Webprogrammiermodell. Weitere Informationen finden Sie unter [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) und [WCF Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).  
  
## <a name="self-hosted-wcf-services"></a>Selbst gehostete WCF-Dienste  
 Da es sich um einen WCF-Implementierung integriert [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] selbst Hosten eines Datendiensts als WCF-Dienst zu unterstützen. Ein Dienst kann in allen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Anwendungen selbst gehostet werden, z. B. in einer Konsolenanwendung. Die <xref:System.Data.Services.DataServiceHost>-Klasse, die von <xref:System.ServiceModel.Web.WebServiceHost> erbt, wird verwendet, um den Datendienst bei einer bestimmten Adresse zu instanziieren.  
  
 Selbsthosting kann für die Entwicklung und für Tests verwendet werden, da die Bereitstellung und Problembehandlung vereinfacht wird. Diese Art von Hosting stellt jedoch nicht die erweiterten Hosting- und Verwaltungsfunktionen von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] oder der Internetinformationsdienste (IIS) bereit. Weitere Informationen finden Sie unter [Hosten in einer verwalteten Anwendung](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).  
  
## <a name="defining-a-custom-data-service-host"></a>Definieren eines benutzerdefinierten Datendiensthosts  
 Wenn die WCF-Hostimplementierung zu restriktiv ist, können Sie für einen Datendienst auch einen benutzerdefinierten Host definieren. Alle Klassen, die eine <xref:System.Data.Services.IDataServiceHost>-Schnittstelle implementieren, können für einen Datendienst als Netzwerkhost verwendet werden. Ein benutzerdefinierter Host muss die <xref:System.Data.Services.IDataServiceHost>-Schnittstelle implementieren und in der Lage sein, die folgenden grundlegenden Aufgaben des Datendiensthosts zu übernehmen:  
  
-   Bereitstellen des Dienststammpfads für den Datendienst  
  
-   Verarbeiten der Anforderungs- und Antwortheaderinformationen für die entsprechende <xref:System.Data.Services.IDataServiceHost>-Memberimplementierung  
  
-   Behandeln der vom Datendienst ausgelösten Ausnahmen  
  
-   Überprüfen der Parameter in der Abfragezeichenfolge  
  
## <a name="see-also"></a>Siehe auch  
 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Verfügbarmachen der Daten als Dienst](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)  
 [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
