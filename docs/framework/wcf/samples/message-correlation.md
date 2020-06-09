---
title: Nachrichtenkorrelation
ms.date: 03/30/2017
ms.assetid: 3f62babd-c991-421f-bcd8-391655c82a1f
ms.openlocfilehash: 84b10b507f9fdaa7c53cf937bb132c8cc0aac33f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591633"
---
# <a name="message-correlation"></a><span data-ttu-id="39b37-102">Nachrichtenkorrelation</span><span class="sxs-lookup"><span data-stu-id="39b37-102">Message Correlation</span></span>

<span data-ttu-id="39b37-103">Dieses Beispiel veranschaulicht, wie eine Message Queuing (MSMQ)-Anwendung eine MSMQ-Nachricht an einen Windows Communication Foundation (WCF)-Dienst senden kann und wie Nachrichten zwischen Absender-und Empfänger Anwendungen in einem Anforderungs-/Antwort-Szenario korreliert werden können.</span><span class="sxs-lookup"><span data-stu-id="39b37-103">This sample demonstrates how a Message Queuing (MSMQ) application can send an MSMQ message to a Windows Communication Foundation (WCF) service and how messages can be correlated between sender and receiver applications in a request/response scenario.</span></span> <span data-ttu-id="39b37-104">In diesem Beispiel wird die msmqIntegrationBinding-Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="39b37-104">This sample uses the msmqIntegrationBinding binding.</span></span> <span data-ttu-id="39b37-105">Der Dienst ist in diesem Fall eine selbst gehostete Konsolenanwendung, sodass Sie den Dienst beobachten können, der Nachrichten in Warteschlangen empfängt.</span><span class="sxs-lookup"><span data-stu-id="39b37-105">The service in this case is a self-hosted console application to allow you to observe the service that receives queued messages.</span></span> <span data-ttu-id="39b37-106">k</span><span class="sxs-lookup"><span data-stu-id="39b37-106">k</span></span>

 <span data-ttu-id="39b37-107">Der Dienst verarbeitet die vom Sender empfangene Nachricht und sendet eine Antwortnachricht zurück an den Sender.</span><span class="sxs-lookup"><span data-stu-id="39b37-107">The service processes the message received from the sender and sends a response message back to the sender.</span></span> <span data-ttu-id="39b37-108">Der Sender korreliert die Antwort, die er auf die ursprünglich gesendete Anforderung empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="39b37-108">The sender correlates the response it received to the request it sent originally.</span></span> <span data-ttu-id="39b37-109">Die `MessageID`-Eigenschaft und die `CorrelationID`-Eigenschaft der Nachricht werden zum Korrelieren der Anforderungs- und Antwortnachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="39b37-109">The `MessageID` and `CorrelationID` properties of the message are used to correlate the request and response messages.</span></span>

 <span data-ttu-id="39b37-110">Der `IOrderProcessor`-Dienstvertrag definiert einen unidirektionalen Dienstvorgang, der für die Verwendung mit Warteschlangen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="39b37-110">The `IOrderProcessor` service contract defines a one-way service operation that is suitable for use with queuing.</span></span> <span data-ttu-id="39b37-111">Eine MSMQ-Nachricht verfügt über keinen Aktionsheader, d h. es ist nicht möglich, verschiedene MSMQ-Nachrichten Vorgangsverträgen automatisch zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="39b37-111">An MSMQ message does not have an Action header, so it is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="39b37-112">Deshalb kann es in diesem Fall nur einen Vorgangsvertrag geben.</span><span class="sxs-lookup"><span data-stu-id="39b37-112">Therefore, there can be only one operation contract in this case.</span></span> <span data-ttu-id="39b37-113">Wenn Sie mehrere Vorgangsverträge in dem Dienst definieren möchten, muss die Anwendung Informationen darüber bereitstellen, anhand welchen Headers in der MSMQ-Nachricht (z. B. die Bezeichnung oder die CorrelationID) entschieden werden kann, welcher Vorgangsvertrag verteilt werden soll.</span><span class="sxs-lookup"><span data-stu-id="39b37-113">If you want to define more operation contracts in the service, the application must provide information as to which header in the MSMQ message (for example, the label, or correlationID) can be used to decide which operation contract to dispatch.</span></span>

 <span data-ttu-id="39b37-114">Die MSMQ-Nachricht enthält auch keine Informationen darüber, welche Header den verschiedenen Parametern des Vorgangsvertrags zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="39b37-114">The MSMQ message also does not contain information as to which headers are mapped to the different parameters of the operation contract.</span></span> <span data-ttu-id="39b37-115">Daher kann sich im Vorgangsvertrag nur ein Parameter befinden.</span><span class="sxs-lookup"><span data-stu-id="39b37-115">Therefore, there can be only one parameter in the operation contract.</span></span> <span data-ttu-id="39b37-116">Der-Parameter ist vom Typ <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601> , der die zugrunde liegende MSMQ-Nachricht enthält.</span><span class="sxs-lookup"><span data-stu-id="39b37-116">The parameter is of type <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, which contains the underlying MSMQ message.</span></span> <span data-ttu-id="39b37-117">Der Typ "T" in der `MsmqMessage<T>`-Klasse stellt die Daten dar, die in den MSMQ-Nachrichtentext serialisiert sind.</span><span class="sxs-lookup"><span data-stu-id="39b37-117">The type "T" in the `MsmqMessage<T>` class represents the data that is serialized into the MSMQ message body.</span></span> <span data-ttu-id="39b37-118">In diesem Beispiel wird der `PurchaseOrder`-Typ zum MSMQ-Nachrichtentext serialisiert.</span><span class="sxs-lookup"><span data-stu-id="39b37-118">In this sample, the `PurchaseOrder` type is serialized into the MSMQ message body.</span></span>

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
[ServiceKnownType(typeof(PurchaseOrder))]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}
```

 <span data-ttu-id="39b37-119">Der Dienstvorgang verarbeitet die Bestellung und zeigt den Inhalt der Bestellung und deren Status im Dienstkonsolenfenster an.</span><span class="sxs-lookup"><span data-stu-id="39b37-119">The service operation processes the purchase order and displays the contents of the purchase order and its status in the service console window.</span></span> <span data-ttu-id="39b37-120">Das <xref:System.ServiceModel.OperationBehaviorAttribute> konfiguriert, dass der Vorgang in eine Transaktion mit der Warteschlange eingetragen wird und dass die Transaktion als abgeschlossen gekennzeichnet wird, wenn der Vorgang zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="39b37-120">The <xref:System.ServiceModel.OperationBehaviorAttribute> configures the operation to enlist in a transaction with the queue and to mark the transaction complete when the operation returns.</span></span> <span data-ttu-id="39b37-121">Die `PurchaseOrder` enthält die Bestellungsdetails, die vom Dienst verarbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="39b37-121">The `PurchaseOrder` contains the order details that must be processed by the service.</span></span>

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

 <span data-ttu-id="39b37-122">Der Dienst verwendet einen benutzerdefinierten `OrderResponseClient`-Client zum Senden der MSMQ-Nachricht an die Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="39b37-122">The service uses a custom client `OrderResponseClient` to send the MSMQ message to the queue.</span></span> <span data-ttu-id="39b37-123">Da es sich bei der Anwendung, die die Nachricht empfängt und verarbeitet, um eine MSMQ-Anwendung und nicht um eine WCF-Anwendung handelt, gibt es keinen impliziten Dienstvertrag zwischen den beiden Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="39b37-123">Because the application that receives and processes the message is an MSMQ application and not a WCF application, there is no implicit service contract between the two applications.</span></span> <span data-ttu-id="39b37-124">Deshalb kann in diesem Szenario kein Proxy mit dem Tool Svcutil.exe erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="39b37-124">So we cannot create a proxy using the Svcutil.exe tool in this scenario.</span></span>

 <span data-ttu-id="39b37-125">Der benutzerdefinierte Proxy ist für alle WCF-Anwendungen, die die- `msmqIntegrationBinding` Bindung zum Senden von Nachrichten verwenden, im Wesentlichen identisch.</span><span class="sxs-lookup"><span data-stu-id="39b37-125">The custom proxy is essentially the same for all WCF applications that use the `msmqIntegrationBinding` binding to send messages.</span></span> <span data-ttu-id="39b37-126">Im Gegensatz zu anderen Proxys enthält dieser keinen Bereich von Dienstvorgängen.</span><span class="sxs-lookup"><span data-stu-id="39b37-126">Unlike other proxies, it does not include a range of service operations.</span></span> <span data-ttu-id="39b37-127">Es ist nur ein Sende-Nachricht-Vorgang.</span><span class="sxs-lookup"><span data-stu-id="39b37-127">It is a submit message operation only.</span></span>

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

 <span data-ttu-id="39b37-128">Der Dienst ist selbst gehostet.</span><span class="sxs-lookup"><span data-stu-id="39b37-128">The service is self hosted.</span></span> <span data-ttu-id="39b37-129">Bei Verwendung des MSMQ-Integrationstransports muss die Warteschlange im Voraus erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="39b37-129">When using the MSMQ integration transport, the queue used must be created in advance.</span></span> <span data-ttu-id="39b37-130">Dies kann manuell erfolgen oder mithilfe eines Codes.</span><span class="sxs-lookup"><span data-stu-id="39b37-130">This can be done manually or through code.</span></span> <span data-ttu-id="39b37-131">In diesem Beispiel enthält der Dienst <xref:System.Messaging>-Code, um zu überprüfen, ob die Warteschlange bereits vorhanden ist, und um sie andernfalls zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="39b37-131">In this sample, the service contains <xref:System.Messaging> code to check for the existence of the queue and create it if necessary.</span></span> <span data-ttu-id="39b37-132">Der Warteschlangenname wird aus der Konfigurationsdatei gelesen.</span><span class="sxs-lookup"><span data-stu-id="39b37-132">The queue name is read from the configuration file.</span></span>

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

 <span data-ttu-id="39b37-133">Die MSMQ-Warteschlange, an die die Bestellanforderungen gesendet werden, wird im Abschnitt "appSettings" in der Konfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="39b37-133">The MSMQ queue to which the order requests are sent is specified in the appSettings section of the configuration file.</span></span> <span data-ttu-id="39b37-134">Die Client- und Dienstendpunkte werden im Abschnitt "system.serviceModel" der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="39b37-134">The client and service endpoints are defined in the system.serviceModel section of the configuration file.</span></span> <span data-ttu-id="39b37-135">Beide geben die `msmqIntegrationbinding`-Bindung an.</span><span class="sxs-lookup"><span data-stu-id="39b37-135">Both specify the `msmqIntegrationbinding` binding.</span></span>

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

 <span data-ttu-id="39b37-136">Die Clientanwendung verwendet <xref:System.Messaging>, um eine permanente und Transaktionsnachricht an die Warteschlange zu senden.</span><span class="sxs-lookup"><span data-stu-id="39b37-136">The client application uses <xref:System.Messaging> to send a durable and transactional message to the queue.</span></span> <span data-ttu-id="39b37-137">Der Text der Nachricht enthält die Bestellung.</span><span class="sxs-lookup"><span data-stu-id="39b37-137">The message's body contains the purchase order.</span></span>

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

 <span data-ttu-id="39b37-138">Die MSMQ-Warteschlange, aus der die Bestellantworten empfangen werden, wird in einem appSettings-Abschnitt der Konfigurationsdatei angegeben, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="39b37-138">The MSMQ queue from which the order responses are received is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="39b37-139">Im Warteschlangennamen wird ein Punkt (.) für den lokalen Computer verwendet, und in der Pfadangabe werden umgekehrte Schrägstriche als Trennzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="39b37-139">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="39b37-140">Die WCF-Endpunkt Adresse gibt ein MSMQ. Format Name-Schema an und verwendet "localhost" für den lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="39b37-140">The WCF endpoint address specifies a msmq.formatname scheme, and uses "localhost" for the local computer.</span></span> <span data-ttu-id="39b37-141">Im URI steht hinter msmq.formatname ein korrekt aufgebauter Formatname gemäß MSMQ-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="39b37-141">A properly formed format name follows msmq.formatname in the URI according to MSMQ guidelines.</span></span>

```xml
<appSettings>
    <add key=" orderResponseQueueName" value=".\private$\Orders" />
