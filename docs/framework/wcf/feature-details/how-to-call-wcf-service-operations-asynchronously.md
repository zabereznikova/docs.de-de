---
title: 'Vorgehensweise: Asynchrones Aufrufen von WCF-Dienstvorgängen'
description: Erfahren Sie, wie Sie einen WCF-Client erstellen, der asynchron auf einen Dienst Vorgang zugreifen kann, indem Sie das ereignisgesteuerte asynchrone Aufruf Modell verwenden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: aa31f64473111800f4cd01907a0446c94f368456
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247233"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a>Vorgehensweise: Asynchrones Aufrufen von WCF-Dienstvorgängen

In diesem Artikel wird beschrieben, wie ein Client auf einen Dienst Vorgang asynchron zugreifen kann. Der Dienst in diesem Artikel implementiert die- `ICalculator` Schnittstelle. Der Client kann mithilfe des ereignisgesteuerten asynchronen Aufrufmodells die Vorgänge asynchron an dieser Schnittstelle aufrufen. (Weitere Informationen über das ereignisbasierte asynchrone Aufruf Modell finden Sie unter [Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)). Ein Beispiel für das asynchrone Implementieren eines Vorgangs in einem Dienst finden Sie unter Gewusst [wie: Implementieren eines asynchronen Dienst Vorgangs](../how-to-implement-an-asynchronous-service-operation.md). Weitere Informationen zu synchronen und asynchronen Vorgängen finden Sie unter [synchrone und asynchrone Vorgänge](../synchronous-and-asynchronous-operations.md).  
  
> [!NOTE]
> Bei Verwendung einer <xref:System.ServiceModel.ChannelFactory%601> wird das ereignisgesteuerte asynchrone Aufrufmodell nicht unterstützt. Weitere Informationen zum Ausführen von asynchronen Aufrufen mithilfe von finden Sie unter Gewusst <xref:System.ServiceModel.ChannelFactory%601> [wie: Asynchrones Aufrufen von Vorgängen mithilfe einer Kanalfactory](how-to-call-operations-asynchronously-using-a-channel-factory.md).  
  
## <a name="procedure"></a>Vorgehensweise  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>So rufen Sie WCF-Dienstvorgänge asynchron auf  
  
1. Führen Sie das [Service Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) -Tool mit den `/async` `/tcv:Version35` Befehlsoptionen und aus, wie im folgenden Befehl gezeigt.  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     Dies generiert zusätzlich zu den synchronen und standardmäßigen delegatbasierten asynchronen Vorgängen eine WCF-Client Klasse, die Folgendes enthält:  
  
    - Zwei <`operationName` > `Async` Vorgänge für die Verwendung mit dem ereignisbasierten asynchronen Aufruf Ansatz. Beispiel:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - Der Vorgang hat Ereignisse der Form <`operationName` > `Completed` für die Verwendung mit dem ereignisbasierten asynchronen Aufruf Ansatz verwendet. Beispiel:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <xref:System.EventArgs?displayProperty=nameWithType>Typen für jeden Vorgang (in der Form <`operationName` > `CompletedEventArgs` ) für die Verwendung mit dem ereignisbasierten asynchronen Aufruf Ansatz. Beispiel:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. Erstellen Sie in der aufrufenden Anwendung eine Rückrufmethode, die aufgerufen wird, wenn der asynchrone Vorgang abgeschlossen ist, wie im folgenden Beispielcode dargestellt.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. Verwenden Sie vor dem Aufrufen des Vorgangs einen neuen generischen <xref:System.EventHandler%601?displayProperty=nameWithType> vom Typ <, `operationName` > `EventArgs` um die Handlermethode (die im vorherigen Schritt erstellt wurde) dem <-Ereignis hinzuzufügen `operationName` > `Completed` . Anschließend wird die <- `operationName` > `Async` Methode aufgerufen. Zum Beispiel:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a>Beispiel  
  
> [!NOTE]
> Die Entwurfsrichtlinien für das ereignisbasierte asynchrone Modell besagen, dass in den Fällen, in denen mehr als ein Wert zurückgegeben wird, ein Wert in der `Result`-Eigenschaft und die übrigen Werte in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben werden sollen. Wenn ein Client Metadaten mithilfe der ereignisbasierten asynchronen Befehlsoptionen importiert und der Vorgang mehr als einen Wert zurückgibt, dann gibt das <xref:System.EventArgs>-Objekt infolgedessen einen Wert in der `Result`-Eigenschaft zurück, und die übrigen Werte werden in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben. Wenn das Nachrichtenobjekt in der `Result`-Eigenschaft und die Rückgabewerte als Eigenschaften dieses Objekts übermittelt werden sollen, verwenden Sie die Befehlsoption `/messageContract`. Damit wird eine Signatur generiert, bei der die Antwortnachricht in der `Result`-Eigenschaft des <xref:System.EventArgs>-Objekts zurückgegeben wird. Alle internen Rückgabewerte sind dann Eigenschaften des Antwortnachrichtenobjekts.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs](../how-to-implement-an-asynchronous-service-operation.md)
