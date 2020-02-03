---
title: Nachrichtenkorrelation
ms.date: 03/30/2017
ms.assetid: 3f62babd-c991-421f-bcd8-391655c82a1f
ms.openlocfilehash: 9ded0886920f9f0b3d2f9b441061253b42a1c567
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747168"
---
# <a name="message-correlation"></a>Nachrichtenkorrelation

Dieses Beispiel veranschaulicht, wie eine Message Queuing (MSMQ)-Anwendung eine MSMQ-Nachricht an einen Windows Communication Foundation (WCF)-Dienst senden kann und wie Nachrichten zwischen Absender-und Empfänger Anwendungen in einem Anforderungs-/Antwort-Szenario korreliert werden können. In diesem Beispiel wird die msmqIntegrationBinding-Bindung verwendet. Der Dienst ist in diesem Fall eine selbst gehostete Konsolenanwendung, sodass Sie den Dienst beobachten können, der Nachrichten in Warteschlangen empfängt. k

 Der Dienst verarbeitet die vom Sender empfangene Nachricht und sendet eine Antwortnachricht zurück an den Sender. Der Sender korreliert die Antwort, die er auf die ursprünglich gesendete Anforderung empfangen hat. Die `MessageID`-Eigenschaft und die `CorrelationID`-Eigenschaft der Nachricht werden zum Korrelieren der Anforderungs- und Antwortnachrichten verwendet.

 Der `IOrderProcessor`-Dienstvertrag definiert einen unidirektionalen Dienstvorgang, der für die Verwendung mit Warteschlangen geeignet ist. Eine MSMQ-Nachricht verfügt über keinen Aktionsheader, d h. es ist nicht möglich, verschiedene MSMQ-Nachrichten Vorgangsverträgen automatisch zuzuordnen. Deshalb kann es in diesem Fall nur einen Vorgangsvertrag geben. Wenn Sie mehrere Vorgangsverträge in dem Dienst definieren möchten, muss die Anwendung Informationen darüber bereitstellen, anhand welchen Headers in der MSMQ-Nachricht (z. B. die Bezeichnung oder die CorrelationID) entschieden werden kann, welcher Vorgangsvertrag verteilt werden soll.

 Die MSMQ-Nachricht enthält auch keine Informationen darüber, welche Header den verschiedenen Parametern des Vorgangsvertrags zugeordnet sind. Daher kann sich im Vorgangsvertrag nur ein Parameter befinden. Der-Parameter ist vom Typ <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, der die zugrunde liegende MSMQ-Nachricht enthält. Der Typ "T" in der `MsmqMessage<T>`-Klasse stellt die Daten dar, die in den MSMQ-Nachrichtentext serialisiert sind. In diesem Beispiel wird der `PurchaseOrder`-Typ zum MSMQ-Nachrichtentext serialisiert.

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
[ServiceKnownType(typeof(PurchaseOrder))]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}
```

 Der Dienstvorgang verarbeitet die Bestellung und zeigt den Inhalt der Bestellung und deren Status im Dienstkonsolenfenster an. Das <xref:System.ServiceModel.OperationBehaviorAttribute> konfiguriert, dass der Vorgang in eine Transaktion mit der Warteschlange eingetragen wird und dass die Transaktion als abgeschlossen gekennzeichnet wird, wenn der Vorgang zurückkehrt. Die `PurchaseOrder` enthält die Bestellungsdetails, die vom Dienst verarbeitet werden müssen.

```csharp
// Service class that implements the service contract.
public class OrderProcessorService : IOrderProcessor
{
   [OperationBehavior(TransactionScopeRequired = true,
          TransactionAutoComplete = true)]
   public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> ordermsg)
   {
       PurchaseOrder po = (PurchaseOrder)ordermsg.Body;
       Random statusIndexer = new Random();
       po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];
       Console.WriteLine("Processing {0} ", po);
       //Send a response to the client that the order has been received
         and is pending fullfillment.
       SendResponse(ordermsg);
    }

    private void SendResponse(MsmqMessage<PurchaseOrder> ordermsg)
    {
        OrderResponseClient client = new OrderResponseClient("OrderResponseEndpoint");

        //Set the correlation ID such that the client can correlate the response to the order.
        MsmqMessage<PurchaseOrder> orderResponsemsg = new MsmqMessage<PurchaseOrder>(ordermsg.Body);
        orderResponsemsg.CorrelationId = ordermsg.Id;
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            client.SendOrderResponse(orderResponsemsg);
            scope.Complete();
        }

        client.Close();
    }
}
```

 Der Dienst verwendet einen benutzerdefinierten `OrderResponseClient`-Client zum Senden der MSMQ-Nachricht an die Warteschlange. Da es sich bei der Anwendung, die die Nachricht empfängt und verarbeitet, um eine MSMQ-Anwendung und nicht um eine WCF-Anwendung handelt, gibt es keinen impliziten Dienstvertrag zwischen den beiden Anwendungen. Deshalb kann in diesem Szenario kein Proxy mit dem Tool Svcutil.exe erstellt werden.

 Der benutzerdefinierte Proxy ist für alle WCF-Anwendungen, die die `msmqIntegrationBinding` Bindung zum Senden von Nachrichten verwenden, im Wesentlichen identisch. Im Gegensatz zu anderen Proxys enthält dieser keinen Bereich von Dienstvorgängen. Es ist nur ein Sende-Nachricht-Vorgang.

```csharp
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IOrderResponse
{

    [System.ServiceModel.OperationContractAttribute(IsOneWay = true, Action = "*")]
    void SendOrderResponse(MsmqMessage<PurchaseOrder> msg);
}

