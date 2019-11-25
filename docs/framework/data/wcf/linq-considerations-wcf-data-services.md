---
title: Überlegungen zu LINQ (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ
- querying the data service [WCF Data Services]
- WCF Data Services, querying
ms.assetid: cc4ec9e9-348f-42a6-a78e-1cd40e370656
ms.openlocfilehash: 4792850221da69be79b064313792dcd7ad226788
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975217"
---
# <a name="linq-considerations-wcf-data-services"></a>Überlegungen zu LINQ (WCF Data Services)
Dieses Thema enthält Informationen über die Art und Weise, in der LINQ-Abfragen zusammengestellt und ausgeführt werden, wenn Sie den [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Client verwenden und Einschränkungen bei der Verwendung von LINQ zum Abfragen eines Daten Dienstanbieter, der die Open Data Protocol (odata) implementiert. Weitere Informationen zum Erstellen und Ausführen von Abfragen für einen odata-basierten Datendienst finden Sie unter [Abfragen des Daten Dienstanbieter](querying-the-data-service-wcf-data-services.md).  
  
## <a name="composing-linq-queries"></a>Verfassen von LINQ-Abfragen  
 LINQ ermöglicht es Ihnen, Abfragen für eine Auflistung von Objekten zu verfassen, die <xref:System.Collections.Generic.IEnumerable%601> implementiert. Sowohl das Dialogfeld **Dienstverweis hinzufügen** in Visual Studio als auch das Tool DataSvcUtil. exe werden verwendet, um eine Darstellung eines odata-diensdienstanbieter als Entitäts Container Klasse zu generieren, die von <xref:System.Data.Services.Client.DataServiceContext>erbt, sowie von Objekten, die die in Feeds zurückgegebenen Entitäten darstellen. Diese Tools generieren auch Eigenschaften der Entitätscontainerklasse für die Auflistungen, die als Feeds vom Dienst verfügbar gemacht werden. Jede Eigenschaft der Klasse, die den Datendienst kapselt, gibt eine <xref:System.Data.Services.Client.DataServiceQuery%601> zurück. Da die <xref:System.Data.Services.Client.DataServiceQuery%601>-Klasse die von LINQ definierte <xref:System.Linq.IQueryable%601>-Schnittstelle implementiert, können Sie eine LINQ-Abfrage für vom Datendienst verfügbar gemachte Feeds verfassen. Diese Abfrage wird von der Clientbibliothek in einen Abfrageanforderungs-URI übersetzt, der bei der Ausführung an den Datendienst gesendet wird.  
  
> [!IMPORTANT]
> Der Satz von Abfragen, der in der LINQ-Syntax ausgedrückt werden kann, ist breiter als der Satz von Abfragen, der in der von odata Data Services verwendeten URI-Syntax aktiviert ist. Wenn die Abfrage keinem URI im Zieldatendienst zugeordnet werden kann, wird eine Ausnahme vom Typ <xref:System.NotSupportedException> ausgelöst. Weitere Informationen finden Sie unter den [nicht unterstützten LINQ-Methoden](linq-considerations-wcf-data-services.md#unsupportedMethods) in diesem Thema.  
  
 Das folgende Beispiel zeigt eine LINQ-Abfrage, die `Orders` mit Frachtkosten über $30 zurückgibt und die Ergebnisse nach dem Lieferdatum sortiert (beginnend mit dem aktuellsten Lieferdatum):  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqspecific)]      
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqspecific)]    
  
 Diese LINQ-Abfrage wird in den folgenden Abfrage-URI übersetzt, der für den auf Northwind basierenden [Schnellstart](quickstart-wcf-data-services.md) -Datendienst ausgeführt wird:  
  
