---
title: "Aufrufen von Dienstvorgängen (WCF Data Services)"
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
ms.assetid: 1767f3a7-29d2-4834-a763-7d169693fa8b
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1480047f14d9528d4d498b417e5d0b4a0f87a622
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="calling-service-operations-wcf-data-services"></a>Aufrufen von Dienstvorgängen (WCF Data Services)
Der [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] definiert Dienstvorgänge für einen Datendienst. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es Ihnen, solche Vorgänge als Methoden im Datendienst zu definieren. Wie andere Datendienstressourcen werden diese Dienstvorgänge durch URIs adressiert. Ein Dienstvorgang kann Auflistungen von Entitätstypen, einzelnen Entitätstypinstanzen und primitiven Typen zurückgeben, z. B. ganze Zahl und Zeichenfolge. Ein Dienstvorgang kann auch `null` (`Nothing` in Visual Basic) zurückgeben. Die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliothek kann verwendet werden, um auf Dienstvorgänge zuzugreifen, die HTTP-GET-Anforderungen unterstützen. Diese Arten von Dienstvorgängen werden als Methoden definiert, die über das <xref:System.ServiceModel.Web.WebGetAttribute> verfügen. Weitere Informationen finden Sie unter [Dienstvorgänge](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).  
  
 Dienstvorgänge werden in den Metadaten verfügbar gemacht, die von einem Datendienst zurückgegeben werden, der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] implementiert. In den Metadaten werden Dienstvorgänge als `FunctionImport`-Elemente dargestellt. Beim Generieren des stark typisierten <xref:System.Data.Services.Client.DataServiceContext> ignorieren die Tools Dienstverweis hinzufügen und DataSvcUtil.exe dieses Element. Daher finden Sie keine Methode im Kontext, die zum direkten Aufrufen eines Dienstvorgangs verwendet werden kann. Sie können Dienstvorgänge jedoch mithilfe des [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clients auf eine der beiden folgenden Weisen aufrufen:  
  
-   Durch das Aufrufen der <xref:System.Data.Services.Client.DataServiceContext.Execute%2A>-Methode im <xref:System.Data.Services.Client.DataServiceContext> und das Angeben des URI des Dienstvorgangs zusammen mit Parametern. Diese Methode wird verwendet, um GET-Dienstvorgänge aufzurufen.  
  
-   Verwenden Sie die <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>-Methode für den <xref:System.Data.Services.Client.DataServiceContext>, um ein <xref:System.Data.Services.Client.DataServiceQuery%601>-Objekt zu erstellen. Beim Aufruf von <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> wird der Name des Dienstvorgangs im `entitySetName`-Parameter angegeben. Diese Methode gibt ein <xref:System.Data.Services.Client.DataServiceQuery%601>-Objekt zurück, das den Dienstvorgang bei einer Enumeration oder bei einem Aufruf der <xref:System.Data.Services.Client.DataServiceQuery%601.Execute%2A>-Methode aufruft. Diese Methode wird verwendet, um GET-Dienstvorgänge aufzurufen, die eine Auflistung zurückgeben. Ein einzelner Parameter kann mit der <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode angegeben werden. Das von dieser Methode zurückgegebene <xref:System.Data.Services.Client.DataServiceQuery%601>-Objekt kann wie jedes andere Abfrageobjekt weiter zusammengesetzt werden. Weitere Informationen finden Sie unter [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
## <a name="considerations-for-calling-service-operations"></a>Überlegungen zum Aufrufen von Dienstvorgängen  
 Die folgenden Überlegungen betreffen den Aufruf von Dienstvorgängen mithilfe des [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clients.  
  
-   Wenn Sie asynchron auf den Datendienst zugreifen zu können, müssen Sie die entsprechenden asynchronen verwenden <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A> / <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A> Methoden auf <xref:System.Data.Services.Client.DataServiceContext> oder die <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> / <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> Methoden auf <xref:System.Data.Services.Client.DataServiceQuery%601>.  
  
-   Die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliothek kann die Ergebnisse eines Dienstvorgangs nicht materialisieren, der eine Auflistung von primitiven Typen zurückgibt.  
  
-   Die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliothek unterstützt das Aufrufen von POST-Dienstvorgängen nicht. Dienstvorgänge, die durch HTTP POST aufgerufen werden, werden mithilfe des <xref:System.ServiceModel.Web.WebInvokeAttribute> mit dem `Method="POST"`-Parameter definiert. Um einen Dienstvorgang mit einer HTTP-POST-Anforderung aufzurufen, müssen Sie stattdessen eine <xref:System.Net.HttpWebRequest> verwenden.  
  
-   Sie können einen GET-Dienstvorgang, der ein einzelnes Ergebnis des Typs Entität oder Primitiv zurückgibt oder mehr als einen Eingabeparameter erfordert, nicht mithilfe von <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> aufrufen. Sie müssen stattdessen die <xref:System.Data.Services.Client.DataServiceContext.Execute%2A>-Methode aufrufen.  
  
-   Ziehen Sie das Erstellen einer Erweiterungsmethode in der stark typisierten <xref:System.Data.Services.Client.DataServiceContext>-Teilklasse in Betracht, die von den Tools generiert wird und entweder die <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>-Methode oder die <xref:System.Data.Services.Client.DataServiceContext.Execute%2A>-Methode zum Aufrufen eines Dienstvorgangs verwendet. Dies ermöglicht es Ihnen, Dienstvorgänge direkt aus dem Kontext heraus aufzurufen. Weitere Informationen finden Sie im Blogbeitrag [Dienstvorgänge und WCF Data Services-Client](http://go.microsoft.com/fwlink/?LinkId=215668).  
  
-   Wenn Sie mithilfe von <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> einen Dienstvorgang aufrufen, versieht die Clientbibliothek automatisch an <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> übergebene Zeichen mit Escapezeichen, indem eine Prozentcodierung der reservierten Zeichen wie das kaufmännische Und-Zeichen (&) durchgeführt wird, sowie einfache Anführungszeichen in Zeichenfolgen. Allerdings beim Aufrufen eines der *Execute* Methoden zum Aufrufen eines Dienstvorgangs, müssen Sie zum Ausführen dieser Schutz aller Benutzer bereitgestellte Zeichenfolge Werte berücksichtigen. Einfache Anführungszeichen in URIs werden als Paare einfacher Anführungszeichen mit Escapezeichen versehen.  
  
## <a name="examples-of-calling-service-operations"></a>Beispiele für das Aufrufen von Dienstvorgängen  
 Dieser Abschnitt enthält die folgenden Beispiele zum Aufrufen von Dienstvorgängen mit der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliothek:  
  
-   [Aufrufen von Execute&lt;T&gt; zum Zurückgeben einer Auflistung von Entitäten](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#ExecuteIQueryable)  
  
-   [Verwenden von CreateQuery&lt;T&gt; zum Zurückgeben einer Auflistung von Entitäten](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#CreateQueryIQueryable)  
  
-   [Aufrufen von Execute&lt;T&gt; zum Zurückgeben einer einzelnen Entität](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#ExecuteSingleEntity)  
  
-   [Aufrufen von Execute&lt;T&gt; zum Zurückgeben einer Auflistung primitiver Werte](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#ExecutePrimitiveCollection)  
  
-   [Aufrufen von Execute&lt;T&gt; zum Zurückgeben eines einzelnen primitiven Werts](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#ExecutePrimitiveValue)  
  
-   [Aufrufen eines Dienstvorgangs, die zurückgibt keine Daten](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#ExecuteVoid)  
  
-   [Asynchrones Aufrufen eines Dienstvorgangs](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#ExecuteAsync)  
  
<a name="ExecuteIQueryable"></a>   
### <a name="calling-executet-to-return-a-collection-of-entities"></a>Aufrufen von Execute\<T > zum Zurückgeben einer Auflistung von Entitäten  
 Im folgenden Beispiel wird ein Dienstvorgang mit dem Namen GetOrdersByCity aufgerufen, der den Zeichenfolgenparameter `city` akzeptiert und ein <xref:System.Linq.IQueryable%601> zurückgibt:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationiqueryable)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationiqueryable)]  
  
 In diesem Beispiel gibt der Dienstvorgang eine Auflistung von `Order`-Objekten mit zugehörigen `Order_Detail`-Objekten zurück.  
  
<a name="CreateQueryIQueryable"></a>   
### <a name="using-createqueryt-to-return-a-collection-of-entities"></a>Verwenden von CreateQuery\<T > zum Zurückgeben einer Auflistung von Entitäten  
 Das folgende Beispiel gibt mithilfe der <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> eine <xref:System.Data.Services.Client.DataServiceQuery%601> zurück, die verwendet wird, um den gleichen GetOrdersByCity-Dienstvorgang aufzurufen:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationcreatequery)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationcreatequery)]  
  
 In diesem Beispiel wird die <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode verwendet, um der Abfrage den Parameter hinzuzufügen, und die <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>-Methode wird verwendet, um zugehörige Order_Details-Objekte in die Ergebnisse einzuschließen.  
  
<a name="ExecuteSingleEntity"></a>   
### <a name="calling-executet-to-return-a-single-entity"></a>Aufrufen von Execute\<T > zum Zurückgeben einer einzelnen Entität  
 Im folgenden Beispiel wird ein Dienstvorgang mit dem Namen GetNewestOrder aufgerufen, der nur eine einzelne Order-Entität zurückgibt:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationsingleentity)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationsingleentity)]  
  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.FirstOrDefault%2A>-Methode zur Anforderung einer einzelnen Order-Entität bei der Ausführung verwendet.  
  
<a name="ExecutePrimitiveCollection"></a>   
### <a name="calling-executet-to-return-a-collection-of-primitive-values"></a>Aufrufen von Execute\<T > zum Zurückgeben einer Auflistung primitiver Werte  
 Im folgenden Beispiel wird ein Dienstvorgang aufgerufen, der eine Auflistung von Zeichenfolgenwerten zurückgibt:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationEnumString](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationenumstring)]  
  