public partial class OrderResponseClient : System.ServiceModel.ClientBase<IOrderResponse>, IOrderResponse
{

    public OrderResponseClient()
    { }

    public OrderResponseClient(string configurationName)
        : base(configurationName)
    { }

    public OrderResponseClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)
        : base(binding, address)
    { }

    public void SendOrderResponse(MsmqMessage<PurchaseOrder> msg)
    {
        base.Channel.SendOrderResponse(msg);
    }
}
```

 Der Dienst ist selbst gehostet. Bei Verwendung des MSMQ-Integrationstransports muss die Warteschlange im Voraus erstellt werden. Dies kann manuell erfolgen oder mithilfe eines Codes. In diesem Beispiel enthält der Dienst <xref:System.Messaging>-Code, um zu überprüfen, ob die Warteschlange bereits vorhanden ist, und um sie andernfalls zu erstellen. Der Warteschlangenname wird aus der Konfigurationsdatei gelesen.

```csharp
public static void Main()
{
       // Get the MSMQ queue name from application settings in configuration.
      string queueName =
                ConfigurationManager.AppSettings["orderQueueName"];
      // Create the transacted MSMQ queue if necessary.
      if (!MessageQueue.Exists(queueName))
                MessageQueue.Create(queueName, true);
     // Create a ServiceHost for the OrderProcessorService type.
     using (ServiceHost serviceHost = new
                   ServiceHost(typeof(OrderProcessorService)))
     {
            serviceHost.Open();
            // The service can now be accessed.
            Console.WriteLine("The service is ready.");
            Console.WriteLine("Press <ENTER> to terminate service.");
            Console.ReadLine();
            // Close the ServiceHost to shutdown the service.
            serviceHost.Close();
      }
}
```

 Die MSMQ-Warteschlange, an die die Bestellanforderungen gesendet werden, wird im Abschnitt "appSettings" in der Konfigurationsdatei angegeben. Die Client- und Dienstendpunkte werden im Abschnitt "system.serviceModel" der Konfigurationsdatei definiert. Beide geben die `msmqIntegrationbinding`-Bindung an.

```xml
<appSettings>
  <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>

<system.serviceModel>
  <client>
    <endpoint    name="OrderResponseEndpoint"
              address="msmq.formatname:DIRECT=OS:.\private$\OrderResponse"
              binding="msmqIntegrationBinding"
              bindingConfiguration="OrderProcessorBinding"
              contract="Microsoft.ServiceModel.Samples.IOrderResponse">
    </endpoint>
  </client>

  <services>
    <service
      name="Microsoft.ServiceModel.Samples.OrderProcessorService">
      <endpoint address="msmq.formatname:DIRECT=OS:.\private$\Orders"
                            binding="msmqIntegrationBinding"
                bindingConfiguration="OrderProcessorBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor">
      </endpoint>
    </service>
  </services>

  <bindings>
    <msmqIntegrationBinding>
      <binding name="OrderProcessorBinding" >
        <security mode="None" />
      </binding>
    </msmqIntegrationBinding>
  </bindings>

</system.serviceModel>
```

 Die Clientanwendung verwendet <xref:System.Messaging>, um eine permanente und Transaktionsnachricht an die Warteschlange zu senden. Der Text der Nachricht enthält die Bestellung.

```csharp
static void PlaceOrder()
{
    //Connect to the queue
    MessageQueue orderQueue =
            new MessageQueue(
                    ConfigurationManager.AppSettings["orderQueueName"])
    // Create the purchase order.
    PurchaseOrder po = new PurchaseOrder();
    po.CustomerId = "somecustomer.com";
    po.PONumber = Guid.NewGuid().ToString();
    PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();
    lineItem1.ProductId = "Blue Widget";
    lineItem1.Quantity = 54;
    lineItem1.UnitCost = 29.99F;

    PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();
    lineItem2.ProductId = "Red Widget";
    lineItem2.Quantity = 890;
    lineItem2.UnitCost = 45.89F;

    po.orderLineItems = new PurchaseOrderLineItem[2];
    po.orderLineItems[0] = lineItem1;
    po.orderLineItems[1] = lineItem2;

    Message msg = new Message();
    msg.UseDeadLetterQueue = true;
    msg.Body = po;

    //Create a transaction scope.
    using (TransactionScope scope = new
     TransactionScope(TransactionScopeOption.Required))
    {
        // Submit the purchase order.
        orderQueue.Send(msg, MessageQueueTransactionType.Automatic);
        // Complete the transaction.
        scope.Complete();
    }
    //Save the messageID for order response correlation.
    orderMessageID = msg.Id;
    Console.WriteLine("Placed the order, waiting for response...");
}
```

 Die MSMQ-Warteschlange, aus der die Bestellantworten empfangen werden, wird in einem appSettings-Abschnitt der Konfigurationsdatei angegeben, wie in der folgenden Beispielkonfiguration gezeigt.

> [!NOTE]
> Im Warteschlangennamen wird ein Punkt (.) für den lokalen Computer verwendet, und in der Pfadangabe werden umgekehrte Schrägstriche als Trennzeichen verwendet. Die WCF-Endpunkt Adresse gibt ein MSMQ. Format Name-Schema an und verwendet "localhost" für den lokalen Computer. Im URI steht hinter msmq.formatname ein korrekt aufgebauter Formatname gemäß MSMQ-Richtlinien.

```xml
<appSettings>
    <add key=" orderResponseQueueName" value=".\private$\Orders" />
