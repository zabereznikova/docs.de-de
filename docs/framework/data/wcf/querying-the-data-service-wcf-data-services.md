---
title: Abfragen des Datendiensts (WCF Data Services)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: 823e9444-27aa-4f1f-be8e-0486d67f54c0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 976f1e4d8a149f8104325fd5d006d245afee04a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="querying-the-data-service-wcf-data-services"></a>Abfragen des Datendiensts (WCF Data Services)
Die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliothek ermöglicht es Ihnen, Abfragen für einen Datendienst mit vertrauten [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Programmierschemas auszuführen, u. a. mithilfe von LINQ (Language Integrated Query). Die Clientbibliothek übersetzt eine Abfrage, die auf dem Client als Instanz der <xref:System.Data.Services.Client.DataServiceQuery%601>-Klasse definiert wird, in eine HTTP GET-Anforderungsnachricht. Die Bibliothek empfängt die Antwortnachricht und übersetzt sie in Instanzen von clientdatendienstklassen. Diese Klassen werden vom <xref:System.Data.Services.Client.DataServiceContext> verfolgt, zu dem <xref:System.Data.Services.Client.DataServiceQuery%601> gehört.  
  
## <a name="data-service-queries"></a>Datendienstabfragen  
 Die generische Klasse <xref:System.Data.Services.Client.DataServiceQuery%601> stellt eine Abfrage dar, die eine Auflistung von null oder mehr Entitätstypinstanzen zurückgibt. Eine Datendienstabfrage ist immer einem vorhandenen Datendienstkontext zugeordnet. Dieser Kontext verwaltet den Dienst-URI und die Metadateninformationen, die zum Erstellen und Ausführen der Abfrage erforderlich sind.  
  
 Bei Verwendung der **Hinzufügen eines Dienstverweises** Dialogfeld zum Hinzufügen eines Datendiensts auf eine [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]--basierten Clientanwendung eine entitätscontainerklasse erstellt, die von erben die <xref:System.Data.Services.Client.DataServiceContext> Klasse. Diese Klasse enthält Eigenschaften, die typisierte <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanzen zurückgeben. Es ist eine Eigenschaft für jede Entitätenmenge vorhanden, die der Datendienst verfügbar macht. Diese Eigenschaften erleichtern es, eine Instanz eines typisierten <xref:System.Data.Services.Client.DataServiceQuery%601>-Objekts zu erstellen.  
  
 In den folgenden Szenarien wird eine Abfrage ausgeführt:  
  
-   Wenn Ergebnisse implizit aufgezählt werden, z. B.:  
  
    -   Wenn eine Eigenschaft für den <xref:System.Data.Services.Client.DataServiceContext>, der eine Entitätenmenge darstellt, aufgezählt wird, z. B. in einer `foreach`-Schleife (C#) oder einer `For Each`-Schleife ([!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]).  
  
    -   Wenn die Abfrage einer `List`-Auflistung zugewiesen wird.  
  
-   Wenn die <xref:System.Data.Services.Client.DataServiceQuery%601.Execute%2A>-Methode oder die <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>-Methode explizit aufgerufen wird.  
  
-   Wenn ein LINQ-Abfrageausführungsoperator wie <xref:System.Linq.Enumerable.First%2A> oder <xref:System.Linq.Enumerable.Single%2A> aufgerufen wird.  
  
 Wenn die folgende Abfrage ausgeführt wird, gibt sie alle `Customers`-Entitäten im Northwind-Datendienst zurück:  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getallcustomersspecific)]  
 [!code-vb[Astoria Northwind Client#GetAllCustomersSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getallcustomersspecific)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen von Datendienstabfragen](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md).  
  
 Die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Client unterstützt Abfragen für spät gebundene Objekte, z. B. bei Verwendung der *dynamische* Typ in C# geschrieben. Aus Leistungsgründen sollten für den Datendienst jedoch immer stark typisierte Abfragen verfasst werden. Der <xref:System.Tuple>-Typ und dynamische Objekte werden nicht vom Client unterstützt.  
  
## <a name="linq-queries"></a>LINQ-Abfragen  
 Da die <xref:System.Data.Services.Client.DataServiceQuery%601> -Klasse implementiert die <xref:System.Linq.IQueryable%601> von LINQ definierte Schnittstelle die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] -Clientbibliothek kann LINQ-Abfragen für entitätenmengendaten in einen URI umwandeln, der einen für einen Datendienst ausgewerteten Abfrageausdruck darstellt. die Ressource. Das folgende Beispiel ist eine LINQ-Abfrage, die der vorherigen <xref:System.Data.Services.Client.DataServiceQuery%601>-Abfrage entspricht, die `Orders` mit Frachtkosten von mehr als $30 zurückgibt und die Ergebnisse nach den Frachtkosten sortiert:  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionslinqspecific)]  
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionslinqspecific)]  
  
 Diese LINQ-Abfrage wird in der folgenden Abfrage-URI, der in der Northwind-basierten ausgeführt wird, übersetzt [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) Datendienst:  
  
