---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 148e6e50e81552b2418abba9f6655234fc023c4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] (früher als „ADO.NET Data Services“ bezeichnet) ist eine Komponente von .NET Framework, die Ihnen ermöglicht, Dienste zu erstellen, die mithilfe von [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Daten über das Internet oder Intranet mit der Semantik von [Representational State Transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919). [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] macht Daten als durch URIs adressierbare Ressourcen verfügbar. Der Zugriff auf und die Änderung von Daten erfolgt mithilfe der Standard-HTTP-Befehle GET, PUT, POST und DELETE. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] verwendet die Entitätsbeziehungskonventionen von [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md), um Ressourcen als Mengen von durch Zuordnungen verknüpften Entitäten verfügbar zu machen.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verwendet das [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Protokoll zum Adressieren und Aktualisieren von Ressourcen. Auf diese Weise können Sie von jedem Client aus auf diese Dienste zugreifen, der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] ermöglicht das Anfordern von Daten und das Schreiben von Daten in Ressourcen mithilfe der folgenden bekannten Übertragungsformate: Atom, ein Satz von Standards zum Austauschen und Aktualisieren von Daten als XML, und JSON (JavaScript Object Notation), ein in AJAX-Anwendungen häufig verwendetes textbasiertes Datenaustauschformat.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] kann Daten, die aus verschiedenen Quellen stammen, als [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feeds verfügbar machen. Visual Studio Tools vereinfachen das Erstellen eines [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-basierten Diensts mithilfe eines ADO.NET Entity Framework-Datenmodells. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feeds können auch auf Grundlage von CLR-Klassen (Common Language Runtime) und sogar auf Grundlage von spät gebundenen oder nicht typisierten Daten erstellt werden.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] umfasst auch einen Satz Clientbibliotheken; eine Bibliothek für allgemeine .NET Framework-Clientanwendungen und eine andere speziell für Silverlight-basierte Anwendungen. Diese Clientbibliotheken stellen ein objektbasiertes Programmiermodell für den Zugriff auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feeds aus Umgebungen wie .NET Framework und Silverlight bereit.  
  
## <a name="where-should-i-start"></a>Wo sollte ich beginnen?  
 Je nach Ihren Interessen sollten Sie zuerst mit einem der folgenden [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Themen beginnen.  
  
 Ich möchte direkt beginnen…  
 -   [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [Erste Schritte](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
  
-   [Silverlight-Schnellstart](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [Silverlight-Schnellstart für Windows Phone-Entwicklung](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
 Ich möchte einige Codebeispiele anzeigen…  
 -   [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [Vorgehensweise: Ausführen von Datendienstabfragen](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
-   [Vorgehensweise: Binden von Daten an Windows Presentation Foundation-Elemente](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)  
  
 Ich möchte mehr über [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] erfahren...  
 -   [Whitepaper: Einführung in OData](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [Open Data Protocol-Website](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
-   [OData: SDK](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
-   [OData: Häufig gestellte Fragen](http://go.microsoft.com/fwlink/?LinkId=185867)  
  
 Ich möchte Videos ansehen…  
 -   [Einführung in WCF Data Services](http://go.microsoft.com/fwlink/?LinkId=220864)  
  
-   [WCF Data Services Developer-Videos](http://go.microsoft.com/fwlink/?LinkId=220861)  
  
-   [OData: Entwickler-Website](http://go.microsoft.com/fwlink/?LinkId=185866)  
  
 Ich möchte End-to-End-Beispiele anzeigen  
 -   [WCF Data Services-Dokumentationsbeispiele auf MSDN Samples Gallery](http://go.microsoft.com/fwlink/?LinkID=220865)  
  
-   [Weitere WCF Data Services-Beispiele auf MSDN Samples Gallery](http://go.microsoft.com/fwlink/?LinkId=220866)  
  
-   [OData: SDK](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
 Wie erfolgt die Integration in Visual Studio?  
 -   [Generieren der Datendienst-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
  
-   [Erstellen des Datendiensts](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
  
-   [Entity Framework-Anbieter](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
  
 Für welche Aufgaben kann ich es verwenden?  
 -   [Übersicht](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
  
-   [Whitepaper: Einführung in OData](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [Anwendungsszenarios](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)  
  
 Ich möchte Silverlight verwenden…  
 -   [Silverlight-Schnellstart](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [WCF Data Services (Silverlight)](http://go.microsoft.com/fwlink/?LinkID=143149)  
  
-   [Erste Schritte mit Silverlight](http://go.microsoft.com/fwlink/?LinkId=148366)  
  
 Ich möchte eine Windows Phone-Anwendung erstellen…  
 -   [Silverlight-Schnellstart für Windows Phone-Entwicklung](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
-   [Open Data Protocol (OData) Client für Windows Phone](http://go.microsoft.com/fwlink/?LinkID=208749)  
  
 Ich möchte LINQ verwenden…  
 -   [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
  
-   [Überlegungen zu LINQ](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)  
  
-   [Vorgehensweise: Ausführen von Datendienstabfragen](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
 Ich benötige weitere Informationen…  
 -   [WCF Data Services-Teamblog](http://go.microsoft.com/fwlink/?LinkID=150511)  
  
-   [Ressourcen](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)  
  
-   [WCF Data Services Developer Center](http://go.microsoft.com/fwlink/?LinkId=220868)  
  
-   [Open Data Protocol-Website](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
 Bietet eine Übersicht über die in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verfügbaren Features und Funktionen.  
  
 [Neues in WCF Data Services](http://msdn.microsoft.com/library/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 Beschreibt neue Funktionen in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] und Unterstützung für neue [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Funktionen.  
  
 [Erste Schritte](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 Beschreibt das Verfügbarmachen und Verarbeiten von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feeds mithilfe von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  
  
 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 Beschreibt das Erstellen und Konfigurieren eines Datendiensts, der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feeds verfügbar macht.  
  
 [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 Beschreibt, wie Sie mithilfe von Clientbibliotheken [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feeds aus einer .NET Framework-Clientanwendung verwenden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Representational State Transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919)
