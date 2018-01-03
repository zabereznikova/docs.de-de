---
title: "Überlegungen zu LINQ (WCF Data Services)"
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
- WCF Data Services, LINQ
- querying the data service [WCF Data Services]
- WCF Data Services, querying
ms.assetid: cc4ec9e9-348f-42a6-a78e-1cd40e370656
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f6742294c570501b20646c89455c7856f393f7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="linq-considerations-wcf-data-services"></a>Überlegungen zu LINQ (WCF Data Services)
Dieses Thema enthält Informationen zum Erstellen und Ausführen von LINQ-Abfragen bei der Verwendung des [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clients und zu den Einschränkungen, die gelten, wenn Sie einen Datendienst, der [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] implementiert, mithilfe von LINQ abfragen. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Verfassen und Ausführen von Abfragen für eine [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-basierten Datendienst, finden Sie unter [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
## <a name="composing-linq-queries"></a>Verfassen von LINQ-Abfragen  
 LINQ ermöglicht es Ihnen, Abfragen für eine Auflistung von Objekten zu verfassen, die <xref:System.Collections.Generic.IEnumerable%601> implementiert. Sowohl die **Hinzufügen eines Dienstverweises** im Dialogfeld [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] und das Tool DataSvcUtil.exe zum Generieren einer Darstellung eines ein [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Diensts als entitätscontainerklasse, die von erben <xref:System.Data.Services.Client.DataServiceContext>, als auch Objekte, die die zurückgegebenen Entitäten im Feeds darstellen. Diese Tools generieren auch Eigenschaften der Entitätscontainerklasse für die Auflistungen, die als Feeds vom Dienst verfügbar gemacht werden. Jede Eigenschaft der Klasse, die den Datendienst kapselt, gibt eine <xref:System.Data.Services.Client.DataServiceQuery%601> zurück. Da die <xref:System.Data.Services.Client.DataServiceQuery%601>-Klasse die von LINQ definierte <xref:System.Linq.IQueryable%601>-Schnittstelle implementiert, können Sie eine LINQ-Abfrage für vom Datendienst verfügbar gemachte Feeds verfassen. Diese Abfrage wird von der Clientbibliothek in einen Abfrageanforderungs-URI übersetzt, der bei der Ausführung an den Datendienst gesendet wird.  
  
> [!IMPORTANT]
>  In der LINQ-Syntax können mehr Abfragen ausgedrückt werden als in der von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Datendiensten verwendeten URI-Syntax. Wenn die Abfrage keinem URI im Zieldatendienst zugeordnet werden kann, wird eine Ausnahme vom Typ <xref:System.NotSupportedException> ausgelöst. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]die [nicht unterstützte LINQ-Methoden](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md#unsupportedMethods) in diesem Thema.  
  
 Das folgende Beispiel zeigt eine LINQ-Abfrage, die `Orders` mit Frachtkosten über $30 zurückgibt und die Ergebnisse nach dem Lieferdatum sortiert (beginnend mit dem aktuellsten Lieferdatum):  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionslinqspecific)]      
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionslinqspecific)]    
  
 Diese LINQ-Abfrage wird in der folgenden Abfrage-URI, der in der Northwind-basierten ausgeführt wird, übersetzt [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) Datendienst:  
  
```  
http://localhost:12345/Northwind.svc/Orders?Orderby=ShippedDate&?filter=Freight gt 30  
```  
  
 Weitere allgemeine Informationen über LINQ finden Sie unter [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).  
  
 Mit LINQ können Sie Abfragen sowohl unter Verwendung der im obigen Beispiel gezeigten sprachspezifischen deklarativen Abfragesyntax als auch mit einem als Standardabfrageoperatoren bezeichneten Satz von Abfragemethoden verfassen. Eine Abfrage, die dem obigen Beispiel funktional entspricht, kann wie im folgenden Beispiel dargestellt auch nur mithilfe der methodenbasierten Syntax verfasst werden:  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionslinqexpressionspecific)]      
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionslinqexpressionspecific)]    
  
 Der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Client kann beide Abfragearten in einen Abfrage-URI übersetzen, und Sie können eine LINQ-Abfrage erweitern, indem Sie Abfragemethoden an einen Abfrageausdruck anfügen. Wenn Sie LINQ-Abfragen verfassen, indem Sie Methodensyntax an einen Abfrageausdruck oder eine <xref:System.Data.Services.Client.DataServiceQuery%601> anfügen, werden die Vorgänge dem Abfrage-URI in der Reihenfolge hinzugefügt, in der Methoden aufgerufen werden. Dies hat die gleiche Funktion wie das Aufrufen der <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode zum Hinzufügen der einzelnen Abfrageoptionen zum Abfrage-URI.  
  
