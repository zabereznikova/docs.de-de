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
ms.openlocfilehash: f1af991d7db9bfeeb0737e65a0517629f359f4a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365328"
---
# <a name="accessing-data-service-resources-wcf-data-services"></a>Zugreifen auf Datendienstressourcen (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] unterstützt die [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Ihre Daten als Feed mit Ressourcen verfügbar machen, die durch URIs adressierbar sind. Diese Ressourcen werden anhand der entitätsbeziehungskonventionen des dargestellt die [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md). In diesem Modell stellen Entitäten Funktionsbausteine von Daten, die Datentypen sind, in einer Anwendungsdomäne dar, z. B. Kunden, Bestellungen, Artikel und Produkte. Das Zugreifen auf und Ändern von Entitätsdaten erfolgt mit der REST ( Representational State Transfer)-Semantik, speziell mit den Standard-HTTP-Verben GET, PUT, POST und DELETE.  
  
## <a name="addressing-resources"></a>Adressieren von Ressourcen  
 In [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] werden alle vom Datenmodell verfügbar gemachten Daten mit einem URI adressiert. Der folgende URI gibt z. B. einen Feed, die die Customers-Entitätenmenge, die Einträge für alle Instanzen des Customer-Entitätstyps enthält:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers  
```  
  
 Entitäten verfügen über besondere Eigenschaften, die als Entitätsschlüssel bezeichnet werden. Ein Entitätsschlüssel wird verwendet, um eine einzelne Entität in einer Entitätenmenge eindeutig zu identifizieren. Dies ermöglicht es Ihnen, eine bestimmte Instanz eines Entitätstyps in der Entitätenmenge zu adressieren. Der folgende URI gibt z. B. einen Eintrag für eine bestimmte Instanz des Customer-Entitätstyps mit dem Schlüsselwert `ALFKI` zurück:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')  
```  
  
 Primitive und komplexe Eigenschaften einer Entitätsinstanz können auch einzeln behandelt werden. Der folgende URI gibt z. B. ein XML-Element zurück, das den `ContactName`-Eigenschaftswert für einen bestimmten Kunden enthält:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName  
```  
  
 Wenn Sie den `$value`-Endpunkt in den vorherigen URI einschließen, wird in der Antwortnachricht nur der Wert der primitiven Eigenschaft zurückgegeben. Im folgenden Beispiel wird nur die Zeichenfolge "Maria Anders" ohne das XML-Element zurückgegeben:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName/$value  
```  
  
 Beziehungen zwischen Entitäten werden im Datenmodell durch Zuordnungen definiert. Diese Zuordnungen ermöglichen es Ihnen, mithilfe der Navigationseigenschaften einer Entitätsinstanz verknüpfte Entitäten zu adressieren. Eine Navigationseigenschaft kann entweder eine einzelne verknüpfte Entität (bei einer n:1-Beziehung) oder einen Satz von verknüpften Entitäten (bei einer 1:n-Beziehung) zurückgeben. Der folgende URI gibt z. B. einen Feed zurück, bei dem es sich um den Satz aller Bestellungen handelt, die sich auf einen bestimmten Kunden beziehen:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders  
```  
  
 Gewöhnlich bidirektionale Beziehungen werden mithilfe eines Paars von Navigationseigenschaften dargestellt. Als Gegenstück zu der Beziehung im vorherigen Beispiel gibt der folgende URI einen Verweis auf die Customer-Entität zurück, zu der eine bestimmte Order-Entität gehört:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/Customer  
```  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Außerdem können Sie Adressressourcen anhand der Ergebnisse von Abfrageausdrücken. Dies ermöglicht das Filtern mehrerer Ressourcensätze anhand eines ausgewerteten Ausdrucks. Der folgende URI filtert z. B. die Ressourcen, um nur die Bestellungen für den angegebenen Kunden zurückzugeben, die seit dem 22. September 1997 ausgeliefert wurden:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=ShippedDate gt datetime'1997-09-22T00:00:00'  
```  
  
 Weitere Informationen finden Sie unter [OData: URI-Konventionen](http://go.microsoft.com/fwlink/?LinkId=185564).  
  
## <a name="system-query-options"></a>Systemabfrageoptionen  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] definiert einen Satz von systemabfrageoptionen, mit denen Sie herkömmliche Abfragevorgänge für Ressourcen, z. B. filtern, Sortieren und Paging ausführen können. Der folgende URI gibt z. B. den Satz aller der `Order` -Entitäten sowie die zugehörigen `Order_Detail` Entitäten, die Postleitzahlen darf nicht in enden `100`:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')&$expand=Order_Details&$orderby=ShipCity  
```  
  
 Die Einträge des zurückgegebenen Feeds werden zudem nach dem Wert der ShipCity-Eigenschaft der Bestellungen geordnet.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] unterstützt die folgenden [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] systemabfrageoptionen:  
  