<a name="ExecutePrimitiveValue"></a>   
### <a name="calling-executet-to-return-a-single-primitive-value"></a>Aufrufen von Execute\<T > zum Zurückgeben eines einzelnen primitiven Werts  
 Im folgenden Beispiel wird ein Dienstvorgang aufgerufen, der einen einzelnen Zeichenfolgenwert zurückgibt:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationSingleInt](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationsingleint)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationSingleInt](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationsingleint)]  
  
 In diesem Beispiel wird wieder die <xref:System.Linq.Enumerable.FirstOrDefault%2A>-Methode zur Anforderung eines einzelnen ganzzahligen Werts bei der Ausführung verwendet.  
  
<a name="ExecuteVoid"></a>   
### <a name="calling-a-service-operation-that-returns-no-data"></a>Aufrufen eines Dienstvorgangs, der keine Daten zurückgibt  
 Im folgenden Beispiel wird ein Dienstvorgang aufgerufen, der keine Daten zurückgibt:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationVoid](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationvoid)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationVoid](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationvoid)]  
  
 Da keine Daten zurückgegeben werden, ist der Wert der Ausführung nicht zugewiesen. Das einzige Anzeichen, dass die Anforderung erfolgreich war, besteht darin, dass keine <xref:System.Data.Services.Client.DataServiceQueryException> ausgelöst wird.  
  