## <a name="executing-linq-queries"></a>Ausführen von LINQ-Abfragen  
 Wenn bestimmte LINQ-Abfragemethoden wie <xref:System.Linq.Enumerable.First%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> oder <xref:System.Linq.Enumerable.Single%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> an die Abfrage angefügt werden, führt dies dazu, dass die Abfrage ausgeführt wird. Eine Abfrage wird auch ausgeführt, wenn Ergebnisse implizit aufgezählt werden, z. B. während einer `foreach`-Schleife oder wenn die Abfrage einer `List`-Auflistung zugewiesen wird. Weitere Informationen finden Sie unter [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Der Client führt eine LINQ-Abfrage in zwei Teilen aus. Nach Möglichkeit werden LINQ-Ausdrücke in einer Abfrage zuerst auf dem Client ausgewertet, und anschließend wird eine URI-basierte Abfrage generiert und zur Auswertung anhand der Daten im Dienst an den Datendienst gesendet. Weitere Informationen finden Sie im Abschnitt [Clientausführung und Serverausführung](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md#executingQueries) in [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Wenn eine LINQ-Abfrage nicht in einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-kompatiblen Abfrage-URI übersetzt werden kann, wird beim Ausführen der Abfrage eine Ausnahme ausgelöst. Weitere Informationen finden Sie unter [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
## <a name="linq-query-examples"></a>LINQ-Abfragebeispiele  
 Die Beispiele in den folgenden Abschnitten veranschaulichen die Arten von LINQ-Abfragen, die für einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Dienst ausgeführt werden können.  
  
<a name="filtering"></a>   
### <a name="filtering"></a>Filtern  
 In den LINQ-Abfragebeispielen in diesem Abschnitt werden Daten in dem vom Dienst zurückgegebenen Feed gefiltert.  
  
 Die folgenden Beispiele zeigen funktional gleichwertige Abfragen, durch die zurückgegebene `Orders`-Entitäten so gefiltert werden, dass nur Aufträge mit Frachtkosten über $30 zurückgegeben werden:  
  
-   Verwendung der LINQ-Abfragesyntax:  
  
[!code-csharp[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqwhereclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqwhereclausespecific)]     
  
-   Verwendung von LINQ-Abfragemethoden:  
  
[!code-csharp[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqwheremethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqwheremethodspecific)]       
  
-   `$filter`-Option für die URI-Abfragezeichenfolge:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#explicitquerywheremethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#explicitquerywheremethodspecific)]       
  
 Die obigen Beispiele werden alle in den Abfrage-URI übersetzt: `http://localhost:12345/northwind.svc/Orders()?$filter=Freight gt 30M`.  
  
<a name="sorting"></a>   
### <a name="sorting"></a>Sortieren  
 Die folgenden Beispiele zeigen funktional gleichwertige Abfragen, durch die zurückgegebene Daten in absteigender Reihenfolge nach dem Firmennamen und der Postleitzahl sortiert werden:  
  
-   Verwendung der LINQ-Abfragesyntax:  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqorderbyclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqorderbyclausespecific)]        
  
-   Verwendung von LINQ-Abfragemethoden:  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqorderbymethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqorderbymethodspecific)]        
  
