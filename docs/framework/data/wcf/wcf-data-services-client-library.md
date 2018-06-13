---
title: WCF Data Services-Clientbibliothek
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: 95ca3ab8768b59b52640cfd17d230a544a8b2052
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365513"
---
# <a name="wcf-data-services-client-library"></a>WCF Data Services-Clientbibliothek
Mit einem [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]-basierten Datendienst kann jede Anwendung interagieren, die HTTP-Anforderungen senden und den von einem Datendienst zurückgegebenen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feed verarbeiten kann. Diese Interoperabilität ermöglicht es Ihnen, aus einer Vielzahl webbasierter Anwendungen auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-basierte Dienste zuzugreifen. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] enthält Clientbibliotheken, die umfangreichere Programmierfunktionen bieten, wenn Sie nutzen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds aus .NET Framework- oder Silverlight-basierten Anwendungen.  
  
 Die beiden Hauptklassen der Clientbibliothek sind die <xref:System.Data.Services.Client.DataServiceContext>-Klasse und die <xref:System.Data.Services.Client.DataServiceQuery%601>-Klasse. Die <xref:System.Data.Services.Client.DataServiceContext>-Klasse kapselt Vorgänge, die für einen angegebenen Datendienst unterstützt werden. Im Gegensatz zu [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Diensten ist der Kontext nicht zustandslos. Aus diesem Grund können Sie die <xref:System.Data.Services.Client.DataServiceContext> Klasse zur Statusverwaltung auf dem Client zwischen Interaktionen mit dem Datendienst, um die Unterstützung von Funktionen wie das Änderungsmanagement. Von dieser Klasse werden auch Identitäten verwaltet und Änderungen nachverfolgt. Die <xref:System.Data.Services.Client.DataServiceQuery%601>-Klasse stellt eine Abfrage für eine bestimmte Entitätenmenge dar.  
  
 In diesem Abschnitt wird beschrieben, wie Sie mit Clientbibliotheken von einer .NET Framework-Clientanwendung auf Daten zugreifen und diese ändern. Weitere Informationen zur Verwendung der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] -Clientbibliothek mit einem Silverlight-basierten Anwendung finden Sie unter [WCF Data Services (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=186016). Andere Clientbibliotheken sind verfügbar, mit denen Sie nutzen eine [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in anderen Arten von Anwendungen. Weitere Informationen finden Sie unter der [OData SDK](http://go.microsoft.com/fwlink/?LinkID=185796).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Generieren der Datendienst-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 Beschreibt, wie eine Clientbibliothek und clientdatendienstklassen auf der Grundlage von generieren [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.  
  
 [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 Beschreibt, wie ein Datendienst aus einer .NET Framework-basierten Anwendung mit Clientbibliotheken abgefragt wird.  
  
 [Laden von verzögerten Inhalten](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 Beschreibt, wie zusätzlicher, nicht in der ursprünglichen Abfrageantwort enthaltener Inhalt geladen wird.  
  
 [Aktualisieren des Datendiensts](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)  
 Beschreibt, wie Entitäten und Beziehungen mit den Clientbibliotheken erstellt, geändert und gelöscht werden.  
  
 [Asynchrone Vorgänge](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)  
 Beschreibt die zum Arbeiten mit einem Datendienst auf eine asynchrone Weise von den Clientbibliotheken bereitgestellten Funktionen.  
  
 [Batchvorgänge](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)  
 Beschreibt, wie mit den Clientbibliotheken mehrere Anforderungen an den Datendienst in einem einzelnen Batch gesendet werden.  
  
 [Binden von Daten an Steuerelemente](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)  
 Beschreibt, wie zum Binden von Steuerelementen zu einem [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] von einem Datendienst zurückgegebenen Feed.  
  
 [Aufrufen von Dienstvorgängen](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md)  
 Beschreibt, wie die Clientbibliothek verwendet wird, um Dienstvorgänge aufzurufen.  
  
 [Verwalten des Datendienstkontexts](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md)  
 Beschreibt Optionen zum Verwalten des Verhaltens der Clientbibliothek.  
  
 [Arbeiten mit Binärdaten](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)  
 Beschreibt, wie auf vom Datendienst zurückgegebene Binärdaten als Datenstrom zugegriffen wird und wie diese geändert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Erste Schritte](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
