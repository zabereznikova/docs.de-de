---
title: WCF Data Services-Clientbibliothek
description: Erfahren Sie, wie Sie WCF Data Services-Client Bibliotheken verwenden, um auf Daten aus einer .NET Framework Client Anwendung zuzugreifen und diese zu ändern.
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: 2ff3f63d406a260f83eaba4f2e7a8419046e1931
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559030"
---
# <a name="wcf-data-services-client-library"></a>WCF Data Services-Clientbibliothek
Jede Anwendung kann mit einem Open Data Protocol (odata)-basierten Datendienst interagieren, wenn eine HTTP-Anforderung gesendet und der von einem Datendienst zurückgegebene odata-Feed verarbeitet werden kann. Diese Interoperabilität ermöglicht Ihnen den Zugriff auf odata-basierte Dienste aus einer breiten Palette von webfähigen Anwendungen. WCF Data Services umfasst Client Bibliotheken, die umfangreichere Programmierfunktionen bieten, wenn Sie odata-Feeds aus .NET Framework-oder Silverlight-basierten Anwendungen nutzen.  
  
 Die beiden Hauptklassen der Clientbibliothek sind die <xref:System.Data.Services.Client.DataServiceContext>-Klasse und die <xref:System.Data.Services.Client.DataServiceQuery%601>-Klasse. Die <xref:System.Data.Services.Client.DataServiceContext>-Klasse kapselt Vorgänge, die für einen angegebenen Datendienst unterstützt werden. Obwohl odata-Dienste zustandslos sind, ist der Kontext nicht. Daher können Sie die- <xref:System.Data.Services.Client.DataServiceContext> Klasse verwenden, um den Zustand auf dem Client zwischen Interaktionen mit dem Datendienst aufrechtzuerhalten, um Funktionen wie z. b. Change Management zu unterstützen. Von dieser Klasse werden auch Identitäten verwaltet und Änderungen nachverfolgt. Die <xref:System.Data.Services.Client.DataServiceQuery%601>-Klasse stellt eine Abfrage für eine bestimmte Entitätenmenge dar.  
  
 In diesem Abschnitt wird beschrieben, wie Sie mit Clientbibliotheken von einer .NET Framework-Clientanwendung auf Daten zugreifen und diese ändern. Weitere Informationen zur Verwendung der WCF Data Services-Client Bibliothek mit einer Silverlight-basierten Anwendung finden Sie unter [WCF Data Services (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)). Es stehen weitere Client Bibliotheken zur Verfügung, mit denen Sie einen odata-Feed in anderen Arten von Anwendungen nutzen können. Weitere Informationen zum odata SDK finden Sie unter [odata SDK-Sample Code](https://www.odata.org/ecosystem/#sdk).
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Generieren der Datendienstclientbibliothek](generating-the-data-service-client-library-wcf-data-services.md)  
 Beschreibt, wie eine Client Bibliothek und Client Datendienst Klassen generiert werden, die auf odata-Feeds basieren.  
  
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
 Beschreibt, wie Steuerelemente an einen odata-Feed gebunden werden, der von einem Datendienst zurückgegeben wird.  
  
 [Aufrufen von Dienstvorgängen](calling-service-operations-wcf-data-services.md)  
 Beschreibt, wie die Clientbibliothek verwendet wird, um Dienstvorgänge aufzurufen.  
  
 [Verwalten des Datendienstkontexts](managing-the-data-service-context-wcf-data-services.md)  
 Beschreibt Optionen zum Verwalten des Verhaltens der Clientbibliothek.  
  
 [Arbeiten mit Binärdaten](working-with-binary-data-wcf-data-services.md)  
 Beschreibt, wie auf vom Datendienst zurückgegebene Binärdaten als Datenstrom zugegriffen wird und wie diese geändert werden.  
  
## <a name="see-also"></a>Siehe auch

- [Definieren von WCF Data Services](defining-wcf-data-services.md)
- [Erste Schritte](getting-started-with-wcf-data-services.md)