-   `$orderby`-Option für die URI-Abfragezeichenfolge:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#explicitqueryorderbymethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#explicitqueryorderbymethodspecific)]         
  
 Die obigen Beispiele werden alle in den Abfrage-URI übersetzt: `http://localhost:12345/northwind.svc/Customers()?$orderby=CompanyName,PostalCode desc`.  
  
<a name="projection"></a>   
### <a name="projection"></a>Projection  
 Die folgenden Beispiele zeigen funktional gleichwertige Abfragen, durch die zurückgegebene Daten in den enger gefassten `CustomerAddress`-Typ projiziert werden:  
  
-   Verwendung der LINQ-Abfragesyntax:  
  
[!code-csharp[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqselectclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqselectclausespecific)]         
  
-   Verwendung von LINQ-Abfragemethoden:  
  
[!code-csharp[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqselectmethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqselectmethodspecific)]         
 
  
> [!NOTE]
>  Die `$select`-Abfrageoption kann einem Abfrage-URI nicht mit der <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode hinzugefügt werden. Es wird empfohlen, die <xref:System.Linq.Enumerable.Select%2A>-LINQ-Methode zu verwenden, damit der Client die `$select`-Abfrageoption im Anforderungs-URI generiert.  
  
 Die obigen Beispiele werden beide in den Abfrage-URI übersetzt: `"http://localhost:12345/northwind.svc/Customers()?$filter=Country eq 'GerGerm'&$select=CustomerID,Address,City,Region,PostalCode,Country"`.  
  
<a name="paging"></a>   
### <a name="client-paging"></a>Clientpaging  
 Die folgenden Beispiele zeigen funktional gleichwertige Abfragen, durch die eine Seite sortierter Order-Entitäten angefordert wird, die 25 Aufträge enthält und auf der die ersten 50 Aufträge übersprungen werden:  
  
-   Anwendung von Abfragemethoden auf eine LINQ-Abfrage:  
  
[!code-csharp[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqskiptakemethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqskiptakemethodspecific)]     
  
-   `$skip`- und `$top`-Optionen für die URI-Abfragezeichenfolge:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#explicitqueryskiptakemethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#explicitqueryskiptakemethodspecific)]     
  
 Die obigen Beispiele werden beide in den Abfrage-URI übersetzt: `http://localhost:12345/northwind.svc/Orders()?$orderby=OrderDate desc&$skip=50&$top=25`.  
  
