---
title: Aufrufen von Dienstvorgängen (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1767f3a7-29d2-4834-a763-7d169693fa8b
ms.openlocfilehash: f838cbd0a1884d9fca1f12398b996cde93af453a
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937566"
---
# <a name="calling-service-operations-wcf-data-services"></a>Aufrufen von Dienstvorgängen (WCF Data Services)
Der Open Data Protocol (odata) definiert Dienst Vorgänge für einen Datendienst. WCF Data Services ermöglicht es Ihnen, solche Vorgänge als Methoden für den Datendienst zu definieren. Wie andere Datendienstressourcen werden diese Dienstvorgänge durch URIs adressiert. Ein Dienstvorgang kann Auflistungen von Entitätstypen, einzelnen Entitätstypinstanzen und primitiven Typen zurückgeben, z. B. ganze Zahl und Zeichenfolge. Ein Dienstvorgang kann auch `null` (`Nothing` in Visual Basic) zurückgeben. Die WCF Data Services-Client Bibliothek kann verwendet werden, um auf Dienst Vorgänge zuzugreifen, die HTTP GET-Anforderungen unterstützen. Diese Arten von Dienstvorgängen werden als Methoden definiert, die über das <xref:System.ServiceModel.Web.WebGetAttribute> verfügen. Weitere Informationen finden Sie unter [Dienst Vorgänge](service-operations-wcf-data-services.md).  
  
 Dienst Vorgänge werden in den Metadaten verfügbar gemacht, die von einem Datendienst zurückgegeben werden, der odata implementiert. In den Metadaten werden Dienstvorgänge als `FunctionImport`-Elemente dargestellt. Beim Generieren des stark typisierten <xref:System.Data.Services.Client.DataServiceContext> ignorieren die Tools Dienstverweis hinzufügen und DataSvcUtil.exe dieses Element. Daher finden Sie keine Methode im Kontext, die zum direkten Aufrufen eines Dienstvorgangs verwendet werden kann. Sie können jedoch weiterhin den WCF Data Services-Client verwenden, um Dienst Vorgänge auf eine der beiden folgenden Arten aufzurufen:  
  
- Durch das Aufrufen der <xref:System.Data.Services.Client.DataServiceContext.Execute%2A>-Methode im <xref:System.Data.Services.Client.DataServiceContext> und das Angeben des URI des Dienstvorgangs zusammen mit Parametern. Diese Methode wird verwendet, um GET-Dienstvorgänge aufzurufen.  
  
- Verwenden Sie die <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>-Methode für den <xref:System.Data.Services.Client.DataServiceContext>, um ein <xref:System.Data.Services.Client.DataServiceQuery%601>-Objekt zu erstellen. Beim Aufruf von <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> wird der Name des Dienstvorgangs im `entitySetName`-Parameter angegeben. Diese Methode gibt ein <xref:System.Data.Services.Client.DataServiceQuery%601>-Objekt zurück, das den Dienstvorgang bei einer Enumeration oder bei einem Aufruf der <xref:System.Data.Services.Client.DataServiceQuery%601.Execute%2A>-Methode aufruft. Diese Methode wird verwendet, um GET-Dienstvorgänge aufzurufen, die eine Auflistung zurückgeben. Ein einzelner Parameter kann mit der <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode angegeben werden. Das von dieser Methode zurückgegebene <xref:System.Data.Services.Client.DataServiceQuery%601>-Objekt kann wie jedes andere Abfrageobjekt weiter zusammengesetzt werden. Weitere Informationen finden Sie unter [Abfragen des Daten Dienstanbieter](querying-the-data-service-wcf-data-services.md).  
  
## <a name="considerations-for-calling-service-operations"></a>Überlegungen zum Aufrufen von Dienstvorgängen  
 Die folgenden Überlegungen gelten, wenn Sie den WCF Data Services-Client zum Abrufen von Dienst Vorgängen verwenden.  
  
- Wenn Sie asynchron auf den Datendienst zugreifen, müssen Sie die entsprechenden asynchronen <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A>/<xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A> Methoden auf <xref:System.Data.Services.Client.DataServiceContext> oder <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>/<xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> Methoden auf <xref:System.Data.Services.Client.DataServiceQuery%601>verwenden.  
  
- Die WCF Data Services Client Bibliothek kann die Ergebnisse eines Dienst Vorgangs, der eine Auflistung primitiver Typen zurückgibt, nicht materialisieren.  
  
- Die WCF Data Services-Client Bibliothek unterstützt das Aufrufen von Post Dienst Vorgängen nicht. Dienstvorgänge, die durch HTTP POST aufgerufen werden, werden mithilfe des <xref:System.ServiceModel.Web.WebInvokeAttribute> mit dem `Method="POST"`-Parameter definiert. Um einen Dienstvorgang mit einer HTTP-POST-Anforderung aufzurufen, müssen Sie stattdessen eine <xref:System.Net.HttpWebRequest> verwenden.  
  
- Sie können einen GET-Dienstvorgang, der ein einzelnes Ergebnis des Typs Entität oder Primitiv zurückgibt oder mehr als einen Eingabeparameter erfordert, nicht mithilfe von <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> aufrufen. Sie müssen stattdessen die <xref:System.Data.Services.Client.DataServiceContext.Execute%2A>-Methode aufrufen.  
  
- Ziehen Sie das Erstellen einer Erweiterungsmethode in der stark typisierten <xref:System.Data.Services.Client.DataServiceContext>-Teilklasse in Betracht, die von den Tools generiert wird und entweder die <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>-Methode oder die <xref:System.Data.Services.Client.DataServiceContext.Execute%2A>-Methode zum Aufrufen eines Dienstvorgangs verwendet. Dies ermöglicht es Ihnen, Dienstvorgänge direkt aus dem Kontext heraus aufzurufen. Weitere Informationen finden Sie im Blogbeitrag [Dienst Vorgänge und der WCF Data Services-Client](https://docs.microsoft.com/archive/blogs/astoriateam/service-operations-and-the-wcf-data-services-client).  
  
- Wenn Sie <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> verwenden, um einen Dienst Vorgang aufzurufen, werden von der Client Bibliothek automatisch die Zeichen, die für die <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> bereitgestellt werden, durch die prozentuale Codierung von reservierten Zeichen, wie z. b. kaufmännisches und-Zeichen (&), und das Escapezeichen in Zeichen folgen Wenn Sie jedoch eine der *Execute* -Methoden zum aufzurufen eines Dienst Vorgangs aufzurufen, müssen Sie daran denken, dass Sie diese Escapezeichen für alle vom Benutzer bereitgestellten Zeichen folgen Werte ausführen müssen. Einfache Anführungszeichen in URIs werden als Paare einfacher Anführungszeichen mit Escapezeichen versehen.  
  
## <a name="examples-of-calling-service-operations"></a>Beispiele für das Aufrufen von Dienstvorgängen  
 Dieser Abschnitt enthält die folgenden Beispiele für das Abrufen von Dienst Vorgängen mit der WCF Data Services-Client Bibliothek:  
  
- [Aufrufen von Execute&lt;t&gt;, um eine Auflistung von Entitäten zurückzugeben](calling-service-operations-wcf-data-services.md#ExecuteIQueryable)  
  
- [Zurückgeben einer Auflistung von Entitäten mithilfe von "kreatequery"&lt;t&gt;](calling-service-operations-wcf-data-services.md#CreateQueryIQueryable)  
  
- [Aufrufen von Execute&lt;t&gt;, um eine einzelne Entität zurückzugeben](calling-service-operations-wcf-data-services.md#ExecuteSingleEntity)  
  
- [Aufrufen von Execute&lt;t&gt;, um eine Auflistung primitiver Werte zurückzugeben](calling-service-operations-wcf-data-services.md#ExecutePrimitiveCollection)  
  
- [Aufrufen von Execute&lt;t&gt; zum Zurückgeben eines einzelnen primitiven Werts](calling-service-operations-wcf-data-services.md#ExecutePrimitiveValue)  
  
- [Aufrufen eines Dienst Vorgangs, der keine Daten zurückgibt](calling-service-operations-wcf-data-services.md#ExecuteVoid)  
  
- [Asynchrones Aufrufen eines Dienst Vorgangs](calling-service-operations-wcf-data-services.md#ExecuteAsync)  
  
<a name="ExecuteIQueryable"></a>   
### <a name="calling-executet-to-return-a-collection-of-entities"></a>Aufrufen von Execute\<t >, um eine Auflistung von Entitäten zurückzugeben  
 Im folgenden Beispiel wird ein Dienstvorgang mit dem Namen GetOrdersByCity aufgerufen, der den Zeichenfolgenparameter `city` akzeptiert und ein <xref:System.Linq.IQueryable%601> zurückgibt:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationiqueryable)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationiqueryable)]  
  
 In diesem Beispiel gibt der Dienstvorgang eine Auflistung von `Order`-Objekten mit zugehörigen `Order_Detail`-Objekten zurück.  
  
<a name="CreateQueryIQueryable"></a>   
### <a name="using-createqueryt-to-return-a-collection-of-entities"></a>Zurückgeben einer Auflistung von Entitäten mithilfe von "kreatequery"\<t >  
 Das folgende Beispiel gibt mithilfe der <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> eine <xref:System.Data.Services.Client.DataServiceQuery%601> zurück, die verwendet wird, um den gleichen GetOrdersByCity-Dienstvorgang aufzurufen:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationcreatequery)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationcreatequery)]  
  
 In diesem Beispiel wird die <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode verwendet, um der Abfrage den Parameter hinzuzufügen, und die <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>-Methode wird verwendet, um zugehörige Order_Details-Objekte in die Ergebnisse einzuschließen.  
  
<a name="ExecuteSingleEntity"></a>   
### <a name="calling-executet-to-return-a-single-entity"></a>Aufrufen von Execute\<t >, um eine einzelne Entität zurückzugeben  
 Im folgenden Beispiel wird ein Dienstvorgang mit dem Namen GetNewestOrder aufgerufen, der nur eine einzelne Order-Entität zurückgibt:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationsingleentity)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationsingleentity)]  
  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.FirstOrDefault%2A>-Methode zur Anforderung einer einzelnen Order-Entität bei der Ausführung verwendet.  
  