```http
http://localhost:12345/Northwind.svc/Orders?Orderby=ShippedDate&?filter=Freight gt 30  
```  
  
 Weitere allgemeine Informationen zu LINQ finden Sie unter [Language-Integrated Query (LINQ)- C# ](../../../csharp/programming-guide/concepts/linq/index.md) oder [Language-Integrated Query (LINQ)-Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md).  
  
 Mit LINQ können Sie Abfragen sowohl unter Verwendung der im obigen Beispiel gezeigten sprachspezifischen deklarativen Abfragesyntax als auch mit einem als Standardabfrageoperatoren bezeichneten Satz von Abfragemethoden verfassen. Eine Abfrage, die dem obigen Beispiel funktional entspricht, kann wie im folgenden Beispiel dargestellt auch nur mithilfe der methodenbasierten Syntax verfasst werden:  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqexpressionspecific)]      
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqexpressionspecific)]    
  
 Der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Client kann beide Abfragearten in einen Abfrage-URI übersetzen, und Sie können eine LINQ-Abfrage erweitern, indem Sie Abfragemethoden an einen Abfrageausdruck anfügen. Wenn Sie LINQ-Abfragen verfassen, indem Sie Methodensyntax an einen Abfrageausdruck oder eine <xref:System.Data.Services.Client.DataServiceQuery%601> anfügen, werden die Vorgänge dem Abfrage-URI in der Reihenfolge hinzugefügt, in der Methoden aufgerufen werden. Dies hat die gleiche Funktion wie das Aufrufen der <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode zum Hinzufügen der einzelnen Abfrageoptionen zum Abfrage-URI.  
  
## <a name="executing-linq-queries"></a>Ausführen von LINQ-Abfragen  
 Wenn bestimmte LINQ-Abfragemethoden wie <xref:System.Linq.Enumerable.First%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> oder <xref:System.Linq.Enumerable.Single%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> an die Abfrage angefügt werden, führt dies dazu, dass die Abfrage ausgeführt wird. Eine Abfrage wird auch ausgeführt, wenn Ergebnisse implizit aufgezählt werden, z. B. während einer `foreach`-Schleife oder wenn die Abfrage einer `List`-Auflistung zugewiesen wird. Weitere Informationen finden Sie unter [Abfragen des Daten Dienstanbieter](querying-the-data-service-wcf-data-services.md).  
  
 Der Client führt eine LINQ-Abfrage in zwei Teilen aus. Nach Möglichkeit werden LINQ-Ausdrücke in einer Abfrage zuerst auf dem Client ausgewertet, und anschließend wird eine URI-basierte Abfrage generiert und zur Auswertung anhand der Daten im Dienst an den Datendienst gesendet. Weitere Informationen finden Sie im Abschnitt [Client im Vergleich zur Server Ausführung](querying-the-data-service-wcf-data-services.md#executingQueries) unter [Abfragen des Daten Dienstanbieter](querying-the-data-service-wcf-data-services.md).  
  
 Wenn eine LINQ-Abfrage nicht in einen odata-kompatiblen Abfrage-URI übersetzt werden kann, wird eine Ausnahme ausgelöst, wenn versucht wird, eine Ausführung auszuführen. Weitere Informationen finden Sie unter [Abfragen des Daten Dienstanbieter](querying-the-data-service-wcf-data-services.md).  
  
## <a name="linq-query-examples"></a>LINQ-Abfragebeispiele  
 In den Beispielen in den folgenden Abschnitten werden die Arten von LINQ-Abfragen veranschaulicht, die für einen odata-Dienst ausgeführt werden können.  
  
<a name="filtering"></a>   
### <a name="filtering"></a>Filtern  
 In den LINQ-Abfragebeispielen in diesem Abschnitt werden Daten in dem vom Dienst zurückgegebenen Feed gefiltert.  
  
 Die folgenden Beispiele zeigen funktional gleichwertige Abfragen, durch die zurückgegebene `Orders`-Entitäten so gefiltert werden, dass nur Aufträge mit Frachtkosten über $30 zurückgegeben werden:  
  
- Verwendung der LINQ-Abfragesyntax:  
  
[!code-csharp[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwhereclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwhereclausespecific)]     
  
- Verwendung von LINQ-Abfragemethoden:  
  
[!code-csharp[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwheremethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwheremethodspecific)]       
  
- `$filter`-Option für die URI-Abfragezeichenfolge:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitquerywheremethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitquerywheremethodspecific)]       
  
 Die obigen Beispiele werden alle in den Abfrage-URI übersetzt: `http://localhost:12345/northwind.svc/Orders()?$filter=Freight gt 30M`.  
  
