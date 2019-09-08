---
title: Übersicht über WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services
- WCF Data Services, about
ms.assetid: 7924cf94-c9a6-4015-afc9-f5d22b1743bb
ms.openlocfilehash: 66dd61210e36210f5444eb05355612eeb75c155a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790238"
---
# <a name="wcf-data-services-overview"></a>Übersicht über WCF Data Services
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]ermöglicht die Erstellung und Nutzung von Datendiensten für das Internet oder ein Intranet mithilfe [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]von. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]mit können Sie Ihre Daten als Ressourcen verfügbar machen, die durch URIs adressierbar sind. Dies ermöglicht Ihnen das Zugreifen auf und Ändern von Daten mit der REST (Representational State Transfer)-Semantik, insbesondere mit den Standard-HTTP-Verben GET, PUT, POST und DELETE. Dieses Thema beinhaltet eine Übersicht sowohl über die Muster als auch die Methoden, die mit [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] definiert werden, sowie über die von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] bereitgestellten Funktionen, mit denen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] in .NET Framework-basierten Anwendungen verwendet werden kann.  
  
## <a name="address-data-as-resources"></a>Adressieren von Daten als Ressourcen  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] macht Daten als durch URIs adressierbare Ressourcen verfügbar. Die Ressourcenpfade werden anhand der Entitätsbeziehungskonventionen des Entity Data Model erstellt. In diesem Modell stellen Entitäten Betriebseinheiten von Daten in einer Anwendungsdomäne dar, z. b. Kunden, Bestellungen, Artikel und Produkte. Weitere Informationen finden Sie unter [Entity Data Model](../adonet/entity-data-model.md).  
  
 In [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] werden Entitätsressourcen als Entitätenmenge adressiert, der Instanzen von Entitätstypen enthält. Der URI `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders` gibt z. b. alle Bestellungen aus dem `Northwind` Datendienst zurück, die mit dem Kunden mit `CustomerID` dem Wert verknüpft sind.`ALFKI.`  
  
 Mit Abfrageausdrücken können Sie herkömmliche Abfragevorgänge für Ressourcen ausführen, z. B. Filtern, Sortieren und Paging. Der URI `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=Freight gt 50` filtert z. B. die Ressourcen, um nur die Bestellungen mit Frachtkosten von über 50 Dollar zurückzugeben. Weitere Informationen finden Sie unter [zugreifen auf Datendienst Ressourcen](accessing-data-service-resources-wcf-data-services.md).  
  
## <a name="interoperable-data-access"></a>Interoperabler Datenzugriff  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]basiert auf standardmäßigen Internet Protokollen, damit Datendienste mit Anwendungen interoperabel sind, die die .NET Framework nicht verwenden. Da Sie die Daten mithilfe von Standard-URIs adressieren können, kann die Anwendung mithilfe der Semantik von Representational State Transfer (Rest), insbesondere der standardmäßigen HTTP-Verben GET, Put, Post und DELETE, auf Daten zugreifen und diese ändern. Dies ermöglicht Ihnen den Zugriff auf diese Dienste von einem Client, der über Standard-HTTP-Protokolle übertragene Daten analysieren und darauf zugreifen kann.  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] definiert einen Satz von Erweiterungen für das Atom Publishing Protocol (AtomPub). HTTP-Anforderungen und -Antworten werden in mehreren Datenformaten unterstützt, um verschiedene Clientanwendungen und -plattformen zu unterstützen. Ein [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feed kann Daten in Atom, JavaScript Object Notation (JSON) und als einfaches XML darstellen. Atom ist zwar das Standardformat, das Format des Feeds wird jedoch im Header der HTTP-Anforderung angegeben. Weitere Informationen finden [Sie unter odata: Atom-](https://go.microsoft.com/fwlink/?LinkID=185794) Format [und odata: JSON-](https://go.microsoft.com/fwlink/?LinkID=185795)Format.  
  
 Beim Veröffentlichen von Daten als [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Feed [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] werden von andere vorhandene Internet Funktionen für Vorgänge wie Caching und Authentifizierung unterstützt. Um dies zu erreichen [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] , können vorhandene Hostinganwendungen und-Dienste wie ASP.net, Windows Communication Foundation (WCF) und Internetinformationsdienste (IIS) integriert werden.  
  
## <a name="storage-independence"></a>Speicherunabhängigkeit  
 Obwohl Ressourcen auf der Grundlage eines Entitätsbeziehungsmodells adressiert werden, macht [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)][!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feeds unabhängig von der zugrunde liegenden Datenquelle verfügbar. Nachdem [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] eine HTTP-Anforderung an eine Ressource akzeptiert, die ein URI identifiziert, wird die Anforderung deserialisiert, und eine Darstellung dieser Anforderung wird an einen [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Anbieter übergeben. Dieser Anbieter übersetzt die Anforderung in ein datenquellenspezifisches Format und führt die Anforderung für die zugrunde liegende Datenquelle aus. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] erreicht Speicherunabhängigkeit durch das Trennen des konzeptionellen Modells, das von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] vorgeschriebene Ressourcen aus dem jeweiligen Schema der zugrunde liegenden Datenquelle adressiert.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ist in ADO.NET Entity Framework integriert, sodass Sie Datendienste erstellen können, die relationale Daten verfügbar machen. Sie können die Entity Data Model-Tools verwenden, um ein Datenmodell zu erstellen, das adressierbare Ressourcen als Entitäten enthält, und gleichzeitig die Zuordnung zwischen diesem Modell und den Tabellen in der zugrunde liegenden Datenbank definieren. Weitere Informationen finden Sie unter [Entity Framework-Anbieter](entity-framework-provider-wcf-data-services.md).  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]ermöglicht Ihnen außerdem das Erstellen von Datendiensten, die alle Datenstrukturen verfügbar machen, die eine <xref:System.Linq.IQueryable%601> Implementierung der-Schnittstelle zurückgeben. Dies ermöglicht das Erstellen von Datendiensten, die Daten aus .NET Framework-Typen verfügbar machen. Erstellungs-, Aktualisierungs- und Löschvorgänge werden unterstützt, wenn Sie außerdem die <xref:System.Data.Services.IUpdatable>-Schnittstelle implementieren. Weitere Informationen finden Sie unter [reflektionsanbieter](reflection-provider-wcf-data-services.md).  
  
 Eine Abbildung der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Integration von in diese Datenanbieter finden Sie im Architektur Diagramm weiter unten in diesem Thema.  
  