<a name="ExecutePrimitiveCollection"></a>   
### <a name="calling-executet-to-return-a-collection-of-primitive-values"></a>Aufrufen von Execute\<t >, um eine Auflistung primitiver Werte zurückzugeben  
 Im folgenden Beispiel wird ein Dienstvorgang aufgerufen, der eine Auflistung von Zeichenfolgenwerten zurückgibt:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationEnumString](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationenumstring)]  
  
<a name="ExecutePrimitiveValue"></a>   
### <a name="calling-executet-to-return-a-single-primitive-value"></a>Aufrufen von Execute\<t > zum Zurückgeben eines einzelnen primitiven Werts  
 Im folgenden Beispiel wird ein Dienstvorgang aufgerufen, der einen einzelnen Zeichenfolgenwert zurückgibt:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationSingleInt](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationsingleint)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationSingleInt](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationsingleint)]  
  
 In diesem Beispiel wird wieder die <xref:System.Linq.Enumerable.FirstOrDefault%2A>-Methode zur Anforderung eines einzelnen ganzzahligen Werts bei der Ausführung verwendet.  
  
<a name="ExecuteVoid"></a>   
### <a name="calling-a-service-operation-that-returns-no-data"></a>Aufrufen eines Dienstvorgangs, der keine Daten zurückgibt  
 Im folgenden Beispiel wird ein Dienstvorgang aufgerufen, der keine Daten zurückgibt:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationVoid](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationvoid)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationVoid](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationvoid)]  
  
 Da keine Daten zurückgegeben werden, ist der Wert der Ausführung nicht zugewiesen. Das einzige Anzeichen, dass die Anforderung erfolgreich war, besteht darin, dass keine <xref:System.Data.Services.Client.DataServiceQueryException> ausgelöst wird.  
  
