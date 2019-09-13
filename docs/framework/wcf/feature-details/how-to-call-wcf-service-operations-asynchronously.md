---
title: 'Vorgehensweise: Asynchrones Abrufen von WCF-Dienst Vorgängen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 2c0a6f1477ceec5471c22fa3e46d85f5856b298e
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895067"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a>Vorgehensweise: Asynchrones Abrufen von WCF-Dienst Vorgängen
In diesem Thema wird beschrieben, wie ein Client auf einen Dienstvorgang asynchron zugreifen kann. Der in diesem Thema behandelte Dienst implementiert die `ICalculator`-Schnittstelle. Der Client kann mithilfe des ereignisgesteuerten asynchronen Aufrufmodells die Vorgänge asynchron an dieser Schnittstelle aufrufen. (Weitere Informationen über das ereignisbasierte asynchrone Aufruf Modell finden Sie unter [Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster](https://go.microsoft.com/fwlink/?LinkId=248184)). Ein Beispiel für das asynchrone Implementieren eines Vorgangs in einem Dienst finden [Sie unter Gewusst wie: Implementieren Sie einen asynchronen Dienst](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)Vorgang. Weitere Informationen zu synchronen und asynchronen Vorgängen finden Sie unter [synchrone und asynchrone Vorgänge](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
> [!NOTE]
> Bei Verwendung einer <xref:System.ServiceModel.ChannelFactory%601> wird das ereignisgesteuerte asynchrone Aufrufmodell nicht unterstützt. Weitere Informationen zum Ausführen von asynchronen Aufrufen mithilfe <xref:System.ServiceModel.ChannelFactory%601>von finden [Sie unter Gewusst wie: Asynchrones Abrufen von Vorgängen mithilfe](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md)einer Kanalfactory.  
  
## <a name="procedure"></a>Prozedur  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>So rufen Sie WCF-Dienstvorgänge asynchron auf  
  
1. Führen Sie das [Service Model Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) -Tool mit `/async` den `/tcv:Version35` Befehlsoptionen und aus, wie im folgenden Befehl gezeigt.  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     Dies generiert zusätzlich zu den synchronen und standardmäßigen delegatbasierten asynchronen Vorgängen eine WCF-Client Klasse, die Folgendes enthält:  
  
    - Zwei <`operationName` > VorgängefürdieVerwendungmitdemereignisbasiertenasynchronenAufrufAnsatz.`Async` Beispiel:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - Der Vorgang hat Ereignisse der Form <`operationName` > `Completed` für die Verwendung mit dem ereignisbasierten asynchronen Aufruf Ansatz verwendet. Beispiel:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <xref:System.EventArgs?displayProperty=nameWithType>Typen für jeden Vorgang (in der Form <`operationName`>`CompletedEventArgs`) für die Verwendung mit dem ereignisbasierten asynchronen Aufruf Ansatz. Beispiel:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. Erstellen Sie in der aufrufenden Anwendung eine Rückrufmethode, die aufgerufen wird, wenn der asynchrone Vorgang abgeschlossen ist, wie im folgenden Beispielcode dargestellt.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. Verwenden Sie vor dem Aufrufen des <xref:System.EventHandler%601?displayProperty=nameWithType> Vorgangs einen neuen generischen vom Typ <> `Completed` `operationName` `EventArgs` , um die Handlermethode (die im vorherigen Schritt erstellt wurde)`operationName` dem <> -Ereignis hinzuzufügen. Anschließend wird die <`operationName` > `Async` -Methode aufgerufen. Beispiel:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a>Beispiel  
  
> [!NOTE]
> Die Entwurfsrichtlinien für das ereignisbasierte asynchrone Modell besagen, dass in den Fällen, in denen mehr als ein Wert zurückgegeben wird, ein Wert in der `Result`-Eigenschaft und die übrigen Werte in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben werden sollen. Wenn ein Client Metadaten mithilfe der ereignisbasierten asynchronen Befehlsoptionen importiert und der Vorgang mehr als einen Wert zurückgibt, dann gibt das <xref:System.EventArgs>-Objekt infolgedessen einen Wert in der `Result`-Eigenschaft zurück, und die übrigen Werte werden in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben. Wenn das Nachrichtenobjekt in der `Result`-Eigenschaft und die Rückgabewerte als Eigenschaften dieses Objekts übermittelt werden sollen, verwenden Sie die Befehlsoption `/messageContract`. Damit wird eine Signatur generiert, bei der die Antwortnachricht in der `Result`-Eigenschaft des <xref:System.EventArgs>-Objekts zurückgegeben wird. Alle internen Rückgabewerte sind dann Eigenschaften des Antwortnachrichtenobjekts.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Implementieren eines asynchronen Dienst Vorgangs](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