<a name="sorting"></a>   
### <a name="sorting"></a>Sortieren  
 Die folgenden Beispiele zeigen funktional gleichwertige Abfragen, durch die zurückgegebene Daten in absteigender Reihenfolge nach dem Firmennamen und der Postleitzahl sortiert werden:  
  
- Verwendung der LINQ-Abfragesyntax:  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbyclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbyclausespecific)]        
  
- Verwendung von LINQ-Abfragemethoden:  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbymethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbymethodspecific)]        
  
- `$orderby`-Option für die URI-Abfragezeichenfolge:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryorderbymethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryorderbymethodspecific)]         
  
 Die obigen Beispiele werden alle in den Abfrage-URI übersetzt: `http://localhost:12345/northwind.svc/Customers()?$orderby=CompanyName,PostalCode desc`.  
  
<a name="projection"></a>   
### <a name="projection"></a>Projection  
 Die folgenden Beispiele zeigen funktional gleichwertige Abfragen, durch die zurückgegebene Daten in den enger gefassten `CustomerAddress`-Typ projiziert werden:  
  
- Verwendung der LINQ-Abfragesyntax:  
  
[!code-csharp[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectclausespecific)]         
  
- Verwendung von LINQ-Abfragemethoden:  
  
[!code-csharp[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectmethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectmethodspecific)]         

> [!NOTE]
> Die `$select`-Abfrageoption kann einem Abfrage-URI nicht mit der <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode hinzugefügt werden. Es wird empfohlen, die <xref:System.Linq.Enumerable.Select%2A>-LINQ-Methode zu verwenden, damit der Client die `$select`-Abfrageoption im Anforderungs-URI generiert.  
  
 Die obigen Beispiele werden beide in den Abfrage-URI übersetzt: `"http://localhost:12345/northwind.svc/Customers()?$filter=Country eq 'GerGerm'&$select=CustomerID,Address,City,Region,PostalCode,Country"`.  
  
<a name="paging"></a>   
### <a name="client-paging"></a>Clientpaging  
 Die folgenden Beispiele zeigen funktional gleichwertige Abfragen, durch die eine Seite sortierter Order-Entitäten angefordert wird, die 25 Aufträge enthält und auf der die ersten 50 Aufträge übersprungen werden:  
  
- Anwendung von Abfragemethoden auf eine LINQ-Abfrage:  
  
[!code-csharp[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqskiptakemethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqskiptakemethodspecific)]     
  
- `$skip`- und `$top`-Optionen für die URI-Abfragezeichenfolge:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryskiptakemethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryskiptakemethodspecific)]     
  
 Die obigen Beispiele werden beide in den Abfrage-URI übersetzt: `http://localhost:12345/northwind.svc/Orders()?$orderby=OrderDate desc&$skip=50&$top=25`.  
  
<a name="expand"></a>   
### <a name="expand"></a>Expand  
 Wenn Sie einen odata-Datendienst Abfragen, können Sie anfordern, dass Entitäten im Zusammenhang mit der Entität, die von der Abfrage betroffen ist, den zurückgegebenen Feed einschließen. Die <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>-Methode wird in der <xref:System.Data.Services.Client.DataServiceQuery%601> für die in der LINQ-Abfrage angegebene Entität aufgerufen, und der Name der verknüpften Entitätenmenge wird als `path`-Parameter angegeben. Weitere Informationen finden Sie unter [Laden von verzögertem Inhalt](loading-deferred-content-wcf-data-services.md).  
  
 Die folgenden Beispiele zeigen funktional gleichwertige Möglichkeiten zur Verwendung der <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>-Methode in einer Abfrage:  
  
