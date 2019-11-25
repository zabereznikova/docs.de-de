---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 1ce152b84f17a35982a75f54b5418623ba39210f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975234"
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5

WCF Data Services (früher als "ADO.NET Data Services" bezeichnet) ist eine Komponente des .NET Framework, die es Ihnen ermöglicht, Dienste zu erstellen, die die Open Data Protocol (odata) verwenden, um Daten mithilfe der Semantik von [Representational State Transfer (Rest)](https://go.microsoft.com/fwlink/?LinkId=113919)über das Internet oder Intranet verfügbar zu machen und zu nutzen. OData macht Daten als durch URIs adressierbare Ressourcen verfügbar. Der Zugriff auf und die Änderung von Daten erfolgt mithilfe der Standard-HTTP-Befehle GET, PUT, POST und DELETE. Odata verwendet die Entitäts Beziehungs Konventionen des [Entity Data Model](../adonet/entity-data-model.md) , um Ressourcen als Sätze von Entitäten verfügbar zu machen, die durch Zuordnungen verknüpft sind.

WCF Data Services verwendet das odata-Protokoll zum adressieren und Aktualisieren von Ressourcen. Auf diese Weise können Sie von jedem Client aus auf diese Dienste zugreifen, der odata unterstützt. Odata ermöglicht das anfordern und Schreiben von Daten in Ressourcen mithilfe von bekannten Übertragungs Formaten: Atom, ein Satz von Standards zum austauschen und Aktualisieren von Daten als XML und JavaScript Object Notation (JSON), ein in AJAX häufig verwendetes textbasiertes Datenaustauschformat. Bereich.

WCF Data Services können Daten, die aus verschiedenen Quellen stammen, als odata-Feeds verfügbar machen. Mithilfe von Visual Studio-Tools können Sie einen odata-basierten Dienst einfacher erstellen, indem Sie ein ADO.NET Entity Framework-Datenmodell verwenden. Sie können auch odata-Feeds basierend auf Common Language Runtime (CLR)-Klassen und sogar spät gebundenen oder nicht typisierten Daten erstellen.

WCF Data Services umfasst auch eine Reihe von Client Bibliotheken, eine für allgemeine .NET Framework Client Anwendungen und eine für Silverlight-basierte Anwendungen. Diese Client Bibliotheken stellen ein objektbasiertes Programmiermodell bereit, wenn Sie auf einen odata-Feed aus Umgebungen wie .NET Framework und Silverlight zugreifen.

## <a name="where-should-i-start"></a>Wo sollte ich beginnen?

In Abhängigkeit von ihren Interessen sollten Sie die ersten Schritte mit WCF Data Services in einem der folgenden Themen Unternehmen.

Ich möchte direkt beginnen…

- [Schnellstart](quickstart-wcf-data-services.md)

- [Erste Schritte](getting-started-with-wcf-data-services.md)

- [Silverlight-Schnellstart](https://go.microsoft.com/fwlink/?LinkID=192782)

- [Silverlight-Schnellstart für Windows Phone-Entwicklung](https://go.microsoft.com/fwlink/?LinkID=214535)

Nur Code anzeigen...

- [Schnellstart](quickstart-wcf-data-services.md)

- [Vorgehensweise: Ausführen von Datendienstabfragen](how-to-execute-data-service-queries-wcf-data-services.md)

- [Vorgehensweise: Binden von Daten an Windows Presentation Foundation-Elemente](bind-data-to-wpf-elements-wcf-data-services.md)

Ich möchte mehr über odata erfahren...

- [Whitepaper: Einführung in OData](https://go.microsoft.com/fwlink/?LinkId=220867)

- [Open Data Protocol-Website](https://go.microsoft.com/fwlink/?LinkID=184554)

- [OData: SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

- [OData: Häufig gestellte Fragen](https://go.microsoft.com/fwlink/?LinkId=185867)

Ich möchte einige Videos ansehen...

- [Einführung in WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=220864)

- [WCF Data Services Developer-Videos](https://go.microsoft.com/fwlink/?LinkId=220861)

- [OData: Entwickler-Website](https://go.microsoft.com/fwlink/?LinkId=185866)

Ich möchte End-to-End-Beispiele sehen...

- [WCF Data Services-Dokumentationsbeispiele auf MSDN Samples Gallery](https://go.microsoft.com/fwlink/?LinkID=220865)

- [Weitere WCF Data Services-Beispiele auf MSDN Samples Gallery](https://go.microsoft.com/fwlink/?LinkId=220866)

- [OData: SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

Wie erfolgt die Integration in Visual Studio?

- [Generieren der Datendienst-Clientbibliothek](generating-the-data-service-client-library-wcf-data-services.md)

- [Erstellen des Datendiensts](creating-the-data-service.md)

- [Entity Framework-Anbieter](entity-framework-provider-wcf-data-services.md)

Für welche Aufgaben kann ich es verwenden?

- [Übersicht](wcf-data-services-overview.md)

- [Whitepaper: Einführung in OData](https://go.microsoft.com/fwlink/?LinkId=220867)

- [Anwendungsszenarios](application-scenarios-wcf-data-services.md)

Ich möchte Silverlight verwenden...

- [Silverlight-Schnellstart](https://go.microsoft.com/fwlink/?LinkID=192782)

- [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149)

- [Erste Schritte mit Silverlight](https://go.microsoft.com/fwlink/?LinkId=148366)

Ich möchte LINQ verwenden...

- [Abfragen des Datendiensts](querying-the-data-service-wcf-data-services.md)

- [Überlegungen zu LINQ](linq-considerations-wcf-data-services.md)

- [Vorgehensweise: Ausführen von Datendienstabfragen](how-to-execute-data-service-queries-wcf-data-services.md)

Ich benötige noch weitere Informationen...

- [WCF Data Services-Teamblog](https://go.microsoft.com/fwlink/?LinkID=150511)

- [Ressourcen](wcf-data-services-resources.md)

- [WCF Data Services Developer Center](https://go.microsoft.com/fwlink/?LinkId=220868)

- [Open Data Protocol-Website](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a>In diesem Abschnitt

[Übersicht](wcf-data-services-overview.md)

Bietet eine Übersicht über die Features und Funktionen, die in WCF Data Services verfügbar sind.

[Neues in WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))

Beschreibt neue Funktionen in WCF Data Services und Unterstützung neuer odata-Funktionen.

[Erste Schritte](getting-started-with-wcf-data-services.md)

Beschreibt, wie odata-Feeds mithilfe von WCF Data Services verfügbar gemacht und genutzt werden.

[Defining WCF Data Services](defining-wcf-data-services.md)

Beschreibt, wie Sie einen Datendienst erstellen und konfigurieren, der odata-Feeds verfügbar macht.

[WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)

Beschreibt die Verwendung von Client Bibliotheken für die Nutzung von odata-Feeds aus einer .NET Framework Client Anwendung.

## <a name="see-also"></a>Siehe auch

- [Representational State Transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919)
