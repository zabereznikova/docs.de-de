---
title: "Windows Communication Foundation zu Message Queuing | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 78d0d0c9-648e-4d4a-8f0a-14d9cafeead9
caps.latest.revision: 32
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 32
---
# Windows Communication Foundation zu Message Queuing
In diesem Beispiel wird veranschaulicht, wie eine [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Anwendung eine Nachricht an eine MSMQ\-Anwendung \(Message Queuing\) senden kann.Der Dienst ist eine selbst gehostete Konsolenanwendung, die es Ihnen ermöglicht, den Dienst beim Empfang von Nachrichten in der Warteschlange zu beobachten.Der Dienst und der Client müssen dazu nicht gleichzeitig ausgeführt werden.  
  
 Der Dienst empfängt Nachrichten von der Warteschlange und verarbeitet Bestellungen.Der Dienst erstellt eine Transaktionswarteschlage und richtet einen "Nachricht empfangen"\-Nachrichtenhandler ein, wie im folgenden Beispielcode gezeigt.  
  
```  
static void Main(string[] args)  
{  
    if (!MessageQueue.Exists(  
              ConfigurationManager.AppSettings["queueName"]))  
       MessageQueue.Create(  
           ConfigurationManager.AppSettings["queueName"], true);  
        //Connect to the queue  
        MessageQueue Queue = new   
    MessageQueue(ConfigurationManager.AppSettings["queueName"]);  
    Queue.ReceiveCompleted +=   
                 new ReceiveCompletedEventHandler(ProcessOrder);  
    Queue.BeginReceive();  
    Console.WriteLine("Order Service is running");  
    Console.ReadLine();  
}  
  
```  
  
 Wenn die Nachricht in der Warteschlange empfangen wird, wird der Nachrichtenhandler `ProcessOrder` aufgerufen.  
  
```  
public static void ProcessOrder(Object source,  
    ReceiveCompletedEventArgs asyncResult)  
{  
    try  
    {  
        // Connect to the queue.  
        MessageQueue Queue = (MessageQueue)source;  
        // End the asynchronous receive operation.  
        System.Messaging.Message msg =   
                     Queue.EndReceive(asyncResult.AsyncResult);  
        msg.Formatter = new System.Messaging.XmlMessageFormatter(  
                                new Type[] { typeof(PurchaseOrder) });  
        PurchaseOrder po = (PurchaseOrder) msg.Body;  
        Random statusIndexer = new Random();  
        po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];  
        Console.WriteLine("Processing {0} ", po);  
        Queue.BeginReceive();  
    }  
    catch (System.Exception ex)  
    {  
        Console.WriteLine(ex.Message);  
    }  
  
}  
  
```  
  
 Der Dienst extrahiert die `ProcessOrder` aus dem MSMQ\-Nachrichtentext heraus und verarbeitet die Bestellung.  
  
 Der Name der MSMQ\-Warteschlange wird im appSettings\-Abschnitt der Konfigurationsdatei angegeben, wie in der folgenden Beispielkonfiguration gezeigt.  
  
```  
<appSettings>  
    <add key="orderQueueName" value=".\private$\Orders" />  
</appSettings>  
  
```  
  
> [!NOTE]
>  Im Warteschlangennamen wird ein Punkt \(.\) für den lokalen Computer verwendet, und in der Pfadangabe werden umgekehrte Schrägstriche als Trennzeichen verwendet.  
  
 Der Client erstellt eine Bestellung und reicht die Bestellung im Geltungsbereich der Transaktion ein, wie im folgenden Beispielcode gezeigt.  
  
```  
// Create the purchase order  
PurchaseOrder po = new PurchaseOrder();  
// Fill in the details  
...  
  
OrderProcessorClient client = new OrderProcessorClient("OrderResponseEndpoint");  
  
MsmqMessage<PurchaseOrder> ordermsg = new MsmqMessage<PurchaseOrder>(po);  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
    client.SubmitPurchaseOrder(ordermsg);  
    scope.Complete();  
}  
Console.WriteLine("Order has been submitted:{0}", po);  
  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
  
```  
  
 Der Client verwendet einen benutzerdefinierten Client zum Senden der MSMQ\-Nachricht an die Warteschlange.Da die Anwendung, die die Nachricht empfängt und verarbeitet, keine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\- sondern eine MSMQ\-Anwendung ist, besteht zwischen den beiden Anwendungen kein implizierter Dienstvertrag.Deshalb kann in diesem Szenario kein Proxy mit dem Tool "Svcutil.exe" erstellt werden.  
  
 Der benutzerdefinierte Client ist im Wesentlichen bei allen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendungen gleich, die die `MsmqIntegration`\-Bindung zum Senden von Nachrichten verwenden.Im Gegensatz zu anderen Clients enthält dieser keinen Bereich von Dienstvorgängen.Es ist nur ein Sende\-Nachricht\-Vorgang.  
  
```  
  
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Action = "*")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
}  
  
public partial class OrderProcessorClient : System.ServiceModel.ClientBase<IOrderProcessor>, IOrderProcessor  
{  
    public OrderProcessorClient(){}  
  
    public OrderProcessorClient(string configurationName)  
        : base(configurationName)  
    { }  
  
    public OrderProcessorClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)  
        : base(binding, address)  
    { }  
  
    public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
    {  
        base.Channel.SubmitPurchaseOrder(msg);  
    }  
}  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Client\- und Dienstaktivitäten sowohl im Dienst\- als auch Clientkonsolenfenster angezeigt.Sie können sehen, wie der Dienst Nachrichten vom Client empfängt.Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.Beachten Sie, dass aufgrund der Verwendung einer Warteschlange der Client und der Dienst nicht gleichzeitig ausgeführt werden müssen.Sie können beispielsweise den Client ausführen, ihn schließen und anschließend den Dienst starten, der dann trotzdem noch die Nachrichten des Clients empfängt.  
  
> [!NOTE]
>  Dieses Beispiel erfordert die Installation von Message Queuing.Informationen dazu finden Sie in den Installationsanweisungen unter [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=94968) \(möglicherweise nur in englischer Sprache\).  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist.Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt.Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ\-Warteschlangen\-Manager erstellen.Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:  
  
    1.  Öffnen Sie Server\-Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Erweitern Sie die Registerkarte **Funktionen**.  
  
    3.  Klicken Sie mit der rechten Maustaste auf **Private Meldungswarteschlangen**, und klicken Sie anschließend auf **Neu** und **Private Warteschlange**.  
  
    4.  Aktivieren Sie das Kontrollkästchen **Transaktional**.  
  
    5.  Geben Sie `ServiceModelSamplesTransacted` als Namen der neuen Warteschlange ein.  
  
3.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Um das Beispiel in einer Konfiguration mit einem einzigen Computer auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### So führen Sie das Beispiel computerübergreifend aus  
  
1.  Kopieren Sie die Dienstprogrammdateien aus dem Ordner \\service\\bin\\ \(unterhalb des sprachspezifischen Ordners\) auf den Dienstcomputer.  
  
2.  Kopieren Sie die Clientprogrammdateien aus dem Ordner \\client\\bin\\ \(unterhalb des sprachspezifischen Ordners\) auf den Clientcomputer.  
  
3.  Ändern Sie in der Datei Client.exe.config die Clientendpunktadresse, und geben Sie anstelle von "." den Namen des Dienstcomputers an.  
  
4.  Starten Sie auf dem Dienstcomputer Service.exe an einer Eingabeaufforderung.  
  
5.  Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\WcfToMsmq`  
  
## Siehe auch  
 [Vorgehensweise: Nachrichtenaustausch mit WCF\-Endpunkten und Message Queuing\-Anwendungen](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)   
 [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=94968)