- In der LINQ-Abfragesyntax:  
  
[!code-csharp[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandspecific)]      
[!code-vb[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandspecific)]  
  
- Mit LINQ-Abfragemethoden:  

[!code-csharp[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandmethodspecific)]       
[!code-vb[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandmethodspecific)]       

 Die obigen Beispiele werden beide in den Abfrage-URI übersetzt: `http://localhost:12345/northwind.svc/Orders()?$filter=CustomerID eq 'ALFKI'&$expand=Order_Details`.  
  
<a name="unsupportedMethods"></a>   
## <a name="unsupported-linq-methods"></a>Nicht unterstützte LINQ-Methoden  
 Die folgende Tabelle enthält die Klassen von LINQ-Methoden, die nicht unterstützt werden und nicht in einer Abfrage enthalten sein können, die für einen odata-Dienst ausgeführt wird:  
  
|Vorgangstyp|Nicht unterstützte Methode|  
|--------------------|------------------------|  
|Mengenoperatoren|Alle Mengenoperatoren werden nicht für eine <xref:System.Data.Services.Client.DataServiceQuery%601> unterstützt. Dazu zählen folgende Operatoren:<br /><br /> -   <xref:System.Linq.Enumerable.All%2A><br />-   <xref:System.Linq.Enumerable.Any%2A><br />-   <xref:System.Linq.Enumerable.Concat%2A><br />-   <xref:System.Linq.Enumerable.DefaultIfEmpty%2A><br />-   <xref:System.Linq.Enumerable.Distinct%2A><br />-   <xref:System.Linq.Enumerable.Except%2A><br />-   <xref:System.Linq.Enumerable.Intersect%2A><br />-   <xref:System.Linq.Enumerable.Union%2A><br />-   <xref:System.Linq.Enumerable.Zip%2A>|  
|Sortierungsoperatoren|Die folgenden Sortierungsoperatoren, die <xref:System.Collections.Generic.IComparer%601> erfordern, werden für eine <xref:System.Data.Services.Client.DataServiceQuery%601> nicht unterstützt:<br /><br /> -   <xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29>|  
|Projektions- und Filterungsoperatoren|Die folgenden Projektions- und Filterungsoperatoren, die ein Positionsargument akzeptieren, werden für eine <xref:System.Data.Services.Client.DataServiceQuery%601> nicht unterstützt:<br /><br /> -   <xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2C%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Where%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Boolean%7D%29>|  
|Gruppierungsoperatoren|Alle Gruppierungsoperatoren werden nicht für eine <xref:System.Data.Services.Client.DataServiceQuery%601> unterstützt. Dazu zählen folgende Operatoren:<br /><br /> -   <xref:System.Linq.Enumerable.GroupBy%2A><br />-   <xref:System.Linq.Enumerable.GroupJoin%2A><br /><br /> Gruppierungsvorgänge müssen auf dem Client ausgeführt werden.|  
|Aggregatoperatoren|Alle Aggregatoperatoren werden nicht für eine <xref:System.Data.Services.Client.DataServiceQuery%601> unterstützt. Dazu zählen folgende Operatoren:<br /><br /> -   <xref:System.Linq.Enumerable.Aggregate%2A><br />-   <xref:System.Linq.Enumerable.Average%2A><br />-   <xref:System.Linq.Enumerable.Count%2A><br />-   <xref:System.Linq.Enumerable.LongCount%2A><br />-   <xref:System.Linq.Enumerable.Max%2A><br />-   <xref:System.Linq.Enumerable.Min%2A><br />-   <xref:System.Linq.Enumerable.Sum%2A><br /><br /> Aggregatvorgänge müssen entweder auf dem Client ausgeführt oder von einem Dienstvorgang gekapselt werden.|  
|Pagingoperatoren|Die folgenden Pagingoperatoren werden nicht für eine <xref:System.Data.Services.Client.DataServiceQuery%601> unterstützt:<br /><br /> -   <xref:System.Linq.Enumerable.ElementAt%2A><br />-   <xref:System.Linq.Enumerable.Last%2A><br />-   <xref:System.Linq.Enumerable.LastOrDefault%2A><br />-   <xref:System.Linq.Enumerable.SkipWhile%2A><br />-   <xref:System.Linq.Enumerable.TakeWhile%2A> **Hinweis:** Paging-Operatoren, die für eine leere Sequenz ausgeführt werden, geben NULL zurück.|  
|Andere Operatoren|Die folgenden anderen Operatoren werden nicht für eine <xref:System.Data.Services.Client.DataServiceQuery%601> unterstützt:<br /><br /> 1. <xref:System.Linq.Enumerable.Empty%2A><br />2. <xref:System.Linq.Enumerable.Range%2A><br />3. <xref:System.Linq.Enumerable.Repeat%2A><br />4. <xref:System.Linq.Enumerable.ToDictionary%2A><br />5. <xref:System.Linq.Enumerable.ToLookup%2A>|  
  