## <a name="custom-business-logic"></a>Benutzerdefinierte Geschäftslogik  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]vereinfacht das Hinzufügen von benutzerdefinierter Geschäftslogik zu einem Datendienst durch Dienst Vorgänge und Interceptors. Dienstvorgänge sind auf dem Server definierte Methoden, die genau wie Datenressourcen über URIs adressierbar sind. Dienstvorgänge können auch Abfrageausdruckssyntax zum Filtern, Sortieren und Paging der von einem Vorgang zurückgegebenen Daten verwenden. Der URI `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$orderby=OrderDate&$top=10&$skip=10` stellt z. B. einen Aufruf des Dienstvorgangs mit dem Namen `GetOrdersByCity` im Northwind-Datendienst dar, der Bestellungen für Kunden aus London mit nach `OrderDate` sortierten Seitenergebnissen zurückgibt. Weitere Informationen finden Sie unter [Dienst Vorgänge](service-operations-wcf-data-services.md).  
  
 Mit Interceptoren können Sie eine benutzerdefinierte Anwendungslogik in die Verarbeitung von Anforderungs- oder Antwortnachrichten durch einen Datendienst integrieren. Interceptors werden aufgerufen, wenn für die angegebene Entitätenmenge ein Abfrage-, Einfüge-, Aktualisierungs- oder Löschvorgang durchgeführt wird. Dadurch kann ein Interceptor die Daten ändern, eine Autorisierungsrichtlinie erzwingen oder sogar den Vorgang beenden. Interceptormethoden müssen explizit für eine bestimmte Entitätenmenge, die von einem Datendienst zur Verfügung gestellt wird, registriert werden. Weitere Informationen finden Sie unter [Interceptors](interceptors-wcf-data-services.md).  
  
## <a name="client-libraries"></a>Clientbibliotheken  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]definiert einen Satz von einheitlichen Mustern für die Interaktion mit Datendiensten. Dies bietet die Möglichkeit, wiederverwendbare Komponenten zu erstellen, die auf diesen Diensten basieren, z. b. Client seitige Bibliotheken, die die Nutzung von Datendiensten vereinfachen.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] enthält Clientbibliotheken sowohl für .NET Framework-basierte als auch für Silverlight-basierte Clientanwendungen. Diese Clientbibliotheken ermöglichen die Interaktion mit Datendiensten mithilfe von .NET Framework-Objekten. Zudem werden objektbasierte Abfragen und LINQ-Abfragen, das Laden verknüpfter Objekte, eine Änderungsnachverfolgung und die Identitätsauflösung unterstützt. Weitere Informationen finden Sie unter [WCF Data Services-Client Bibliothek](wcf-data-services-client-library.md).  
  
 Zusätzlich zu den [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Client Bibliotheken, die in der .NET Framework und mit Silverlight enthalten sind, gibt es weitere Client Bibliotheken, die es Ihnen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] ermöglichen, einen-Feed in Client Anwendungen wie PHP, AJAX und Java-Anwendungen zu nutzen. Weitere Informationen finden Sie unter [odata SDK](https://go.microsoft.com/fwlink/?LinkID=185796).  
  
## <a name="architecture-overview"></a>Architekturübersicht  
 Das folgende Diagramm veranschaulicht die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Architektur [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] für das verfügbar machen von Feeds und die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]Verwendung dieser Feeds in-fähigen Client Bibliotheken:  
  
 ![Screenshot, der ein WCF Data Services Architektur Diagramm zeigt.](./media/wcf-data-services-overview/windows-communication-foundation-data-services-architecture.gif)  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services 4.5](index.md)
- [Erste Schritte](getting-started-with-wcf-data-services.md)
- [Defining WCF Data Services](defining-wcf-data-services.md)
- [Zugreifen auf Datendienst Ressourcen (WCF Data Services)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd728283(v=vs.100))
- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
- [Representational State Transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919)
