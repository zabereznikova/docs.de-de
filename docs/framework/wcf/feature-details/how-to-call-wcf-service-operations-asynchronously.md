---
title: "Vorgehensweise: Asynchrones Aufrufen von WCF-Dienstvorg&#228;ngen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Vorgehensweise: Asynchrones Aufrufen von WCF-Dienstvorg&#228;ngen
In diesem Thema wird beschrieben, wie ein Client auf einen Dienstvorgang asynchron zugreifen kann.Der in diesem Thema behandelte Dienst implementiert die `ICalculator`\-Schnittstelle.Der Client kann mithilfe des ereignisgesteuerten asynchronen Aufrufmodells die Vorgänge asynchron an dieser Schnittstelle aufrufen.\(Weitere Informationen über die Verwendung des ereignisgesteuerten asynchronen Aufrufmodells finden Sie unter [Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster](http://go.microsoft.com/fwlink/?LinkId=248184).\)Ein Beispiel für das asynchrone Implementieren eines Vorgangs in einem Dienst finden Sie unter [Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).Weitere Informationen zu synchronen und asynchronen Vorgängen finden Sie unter [Synchrone und asynchrone Vorgänge](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
> [!NOTE]
>  Bei Verwendung einer <xref:System.ServiceModel.ChannelFactory%601> wird das ereignisgesteuerte asynchrone Aufrufmodell nicht unterstützt.Weitere Informationen zur Verwendung asynchroner Aufrufe mit <xref:System.ServiceModel.ChannelFactory%601> finden Sie unter [Vorgehensweise: Asynchrones Aufrufen von Vorgängen mit einer Kanalfactory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).  
  
## Vorgehensweise  
  
#### So rufen Sie WCF\-Dienstvorgänge asynchron auf  
  
1.  Führen Sie das Tool [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) unter Angabe der beiden Befehlsoptionen `/async` und `/tcv:Version35` wie in folgendem Befehl dargestellt aus.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     Damit wird neben den synchronen Vorgängen und den standardmäßigen delegatenbasierten asynchronen Vorgängen eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientklasse erstellt, die Folgendes enthält:  
  
    -   Zwei \<`operationName`\>`Async`\-Vorgänge zur Verwendung mit dem ereignisbasierten asynchronen Aufrufmodell.Beispiel:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   Ereignisse, die nach Beendigung des Vorgangs ausgelöst werden und das Format \<`operationName`\>`Completed` haben, zur Verwendung mit dem ereignisbasierten asynchronen Aufrufmodell.Beispiel:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   <xref:System.EventArgs?displayProperty=fullName>\-Typen für jeden Vorgang \(im Format \<`operationName`\>`CompletedEventArgs`\) zur Verwendung mit dem ereignisbasierten asynchronen Aufrufmodell.Beispiel:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2.  Erstellen Sie in der aufrufenden Anwendung eine Rückrufmethode, die aufgerufen wird, wenn der asynchrone Vorgang abgeschlossen ist, wie im folgenden Beispielcode dargestellt.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3.  Vor dem Aufruf des Vorgangs verwenden Sie einen generischen <xref:System.EventHandler%601?displayProperty=fullName> vom Typ \<`operationName`\>`EventArgs`, um die Handlermethode \(die im vorigen Schritt erstellt wurde\) dem \<`operationName`\>`Completed`\-Ereignis hinzuzufügen.Dann rufen Sie die \<`operationName`\>`Async`\-Methode auf.Beispiel:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## Beispiel  
  
> [!NOTE]
>  Die Entwurfsrichtlinien für das ereignisbasierte asynchrone Modell besagen, dass in den Fällen, in denen mehr als ein Wert zurückgegeben wird, ein Wert in der `Result`\-Eigenschaft und die übrigen Werte in Eigenschaften des <xref:System.EventArgs>\-Objekts zurückgegeben werden sollen.Wenn ein Client Metadaten mithilfe der ereignisbasierten asynchronen Befehlsoptionen importiert und der Vorgang mehr als einen Wert zurückgibt, dann gibt das <xref:System.EventArgs>\-Objekt infolgedessen einen Wert in der `Result`\-Eigenschaft zurück, und die übrigen Werte werden in Eigenschaften des <xref:System.EventArgs>\-Objekts zurückgegeben. Wenn das Nachrichtenobjekt in der `Result`\-Eigenschaft und die Rückgabewerte als Eigenschaften dieses Objekts übermittelt werden sollen, verwenden Sie die Befehlsoption `/messageContract`.Damit wird eine Signatur generiert, bei der die Antwortnachricht in der `Result`\-Eigenschaft des <xref:System.EventArgs>\-Objekts zurückgegeben wird.Alle internen Rückgabewerte sind dann Eigenschaften des Antwortnachrichtenobjekts.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## Siehe auch  
 [Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)