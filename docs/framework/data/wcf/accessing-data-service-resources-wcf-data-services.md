---
title: Zugreifen auf Datendienstressourcen (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, querying
- getting started, WCF Data Services
- querying the data service [WCF Data Service]
- WCF Data Services, getting started
- WCF Data Services, accessing data
ms.assetid: 9665ff5b-3e3a-495d-bf83-d531d5d060ed
ms.openlocfilehash: 02e45f4e67a80d3afb600f44ea9fa6a5e175310c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186677"
---
# <a name="accessing-data-service-resources-wcf-data-services"></a>Zugreifen auf Datendienstressourcen (WCF Data Services)

WCF Data Services unterstützt die Open Data Protocol (odata), um Ihre Daten als Feed mit Ressourcen verfügbar zu machen, die durch URIs adressierbar sind. Diese Ressourcen werden entsprechend den Entitäts Beziehungs Konventionen des [Entity Data Model](../adonet/entity-data-model.md)dargestellt. In diesem Modell stellen Entitäten Funktionsbausteine von Daten, die Datentypen sind, in einer Anwendungsdomäne dar, z. B. Kunden, Bestellungen, Artikel und Produkte. Das Zugreifen auf und Ändern von Entitätsdaten erfolgt mit der REST ( Representational State Transfer)-Semantik, speziell mit den Standard-HTTP-Verben GET, PUT, POST und DELETE.  
  
## <a name="addressing-resources"></a>Adressieren von Ressourcen  

 In odata adressieren Sie alle Daten, die vom Datenmodell mithilfe eines URI verfügbar gemacht werden. So gibt der folgende URI z. B. einen Feed zurück, bei dem es sich um die Customers-Entitätenmenge handelt, die Einträge für alle Instanzen des Customer-Entitätstyps enthält:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers>
  
 Entitäten verfügen über besondere Eigenschaften, die als Entitätsschlüssel bezeichnet werden. Ein Entitätsschlüssel wird verwendet, um eine einzelne Entität in einer Entitätenmenge eindeutig zu identifizieren. Dies ermöglicht es Ihnen, eine bestimmte Instanz eines Entitätstyps in der Entitätenmenge zu adressieren. Der folgende URI gibt z. B. einen Eintrag für eine bestimmte Instanz des Customer-Entitätstyps mit dem Schlüsselwert `ALFKI` zurück:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')>
  
 Primitive und komplexe Eigenschaften einer Entitätsinstanz können auch einzeln behandelt werden. Der folgende URI gibt z. B. ein XML-Element zurück, das den `ContactName`-Eigenschaftswert für einen bestimmten Kunden enthält:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName>
  
 Wenn Sie den `$value`-Endpunkt in den vorherigen URI einschließen, wird in der Antwortnachricht nur der Wert der primitiven Eigenschaft zurückgegeben. Im folgenden Beispiel wird nur die Zeichenfolge "Maria Anders" ohne das XML-Element zurückgegeben:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName/$value>
  
 Beziehungen zwischen Entitäten werden im Datenmodell durch Zuordnungen definiert. Diese Zuordnungen ermöglichen es Ihnen, mithilfe der Navigationseigenschaften einer Entitätsinstanz verknüpfte Entitäten zu adressieren. Eine Navigationseigenschaft kann entweder eine einzelne verknüpfte Entität (bei einer n:1-Beziehung) oder einen Satz von verknüpften Entitäten (bei einer 1:n-Beziehung) zurückgeben. Der folgende URI gibt z. B. einen Feed zurück, bei dem es sich um den Satz aller Bestellungen handelt, die sich auf einen bestimmten Kunden beziehen:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders>
  
 Gewöhnlich bidirektionale Beziehungen werden mithilfe eines Paars von Navigationseigenschaften dargestellt. Als Gegenstück zu der Beziehung im vorherigen Beispiel gibt der folgende URI einen Verweis auf die Customer-Entität zurück, zu der eine bestimmte Order-Entität gehört:  
  
<https://services.odata.org/Northwind/Northwind.svc/Orders(10643)/Customer>
  
 Odata ermöglicht Ihnen außerdem das Adressieren von Ressourcen auf der Grundlage der Ergebnisse von Abfrage Ausdrücken. Dies ermöglicht das Filtern mehrerer Ressourcensätze anhand eines ausgewerteten Ausdrucks. Der folgende URI filtert z. B. die Ressourcen, um nur die Bestellungen für den angegebenen Kunden zurückzugeben, die seit dem 22. September 1997 ausgeliefert wurden:  
  
`https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=ShippedDate gt datetime'1997-09-22T00:00:00'`
  
 Weitere Informationen finden Sie unter [odata: URI-Konventionen](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/).
  
## <a name="system-query-options"></a>Systemabfrageoptionen  

 Odata definiert einen Satz von System Abfrage Optionen, mit denen Sie herkömmliche Abfrage Vorgänge für Ressourcen ausführen können, z. b. Filtern, Sortieren und Paging. Der folgende URI gibt z. b. den Satz aller `Order` Entitäten zusammen mit verknüpften `Order_Detail` Entitäten zurück, deren Postleitzahlen nicht auf enden `100` :  
  
`https://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')&$expand=Order_Details&$orderby=ShipCity`
  
 Die Einträge des zurückgegebenen Feeds werden zudem nach dem Wert der ShipCity-Eigenschaft der Bestellungen geordnet.  
  
 WCF Data Services unterstützt die folgenden odata-System Abfrage Optionen:  
  
|Abfrageoption|Beschreibung|  
|------------------|-----------------|  
|`$orderby`|Definiert im zurückgegebenen Feed eine Standardsortierreihenfolge für Entitäten. Die folgende Abfrage sortiert den zurückgegebenen Kundenfeed nach Landkreis und Ort:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers?$orderby=Country,City>`|  
|`$top`|Gibt die Anzahl der Entitäten an, die in den zurückgegebenen Feed eingeschlossen werden soll. Im folgenden Beispiel werden die ersten zehn Kunden übersprungen und die folgenden zehn zurückgegeben:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`|  
|`$skip`|Gibt die Anzahl der Entitäten an, die vor dem Beginn der Rückgabe der Entitäten im Feed übersprungen werden sollen. Im folgenden Beispiel werden die ersten zehn Kunden übersprungen und die folgenden zehn zurückgegeben:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`|  
|`$filter`|Definiert einen Ausdruck, der die im Feed zurückgegebenen Entitäten anhand bestimmter Kriterien filtert. Diese Abfrageoption unterstützt einen Satz logischer Vergleichsoperatoren, arithmetische Operatoren und vordefinierte Abfragefunktionen, die zur Auswertung des Filterausdrucks verwendet werden. Im folgenden Beispiel werden alle Bestellungen zurückgegeben, deren Postleitzahlen nicht mit "100" enden:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')`|  
|`$expand`|Gibt an, welche verknüpften Entitäten von der Abfrage zurückgegeben werden. Verknüpfte Entitäten sind entweder als Feed oder als Eintrag in der von der Abfrage zurückgegebenen Entität inline enthalten. Im folgenden Beispiel werden die Bestellungen des Kunden "ALFKI" zusammen mit den Artikeldetails der einzelnen Bestellungen zurückgegeben:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$expand=Order_Details`|  
|`$select`|Gibt eine Projektion an, die die Eigenschaften der Entität definiert, die in der Projektion zurückgegeben werden. In der Standardeinstellung werden alle Eigenschaften einer Entität in einem Feed zurückgegeben. Die folgende Abfrage gibt nur drei Eigenschaften der `Customer`-Entität zurück:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers?$select=CustomerID,CompanyName,City`|  
|`$inlinecount`|Fordert an, dass die Anzahl der im Feed zurückgegebenen Entitäten im Feed enthalten sein muss.|  
  
## <a name="addressing-relationships"></a>Behandeln von Beziehungen  

 Zusätzlich zum Adressieren von Entitätenmengen und Entitäts Instanzen ermöglicht odata auch das adressieren der Zuordnungen, die Beziehungen zwischen Entitäten darstellen. Diese Funktionalität ist erforderlich, um eine Beziehung zwischen zwei Entitätsinstanzen erstellen oder ändern zu können, z. B. das Versandunternehmen, das sich auf eine angegebene Bestellung in der Northwind-Beispieldatenbank bezieht. Odata unterstützt einen- `$link` Operator, um die Zuordnungen zwischen Entitäten zu adressieren. Der folgende URI wird z. B. in einer HTTP PUT-Anforderungsnachricht angegeben, um das Versandunternehmen für die angegebene Bestellung in ein neues Versandunternehmen zu ändern.  
  
`https://services.odata.org/Northwind/Northwind.svc/Orders(10643)/$links/Shipper`
  
 Weitere Informationen finden Sie im Abschnitt `3.2. Addressing Links between Entries` unter [odata: URI-Konventionen](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/).
  
## <a name="consuming-the-returned-feed"></a>Verwenden des zurückgegebenen Feeds  

 Der URI einer odata-Ressource ermöglicht es Ihnen, vom Dienst verfügbar gemachte Entitäts Daten zu adressieren. Wenn Sie einen URI in das Adressfeld eines Webbrowsers eingeben, wird eine odata-Feed-Darstellung der angeforderten Ressource zurückgegeben. Weitere Informationen finden Sie in der [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)Anleitung. Obwohl ein Webbrowser nützlich sein kann, um zu testen, ob eine Datendienstressource die erwarteten Daten zurückgibt, wird auf Produktionsdatendiensten, die Daten auch erstellen, aktualisieren und löschen können, im Allgemeinen mit Anwendungscode oder Skriptsprachen auf einer Webseite zugegriffen. Weitere Informationen finden Sie unter [Verwenden eines Daten Dienstanbieter in einer Client Anwendung](using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Open Data Protocol-Website](https://www.odata.org/)