</appSettings>
```

 Die Clientanwendung speichert die `messageID` der Bestellungsanforderungsnachricht, die sie an den Dienst sendet, und wartet auf eine Antwort vom Dienst. Sobald in der Warteschlange eine Antwort eingeht, korreliert der Client diese mit der Bestellnachricht, die er mit der `correlationID`-Eigenschaft der Nachricht gesendet hat, die die `messageID` der Bestellnachricht enthält, die der Dienst ursprünglich an den Dienst gesendet hat.

```csharp
static void DisplayOrderStatus()
{
    MessageQueue orderResponseQueue = new
     MessageQueue(ConfigurationManager.AppSettings
                  ["orderResponseQueueName"]);
    //Create a transaction scope.
    bool responseReceived = false;
    orderResponseQueue.MessageReadPropertyFilter.CorrelationId = true;
    while (!responseReceived)
    {
       Message responseMsg;
       using (TransactionScope scope2 = new
         TransactionScope(TransactionScopeOption.Required))
       {
          //Receive the Order Response message.
          responseMsg =
              orderResponseQueue.Receive
                   (MessageQueueTransactionType.Automatic);
          scope2.Complete();
     }
     responseMsg.Formatter = new
     System.Messaging.XmlMessageFormatter(new Type[] {
         typeof(PurchaseOrder) });
     PurchaseOrder responsepo = (PurchaseOrder)responseMsg.Body;
    //Check if the response is for the order placed.
    if (orderMessageID == responseMsg.CorrelationId)
    {
       responseReceived = true;
       Console.WriteLine("Status of current Order: OrderID-{0},Order
            Status-{1}", responsepo.PONumber, responsepo.Status);
    }
    else
    {
       Console.WriteLine("Status of previous Order: OrderID-{0},Order
            Status-{1}", responsepo.PONumber, responsepo.Status);
    }
  }
}
```

 Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt. Sie können sehen, dass der Dienst Nachrichten vom Client empfängt und eine Antwort an den Client zurücksendet. Der Client zeigt die vom Dienst empfangene Antwort an. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.

> [!NOTE]
> Dieses Beispiel erfordert die Installation von Message Queuing (MSMQ). Informationen dazu finden Sie in den MSMQ-Installationsanleitungen im Abschnitt "Siehe auch".

## <a name="set-up-build-and-run-the-sample"></a>Einrichten, erstellen und Ausführen des Beispiels

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist. Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt. Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen. Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:

    1. Öffnen Sie Server-Manager in Visual Studio 2012.

    2. Erweitern Sie die Registerkarte **Features** .

    3. Klicken Sie mit der rechten Maustaste auf private Meldungs **Warteschlangen**, und wählen Sie **neu**, **private**

    4. Aktivieren Sie das Kontrollkästchen **transaktional** .

    5. Geben Sie `ServiceModelSamplesTransacted` als Namen für die neue Warteschlange ein.

3. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.

4. Um das Beispiel in einer Konfiguration mit einem einzelnen Computer auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).

## <a name="run-the-sample-across-computers"></a>Führen Sie das Beispiel Computer übergreifend aus.

1. Kopieren Sie die Dienstprogrammdateien aus dem Ordner \service\bin\ (unterhalb des sprachspezifischen Ordners) auf den Dienstcomputer.

2. Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.

3. Ändern Sie in der Datei Client.exe.config den Wert von orderQueueName, und geben Sie anstelle von "." den Namen des Dienstcomputers an.

4. Ändern Sie in der Datei Service.exe.config die Clientendpunktadresse, und geben Sie anstelle von "." den Namen des Clientcomputers an.

5. Starten Sie auf dem Dienstcomputer Service.exe an einer Eingabeaufforderung.

6. Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MessageCorrelation`

## <a name="see-also"></a>Weitere Informationen

- [Queuing in WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
- [Message Queuing](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))