<a name="supportedExpressions"></a>   
## <a name="supported-expression-functions"></a>Unterstützte Ausdrucksfunktionen  
 Die folgenden CLR (Common Language Runtime)-Methoden und-Eigenschaften werden unterstützt, da Sie in einen Abfrage Ausdruck konvertiert werden können, um Sie in den Anforderungs-URI für einen odata-Dienst einzubeziehen:  
  
|<xref:System.String>-Member|Unterstützte odata-Funktion|  
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
  
|<xref:System.DateTime> Mitglied<sup>1</sup>|Unterstützte odata-Funktion|  
|-------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Day>|`int day(DateTime p0)`|  
|<xref:System.DateTime.Hour>|`int hour(DateTime p0)`|  
|<xref:System.DateTime.Minute>|`int minute(DateTime p0)`|  
|<xref:System.DateTime.Month>|`int month(DateTime p0)`|  
|<xref:System.DateTime.Second>|`int second(DateTime p0)`|  
|<xref:System.DateTime.Year>|`int year(DateTime p0)`|  
  
 <sup>1</sup> Die entsprechenden Datums-und Uhrzeit Eigenschaften von <xref:Microsoft.VisualBasic.DateAndTime?displayProperty=nameWithType>sowie die <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>-Methode in Visual Basic werden ebenfalls unterstützt.  
  
|<xref:System.Math>-Member|Unterstützte odata-Funktion|  
|---------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Math.Ceiling%28System.Decimal%29>|`decimal ceiling(decimal p0)`|  
|<xref:System.Math.Ceiling%28System.Double%29>|`double ceiling(double p0)`|  
|<xref:System.Math.Floor%28System.Decimal%29>|`decimal floor(decimal p0)`|  
|<xref:System.Math.Floor%28System.Double%29>|`double floor(double p0)`|  
|<xref:System.Math.Round%28System.Decimal%29>|`decimal round(decimal p0)`|  
|<xref:System.Math.Round%28System.Double%29>|`double round(double p0)`|  
  
|<xref:System.Linq.Expressions.Expression>-Member|Unterstützte odata-Funktion|  
|---------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Linq.Expressions.Expression.TypeIs%28System.Linq.Expressions.Expression%2CSystem.Type%29>|`bool isof(type p0)`|  
  
 Der Client kann möglicherweise auch weitere CLR-Funktionen auf dem Client auswerten. Für einen Ausdruck, der nicht auf dem Client ausgewertet und nicht in einen gültigen URI für die Auswertung auf dem Server übersetzt werden kann, wird eine <xref:System.NotSupportedException> ausgelöst.  
  
## <a name="see-also"></a>Siehe auch

- [Abfragen des Datendiensts](querying-the-data-service-wcf-data-services.md)
- [Abfrageprojektionen](query-projections-wcf-data-services.md)
- [Objektmaterialisierung](object-materialization-wcf-data-services.md)
- [Odata: URI-Konventionen](https://go.microsoft.com/fwlink/?LinkID=185564)
