---
title: Übersicht über WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services
- WCF Data Services, about
ms.assetid: 7924cf94-c9a6-4015-afc9-f5d22b1743bb
ms.openlocfilehash: 6f085f87286aa5af4a3c2aaf2b74c9bf19023356
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899437"
---
# <a name="wcf-data-services-overview"></a>Übersicht über WCF Data Services

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

## <a name="overview"></a>Übersicht

WCF Data Services ermöglicht die Erstellung und Nutzung von Datendiensten für das Internet oder ein Intranet mithilfe des Open Data Protocol (odata). Mit odata können Sie Ihre Daten als Ressourcen verfügbar machen, die durch URIs adressierbar sind. Dies ermöglicht Ihnen das Zugreifen auf und Ändern von Daten mit der REST (Representational State Transfer)-Semantik, insbesondere mit den Standard-HTTP-Verben GET, PUT, POST und DELETE. Dieses Thema enthält eine Übersicht über die von odata definierten Muster und Methoden sowie über die von WCF Data Services bereitgestellten Funktionen, um odata in .NET Framework basierten Anwendungen zu nutzen.  
  
## <a name="address-data-as-resources"></a>Adressieren von Daten als Ressourcen  

 OData macht Daten als durch URIs adressierbare Ressourcen verfügbar. Die Ressourcenpfade werden anhand der Entitätsbeziehungskonventionen des Entity Data Model erstellt. In diesem Modell stellen Entitäten Operationseinheiten von Daten in einer Anwendungsdomäne dar, z. B. Kunden, Bestellungen, Artikel und Produkte. Weitere Informationen finden Sie unter [Entity Data Model](../adonet/entity-data-model.md).  
  
 In odata adressieren Sie Entitäts Ressourcen als Entitätenmenge, die Instanzen von Entitäts Typen enthält. Der URI gibt z. b. `https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders` alle Bestellungen aus dem `Northwind` Datendienst zurück, die mit dem Kunden mit dem Wert verknüpft sind. `CustomerID``ALFKI.`  
  
 Mit Abfrageausdrücken können Sie herkömmliche Abfragevorgänge für Ressourcen ausführen, z. B. Filtern, Sortieren und Paging. Der URI `https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=Freight gt 50` filtert z. B. die Ressourcen, um nur die Bestellungen mit Frachtkosten von über 50 Dollar zurückzugeben. Weitere Informationen finden Sie unter [zugreifen auf Datendienst Ressourcen](accessing-data-service-resources-wcf-data-services.md).  
  
## <a name="interoperable-data-access"></a>Interoperabler Datenzugriff  

 Odata basiert auf standardmäßigen Internet Protokollen, damit Datendienste mit Anwendungen interoperabel sind, die die .NET Framework nicht verwenden. Da Sie Daten mithilfe von Standard-URIs adressieren können, kann die Anwendung mit der REST-Semantik ( Representational State Transfer), speziell mit den Standard-HTTP-Verben GET, PUT, POST und DELETE, auf Daten zugreifen und diese ändern. Dies ermöglicht Ihnen den Zugriff auf diese Dienste von einem Client, der über Standard-HTTP-Protokolle übertragene Daten analysieren und darauf zugreifen kann.  
  
