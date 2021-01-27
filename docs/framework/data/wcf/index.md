---
title: WCF Data Services 4.5
description: Erfahren Sie mehr über WCF Data Services, eine .NET Framework Komponente, die Dienste zum verfügbar machen und Nutzen von Daten mithilfe der Rest-Semantik unterstützt.
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 2d3da2ca9cd958fc70d3b91362dde71d68dc9d8a
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98898754"
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

## <a name="overview"></a>Übersicht

WCF Data Services (früher als "ADO.NET Data Services" bezeichnet) ist eine Komponente des .NET Framework, die es Ihnen ermöglicht, Dienste zu erstellen, die die Open Data Protocol (odata) verwenden, um Daten mithilfe der Semantik von [Representational State Transfer (Rest)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)über das Internet oder Intranet verfügbar zu machen und zu nutzen. OData macht Daten als durch URIs adressierbare Ressourcen verfügbar. Der Zugriff auf und die Änderung von Daten erfolgt mithilfe der Standard-HTTP-Befehle GET, PUT, POST und DELETE. Odata verwendet die Entitäts Beziehungs Konventionen des [Entity Data Model](../adonet/entity-data-model.md) , um Ressourcen als Sätze von Entitäten verfügbar zu machen, die durch Zuordnungen verknüpft sind.

WCF Data Services verwendet das odata-Protokoll zum adressieren und Aktualisieren von Ressourcen. Auf diese Weise können Sie von jedem Client aus auf diese Dienste zugreifen, der odata unterstützt. Odata ermöglicht das anfordern und Schreiben von Daten in Ressourcen mithilfe von bekannten Übertragungs Formaten: Atom, ein Satz von Standards zum austauschen und Aktualisieren von Daten als XML und JavaScript Object Notation (JSON), ein in AJAX-Anwendungen häufig verwendetes textbasiertes Datenaustauschformat.

WCF Data Services können Daten, die aus verschiedenen Quellen stammen, als odata-Feeds verfügbar machen. Mithilfe von Visual Studio-Tools können Sie einen odata-basierten Dienst einfacher erstellen, indem Sie ein ADO.NET Entity Framework-Datenmodell verwenden. Sie können auch odata-Feeds basierend auf Common Language Runtime (CLR)-Klassen und sogar spät gebundenen oder nicht typisierten Daten erstellen.

WCF Data Services umfasst auch eine Reihe von Client Bibliotheken, eine für allgemeine .NET Framework Client Anwendungen und eine für Silverlight-basierte Anwendungen. Diese Clientbibliotheken stellen ein objektbasiertes Programmiermodell bereit, das in Umgebungen wie .NET Framework und Silverlight für den Zugriff auf OData-Feeds verwendet wird.

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

- [Generieren der Datendienstclientbibliothek](generating-the-data-service-client-library-wcf-data-services.md)

- [Erstellen des Datendiensts](creating-the-data-service.md)

- [Entity Framework-Anbieter](entity-framework-provider-wcf-data-services.md)

Verwendungsmöglichkeiten

- [Übersicht](wcf-data-services-overview.md)

- [Anwendungs Szenarios](application-scenarios-wcf-data-services.md)

Ich möchte LINQ verwenden...

- [Abfragen des Datendiensts](querying-the-data-service-wcf-data-services.md)

- [Überlegungen zu LINQ](linq-considerations-wcf-data-services.md)

- [Vorgehensweise: Ausführen von Datendienstabfragen](how-to-execute-data-service-queries-wcf-data-services.md)

Ich benötige noch weitere Informationen...

- [WCF Data Services-Teamblog](/archive/blogs/astoriateam/)

- [Ressourcen](wcf-data-services-resources.md)

## <a name="in-this-section"></a>In diesem Abschnitt

[Übersicht](wcf-data-services-overview.md)

Bietet eine Übersicht über die Features und Funktionen, die in WCF Data Services verfügbar sind.

[Neues in WCF Data Services 5,0](/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))

Beschreibt neue Funktionen in WCF Data Services und Unterstützung neuer odata-Funktionen.

[Erste Schritte](getting-started-with-wcf-data-services.md)

Beschreibt, wie odata-Feeds mithilfe von WCF Data Services verfügbar gemacht und genutzt werden.

[Definieren von WCF Data Services](defining-wcf-data-services.md)

Beschreibt, wie Sie einen Datendienst erstellen und konfigurieren, der odata-Feeds verfügbar macht.

[WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)

Beschreibt die Verwendung von Client Bibliotheken für die Nutzung von odata-Feeds aus einer .NET Framework Client Anwendung.

## <a name="see-also"></a>Siehe auch

- [Representational State Transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
