---
title: "WCF Data Services-Clientbibliothek | Microsoft Docs"
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
  - "DataServiceContext-Klasse, Info zur DataServiceContext-Klasse"
  - "DataServiceQuery-Klasse, Info zur DataServiceQuery-Klasse"
  - "WCF Data Services, Clientbibliothek"
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# WCF Data Services-Clientbibliothek
Jede Anwendung kann mit einem [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]\-basierten Datendienst interagieren, wenn sie eine HTTP\-Anforderung senden und den [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed verarbeiten kann, den ein Datendienst zurückgibt. Diese Interoperabilität ermöglicht es Ihnen, aus einer Vielzahl webbasierter Anwendungen auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-basierte Dienste zuzugreifen.  [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] umfasst auch Clientbibliotheken, die umfangreichere Programmierfunktionen bieten, wenn Sie aus .NET Framework\- oder Silverlight\-basierten Anwendungen heraus [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feeds nutzen.  
  
 Die beiden Hauptklassen der Clientbibliothek sind die <xref:System.Data.Services.Client.DataServiceContext>\-Klasse und die <xref:System.Data.Services.Client.DataServiceQuery%601>\-Klasse.  Die <xref:System.Data.Services.Client.DataServiceContext>\-Klasse kapselt Vorgänge, die für einen angegebenen Datendienst unterstützt werden.  Im Gegensatz zu [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Diensten ist der Kontext nicht zustandslos.  Sie können daher mithilfe der <xref:System.Data.Services.Client.DataServiceContext>\-Klasse den Zustand auf dem Client zwischen Interaktionen mit dem Datendienst beibehalten, um Funktionen wie das Änderungsmanagement zu unterstützen.  Von dieser Klasse werden auch Identitäten verwaltet und Änderungen nachverfolgt.  Die <xref:System.Data.Services.Client.DataServiceQuery%601>\-Klasse stellt eine Abfrage für eine bestimmte Entitätenmenge dar.  
  
 In diesem Abschnitt wird beschrieben, wie Sie mit Clientbibliotheken von einer .NET Framework\-Clientanwendung auf Daten zugreifen und diese ändern.  Weitere Informationen zur Verwendung der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Clientbibliothek mit einer Silverlight\-basierten Anwendung finden Sie unter [WCF Data Services \(Silverlight\)](http://go.microsoft.com/fwlink/?LinkId=186016).  Andere Clientbibliotheken sind verfügbar, die es Ihnen ermöglichen, in anderen Arten von Anwendungen einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed zu nutzen.  Weitere Informationen finden Sie unter [OData SDK](http://go.microsoft.com/fwlink/?LinkID=185796).  
  
## In diesem Abschnitt  
 [Generieren der Datendienst\-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 Beschreibt, wie eine Clientbibliothek und Clientdatendienstklassen generiert werden, die auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feeds basieren.  
  
 [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 Beschreibt, wie ein Datendienst aus einer .NET Framework\-basierten Anwendung mit Clientbibliotheken abgefragt wird.  
  
 [Laden von verzögertem Inhalt](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 Beschreibt, wie zusätzlicher, nicht in der ursprünglichen Abfrageantwort enthaltener Inhalt geladen wird.  
  
 [Aktualisieren des Datendiensts](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)  
 Beschreibt, wie Entitäten und Beziehungen mit den Clientbibliotheken erstellt, geändert und gelöscht werden.  
  
 [Asynchrone Vorgänge](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)  
 Beschreibt die zum Arbeiten mit einem Datendienst auf eine asynchrone Weise von den Clientbibliotheken bereitgestellten Funktionen.  
  
 [Batchverarbeitungsvorgänge](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)  
 Beschreibt, wie mit den Clientbibliotheken mehrere Anforderungen an den Datendienst in einem einzelnen Batch gesendet werden.  
  
 [Binden von Daten an Steuerelemente](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)  
 Beschreibt, wie Steuerelemente an einen von einem Datendienst zurückgegebenen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed gebunden werden.  
  
 [Aufrufen von Dienstvorgängen](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md)  
 Beschreibt, wie die Clientbibliothek verwendet wird, um Dienstvorgänge aufzurufen.  
  
 [Verwalten des Datendienstkontextes](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md)  
 Beschreibt Optionen zum Verwalten des Verhaltens der Clientbibliothek.  
  
 [Arbeiten mit Binärdaten](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)  
 Beschreibt, wie auf vom Datendienst zurückgegebene Binärdaten als Datenstrom zugegriffen wird und wie diese geändert werden.  
  
## Siehe auch  
 [Definieren von WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [Erste Schritte](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)