<a name="ExecuteAsync"></a>   
### <a name="calling-a-service-operation-asynchronously"></a>Asynchrones Aufrufen von Dienstvorgängen  
 Im folgenden Beispiel wird ein Dienstvorgang asynchron aufgerufen, indem <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A> und <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A> aufgerufen werden:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationasync)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationasync)]  
  
 [!code-csharp[Astoria Northwind Client#OnAsyncExecutionComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#onasyncexecutioncomplete)]
 [!code-vb[Astoria Northwind Client#OnAsyncExecutionComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#onasyncexecutioncomplete)]  
  
 Da keine Daten zurückgegeben werden, ist der von der Ausführung zurückgegebene Wert nicht zugewiesen. Das einzige Anzeichen, dass die Anforderung erfolgreich war, besteht darin, dass keine <xref:System.Data.Services.Client.DataServiceQueryException> ausgelöst wird.  
  
 Im folgenden Beispiel wird der gleiche Dienstvorgang asynchron mit <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> aufgerufen:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationqueryasync)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationqueryasync)]  
  
 [!code-csharp[Astoria Northwind Client#OnAsyncQueryExecutionComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#onasyncqueryexecutioncomplete)]
 [!code-vb[Astoria Northwind Client#OnAsyncQueryExecutionComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#onasyncqueryexecutioncomplete)]  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