Odata definiert einen Satz von Erweiterungen für das Atom Publishing Protocol (AtomPub). HTTP-Anforderungen und -Antworten werden in mehreren Datenformaten unterstützt, um verschiedene Clientanwendungen und -plattformen zu unterstützen. Ein odata-Feed kann Daten in Atom, JavaScript Object Notation (JSON) und als reines XML darstellen. Atom ist zwar das Standardformat, das Format des Feeds wird jedoch im Header der HTTP-Anforderung angegeben. Weitere Informationen finden Sie unter [odata: Atom-Format](https://www.odata.org/documentation/odata-version-2-0/atom-format/) und [odata: JSON-Format](https://www.odata.org/documentation/odata-version-2-0/json-format/).  
  
 Beim Veröffentlichen von Daten als odata-Feed stützt WCF Data Services andere vorhandene Internet Funktionen für Vorgänge wie Caching und Authentifizierung. Um dies zu erreichen, WCF Data Services in vorhandene Hostinganwendungen und-Dienste wie ASP.net, Windows Communication Foundation (WCF) und Internetinformationsdienste (IIS) integriert.  
  
## <a name="storage-independence"></a>Speicherunabhängigkeit  

 Obwohl Ressourcen auf Grundlage eines Entitäts Beziehungs Modells adressiert werden, WCF Data Services odata-Feeds unabhängig von der zugrunde liegenden Datenquelle verfügbar machen. Nachdem WCF Data Services eine HTTP-Anforderung für eine Ressource akzeptiert, die ein URI identifiziert, wird die Anforderung deserialisiert, und eine Darstellung dieser Anforderung wird an einen WCF Data Services Anbieter übergeben. Dieser Anbieter übersetzt die Anforderung in ein datenquellenspezifisches Format und führt die Anforderung für die zugrunde liegende Datenquelle aus. WCF Data Services erzielt Speicher Unabhängigkeit, indem das konzeptionelle Modell, das die von odata vorgeschriebenen Ressourcen adressiert, von dem spezifischen Schema der zugrunde liegenden Datenquelle getrennt wird.  
  
 WCF Data Services in den ADO.NET-Entity Framework integriert, damit Sie Datendienste erstellen können, die relationale Daten verfügbar machen. Sie können die Entity Data Model-Tools verwenden, um ein Datenmodell zu erstellen, das adressierbare Ressourcen als Entitäten enthält, und gleichzeitig die Zuordnung zwischen diesem Modell und den Tabellen in der zugrunde liegenden Datenbank definieren. Weitere Informationen finden Sie unter [Entity Framework-Anbieter](entity-framework-provider-wcf-data-services.md).  
  
 WCF Data Services ermöglicht außerdem das Erstellen von Datendiensten, die alle Datenstrukturen verfügbar machen, die eine Implementierung der- <xref:System.Linq.IQueryable%601> Schnittstelle zurückgeben. Dies ermöglicht das Erstellen von Datendiensten, die Daten aus .NET Framework-Typen verfügbar machen. Erstellungs-, Aktualisierungs- und Löschvorgänge werden unterstützt, wenn Sie außerdem die <xref:System.Data.Services.IUpdatable>-Schnittstelle implementieren. Weitere Informationen finden Sie unter [reflektionsanbieter](reflection-provider-wcf-data-services.md).  
  
 Eine Abbildung der Integration von WCF Data Services in diese Datenanbieter finden Sie im Architektur Diagramm weiter unten in diesem Thema.  
  
## <a name="custom-business-logic"></a>Benutzerdefinierte Geschäftslogik  

 WCF Data Services vereinfacht das Hinzufügen von benutzerdefinierter Geschäftslogik zu einem Datendienst durch Dienst Vorgänge und Interceptors. Dienstvorgänge sind auf dem Server definierte Methoden, die genau wie Datenressourcen über URIs adressierbar sind. Dienstvorgänge können auch Abfrageausdruckssyntax zum Filtern, Sortieren und Paging der von einem Vorgang zurückgegebenen Daten verwenden. Der URI `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$orderby=OrderDate&$top=10&$skip=10` stellt z. B. einen Aufruf des Dienstvorgangs mit dem Namen `GetOrdersByCity` im Northwind-Datendienst dar, der Bestellungen für Kunden aus London mit nach `OrderDate` sortierten Seitenergebnissen zurückgibt. Weitere Informationen finden Sie unter [Dienst Vorgänge](service-operations-wcf-data-services.md).  
  
 Mit Interceptoren können Sie eine benutzerdefinierte Anwendungslogik in die Verarbeitung von Anforderungs- oder Antwortnachrichten durch einen Datendienst integrieren. Interceptors werden aufgerufen, wenn für die angegebene Entitätenmenge ein Abfrage-, Einfüge-, Aktualisierungs- oder Löschvorgang durchgeführt wird. Dadurch kann ein Interceptor die Daten ändern, eine Autorisierungsrichtlinie erzwingen oder sogar den Vorgang beenden. Interceptormethoden müssen explizit für eine bestimmte Entitätenmenge, die von einem Datendienst zur Verfügung gestellt wird, registriert werden. Weitere Informationen finden Sie unter [Interceptors](interceptors-wcf-data-services.md).  
  
## <a name="client-libraries"></a>Clientbibliotheken  

 Odata definiert einen Satz von einheitlichen Mustern für die Interaktion mit Datendiensten. Dies ermöglicht das Erstellen wiederverwendbarer Komponenten auf Grundlage dieser Dienste, z. B. clientseitiger Bibliotheken, die die Verwendung dieser Datendienste erleichtern.  
  
 WCF Data Services umfasst Client Bibliotheken sowohl für .NET Framework-als auch für Silverlight-basierte Client Anwendungen. Diese Clientbibliotheken ermöglichen die Interaktion mit Datendiensten mithilfe von .NET Framework-Objekten. Zudem werden objektbasierte Abfragen und LINQ-Abfragen, das Laden verknüpfter Objekte, eine Änderungsnachverfolgung und die Identitätsauflösung unterstützt. Weitere Informationen finden Sie unter [WCF Data Services-Client Bibliothek](wcf-data-services-client-library.md).  
  
 Zusätzlich zu den odata-Client Bibliotheken, die in der .NET Framework und mit Silverlight enthalten sind, gibt es weitere Client Bibliotheken, die es Ihnen ermöglichen, einen odata-Feed in Client Anwendungen (z. b. php-, AJAX-und Java-Anwendungen) zu nutzen. Weitere Informationen zum odata SDK finden Sie unter [odata SDK-Sample Code](https://www.odata.org/ecosystem/#sdk).
  
## <a name="architecture-overview"></a>Übersicht über die Architektur  

 Das folgende Diagramm veranschaulicht die WCF Data Services-Architektur für das verfügbar machen von odata-Feeds und die Verwendung dieser Feeds in odata-fähigen Client Bibliotheken:  
  
 ![Screenshot, der ein WCF Data Services Architektur Diagramm zeigt.](./media/wcf-data-services-overview/windows-communication-foundation-data-services-architecture.gif)  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services 4.5](index.md)
- [Erste Schritte](getting-started-with-wcf-data-services.md)
- [Definieren von WCF Data Services](defining-wcf-data-services.md)
- [Zugreifen auf Datendienstressourcen (WCF Data Services)](/previous-versions/dotnet/netframework-4.0/dd728283(v=vs.100))
- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
- [Representational State Transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