<a name="expand"></a>   
### <a name="expand"></a>Erweitern  
 Beim Abfragen eines [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Datendiensts können Sie anfordern, dass mit der Zielentität der Abfrage verknüpfte Entitäten in den zurückgegebenen Feed eingeschlossen werden. Die <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>-Methode wird in der <xref:System.Data.Services.Client.DataServiceQuery%601> für die in der LINQ-Abfrage angegebene Entität aufgerufen, und der Name der verknüpften Entitätenmenge wird als `path`-Parameter angegeben. Weitere Informationen finden Sie unter [Content verzögerte Laden von](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 Die folgenden Beispiele zeigen funktional gleichwertige Möglichkeiten zur Verwendung der <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>-Methode in einer Abfrage:  
  
-   In der LINQ-Abfragesyntax:  
  
[!code-csharp[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqqueryexpandspecific)]      
[!code-vb[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqqueryexpandspecific)]  
  
-   Mit LINQ-Abfragemethoden:  

[!code-csharp[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqqueryexpandmethodspecific)]       
[!code-vb[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqqueryexpandmethodspecific)]       
  
  
 Die obigen Beispiele werden beide in den Abfrage-URI übersetzt: `http://localhost:12345/northwind.svc/Orders()?$filter=CustomerID eq 'ALFKI'&$expand=Order_Details`.  
  
<a name="unsupportedMethods"></a>   
## <a name="unsupported-linq-methods"></a>Nicht unterstützte LINQ-Methoden  
 Die folgende Tabelle enthält die Klassen von LINQ-Methoden, die nicht unterstützt werden und nicht in eine Abfrage für einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Dienst eingeschlossen werden können:  
  
|Vorgangstyp|Nicht unterstützte Methode|  
|--------------------|------------------------|  
|Mengenoperatoren|Alle Mengenoperatoren werden nicht für eine <xref:System.Data.Services.Client.DataServiceQuery%601> unterstützt. Dazu zählen folgende Operatoren:<br /><br /> -   <xref:System.Linq.Enumerable.All%2A><br />-   <xref:System.Linq.Enumerable.Any%2A><br />-   <xref:System.Linq.Enumerable.Concat%2A><br />-   <xref:System.Linq.Enumerable.DefaultIfEmpty%2A><br />-   <xref:System.Linq.Enumerable.Distinct%2A><br />-   <xref:System.Linq.Enumerable.Except%2A><br />-   <xref:System.Linq.Enumerable.Intersect%2A><br />-   <xref:System.Linq.Enumerable.Union%2A><br />-   <xref:System.Linq.Enumerable.Zip%2A>|  
|Sortierungsoperatoren|Die folgenden Sortierungsoperatoren, die <xref:System.Collections.Generic.IComparer%601> erfordern, werden für eine <xref:System.Data.Services.Client.DataServiceQuery%601> nicht unterstützt:<br /><br /> -   <xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29>|  
|Projektions- und Filterungsoperatoren|Die folgenden Projektions- und Filterungsoperatoren, die ein Positionsargument akzeptieren, werden für eine <xref:System.Data.Services.Client.DataServiceQuery%601> nicht unterstützt:<br /><br /> -   <xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2C%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Where%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Boolean%7D%29>|  
|Gruppierungsoperatoren|Alle Gruppierungsoperatoren werden nicht für eine <xref:System.Data.Services.Client.DataServiceQuery%601> unterstützt. Dazu zählen folgende Operatoren:<br /><br /> -   <xref:System.Linq.Enumerable.GroupBy%2A><br />-   <xref:System.Linq.Enumerable.GroupJoin%2A><br /><br /> Gruppierungsvorgänge müssen auf dem Client ausgeführt werden.|  
|Aggregatoperatoren|Alle Aggregatoperatoren werden nicht für eine <xref:System.Data.Services.Client.DataServiceQuery%601> unterstützt. Dazu zählen folgende Operatoren:<br /><br /> -   <xref:System.Linq.Enumerable.Aggregate%2A><br />-   <xref:System.Linq.Enumerable.Average%2A><br />-   <xref:System.Linq.Enumerable.Count%2A><br />-   <xref:System.Linq.Enumerable.LongCount%2A><br />-   <xref:System.Linq.Enumerable.Max%2A><br />-   <xref:System.Linq.Enumerable.Min%2A><br />-   <xref:System.Linq.Enumerable.Sum%2A><br /><br /> Aggregatvorgänge müssen entweder auf dem Client ausgeführt oder von einem Dienstvorgang gekapselt werden.|  
|Pagingoperatoren|Die folgenden Pagingoperatoren werden nicht für eine <xref:System.Data.Services.Client.DataServiceQuery%601> unterstützt:<br /><br /> -   <xref:System.Linq.Enumerable.ElementAt%2A><br />-   <xref:System.Linq.Enumerable.Last%2A><br />-   <xref:System.Linq.Enumerable.LastOrDefault%2A><br />-   <xref:System.Linq.Enumerable.SkipWhile%2A><br />-   <xref:System.Linq.Enumerable.TakeWhile%2A>**Hinweis:** pagingoperatoren, die auf eine leere Sequenz ausgeführt werden, die null zurückgeben.|  
|Andere Operatoren|Die folgenden anderen Operatoren werden nicht für eine <xref:System.Data.Services.Client.DataServiceQuery%601> unterstützt:<br /><br /> 1.  <xref:System.Linq.Enumerable.Empty%2A><br />2.  <xref:System.Linq.Enumerable.Range%2A><br />3.  <xref:System.Linq.Enumerable.Repeat%2A><br />4.  <xref:System.Linq.Enumerable.ToDictionary%2A><br />5.  <xref:System.Linq.Enumerable.ToLookup%2A>|  
  
<a name="supportedExpressions"></a>   
## <a name="supported-expression-functions"></a>Unterstützte Ausdrucksfunktionen  
 Die folgenden CLR-Methoden und -Eigenschaften (Common Language Runtime) werden unterstützt, da sie zum Einschließen in den Anforderungs-URI für einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Dienst in einen Abfrageausdruck übersetzt werden können:  
  
|<xref:System.String>-Member|Unterstützte [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Funktion|  
|-----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.String.Concat%28System.String%2CSystem.String%29>|`string concat(string p0, string p1)`|  
|<xref:System.String.Contains%28System.String%29>|`bool substringof(string p0, string p1)`|  
|<xref:System.String.EndsWith%28System.String%29>|`bool endswith(string p0, string p1)`|  
|<xref:System.String.IndexOf%28System.String%2CSystem.Int32%29>|`int indexof(string p0, string p1)`|  
|<xref:System.String.Length>|`int length(string p0)`|  
|<xref:System.String.Replace%28System.String%2CSystem.String%29>|`string replace(string p0, string find, string replace)`|  
|<xref:System.String.Substring%28System.Int32%29>|`string substring(string p0, int pos)`|  
|<xref:System.String.Substring%28System.Int32%2CSystem.Int32%29>|`string substring(string p0, int pos, int length)`|  
|<xref:System.String.ToLower>|`string tolower(string p0)`|  
|<xref:System.String.ToUpper>|`string toupper(string p0)`|  
|<xref:System.String.Trim>|`string trim(string p0)`|  
  
|<xref:System.DateTime>Member<sup>1</sup>|Unterstützte [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Funktion|  
|-------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Day>|`int day(DateTime p0)`|  
|<xref:System.DateTime.Hour>|`int hour(DateTime p0)`|  
|<xref:System.DateTime.Minute>|`int minute(DateTime p0)`|  
|<xref:System.DateTime.Month>|`int month(DateTime p0)`|  
|<xref:System.DateTime.Second>|`int second(DateTime p0)`|  
|<xref:System.DateTime.Year>|`int year(DateTime p0)`|  
  
 <sup>1</sup>das entsprechende Datum und die Eigenschaften des <xref:Microsoft.VisualBasic.DateAndTime?displayProperty=nameWithType>, als auch die <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> Methode in Visual Basic werden ebenfalls unterstützt.  
  
|<xref:System.Math>-Member|Unterstützte [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Funktion|  
|---------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Math.Ceiling%28System.Decimal%29>|`decimal ceiling(decimal p0)`|  
|<xref:System.Math.Ceiling%28System.Double%29>|`double ceiling(double p0)`|  
|<xref:System.Math.Floor%28System.Decimal%29>|`decimal floor(decimal p0)`|  
|<xref:System.Math.Floor%28System.Double%29>|`double floor(double p0)`|  
|<xref:System.Math.Round%28System.Decimal%29>|`decimal round(decimal p0)`|  
|<xref:System.Math.Round%28System.Double%29>|`double round(double p0)`|  
  
|<xref:System.Linq.Expressions.Expression>-Member|Unterstützte [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Funktion|  
|---------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Linq.Expressions.Expression.TypeIs%28System.Linq.Expressions.Expression%2CSystem.Type%29>|`bool isof(type p0)`|  
  
 Der Client kann möglicherweise auch weitere CLR-Funktionen auf dem Client auswerten. Für einen Ausdruck, der nicht auf dem Client ausgewertet und nicht in einen gültigen URI für die Auswertung auf dem Server übersetzt werden kann, wird eine <xref:System.NotSupportedException> ausgelöst.  
  
## <a name="see-also"></a>Siehe auch  
 [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 [Abfrageprojektionen](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md)  
 [Objektmaterialisierung](../../../../docs/framework/data/wcf/object-materialization-wcf-data-services.md)  
 [OData: URI-Konventionen](http://go.microsoft.com/fwlink/?LinkID=185564)
