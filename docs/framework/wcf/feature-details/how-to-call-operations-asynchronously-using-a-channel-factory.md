---
title: 'Vorgehensweise: Asynchrones Aufrufen von Vorgängen mit einer Kanalfactory'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cc17dd47-b9ad-451c-a362-e36e0aac7ba0
ms.openlocfilehash: c288df6059cfe1cd1f4ff35cebffafd3fddb38d1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257534"
---
# <a name="how-to-call-operations-asynchronously-using-a-channel-factory"></a>Vorgehensweise: Asynchrones Aufrufen von Vorgängen mit einer Kanalfactory

In diesem Thema wird beschrieben, wie ein Client auf einen Dienstvorgang asynchron zugreifen kann, wenn eine auf <xref:System.ServiceModel.ChannelFactory%601> basierende Clientanwendung verwendet wird. (Wenn Sie ein <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>-Objekt verwenden, um einen Dienst aufzurufen, können Sie das ereignisgesteuerte asynchrone Aufrufmodell verwenden. Weitere Informationen finden Sie unter Vorgehensweise [: Asynchrones Abrufen von Dienst Vorgängen](how-to-call-wcf-service-operations-asynchronously.md). Weitere Informationen zum ereignisbasierten asynchronen Aufruf Modell finden Sie unter [Ereignis basiertes asynchrones Muster (EAP)](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).)  
  
 Der in diesem Thema behandelte Dienst implementiert die `ICalculator`-Schnittstelle. Der Client kann die Vorgänge an dieser Schnittstelle asynchron aufrufen. Dies bedeutet, dass Vorgänge wie `Add` in zwei Methoden aufgeteilt werden, `BeginAdd` und `EndAdd`, wobei die erste den Aufruf einleitet und die zweite das Ergebnis abruft, wenn der Vorgang abgeschlossen ist. Ein Beispiel für das asynchrone Implementieren eines Vorgangs in einem Dienst finden Sie unter Gewusst [wie: Implementieren eines asynchronen Dienst Vorgangs](../how-to-implement-an-asynchronous-service-operation.md). Ausführliche Informationen zu synchronen und asynchronen Vorgängen finden Sie unter [synchrone und asynchrone Vorgänge](../synchronous-and-asynchronous-operations.md).  
  
## <a name="procedure"></a>Vorgehensweise  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>So rufen Sie WCF-Dienstvorgänge asynchron auf  
  
1. Führen Sie das [Service Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) -Tool mit der- `/async` Option aus, wie im folgenden Befehl gezeigt.  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a  
    ```  
  
     Dies generiert eine asynchrone Clientversion des Dienstvertrags für den Vorgang.  
  
2. Erstellen Sie eine Rückruffunktion, die aufgerufen wird, wenn der asynchrone Vorgang abgeschlossen ist, wie im folgenden Beispielcode dargestellt.  
  
     [!code-csharp[C_How_To_CF_Async#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#2)]
     [!code-vb[C_How_To_CF_Async#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#2)]  
  
3. Zum asynchronen Aufrufen eines Dienstvorgangs erstellen Sie den Client, rufen Sie `Begin[Operation]` auf (z. B. `BeginAdd`), und geben Sie eine Rückruffunktion an, wie in folgendem Beispielcode dargestellt.  
  
     [!code-csharp[C_How_To_CF_Async#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#3)]
     [!code-vb[C_How_To_CF_Async#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#3)]  
  
     Wenn die Rückruffunktion ausgeführt wird, ruft der Client `End<operation>``EndAdd` (z. B. ) auf, um das Ergebnis abzurufen.  
  
## <a name="example"></a>Beispiel  

 Der Dienst, der mit dem im vorhergehenden Verfahren genutzten Clientcode verwendet wird, implementiert die `ICalculator`-Schnittstelle, wie im folgenden Beispielcode gezeigt. Auf der Dienst Seite werden die `Add` -und- `Subtract` Vorgänge des Vertrags synchron von der Windows Communication Foundation (WCF)-Laufzeit aufgerufen, auch wenn die vorherigen Client Schritte asynchron auf dem Client aufgerufen werden. Die `Multiply`- und `Divide`-Vorgänge werden verwendet, um den Dienst asynchron auf der Seite des Diensts aufzurufen, auch wenn der Client sie synchron aufruft. Im folgenden Beispiel wird die <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>-Eigenschaft auf `true` festgelegt. Diese Eigenschafts Einstellung weist in Verbindung mit der Implementierung des asynchronen .NET Framework Musters die Laufzeit an, den Vorgang asynchron aufzurufen.  
  
 [!code-csharp[C_How_To_CF_Async#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/service.cs#4)]
 [!code-vb[C_How_To_CF_Async#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/service.vb#4)]  
