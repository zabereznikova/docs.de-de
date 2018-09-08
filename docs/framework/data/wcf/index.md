---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 9ece2fe051855d0fd39556f56a4343ead2c437bc
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44197010"
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5

WCF Data Services (früher als "ADO.NET Data Services" bezeichnet) ist eine Komponente von .NET Framework, mit der Sie zum Erstellen von Diensten, mit denen, die [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Verfügbarmachen und Verarbeiten von Daten über das Internet oder Intranet mit der Semantik der [ Rest (Representational State Transfer)](https://go.microsoft.com/fwlink/?LinkId=113919). OData macht Daten als durch URIs adressierbare Ressourcen verfügbar. Der Zugriff auf und die Änderung von Daten erfolgt mithilfe der Standard-HTTP-Befehle GET, PUT, POST und DELETE. OData verwendet die entitätsbeziehungskonventionen von der [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) Ressourcen als Sätze von Entitäten verfügbar zu machen, die durch Zuordnungen verknüpft sind.

WCF Data Services verwendet das OData-Protokoll zum Adressieren und Aktualisieren von Ressourcen. Auf diese Weise können Sie diese Dienste von jedem Client aus zugreifen, die von OData unterstützt. OData ermöglicht es Ihnen, anfordern und Schreiben von Daten in Ressourcen mithilfe der folgenden bekannten Übertragungsformate: Atom, ein Satz von Standards zum Austauschen und Aktualisieren von Daten als XML- und JavaScript Object Notation (JSON), eine textbasierte Datenaustauschformat umfassend in AJAX die Anwendung.

WCF Data Services kann Daten, die aus verschiedenen Quellen stammen, als OData-feeds verfügbar machen. Visual Studio-Tools erleichtern Ihnen die Erstellung einen OData-basierten Dienst mit einem ADO.NET Entity Framework-Datenmodell. Sie können auch den OData-Feeds auf Grundlage common Language Runtime (CLR)-Klassen und sogar spät gebundenen oder nicht typisierten Daten erstellen.

WCF Data Services umfasst auch einen Satz von Clientbibliotheken, eine für allgemeine .NET Framework-Clientanwendungen und eine weitere speziell für Silverlight-basierten Anwendungen. Beim Zugriff auf einen OData-Feeds aus Umgebungen wie .NET Framework und Silverlight stellen diese Clientbibliotheken ein objektbasiertes Programmiermodell bereit.

## <a name="where-should-i-start"></a>Wo sollte ich beginnen?

Je nach Ihren Interessen sollten Sie in der erste Schritte mit WCF Data Services in einem der folgenden Themen.

Ich möchte direkt beginnen…

-   [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

-   [Erste Schritte](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

-   [Silverlight-Schnellstart](https://go.microsoft.com/fwlink/?LinkID=192782)

-   [Silverlight-Schnellstart für Windows Phone-Entwicklung](https://go.microsoft.com/fwlink/?LinkID=214535)

Nur Code anzeigen...

-   [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

-   [Vorgehensweise: Ausführen von Datendienstabfragen](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

-   [Vorgehensweise: Binden von Daten an Windows Presentation Foundation-Elemente](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)

Ich möchte mehr über OData erfahren...

 -   [Whitepaper: Einführung in OData](https://go.microsoft.com/fwlink/?LinkId=220867)

-   [Open Data Protocol-Website](https://go.microsoft.com/fwlink/?LinkID=184554)

-   [OData: SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

-   [OData: Häufig gestellte Fragen](https://go.microsoft.com/fwlink/?LinkId=185867)

Ich möchte Videos ansehen…...

-   [Einführung in WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=220864)

-   [WCF Data Services Developer-Videos](https://go.microsoft.com/fwlink/?LinkId=220861)

-   [OData: Entwickler-Website](https://go.microsoft.com/fwlink/?LinkId=185866)

Ich möchte End-to-End-Beispiele finden Sie unter...

-   [WCF Data Services-Dokumentationsbeispiele auf MSDN Samples Gallery](https://go.microsoft.com/fwlink/?LinkID=220865)

-   [Weitere WCF Data Services-Beispiele auf MSDN Samples Gallery](https://go.microsoft.com/fwlink/?LinkId=220866)

-   [OData: SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

Wie erfolgt die Integration in Visual Studio?

-   [Generieren der Datendienst-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)

-   [Erstellen des Datendiensts](../../../../docs/framework/data/wcf/creating-the-data-service.md)

-   [Entity Framework-Anbieter](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)

Für welche Aufgaben kann ich es verwenden?

-   [Übersicht](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

-   [Whitepaper: Einführung in OData](https://go.microsoft.com/fwlink/?LinkId=220867)

-   [Anwendungsszenarios](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)

Ich möchte Silverlight verwenden…

-   [Silverlight-Schnellstart](https://go.microsoft.com/fwlink/?LinkID=192782)

-   [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149)

-   [Erste Schritte mit Silverlight](https://go.microsoft.com/fwlink/?LinkId=148366)

Ich möchte LINQ verwenden…

-   [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)

-   [Überlegungen zu LINQ](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)

-   [Vorgehensweise: Ausführen von Datendienstabfragen](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

Ich benötige weitere...

-   [WCF Data Services-Teamblog](https://go.microsoft.com/fwlink/?LinkID=150511)

-   [Ressourcen](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)

-   [WCF Data Services Developer Center](https://go.microsoft.com/fwlink/?LinkId=220868)

-   [Open Data Protocol-Website](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a>In diesem Abschnitt

 [Übersicht](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

 Bietet eine Übersicht über die Features und Funktionen, die in WCF Data Services verfügbar.

 [Neues in WCF Data Services](https://msdn.microsoft.com/library/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)

 Beschreibt neue Funktionen in WCF Data Services und Unterstützung für neue Features von OData.

 [Erste Schritte](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

 Beschreibt das Verfügbarmachen und Verarbeiten von OData-Feeds mithilfe von WCF Data Services.

 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)

 Beschreibt das Erstellen und Konfigurieren eines Datendiensts, das OData-Feeds verfügbar macht.

 [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

 Beschreibt, wie Clientbibliotheken verwenden, die OData-Feeds aus einer .NET Framework-Clientanwendung nutzen.

## <a name="see-also"></a>Siehe auch

- [Representational State Transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919)
