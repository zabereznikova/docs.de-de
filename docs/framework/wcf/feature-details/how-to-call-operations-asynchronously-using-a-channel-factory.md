---
title: 'Vorgehensweise: Aufrufen von Vorgängen, die asynchron mit einer Kanalfactory'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cc17dd47-b9ad-451c-a362-e36e0aac7ba0
ms.openlocfilehash: e266dbf3fed2c1f1bcadd010e2ad6dfd0804230d
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260646"
---
# <a name="how-to-call-operations-asynchronously-using-a-channel-factory"></a>Vorgehensweise: Aufrufen von Vorgängen, die asynchron mit einer Kanalfactory
In diesem Thema wird beschrieben, wie ein Client auf einen Dienstvorgang asynchron zugreifen kann, wenn eine auf <xref:System.ServiceModel.ChannelFactory%601> basierende Clientanwendung verwendet wird. (Wenn Sie ein <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>-Objekt verwenden, um einen Dienst aufzurufen, können Sie das ereignisgesteuerte asynchrone Aufrufmodell verwenden. Weitere Informationen finden Sie unter [Vorgehensweise: Asynchrones Aufrufen von Dienstvorgängen](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md). Weitere Informationen über den ereignisbasierten asynchronen aufrufmodells finden Sie unter [das ereignisbasierte asynchrone Muster (EAP)](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).)  
  
 Der in diesem Thema behandelte Dienst implementiert die `ICalculator`-Schnittstelle. Der Client kann die Vorgänge an dieser Schnittstelle asynchron aufrufen. Dies bedeutet, dass Vorgänge wie `Add` in zwei Methoden aufgeteilt werden, `BeginAdd` und `EndAdd`, wobei die erste den Aufruf einleitet und die zweite das Ergebnis abruft, wenn der Vorgang abgeschlossen ist. Ein Beispiel zeigt, wie asynchrone Implementieren eines Vorgangs in einem Dienst finden Sie unter [Vorgehensweise: Implementieren ein asynchronen Dienstvorgangs](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md). Weitere Informationen zu synchronen und asynchronen Vorgängen finden Sie unter [synchrone und asynchrone Vorgänge](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
## <a name="procedure"></a>Prozedur  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>So rufen Sie WCF-Dienstvorgänge asynchron auf  
  
1.  Führen Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) -Tool mit der `/async` wie in den folgenden Befehl gezeigt.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a  
    ```  
  
     Dies generiert eine asynchrone Clientversion des Dienstvertrags für den Vorgang.  
  
2.  Erstellen Sie eine Rückruffunktion, die aufgerufen wird, wenn der asynchrone Vorgang abgeschlossen ist, wie im folgenden Beispielcode dargestellt.  
  
     [!code-csharp[C_How_To_CF_Async#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#2)]
     [!code-vb[C_How_To_CF_Async#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#2)]  
  
3.  Zum asynchronen Aufrufen eines Dienstvorgangs erstellen Sie den Client, rufen Sie `Begin[Operation]` auf (z. B. `BeginAdd`), und geben Sie eine Rückruffunktion an, wie in folgendem Beispielcode dargestellt.  
  
     [!code-csharp[C_How_To_CF_Async#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#3)]
     [!code-vb[C_How_To_CF_Async#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#3)]  
  
     Wenn die Rückruffunktion ausgeführt wird, ruft der Client `End<operation>``EndAdd` (z. B. ) auf, um das Ergebnis abzurufen.  
  
## <a name="example"></a>Beispiel  
 Der Dienst, der mit dem im vorhergehenden Verfahren genutzten Clientcode verwendet wird, implementiert die `ICalculator`-Schnittstelle, wie im folgenden Beispielcode gezeigt. Klicken Sie auf der Seite des Diensts die `Add` und `Subtract` Vorgänge des Vertrags werden aufgerufen, synchron von der Windows Communication Foundation (WCF) zur Laufzeit, obwohl die vorangegangenen Schritte auf dem Client asynchron aufgerufen werden. Die `Multiply`- und `Divide`-Vorgänge werden verwendet, um den Dienst asynchron auf der Seite des Diensts aufzurufen, auch wenn der Client sie synchron aufruft. Im folgenden Beispiel wird die <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>-Eigenschaft auf `true` festgelegt. Diese Eigenschaftseinstellung in Verbindung mit der Implementierung des asynchronen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Musters weist die Laufzeit an, den Vorgang asynchron aufzurufen.  
  
 [!code-csharp[C_How_To_CF_Async#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/service.cs#4)]
 [!code-vb[C_How_To_CF_Async#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/service.vb#4)]  
  