</appSettings>
```

 <span data-ttu-id="39b37-142">Die Clientanwendung speichert die `messageID` der Bestellungsanforderungsnachricht, die sie an den Dienst sendet, und wartet auf eine Antwort vom Dienst.</span><span class="sxs-lookup"><span data-stu-id="39b37-142">The client application saves the `messageID` of the order request message that it sends to the service and waits for a response from the service.</span></span> <span data-ttu-id="39b37-143">Sobald in der Warteschlange eine Antwort eingeht, korreliert der Client diese mit der Bestellnachricht, die er mit der `correlationID`-Eigenschaft der Nachricht gesendet hat, die die `messageID` der Bestellnachricht enthält, die der Dienst ursprünglich an den Dienst gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="39b37-143">Once a response arrives in the queue the client correlates it with the order message it sent using the `correlationID` property of the message, which contains the `messageID` of the order message that the client sent to the service originally.</span></span>

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

 <span data-ttu-id="39b37-144">Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39b37-144">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="39b37-145">Sie können sehen, dass der Dienst Nachrichten vom Client empfängt und eine Antwort an den Client zurücksendet.</span><span class="sxs-lookup"><span data-stu-id="39b37-145">You can see the service receive messages from the client and sends a response back to the client.</span></span> <span data-ttu-id="39b37-146">Der Client zeigt die vom Dienst empfangene Antwort an.</span><span class="sxs-lookup"><span data-stu-id="39b37-146">The client displays the response received from the service.</span></span> <span data-ttu-id="39b37-147">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="39b37-147">Press ENTER in each console window to shut down the service and client.</span></span>

> [!NOTE]
> <span data-ttu-id="39b37-148">Dieses Beispiel erfordert die Installation von Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="39b37-148">This sample requires the installation of Message Queuing (MSMQ).</span></span> <span data-ttu-id="39b37-149">Informationen dazu finden Sie in den MSMQ-Installationsanleitungen im Abschnitt "Siehe auch".</span><span class="sxs-lookup"><span data-stu-id="39b37-149">See the MSMQ installation instructions in the See Also section.</span></span>

## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="39b37-150">Einrichten, erstellen und Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="39b37-150">Set up, build, and run the sample</span></span>

1. <span data-ttu-id="39b37-151">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="39b37-151">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="39b37-152">Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="39b37-152">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="39b37-153">Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="39b37-153">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="39b37-154">Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen.</span><span class="sxs-lookup"><span data-stu-id="39b37-154">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="39b37-155">Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="39b37-155">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="39b37-156">Öffnen Sie Server-Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="39b37-156">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="39b37-157">Erweitern Sie die Registerkarte **Features** .</span><span class="sxs-lookup"><span data-stu-id="39b37-157">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="39b37-158">Klicken Sie mit der rechten Maustaste auf private Meldungs **Warteschlangen**, und wählen Sie **neu**, **private**</span><span class="sxs-lookup"><span data-stu-id="39b37-158">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="39b37-159">Aktivieren Sie das Kontrollkästchen **transaktional** .</span><span class="sxs-lookup"><span data-stu-id="39b37-159">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="39b37-160">Geben Sie `ServiceModelSamplesTransacted` als Namen für die neue Warteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="39b37-160">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="39b37-161">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="39b37-161">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="39b37-162">Um das Beispiel in einer Konfiguration mit einem einzelnen Computer auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="39b37-162">To run the sample in a single-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

## <a name="run-the-sample-across-computers"></a><span data-ttu-id="39b37-163">Führen Sie das Beispiel Computer übergreifend aus.</span><span class="sxs-lookup"><span data-stu-id="39b37-163">Run the sample across computers</span></span>

1. <span data-ttu-id="39b37-164">Kopieren Sie die Dienstprogrammdateien aus dem Ordner \service\bin\ (unterhalb des sprachspezifischen Ordners) auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="39b37-164">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>

2. <span data-ttu-id="39b37-165">Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="39b37-165">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>

3. <span data-ttu-id="39b37-166">Ändern Sie in der Datei Client.exe.config den Wert von orderQueueName, und geben Sie anstelle von "." den Namen des Dienstcomputers an.</span><span class="sxs-lookup"><span data-stu-id="39b37-166">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>

4. <span data-ttu-id="39b37-167">Ändern Sie in der Datei Service.exe.config die Clientendpunktadresse, und geben Sie anstelle von "." den Namen des Clientcomputers an.</span><span class="sxs-lookup"><span data-stu-id="39b37-167">In the Service.exe.config file, change the client endpoint address to specify the client computer name instead of ".".</span></span>

5. <span data-ttu-id="39b37-168">Starten Sie auf dem Dienstcomputer Service.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="39b37-168">On the service computer, launch Service.exe from a command prompt.</span></span>

6. <span data-ttu-id="39b37-169">Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="39b37-169">On the client computer, launch Client.exe from a command prompt.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39b37-170">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="39b37-170">The samples may already be installed on your computer.</span></span> <span data-ttu-id="39b37-171">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="39b37-171">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="39b37-172">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39b37-172">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="39b37-173">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="39b37-173">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MessageCorrelation`

## <a name="see-also"></a><span data-ttu-id="39b37-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39b37-174">See also</span></span>

- [<span data-ttu-id="39b37-175">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="39b37-175">Queuing in WCF</span></span>](../feature-details/queuing-in-wcf.md)
- <span data-ttu-id="39b37-176">[Message Queuing](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="39b37-176">[Message Queuing](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span></span>