```  
http://localhost:12345/Northwind.svc/Orders?Orderby=ShippedDate&?filter=Freight gt 30  
```  
  
> [!NOTE]
>  Die Gruppe von Abfragen, die in der LINQ-Syntax ausgedrückt werden kann, ist umfangreicher als bei der von Datendiensten verwendeten REST-basierten (Representational State Transfer) URI-Syntax. Wenn die Abfrage keinem URI im Zieldatendienst zugeordnet werden kann, wird eine Ausnahme vom Typ <xref:System.NotSupportedException> ausgelöst.  
  
 Weitere Informationen finden Sie unter [Überlegungen zu LINQ](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md).  
  
## <a name="adding-query-options"></a>Hinzufügen von Abfrageoptionen  
 Datendienstabfragen unterstützen alle Abfrageoptionen, die in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verfügbar sind. Sie rufen die <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode auf, um einer <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanz Abfrageoptionen hinzuzufügen. <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> gibt eine neue <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanz zurück, die der ursprünglichen Abfrage entspricht, aber die neuen Abfrageoptionen enthält. Wenn die folgende Abfrage ausgeführt wird, gibt sie `Orders`-Objekte zurück, die nach dem `Freight`-Wert gefiltert und in absteigender Reihenfolge nach dem Wert von `OrderID` sortiert werden:  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionsspecific)]  
 [!code-vb[Astoria Northwind Client#AddQueryOptionsSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionsspecific)]  
  
 Sie können die `$orderby`-Abfrageoption verwenden, um eine Abfrage auf der Grundlage einer einzelnen Eigenschaft sowohl zu sortieren als auch zu filtern, wie im folgenden Beispiel, in dem die zurückgegebenen `Orders`-Objekte anhand des Werts der `Freight`-Eigenschaft gefiltert und sortiert werden:  
  
 [!code-csharp[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#orderwithfilter)]
 [!code-vb[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#orderwithfilter)]  
  
 Sie können die <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode aufrufen, um nacheinander komplexe Abfrageausdrücke zu erstellen. Weitere Informationen finden Sie unter [wie: Hinzufügen von Abfrageoptionen zu einer Datendienstabfrage](../../../../docs/framework/data/wcf/how-to-add-query-options-to-a-data-service-query-wcf-data-services.md).  
  
 Abfrageoptionen sind eine weitere Möglichkeit, die syntaktischen Komponenten einer LINQ-Abfrage auszudrücken. Weitere Informationen finden Sie unter [Überlegungen zu LINQ](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md).  
  
> [!NOTE]
>  Die `$select`-Abfrageoption kann einem Abfrage-URI nicht mit der <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode hinzugefügt werden. Es wird empfohlen, die <xref:System.Linq.Enumerable.Select%2A>-LINQ-Methode zu verwenden, damit der Client die `$select`-Abfrageoption im Anforderungs-URI generiert.  
  
<a name="executingQueries"></a>   
## <a name="client-versus-server-execution"></a>Clientausführung und Serverausführung  
 Der Client führt eine Abfrage in zwei Teilen aus. Nach Möglichkeit werden Ausdrücke in einer Abfrage zuerst auf dem Client ausgewertet, und anschließend wird eine URI-basierte Abfrage generiert und zur Auswertung anhand der Daten im Dienst an den Datendienst gesendet. Betrachten Sie die folgende LINQ-Abfrage:  
  
 [!code-csharp[Astoria Northwind Client#LinqQueryClientEvalSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqqueryclientevalspecific)]  
 [!code-vb[Astoria Northwind Client#LinqQueryClientEvalSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqqueryclientevalspecific)]  
  
 In diesem Beispiel wird der Ausdruck `(basePrice – (basePrice * discount))` auf dem Client ausgewertet. Der tatsächliche Abfrage-URI `http://localhost:12345/northwind.svc/Products()?$filter=(UnitPrice gt 90.00M) and substringof('bike',ProductName)`, der an den Datendienst gesendet wird, enthält daher den bereits berechneten Dezimalwert `90` in der Filterklausel. Die anderen Teile des Filterausdrucks, einschließlich des untergeordneten Zeichenfolgenausdrucks, werden vom Datendienst ausgewertet. Auf dem Client ausgewertete Ausdrücke entsprechen der CLR-Semantik (Common Language Runtime), während an den Datendienst gesendete Ausdrücke auf der Datendienstimplementierung des [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Protokolls basieren. Diese getrennte Auswertung kann in bestimmten Szenarien zu unerwarteten Ergebnissen führen, z. B. wenn sowohl der Client als auch der Dienst zeitbasierte Auswertungen in unterschiedlichen Zeitzonen ausführen.  
  
## <a name="query-responses"></a>Abfrageantworten  
 Wenn die Abfrage <xref:System.Data.Services.Client.DataServiceQuery%601> ausgeführt wird, gibt sie eine <xref:System.Collections.Generic.IEnumerable%601> vom angeforderten Entitätstyp zurück. Dieses Abfrageergebnis kann, wie im folgenden Beispiel, in ein <xref:System.Data.Services.Client.QueryOperationResponse%601>-Objekt umgewandelt werden:  
  
 [!code-csharp[Astoria Northwind Client#GetResponseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getresponsespecific)]
 [!code-vb[Astoria Northwind Client#GetResponseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getresponsespecific)]  
  
 Die Entitätstypinstanzen, die Entitäten im Datendienst darstellen, werden von einem Prozess mit dem Namen Objektmaterialisierung auf dem Client erstellt. Weitere Informationen finden Sie unter [Objektmaterialisierung](../../../../docs/framework/data/wcf/object-materialization-wcf-data-services.md). Das <xref:System.Data.Services.Client.QueryOperationResponse%601>-Objekt implementiert <xref:System.Collections.Generic.IEnumerable%601>, um Zugriff auf die Ergebnisse der Abfrage zu bieten.  
  
 Der <xref:System.Data.Services.Client.QueryOperationResponse%601> verfügt auch über die folgenden Member, die es Ihnen ermöglichen, auf weitere Informationen zu einem Abfrageergebnis zuzugreifen:  
  
-   <xref:System.Data.Services.Client.OperationResponse.Error%2A>- ruft einen vom Vorgang ausgelösten Fehler ab, sofern ein Fehler aufgetreten sind.  
  
-   <xref:System.Data.Services.Client.OperationResponse.Headers%2A>- enthält die Sammlung der mit der Abfrageantwort verbundenen HTTP-Antwortheader.  
  
-   <xref:System.Data.Services.Client.QueryOperationResponse.Query%2A> - ruft die ursprüngliche <xref:System.Data.Services.Client.DataServiceQuery%601>-Abfrage ab, welche die <xref:System.Data.Services.Client.QueryOperationResponse%601>-Antwort erzeugte.  
  
-   <xref:System.Data.Services.Client.OperationResponse.StatusCode%2A> - ruft den HTTP-Antwortcode für die Abfrageantwort ab.  
  
-   <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A>- ruft die Gesamtzahl der Entitäten ab, die in der Entitätenmenge enthalten war, wenn die <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A>-Methode für <xref:System.Data.Services.Client.DataServiceQuery%601> aufgerufen wurde.  
  
-   <xref:System.Data.Services.Client.QueryOperationResponse.GetContinuation%2A>- gibt ein <xref:System.Data.Services.Client.DataServiceQueryContinuation>-Objekt zurück, das den URI der nächsten Seite mit Ergebnissen enthält.  
  
 Standardmäßig [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] gibt nur Daten, die explizit von der Abfrage-URI ausgewählt ist. Dies gibt Ihnen die Möglichkeit, bei Bedarf weitere Daten explizit vom Datendienst zu laden. Jedes Mal, wenn Daten explizit aus dem Datendienst geladen werden, wird eine Anforderung an den Datendienst gesendet. Zu den Daten, die explizit geladen werden können, gehören verknüpfte Entitäten, ausgelagerte Antwortdaten und Binärdatenströme.  
  
> [!NOTE]
>  Da ein Datendienst möglicherweise eine ausgelagerte Antwort zurückgibt, empfiehlt es sich, dass die Anwendung das Programmiermuster zur Behandlung ausgelagerter Datendienstantworten verwendet. Weitere Informationen finden Sie unter [Content verzögerte Laden von](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 Die von einer Abfrage zurückgegebene Datenmenge kann auch durch die Angabe reduziert werden, dass nur bestimmte Eigenschaften einer Entität in der Antwort zurückgegeben werden. Weitere Informationen finden Sie unter [Abfrageprojektionen](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md).  
  
## <a name="getting-a-count-of-the-total-number-of-entities-in-the-set"></a>Abrufen der Gesamtanzahl der in der Menge enthaltenen Entitäten  
 In einigen Szenarien ist es hilfreich zu wissen, wie viele Entitäten in einer Entitätenmenge insgesamt enthalten sind, statt nur die von der Abfrage zurückgegebene Anzahl zu kennen. Rufen Sie die <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A>-Methode für <xref:System.Data.Services.Client.DataServiceQuery%601> auf, um anzufordern, dass die Gesamtanzahl von Entitäten dieser Entitätenmenge in das Abfrageergebnis aufgenommen wird. In diesem Fall gibt die <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A>-Eigenschaft der zurückgegebenen <xref:System.Data.Services.Client.QueryOperationResponse%601>-Instanz die Gesamtzahl der in der Menge enthaltenen Entitäten zurück.  
  
 Sie können auch nur die Gesamtanzahl der Entitäten in der Menge als <xref:System.Int32>-Wert oder <xref:System.Int64>-Wert abrufen, indem Sie <xref:System.Linq.Enumerable.Count%2A>-Methode bzw. die <xref:System.Linq.Enumerable.LongCount%2A>-Methode aufrufen. Wenn diese Methoden aufgerufen werden, wird kein <xref:System.Data.Services.Client.QueryOperationResponse%601>-Objekt zurückgegeben. Es wird nur die Anzahl zurückgegeben. Weitere Informationen finden Sie unter [wie: Bestimmen der Anzahl von Entitäten von einer Abfrage zurückgegebenen](../../../../docs/framework/data/wcf/number-of-entities-returned-by-a-query-wcf.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Abfrageprojektionen](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md)  
  
 [Objektmaterialisierung](../../../../docs/framework/data/wcf/object-materialization-wcf-data-services.md)  
  
 [Überlegungen zu LINQ](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)  
  
 [Vorgehensweise: Ausführen von Datendienstabfragen](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
 [Vorgehensweise: Hinzufügen von Abfrageoptionen zu einer Datendienstabfrage](../../../../docs/framework/data/wcf/how-to-add-query-options-to-a-data-service-query-wcf-data-services.md)  
  
 [Vorgehensweise: Bestimmen der Anzahl von Entitäten, die von einer Abfrage zurückgegeben werden](../../../../docs/framework/data/wcf/number-of-entities-returned-by-a-query-wcf.md)  
  
 [Vorgehensweise: Angeben von Clientanmeldeinformationen für eine Datendienstanforderung](../../../../docs/framework/data/wcf/specify-client-creds-for-a-data-service-request-wcf.md)  
  
 [Vorgehensweise: Festlegen von Headern in der Clientanforderung](../../../../docs/framework/data/wcf/how-to-set-headers-in-the-client-request-wcf-data-services.md)  
  
 [Vorgehensweise: Projizieren von Abfrageergebnissen](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md)  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
