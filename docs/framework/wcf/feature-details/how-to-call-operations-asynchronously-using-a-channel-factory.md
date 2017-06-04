---
title: "Vorgehensweise: Asynchrones Aufrufen von Vorg&#228;ngen mit einer Kanalfactory | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cc17dd47-b9ad-451c-a362-e36e0aac7ba0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Vorgehensweise: Asynchrones Aufrufen von Vorg&#228;ngen mit einer Kanalfactory
In diesem Thema wird beschrieben, wie ein Client auf einen Dienstvorgang asynchron zugreifen kann, wenn eine auf <xref:System.ServiceModel.ChannelFactory%601> basierende Clientanwendung verwendet wird.  \(Wenn Sie ein <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName>\-Objekt verwenden, um einen Dienst aufzurufen, können Sie das ereignisgesteuerte asynchrone Aufrufmodell verwenden.  Weitere Informationen finden Sie unter [Vorgehensweise: Asynchrones Aufrufen von Dienstvorgängen](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  Weitere Informationen über die Verwendung des ereignisgesteuerten asynchronen Aufrufmodells finden Sie unter [Multithreaded Programming with the Event\-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md).  
  
 Der in diesem Thema behandelte Dienst implementiert die `ICalculator`\-Schnittstelle.  Der Client kann die Vorgänge an dieser Schnittstelle asynchron aufrufen. Dies bedeutet, dass Vorgänge wie `Add` in zwei Methoden aufgeteilt werden, `BeginAdd` und `EndAdd`, wobei die erste den Aufruf einleitet und die zweite das Ergebnis abruft, wenn der Vorgang abgeschlossen ist.  Ein Beispiel für das asynchrone Implementieren eines Vorgangs in einem Dienst finden Sie unter [Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).  Einzelheiten zu synchronen und asynchronen Vorgängen finden Sie unter [Synchrone und asynchrone Vorgänge](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
## Verfahren  
  
#### So rufen Sie WCF\-Dienstvorgänge asynchron auf  
  
1.  Führen Sie das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)\-Tool mit der `/async`\-Option wie in folgendem Befehl dargestellt aus.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a  
  
    ```  
  
     Dies generiert eine asynchrone Clientversion des Dienstvertrags für den Vorgang.  
  
2.  Erstellen Sie eine Rückruffunktion, die aufgerufen wird, wenn der asynchrone Vorgang abgeschlossen ist, wie im folgenden Beispielcode dargestellt.  
  
     [!code-csharp[C_How_To_CF_Async#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#2)]
     [!code-vb[C_How_To_CF_Async#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#2)]  
  
3.  Zum asynchronen Aufrufen eines Dienstvorgangs erstellen Sie den Client, rufen Sie `Begin[Operation]` auf \(z. B. `BeginAdd`\), und geben Sie eine Rückruffunktion an, wie in folgendem Beispielcode dargestellt.  
  
     [!code-csharp[C_How_To_CF_Async#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#3)]
     [!code-vb[C_How_To_CF_Async#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#3)]  
  
     Wenn die Rückruffunktion ausgeführt wird, ruft der Client `End<operation>``EndAdd` \(z. B. \) auf, um das Ergebnis abzurufen.  
  
## Beispiel  
 Der Dienst, der mit dem im vorhergehenden Verfahren genutzten Clientcode verwendet wird, implementiert die `ICalculator`\-Schnittstelle, wie im folgenden Beispielcode gezeigt.  Auf der Seite des Diensts werden die `Add`\- und `Subtract`\-Vorgänge des Vertrags synchron von der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Laufzeit aufgerufen, auch wenn die vorangegangenen Schritte auf dem Client asynchron aufgerufen wurden.  Die `Multiply`\- und `Divide`\-Vorgänge werden verwendet, um den Dienst asynchron auf der Seite des Diensts aufzurufen, auch wenn der Client sie synchron aufruft.  Im folgenden Beispiel wird die <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>\-Eigenschaft auf `true` festgelegt.  Diese Eigenschaftseinstellung in Verbindung mit der Implementierung des asynchronen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Musters weist die Laufzeit an, den Vorgang asynchron aufzurufen.  
  
 [!code-csharp[C_How_To_CF_Async#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/service.cs#4)]
 [!code-vb[C_How_To_CF_Async#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/service.vb#4)]  
  
## Siehe auch  
 [Service Contract: Asynchronous Sample](http://msdn.microsoft.com/de-de/833db946-f511-4f64-a26f-2759a11217c7)