|Abfrageoption|Beschreibung|  
|------------------|-----------------|  
|`$orderby`|Definiert im zurückgegebenen Feed eine Standardsortierreihenfolge für Entitäten. Die folgende Abfrage sortiert den zurückgegebenen Kundenfeed nach Landkreis und Ort:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$orderby=Country,City`<br /><br /> Weitere Informationen finden Sie unter [OData: OrderBy-Systemabfrageoption ($orderby)](http://go.microsoft.com/fwlink/?LinkId=186968).|  
|`$top`|Gibt die Anzahl der Entitäten an, die in den zurückgegebenen Feed eingeschlossen werden soll. Im folgenden Beispiel werden die ersten zehn Kunden übersprungen und die folgenden zehn zurückgegeben:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Weitere Informationen finden Sie unter [OData: Top System Query Option ($top)](http://go.microsoft.com/fwlink/?LinkId=186969).|  
|`$skip`|Gibt die Anzahl der Entitäten an, die vor dem Beginn der Rückgabe der Entitäten im Feed übersprungen werden sollen. Im folgenden Beispiel werden die ersten zehn Kunden übersprungen und die folgenden zehn zurückgegeben:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Weitere Informationen finden Sie unter [OData: Skip System Query Option ($skip)](http://go.microsoft.com/fwlink/?LinkId=186971).|  
|`$filter`|Definiert einen Ausdruck, der die im Feed zurückgegebenen Entitäten anhand bestimmter Kriterien filtert. Diese Abfrageoption unterstützt einen Satz logischer Vergleichsoperatoren, arithmetische Operatoren und vordefinierte Abfragefunktionen, die zur Auswertung des Filterausdrucks verwendet werden. Im folgenden Beispiel werden alle Bestellungen zurückgegeben, deren Postleitzahlen nicht mit "100" enden:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')`<br /><br /> Weitere Informationen finden Sie unter [OData: Filter System Query Option ($filter)](http://go.microsoft.com/fwlink/?LinkId=186972).|  
|`$expand`|Gibt an, welche verknüpften Entitäten von der Abfrage zurückgegeben werden. Verknüpfte Entitäten sind entweder als Feed oder als Eintrag in der von der Abfrage zurückgegebenen Entität inline enthalten. Im folgenden Beispiel werden die Bestellungen des Kunden "ALFKI" zusammen mit den Artikeldetails der einzelnen Bestellungen zurückgegeben:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$expand=Order_Details`<br /><br /> Weitere Informationen finden Sie unter [OData: Expand System Query-Option (expand, $)](http://go.microsoft.com/fwlink/?LinkId=186973).|  
|`$select`|Gibt eine Projektion an, die die Eigenschaften der Entität definiert, die in der Projektion zurückgegeben werden. In der Standardeinstellung werden alle Eigenschaften einer Entität in einem Feed zurückgegeben. Die folgende Abfrage gibt nur drei Eigenschaften der `Customer`-Entität zurück:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$select=CustomerID,CompanyName,City`<br /><br /> Weitere Informationen finden Sie unter [OData: Select System Query Option ($select)](http://go.microsoft.com/fwlink/?LinkID=186076).|  
|`$inlinecount`|Fordert an, dass die Anzahl der im Feed zurückgegebenen Entitäten im Feed enthalten sein muss. Weitere Informationen finden Sie unter [OData: inlinecount erlaubt-Systemabfrageoption ($inlinecount)](http://go.microsoft.com/fwlink/?LinkId=186975).|  
  
## <a name="addressing-relationships"></a>Behandeln von Beziehungen  
 Zusätzlich zum Adressieren von Entitätenmengen und Entitätsinstanzen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] ermöglicht auch das Adressieren von Zuordnungen, die Beziehungen zwischen Entitäten darstellen. Diese Funktionalität ist erforderlich, um eine Beziehung zwischen zwei Entitätsinstanzen erstellen oder ändern zu können, z. B. das Versandunternehmen, das sich auf eine angegebene Bestellung in der Northwind-Beispieldatenbank bezieht. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt eine `$link` Operator, um speziell die Zuordnungen zwischen Entitäten zu adressieren. Der folgende URI wird z. B. in einer HTTP PUT-Anforderungsnachricht angegeben, um das Versandunternehmen für die angegebene Bestellung in ein neues Versandunternehmen zu ändern.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/$links/Shipper  
```  
  
 Weitere Informationen finden Sie unter [OData: Addressing Links between Entries](http://go.microsoft.com/fwlink/?LinkId=187351).  
  
## <a name="consuming-the-returned-feed"></a>Verwenden des zurückgegebenen Feeds  
 Der URI des ein [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Ressource ermöglicht es Ihnen, Adresse Entitätsdaten, die vom Dienst verfügbar gemacht. Wenn Sie einen URI in das Adressfeld eines Webbrowsers eingeben einer [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeddarstellung der angeforderten Ressource zurückgegeben wird. Weitere Informationen finden Sie unter der [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Obwohl ein Webbrowser nützlich sein kann, für das testen möchten, ob eine datendienstressource die erwarteten Daten zurückgibt, produktionsdatendiensten, die können auch erstellen, aktualisieren und Löschen von Daten erfolgt in der Regel vom Anwendungscode oder Skriptsprachen auf einer Webseite. Weitere Informationen finden Sie unter [Verwenden eines Datendiensts in einer Clientanwendung](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Open Data Protocol-Website](http://go.microsoft.com/fwlink/?LinkID=182204)
