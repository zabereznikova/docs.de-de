---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: aace683b1a105445b5a3ba3de0a6a671859588b5
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937444"
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5

WCF Data Services (früher als "ADO.NET Data Services" bezeichnet) ist eine Komponente des .NET Framework, die es Ihnen ermöglicht, Dienste zu erstellen, die die Open Data Protocol (odata) verwenden, um Daten mithilfe der Semantik von [Representational State Transfer (Rest)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)über das Internet oder Intranet verfügbar zu machen und zu nutzen. OData macht Daten als Ressourcen verfügbar, die durch URIs adressierbar sind. Der Zugriff auf Daten und deren Änderung erfolgt mithilfe der Standard-HTTP-Verben GET, PUT, POST und DELETE. Odata verwendet die Entitäts Beziehungs Konventionen des [Entity Data Model](../adonet/entity-data-model.md) , um Ressourcen als Sätze von Entitäten verfügbar zu machen, die durch Zuordnungen verknüpft sind.

WCF Data Services verwendet das odata-Protokoll zum adressieren und Aktualisieren von Ressourcen. Auf diese Weise können Sie von jedem Client aus auf diese Dienste zugreifen, der odata unterstützt. Odata ermöglicht das anfordern und Schreiben von Daten in Ressourcen mithilfe von bekannten Übertragungs Formaten: Atom, ein Satz von Standards zum austauschen und Aktualisieren von Daten als XML und JavaScript Object Notation (JSON), ein in AJAX häufig verwendetes textbasiertes Datenaustauschformat. Bereich.

WCF Data Services können Daten, die aus verschiedenen Quellen stammen, als odata-Feeds verfügbar machen. Mithilfe von Visual Studio-Tools können Sie einen odata-basierten Dienst einfacher erstellen, indem Sie ein ADO.NET Entity Framework-Datenmodell verwenden. Sie können auch odata-Feeds basierend auf Common Language Runtime (CLR)-Klassen und sogar spät gebundenen oder nicht typisierten Daten erstellen.

WCF Data Services umfasst auch eine Reihe von Client Bibliotheken, eine für allgemeine .NET Framework Client Anwendungen und eine für Silverlight-basierte Anwendungen. Diese Client Bibliotheken stellen ein objektbasiertes Programmiermodell bereit, wenn Sie auf einen odata-Feed aus Umgebungen wie .NET Framework und Silverlight zugreifen.

## <a name="where-should-i-start"></a>Wo sollte ich beginnen?

In Abhängigkeit von ihren Interessen sollten Sie die ersten Schritte mit WCF Data Services in einem der folgenden Themen Unternehmen.

Ich möchte direkt beginnen…

- [Schnellstart](quickstart-wcf-data-services.md)

- [Erste Schritte](getting-started-with-wcf-data-services.md)

Nur Code anzeigen...

- [Schnellstart](quickstart-wcf-data-services.md)

- [Vorgehensweise: Ausführen von Datendienstabfragen](how-to-execute-data-service-queries-wcf-data-services.md)

- [Vorgehensweise: Binden von Daten an Windows Presentation Foundation-Elemente](bind-data-to-wpf-elements-wcf-data-services.md)

Ich möchte mehr über odata erfahren...

- [Whitepaper: Einführung in odata](https://download.microsoft.com/download/E/5/A/E5A59052-EE48-4D64-897B-5F7C608165B8/IntroducingOData.pdf)
- [Open Data Protocol-Website](https://www.odata.org/)
- [OData: SDK](https://www.odata.org/ecosystem/)

Ich möchte End-to-End-Beispiele sehen...

- [WCF Data Services Schnellstart](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))
- [Odata-SDK-Beispiel Code](https://www.odata.org/ecosystem/#sdk)

Wie erfolgt die Integration in Visual Studio?

- [Generieren der Datendienst-Clientbibliothek](generating-the-data-service-client-library-wcf-data-services.md)

- [Erstellen des Datendiensts](creating-the-data-service.md)

- [Entity Framework-Anbieter](entity-framework-provider-wcf-data-services.md)

Für welche Aufgaben kann ich es verwenden?

- [Übersicht](wcf-data-services-overview.md)

- [Anwendungsszenarios](application-scenarios-wcf-data-services.md)

Ich möchte LINQ verwenden...

- [Abfragen des Datendiensts](querying-the-data-service-wcf-data-services.md)

- [Überlegungen zu LINQ](linq-considerations-wcf-data-services.md)

- [Vorgehensweise: Ausführen von Datendienstabfragen](how-to-execute-data-service-queries-wcf-data-services.md)

Ich benötige noch weitere Informationen...

- [WCF Data Services-Teamblog](https://docs.microsoft.com/archive/blogs/astoriateam/)

- [Ressourcen](wcf-data-services-resources.md)

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

- [Representational State Transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