<a name="ExecuteAsync"></a>   
### <a name="calling-a-service-operation-asynchronously"></a>Asynchrones Aufrufen von Dienstvorgängen  
 Im folgenden Beispiel wird ein Dienstvorgang asynchron aufgerufen, indem <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A> und <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A> aufgerufen werden:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationasync)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationasync)]  
  
 [!code-csharp[Astoria Northwind Client#OnAsyncExecutionComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#onasyncexecutioncomplete)]
 [!code-vb[Astoria Northwind Client#OnAsyncExecutionComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#onasyncexecutioncomplete)]  
  
 Da keine Daten zurückgegeben werden, ist der von der Ausführung zurückgegebene Wert nicht zugewiesen. Das einzige Anzeichen, dass die Anforderung erfolgreich war, besteht darin, dass keine <xref:System.Data.Services.Client.DataServiceQueryException> ausgelöst wird.  
  
 Im folgenden Beispiel wird der gleiche Dienstvorgang asynchron mit <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> aufgerufen:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationqueryasync)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationqueryasync)]  
  
 [!code-csharp[Astoria Northwind Client#OnAsyncQueryExecutionComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#onasyncqueryexecutioncomplete)]
 [!code-vb[Astoria Northwind Client#OnAsyncQueryExecutionComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#onasyncqueryexecutioncomplete)]  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
