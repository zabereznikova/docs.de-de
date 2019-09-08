---
title: WCF Data Services-Clientbibliothek
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: 545442b0086361c8ce8c0482801afc10b1fee96e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779681"
---
# <a name="wcf-data-services-client-library"></a>WCF Data Services-Clientbibliothek
Mit einem [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]-basierten Datendienst kann jede Anwendung interagieren, die HTTP-Anforderungen senden und den von einem Datendienst zurückgegebenen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feed verarbeiten kann. Diese Interoperabilität ermöglicht es Ihnen, aus einer Vielzahl webbasierter Anwendungen auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-basierte Dienste zuzugreifen. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]umfasst Client Bibliotheken, die umfangreichere Programmierfunktionen bieten, wenn [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Sie Feeds von .NET Framework-oder Silverlight-basierten Anwendungen nutzen.  
  
 Die beiden Hauptklassen der Clientbibliothek sind die <xref:System.Data.Services.Client.DataServiceContext>-Klasse und die <xref:System.Data.Services.Client.DataServiceQuery%601>-Klasse. Die <xref:System.Data.Services.Client.DataServiceContext>-Klasse kapselt Vorgänge, die für einen angegebenen Datendienst unterstützt werden. Im Gegensatz zu [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Diensten ist der Kontext nicht zustandslos. Daher können Sie die <xref:System.Data.Services.Client.DataServiceContext> -Klasse verwenden, um den Zustand auf dem Client zwischen Interaktionen mit dem Datendienst aufrechtzuerhalten, um Funktionen wie z. b. Change Management zu unterstützen. Von dieser Klasse werden auch Identitäten verwaltet und Änderungen nachverfolgt. Die <xref:System.Data.Services.Client.DataServiceQuery%601>-Klasse stellt eine Abfrage für eine bestimmte Entitätenmenge dar.  
  
 In diesem Abschnitt wird beschrieben, wie Sie mit Clientbibliotheken von einer .NET Framework-Clientanwendung auf Daten zugreifen und diese ändern. Weitere Informationen zur Verwendung der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] -Client Bibliothek mit einer Silverlight-basierten Anwendung finden Sie unter [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=186016). Es stehen weitere Client Bibliotheken zur Verfügung, mit denen Sie [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] einen-Feed in anderen Arten von Anwendungen nutzen können. Weitere Informationen finden Sie unter [odata SDK](https://go.microsoft.com/fwlink/?LinkID=185796).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Generieren der Datendienst-Clientbibliothek](generating-the-data-service-client-library-wcf-data-services.md)  
 Beschreibt, wie eine Client Bibliothek und Client Datendienst Klassen generiert werden, die auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Feeds basieren.  
  
 [Abfragen des Datendiensts](querying-the-data-service-wcf-data-services.md)  
 Beschreibt, wie ein Datendienst aus einer .NET Framework-basierten Anwendung mit Clientbibliotheken abgefragt wird.  
  
 [Laden von verzögerten Inhalten](loading-deferred-content-wcf-data-services.md)  
 Beschreibt, wie zusätzlicher, nicht in der ursprünglichen Abfrageantwort enthaltener Inhalt geladen wird.  
  
 [Aktualisieren des Datendiensts](updating-the-data-service-wcf-data-services.md)  
 Beschreibt, wie Entitäten und Beziehungen mit den Clientbibliotheken erstellt, geändert und gelöscht werden.  
  
 [Asynchrone Vorgänge](asynchronous-operations-wcf-data-services.md)  
 Beschreibt die zum Arbeiten mit einem Datendienst auf eine asynchrone Weise von den Clientbibliotheken bereitgestellten Funktionen.  
  
 [Batchvorgänge](batching-operations-wcf-data-services.md)  
 Beschreibt, wie mit den Clientbibliotheken mehrere Anforderungen an den Datendienst in einem einzelnen Batch gesendet werden.  
  
 [Binden von Daten an Steuerelemente](binding-data-to-controls-wcf-data-services.md)  
 Beschreibt, wie Steuerelemente an einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] von einem Datendienst zurückgegebenen Feed gebunden werden.  
  
 [Aufrufen von Dienstvorgängen](calling-service-operations-wcf-data-services.md)  
 Beschreibt, wie die Clientbibliothek verwendet wird, um Dienstvorgänge aufzurufen.  
  
 [Verwalten des Datendienstkontexts](managing-the-data-service-context-wcf-data-services.md)  
 Beschreibt Optionen zum Verwalten des Verhaltens der Clientbibliothek.  
  
 [Arbeiten mit Binärdaten](working-with-binary-data-wcf-data-services.md)  
 Beschreibt, wie auf vom Datendienst zurückgegebene Binärdaten als Datenstrom zugegriffen wird und wie diese geändert werden.  
  
## <a name="see-also"></a>Siehe auch

- [Defining WCF Data Services](defining-wcf-data-services.md)
- [Erste Schritte](getting-started-with-wcf-data-services.md)
