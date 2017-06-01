---
title: "Hosten des Datendiensts (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "HTML"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "WCF Data Services, Konfigurieren"
  - "WCF Data Services, Windows Communication Foundation"
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Hosten des Datendiensts (WCF Data Services)
Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] können Sie einen Dienst erstellen, der Daten als [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]\-Feed verfügbar macht.  Dieser Datendienst wird als Klasse definiert, die von <xref:System.Data.Services.DataService%601> erbt.  Diese Klasse stellt die Funktionalität bereit, die erforderlich ist, um Anforderungsnachrichten zu verarbeiten, Aktualisierungen für die Datenquelle auszuführen und Antwortnachrichten zu generieren, wie von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] gefordert. Ein Datendienst kann jedoch Netzwerksockets für eingehende HTTP\-Anforderungen weder binden noch diese überwachen.  Für diese erforderliche Funktion benötigt der Datendienst eine Hostingkomponente.  
  
 Der Datendiensthost führt die folgenden Aufgaben im Namen des Datendiensts aus:  
  
-   Lauscht auf Anforderungen und leitet diese an den Datendienst weiter.  
  
-   Erstellt für jede Anforderung eine Instanz des Datendiensts.  
  
-   Fordert an, dass der Datendienst die eingehende Anforderung verarbeitet.  
  
-   Sendet die Antwort im Namen des Datendiensts.  
  
 Um das Hosten eines Datendiensts zu vereinfachen, wurde [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] so entworfen, dass eine Integration in Windows Communication Foundation \(WCF\) möglich ist.  Der Datendienst stellt eine WCF\-Standardimplementierung bereit, die in einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Anwendung als Datendiensthost fungiert.  Daher können Sie einen Datendienst in einer der folgenden Methoden hosten:  
  
-   In einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Anwendung.  
  
-   In einer verwalteten Anwendung, die selbst gehostete WCF\-Dienste unterstützt.  
  
-   In einem anderen benutzerdefinierten Datendiensthost.  
  
## Hosten eines Datendiensts in einer ASP.NET\-Anwendung  
 Wenn Sie das Dialogfeld **Neues Element hinzufügen** in Visual Studio verwenden, um einen Datendienst in einer ASP.NET\-Anwendung zu definieren, generiert das Tool im Projekt zwei neue Dateien.  Die erste Datei verfügt über die `.svc`\-Erweiterung und weist die WCF\-Laufzeit an, wie der Datendienst instanziiert werden soll.  Im Folgenden finden Sie ein Beispiel für diese Datei für den Northwind\-Beispieldatendienst, der beim Abschluss des [Schnellstarts](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) erstellt wird:  
  
```  
<%@ ServiceHost Language="C#"   
    Factory="System.Data.Services.DataServiceHostFactory,   
            System.Data.Services, Version=4.0.0.0,   
            Culture=neutral, PublicKeyToken=b77a5c561934e089"   
    Service="NorthwindService.Northwind" %>   
```  
  
 Diese Direktive weist die Anwendung an, den Diensthost für die benannte Datendienstklasse mithilfe der <xref:System.Data.Services.DataServiceHostFactory>\-Klasse zu erstellen.  
  
 Die CodeBehind\-Seite für die `.svc`\-Datei enthält die Klasse, bei der es sich um die Implementierung des Datendiensts selbst handelt und die für den Northwind\-Beispieldatendienst folgendermaßen definiert wird:  
  
 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
 Da sich ein Datendienst wie ein WCF\-Dienst verhält, wird der Datendienst in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] integriert und folgt dem WCF\-Webprogrammiermodell. Weitere Informationen finden Sie unter [WCF\-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) und [WCF\-Web\-HTTP\-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).  
  
## Selbst gehostete WCF\-Dienste  
 Da [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] eine WCF\-Implementierung beinhaltet, werden selbsthostende Datendienste als WCF\-Dienste unterstützt.  Ein Dienst kann in allen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Anwendungen selbst gehostet werden, z. B. in einer Konsolenanwendung.  Die <xref:System.Data.Services.DataServiceHost>\-Klasse, die von <xref:System.ServiceModel.Web.WebServiceHost> erbt, wird verwendet, um den Datendienst bei einer bestimmten Adresse zu instanziieren.  
  
 Selbsthosting kann für die Entwicklung und für Tests verwendet werden, da die Bereitstellung und Problembehandlung vereinfacht wird.  Diese Art von Hosting stellt jedoch nicht die erweiterten Hosting\- und Verwaltungsfunktionen von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] oder der Internetinformationsdienste \(IIS\) bereit. Weitere Informationen finden Sie unter [Hosten in einer verwalteten Anwendung](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).  
  
## Definieren eines benutzerdefinierten Datendiensthosts  
 Wenn die WCF\-Hostimplementierung zu restriktiv ist, können Sie für einen Datendienst auch einen benutzerdefinierten Host definieren.  Alle Klassen, die eine <xref:System.Data.Services.IDataServiceHost>\-Schnittstelle implementieren, können für einen Datendienst als Netzwerkhost verwendet werden.  Ein benutzerdefinierter Host muss die <xref:System.Data.Services.IDataServiceHost>\-Schnittstelle implementieren und in der Lage sein, die folgenden grundlegenden Aufgaben des Datendiensthosts zu übernehmen:  
  
-   Bereitstellen des Dienststammpfads für den Datendienst  
  
-   Verarbeiten der Anforderungs\- und Antwortheaderinformationen für die entsprechende <xref:System.Data.Services.IDataServiceHost>\-Memberimplementierung  
  
-   Behandeln der vom Datendienst ausgelösten Ausnahmen  
  
-   Überprüfen der Parameter in der Abfragezeichenfolge  
  
## Siehe auch  
 [Definieren von WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [Verfügbarmachen der Daten als Dienst](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)   
 [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)