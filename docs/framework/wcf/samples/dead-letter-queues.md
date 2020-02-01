---
title: Warteschlangen für unzustellbare Meldungen
ms.date: 03/30/2017
ms.assetid: ff664f33-ad02-422c-9041-bab6d993f9cc
ms.openlocfilehash: 5025aa784817d1189f23918eacfef275abf968e1
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921435"
---
# <a name="dead-letter-queues"></a><span data-ttu-id="af52a-102">Warteschlangen für unzustellbare Meldungen</span><span class="sxs-lookup"><span data-stu-id="af52a-102">Dead Letter Queues</span></span>
<span data-ttu-id="af52a-103">Dieses Beispiel veranschaulicht das Behandeln und Verarbeiten von Nachrichten mit Fehlern bei der Zustellung.</span><span class="sxs-lookup"><span data-stu-id="af52a-103">This sample demonstrates how to handle and process messages that have failed delivery.</span></span> <span data-ttu-id="af52a-104">Es basiert auf dem [transaktiven MSMQ-Bindungs](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="af52a-104">It is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="af52a-105">In diesem Beispiel wird die `netMsmqBinding`-Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="af52a-105">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="af52a-106">Der Dienst ist eine selbst gehostete Konsolenanwendung, die es Ihnen ermöglicht, den Dienst beim Empfang von Nachrichten in der Warteschlange zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="af52a-106">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

> [!NOTE]
> <span data-ttu-id="af52a-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="af52a-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="af52a-108">Dieses Beispiel veranschaulicht jede Warteschlange für unzustellbare Nachrichten, die nur unter Windows Vista verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="af52a-108">This sample demonstrates each application dead letter queue that is only available on Windows Vista.</span></span> <span data-ttu-id="af52a-109">Das Beispiel kann so geändert werden, dass die standardmäßigen systemweiten Warteschlangen für MSMQ 3,0 unter Windows Server 2003 und Windows XP verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="af52a-109">The sample can be modified to use the default system-wide queues for MSMQ 3.0 on Windows Server 2003 and Windows XP.</span></span>

 <span data-ttu-id="af52a-110">In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="af52a-110">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="af52a-111">Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet.</span><span class="sxs-lookup"><span data-stu-id="af52a-111">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="af52a-112">Der Dienst empfängt Nachrichten aus der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="af52a-112">The service receives messages from the queue.</span></span> <span data-ttu-id="af52a-113">Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="af52a-113">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>

 <span data-ttu-id="af52a-114">Da die Kommunikation über Warteschlangen zu einer gewissen Verzögerung führen kann, können Sie der Nachricht eine Gültigkeitsdauer zuweisen, um sicherzustellen, dass die Nachricht nach Ablauf der Gültigkeit nicht mehr an die Anwendung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="af52a-114">Because queued communication can involve a certain amount of dormancy, you may want to associate a time-to-live value on the message to ensure that the message does not get delivered to the application if it has gone past the time.</span></span> <span data-ttu-id="af52a-115">Es gibt auch Fälle, in denen eine Anwendung informiert werden muss, wenn eine Nachricht nicht zugestellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="af52a-115">There are also cases, where an application must be informed whether a message failed delivery.</span></span> <span data-ttu-id="af52a-116">In derartigen Fällen, wenn beispielsweise die Gültigkeitsdauer der Nachricht abgelaufen ist, oder wenn die Nachricht nicht zugestellt werden konnte, werden die Nachrichten in der Warteschlange für unzustellbare Nachrichten abgelegt.</span><span class="sxs-lookup"><span data-stu-id="af52a-116">In all of these cases, such as when the time-to-live on the message has expired or the message failed delivery, the message is put in a dead letter queue.</span></span> <span data-ttu-id="af52a-117">Die sendende Anwendung kann die Nachricht daraufhin in der Warteschlange für unzustellbare Nachrichten lesen und Korrekturmaßnahmen ergreifen. Diese reichen von keiner Maßnahme bis zur Behebung der Ursache für die Unzustellbarkeit der Nachricht und erneuter Sendung.</span><span class="sxs-lookup"><span data-stu-id="af52a-117">The sending application can then read the messages in the dead-letter queue and take corrective actions that range from no action to correcting the reasons for failed delivery and resending the message.</span></span>

 <span data-ttu-id="af52a-118">Die Warteschlange für unzustellbare Nachrichten in der `NetMsmqBinding`-Bindung wird in den folgenden Eigenschaften ausgedrückt:</span><span class="sxs-lookup"><span data-stu-id="af52a-118">The dead-letter queue in the `NetMsmqBinding` binding is expressed in the following properties:</span></span>

- <span data-ttu-id="af52a-119"><xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A>-Eigenschaft, um die vom Client benötigte Art der Warteschlange für unzustellbare Nachrichten auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="af52a-119"><xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> property to express the kind of dead-letter queue required by the client.</span></span> <span data-ttu-id="af52a-120">Diese Enumeration verfügt über folgende Werte:</span><span class="sxs-lookup"><span data-stu-id="af52a-120">This enumeration has the following values:</span></span>

- <span data-ttu-id="af52a-121">`None`: Für den Client ist keine Warteschlange für unzustellbare Nachrichten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="af52a-121">`None`: No dead-letter queue is required by the client.</span></span>

- <span data-ttu-id="af52a-122">`System`: Die Systemwarteschlange für unzustellbare Nachrichten wird verwendet, um unzustellbare Nachrichten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="af52a-122">`System`: The system dead-letter queue is used to store dead messages.</span></span> <span data-ttu-id="af52a-123">Die Systemwarteschlange für unzustellbare Nachrichten wird von allen Anwendungen verwendet, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="af52a-123">The system dead-letter queue is shared by all applications running on the computer.</span></span>

- <span data-ttu-id="af52a-124">`Custom`: Die in der <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>-Eigenschaft angegebene benutzerdefinierte Warteschlange für unzustellbare Nachrichten wird verwendet, um unzustellbare Nachrichten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="af52a-124">`Custom`: A custom dead-letter queue specified using the <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> property is used to store dead messages.</span></span> <span data-ttu-id="af52a-125">Diese Funktion ist nur unter Windows Vista verfügbar.</span><span class="sxs-lookup"><span data-stu-id="af52a-125">This feature is only available on Windows Vista.</span></span> <span data-ttu-id="af52a-126">Dieser Wert wird verwendet, wenn die Anwendung ihre eigene Warteschlange für unzustellbare Nachrichten verwenden muss und diese nicht mit anderen Anwendungen auf dem gleichen Computer gemeinsam verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="af52a-126">This is used when the application must use its own dead letter queue instead of sharing it with other applications running on the same computer.</span></span>

- <span data-ttu-id="af52a-127"><xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>-Eigenschaft, um die spezifische Warteschlange für unzustellbare Nachrichten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="af52a-127"><xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> property to express the specific queue to use as a dead-letter queue.</span></span> <span data-ttu-id="af52a-128">Diese ist nur in Windows Vista verfügbar.</span><span class="sxs-lookup"><span data-stu-id="af52a-128">This is available only in Windows Vista.</span></span>

 <span data-ttu-id="af52a-129">In diesem Beispiel sendet der Client einen Stapel von Nachrichten aus dem Bereich der Transaktion an den Dienst und legt einen willkürlichen niedrigen Wert für die Gültigkeitsdauer für diese Nachrichten fest (ca. 2 Sekunden).</span><span class="sxs-lookup"><span data-stu-id="af52a-129">In this sample, the client sends a batch of messages to the service from within the scope of a transaction and specifies an arbitrarily low value for "time-to-live" for these messages (about 2 seconds).</span></span> <span data-ttu-id="af52a-130">Der Client gibt auch eine benutzerdefinierte Warteschlange für unzustellbare Nachrichten an, in der abgelaufene Nachrichten abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="af52a-130">The client also specifies a custom dead-letter queue to use to enqueue the messages that have expired.</span></span>

 <span data-ttu-id="af52a-131">Die Clientanwendung kann die Nachrichten in der Warteschlange für unzustellbare Nachrichten lesen und entweder versuchen, diese erneut zu senden, oder den Fehler beheben, der dazu führte, dass die Nachricht in der Warteschlange für unzustellbare Nachrichten abgelegt wurde, und die Nachricht dann senden.</span><span class="sxs-lookup"><span data-stu-id="af52a-131">The client application can read the messages in the dead-letter queue and either retry sending the message or correct the error that caused the original message to be placed in the dead-letter queue and send the message.</span></span> <span data-ttu-id="af52a-132">Im Beispiel zeigt der Client eine Fehlermeldung an.</span><span class="sxs-lookup"><span data-stu-id="af52a-132">In the sample, the client displays an error message.</span></span>

 <span data-ttu-id="af52a-133">Der Dienstvertrag lautet `IOrderProcessor`, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="af52a-133">The service contract is `IOrderProcessor`, as shown in the following sample code.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 <span data-ttu-id="af52a-134">Der Dienst Code im Beispiel ist der der [transaktiven MSMQ-Bindung](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span><span class="sxs-lookup"><span data-stu-id="af52a-134">The service code in the sample is that of the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span></span>

 <span data-ttu-id="af52a-135">Die Kommunikation mit dem Dienst findet innerhalb des Bereichs der Transaktion statt.</span><span class="sxs-lookup"><span data-stu-id="af52a-135">Communication with the service takes place within the scope of a transaction.</span></span> <span data-ttu-id="af52a-136">Der Dienst liest die Nachrichten in der Warteschlange, führt den Vorgang aus und zeigt anschließend die Ergebnisse des Vorgangs an.</span><span class="sxs-lookup"><span data-stu-id="af52a-136">The service reads messages from the queue, performs the operation and then displays the results of the operation.</span></span> <span data-ttu-id="af52a-137">Die Anwendung erstellt auch eine Warteschlange für unzustellbare Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="af52a-137">The application also creates a dead-letter queue for dead-letter messages.</span></span>

```csharp
//The service contract is defined in generatedClient.cs, generated from the service by the svcutil tool.

//Client implementation code.
class Client
{
    static void Main()
    {
        // Get MSMQ queue name from app settings in configuration
        string deadLetterQueueName = ConfigurationManager.AppSettings["deadLetterQueueName"];

        // Create the transacted MSMQ queue for storing dead message if necessary.
        if (!MessageQueue.Exists(deadLetterQueueName))
            MessageQueue.Create(deadLetterQueueName, true);

        // Create a proxy with given client endpoint configuration
        OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");

        // Create the purchase order
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

        //Create a transaction scope.
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            // Make a queued call to submit the purchase order
            client.SubmitPurchaseOrder(po);
            // Complete the transaction.
            scope.Complete();
        }

        client.Close();

        Console.WriteLine();
        Console.WriteLine("Press <ENTER> to terminate client.");
        Console.ReadLine();
    }
}
```

 <span data-ttu-id="af52a-138">Die Konfiguration des Clients gibt eine kurze Zeitspanne an, während derer die Nachricht den Dienst erreichen muss.</span><span class="sxs-lookup"><span data-stu-id="af52a-138">The client's configuration specifies a short duration for the message to reach the service.</span></span> <span data-ttu-id="af52a-139">Wenn die Nachricht innerhalb der festgelegten Zeitspanne nicht übermittelt werden kann, läuft die Nachricht ab und wird in die Warteschlange für unzustellbare Nachrichten verschoben.</span><span class="sxs-lookup"><span data-stu-id="af52a-139">If the message cannot be transmitted within the duration specified, the message expires and is moved to the dead-letter queue.</span></span>

> [!NOTE]
> <span data-ttu-id="af52a-140">Der Client kann die Nachricht innerhalb der angegebenen Zeitspanne an die Dienstwarteschlange übermitteln.</span><span class="sxs-lookup"><span data-stu-id="af52a-140">It is possible for the client to deliver the message to the service queue within the specified time.</span></span> <span data-ttu-id="af52a-141">Um sicherzustellen, dass Sie die Ausführung des Diensts für unzustellbare Nachrichten beobachten können, sollten Sie den Client vor dem Start des Diensts ausführen.</span><span class="sxs-lookup"><span data-stu-id="af52a-141">To ensure you see the dead-letter service in action, you should run the client before starting the service.</span></span> <span data-ttu-id="af52a-142">Die Nachricht überschreitet das Zeitlimit und wird an den Dienst für unzustellbaren Nachrichten übermittelt.</span><span class="sxs-lookup"><span data-stu-id="af52a-142">The message times out and is delivered to the dead-letter service.</span></span>

 <span data-ttu-id="af52a-143">Die Anwendung muss definieren, welche der Warteschlangen als Warteschlange für unzustellbare Nachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="af52a-143">The application must define which queue to use as its dead-letter queue.</span></span> <span data-ttu-id="af52a-144">Wenn keine Warteschlange angegeben wird, wird die systemweite Standardtransaktionswarteschlange für unzustellbare Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="af52a-144">If no queue is specified, the default system-wide transactional dead-letter queue is used to queue dead messages.</span></span> <span data-ttu-id="af52a-145">In diesem Beispiel gibt die Clientanwendung ihre eigene Anwendungswarteschlange für unzustellbare Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="af52a-145">In this example, the client application specifies its own application dead-letter queue.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
    <!-- use appSetting to configure MSMQ Dead Letter queue name -->
    <add key="deadLetterQueueName" value=".\private$\ServiceModelSamplesOrdersAppDLQ"/>
  </appSettings>

  <system.serviceModel>
    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"
                binding="netMsmqBinding"
                bindingConfiguration="PerAppDLQBinding"
                contract="IOrderProcessor" />
    </client>

    <bindings>
      <netMsmqBinding>
        <binding name="PerAppDLQBinding"
                 deadLetterQueue="Custom"
                 customDeadLetterQueue="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"
                 timeToLive="00:00:02"/>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>

</configuration>
```

 <span data-ttu-id="af52a-146">Der Dienst für unzustellbare Nachrichten liest Nachrichten aus der Warteschlange für unzustellbare Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="af52a-146">The dead-letter message service reads messages from the dead-letter queue.</span></span> <span data-ttu-id="af52a-147">Der Dienst für unzustellbare Nachrichten implementiert den `IOrderProcessor`-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="af52a-147">The dead-letter message service implements the `IOrderProcessor` contract.</span></span> <span data-ttu-id="af52a-148">Seine Implementierung dient jedoch nicht der Verarbeitung von Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="af52a-148">Its implementation however is not to process orders.</span></span> <span data-ttu-id="af52a-149">Der Dienst für unzustellbare Nachrichten ist ein Clientdienst und besitzt keine Funktion für die Verarbeitung von Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="af52a-149">The dead-letter message service is a client service and does not have the facility to process orders.</span></span>

> [!NOTE]
> <span data-ttu-id="af52a-150">Die Warteschlange für unzustellbare Nachrichten ist eine Clientwarteschlange und befindet sich lokal zum Clientwarteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="af52a-150">The dead-letter queue is a client queue and is local to the client queue manager.</span></span>

 <span data-ttu-id="af52a-151">Die Implementierung des Dienst für unzustellbare Nachrichten überprüft die Ursache für die fehlgeschlagene Zustellung und ergreift Abhilfemaßnahmen.</span><span class="sxs-lookup"><span data-stu-id="af52a-151">The dead-letter message service implementation checks for the reason a message failed delivery and takes corrective measures.</span></span> <span data-ttu-id="af52a-152">Die Ursache für die fehlgeschlagene Zustellung wird in zwei Enumerationen, <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryFailure%2A> und <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryStatus%2A>, aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="af52a-152">The reason for a message failure is captured in two enumerations, <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryFailure%2A> and <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryStatus%2A>.</span></span> <span data-ttu-id="af52a-153">Sie können die <xref:System.ServiceModel.Channels.MsmqMessageProperty> vom <xref:System.ServiceModel.OperationContext> abrufen, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="af52a-153">You can retrieve the <xref:System.ServiceModel.Channels.MsmqMessageProperty> from the <xref:System.ServiceModel.OperationContext> as shown in the following sample code:</span></span>

```csharp
public void SubmitPurchaseOrder(PurchaseOrder po)
{
    Console.WriteLine("Submitting purchase order did not succeed ", po);
    MsmqMessageProperty mqProp =
                  OperationContext.Current.IncomingMessageProperties[
                  MsmqMessageProperty.Name] as MsmqMessageProperty;
    Console.WriteLine("Message Delivery Status: {0} ",
                                                mqProp.DeliveryStatus);
    Console.WriteLine("Message Delivery Failure: {0}",
                                               mqProp.DeliveryFailure);
    Console.WriteLine();
    …
}
```

 <span data-ttu-id="af52a-154">Nachrichten in der Warteschlange für unzustellbare Nachrichten sind Nachrichten, die an den Dienst adressiert sind, der die Nachricht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="af52a-154">Messages in the dead-letter queue are messages that are addressed to the service that is processing the message.</span></span> <span data-ttu-id="af52a-155">Wenn der Dienst für unzustellbare Nachrichten Nachrichten aus der Warteschlange liest, findet daher die Windows Communication Foundation (WCF)-Kanal Ebene die nicht Übereinstimmung in Endpunkten und versendet die Nachricht nicht.</span><span class="sxs-lookup"><span data-stu-id="af52a-155">Therefore, when the dead-letter message service reads messages from the queue, the Windows Communication Foundation (WCF) channel layer finds the mismatch in endpoints and does not dispatch the message.</span></span> <span data-ttu-id="af52a-156">In diesem Fall ist die Nachricht an den Auftragsverarbeitungsdienst adressiert, wird jedoch vom Dienst für unzustellbare Nachrichten empfangen.</span><span class="sxs-lookup"><span data-stu-id="af52a-156">In this case, the message is addressed to the order processing service but is received by the dead-letter message service.</span></span> <span data-ttu-id="af52a-157">Um Nachrichten zu empfangen, die an einen anderen Endpunkt adressiert sind, wird im `ServiceBehavior` ein Adressfilter für alle Adressen angegeben.</span><span class="sxs-lookup"><span data-stu-id="af52a-157">To receive a message that is addressed to a different endpoint, an address filter to match any address is specified in the `ServiceBehavior`.</span></span> <span data-ttu-id="af52a-158">Dies ist erforderlich, um Nachrichten, die aus der Warteschlange für unzustellbare Nachrichten gelesen werden, erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="af52a-158">This is required to successfully process messages that are read from the dead-letter queue.</span></span>

 <span data-ttu-id="af52a-159">In diesem Beispiel sendet der Nachrichtendienst für unzustellbare Nachrichten die Nachricht erneut, wenn der Grund für den Fehler darin besteht, dass die Nachricht abgelaufen ist. Aus allen anderen Gründen wird der Übermittlungs Fehler angezeigt, wie im folgenden Beispielcode gezeigt:</span><span class="sxs-lookup"><span data-stu-id="af52a-159">In this sample, the dead-letter message service resends the message if the reason for failure is that the message timed out. For all other reasons, it displays the delivery failure, as shown in the following sample code:</span></span>

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Single, ConcurrencyMode=ConcurrencyMode.Single, AddressFilterMode=AddressFilterMode.Any)]
public class PurchaseOrderDLQService : IOrderProcessor
{
    OrderProcessorClient orderProcessorService;
    public PurchaseOrderDLQService()
    {
        orderProcessorService = new OrderProcessorClient("OrderProcessorEndpoint");
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Console.WriteLine("Submitting purchase order did not succeed ", po);
        MsmqMessageProperty mqProp = OperationContext.Current.IncomingMessageProperties[MsmqMessageProperty.Name] as MsmqMessageProperty;

        Console.WriteLine("Message Delivery Status: {0} ", mqProp.DeliveryStatus);
        Console.WriteLine("Message Delivery Failure: {0}", mqProp.DeliveryFailure);
        Console.WriteLine();

        // resend the message if timed out
        if (mqProp.DeliveryFailure == DeliveryFailure.ReachQueueTimeout ||
            mqProp.DeliveryFailure == DeliveryFailure.ReceiveTimeout)
        {
            // re-send
            Console.WriteLine("Purchase order Time To Live expired");
            Console.WriteLine("Trying to resend the message");

            // reuse the same transaction used to read the message from dlq to enqueue the message to app. queue
            orderProcessorService.SubmitPurchaseOrder(po);
            Console.WriteLine("Purchase order resent");
        }
    }

    // Host the service within this EXE console application.
    public static void Main()
    {
        // Create a ServiceHost for the PurchaseOrderDLQService type.
        using (ServiceHost serviceHost = new ServiceHost(typeof(PurchaseOrderDLQService)))
        {
            // Open the ServiceHostBase to create listeners and start listening for messages.
            serviceHost.Open();

            // The service can now be accessed.
            Console.WriteLine("The dead letter service is ready.");
            Console.WriteLine("Press <ENTER> to terminate service.");
            Console.WriteLine();
            Console.ReadLine();
        }
    }
}
```

 <span data-ttu-id="af52a-160">Im folgenden Beispiel wird die Konfiguration für eine unzustellbare Nachricht veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="af52a-160">The following sample shows the configuration for a dead-letter message:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.PurchaseOrderDLQService">
        <!-- Define NetMsmqEndpoint in this case, DLQ end point to read messages-->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"
                  binding="netMsmqBinding"
                  bindingConfiguration="DefaultBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
      </service>
    </services>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                 address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"
                 binding="netMsmqBinding"
                 bindingConfiguration="SystemDLQBinding"
                 contract="IOrderProcessor" />
    </client>

    <bindings>
      <netMsmqBinding>
        <binding name="DefaultBinding" />
        <binding name="SystemDLQBinding"
                 deadLetterQueue="System"/>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

 <span data-ttu-id="af52a-161">Wenn das Beispiel ausgeführt wird, müssen drei Programmdateien ausgeführt werden, um zu beobachten, wie die Warteschlange für unzustellbare Nachrichten für jede Anwendung funktioniert. Der Client, der Dienst und ein Dienst für unzustellbare Nachrichten, der in allen Anwendungen in der Warteschlange für unzustellbare Nachrichten liest und die Nachricht erneut an den Dienst sendet.</span><span class="sxs-lookup"><span data-stu-id="af52a-161">In running the sample, there are 3 executables to run to see how the dead-letter queue works for each application; the client, service and a dead-letter service that reads from the dead-letter queue for each application and resends the message to the service.</span></span> <span data-ttu-id="af52a-162">Alle sind Konsolenanwendungen mit Ausgabe in Konsolenfenster.</span><span class="sxs-lookup"><span data-stu-id="af52a-162">All are console applications with output in console windows.</span></span>

> [!NOTE]
> <span data-ttu-id="af52a-163">Aufgrund der Verwendung einer Warteschlange müssen der Client und der Dienst nicht gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="af52a-163">Because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="af52a-164">Sie können den Client ausführen, ihn schließen und anschließend den Dienst starten, der dann trotzdem noch die Nachrichten des Clients empfängt.</span><span class="sxs-lookup"><span data-stu-id="af52a-164">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span> <span data-ttu-id="af52a-165">Sie sollten den Dienst starten und wieder schließen, damit die Warteschlange erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="af52a-165">You should start the service and shut it down so that the queue can be created.</span></span>

 <span data-ttu-id="af52a-166">Wenn der Client ausgeführt wird, zeigt er die folgende Nachricht an:</span><span class="sxs-lookup"><span data-stu-id="af52a-166">When running the client, the client displays the message:</span></span>

```console
Press <ENTER> to terminate client.
```

 <span data-ttu-id="af52a-167">Der Client hat versucht, die Nachricht zu senden, aufgrund des kurzen Zeitlimits ist die Nachricht jedoch abgelaufen und befindet sich jetzt in der Warteschlange für unzustellbare Nachrichten für jede Anwendung.</span><span class="sxs-lookup"><span data-stu-id="af52a-167">The client attempted to send the message but with a short timeout, the message expired and is now queued in the dead-letter queue for each application.</span></span>

 <span data-ttu-id="af52a-168">Anschließend führen Sie den Dienst für unzustellbare Nachrichten aus, der die Nachrichten liest, den Fehlercode anzeigt und die Nachricht zurück an den Dienst sendet.</span><span class="sxs-lookup"><span data-stu-id="af52a-168">You then run the dead-letter service, which reads the message and displays the error code and resends the message back to the service.</span></span>

```console
The dead letter service is ready.
Press <ENTER> to terminate service.

Submitting purchase order did not succeed
Message Delivery Status: InDoubt
Message Delivery Failure: ReachQueueTimeout

Purchase order Time To Live expired
Trying to resend the message
Purchase order resent
```

 <span data-ttu-id="af52a-169">Der Dienst startet, liest dann die erneut gesendeten Nachrichten und verarbeitet sie.</span><span class="sxs-lookup"><span data-stu-id="af52a-169">The service starts and then reads the resent message and processes it.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 97897eff-f926-4057-a32b-af8fb11b9bf9
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="af52a-170">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="af52a-170">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="af52a-171">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="af52a-171">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="af52a-172">Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="af52a-172">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="af52a-173">Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="af52a-173">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="af52a-174">Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen.</span><span class="sxs-lookup"><span data-stu-id="af52a-174">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="af52a-175">Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="af52a-175">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="af52a-176">Öffnen Sie Server-Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="af52a-176">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="af52a-177">Erweitern Sie die Registerkarte **Features** .</span><span class="sxs-lookup"><span data-stu-id="af52a-177">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="af52a-178">Klicken Sie mit der rechten Maustaste auf private Meldungs **Warteschlangen**, und wählen Sie **neu**, **private**</span><span class="sxs-lookup"><span data-stu-id="af52a-178">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="af52a-179">Aktivieren Sie das Kontrollkästchen **transaktional** .</span><span class="sxs-lookup"><span data-stu-id="af52a-179">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="af52a-180">Geben Sie `ServiceModelSamplesTransacted` als Namen für die neue Warteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="af52a-180">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="af52a-181">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="af52a-181">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="af52a-182">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, ändern Sie die Warteschlangen Namen entsprechend, indem Sie localhost durch den vollständigen Namen des Computers ersetzen, und befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="af52a-182">To run the sample in a single- or cross-computer configuration change queue names appropriately, replacing localhost with full name of the computer and follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="af52a-183">So führen Sie das Beispiel auf einem Computer aus, der zu einer Arbeitsgruppe gehört</span><span class="sxs-lookup"><span data-stu-id="af52a-183">To run the sample on a computer joined to a workgroup</span></span>

1. <span data-ttu-id="af52a-184">Wenn Ihr Computer nicht zu einer Domäne gehört, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf `None` festlegen, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="af52a-184">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding name="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

     <span data-ttu-id="af52a-185">Stellen Sie sicher, dass der Endpunkt der Bindung zugeordnet ist, indem Sie das `bindingConfiguration`-Attribut des Endpunkts festlegen.</span><span class="sxs-lookup"><span data-stu-id="af52a-185">Ensure the endpoint is associated with the binding by setting the endpoint's `bindingConfiguration` attribute.</span></span>

2. <span data-ttu-id="af52a-186">Ändern Sie die Konfiguration auf dem DeadLetterService, dem Server und dem Client, bevor Sie das Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="af52a-186">Ensure that you change the configuration on the DeadLetterService, server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="af52a-187">Das Festlegen von `security mode` auf `None` entspricht dem Festlegen von `MsmqAuthenticationMode`, `MsmqProtectionLevel` und der `Message`-Sicherheit auf `None`.</span><span class="sxs-lookup"><span data-stu-id="af52a-187">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel` and `Message` security to `None`.</span></span>

## <a name="comments"></a><span data-ttu-id="af52a-188">Comments</span><span class="sxs-lookup"><span data-stu-id="af52a-188">Comments</span></span>
 <span data-ttu-id="af52a-189">Standardmäßig wird mit der `netMsmqBinding`-Bindung die Transportsicherheit aktiviert.</span><span class="sxs-lookup"><span data-stu-id="af52a-189">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="af52a-190">Der Typ der Transportsicherheit wird durch zwei Eigenschaften festgelegt: `MsmqAuthenticationMode` und `MsmqProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="af52a-190">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="af52a-191">Standardmäßig wird der Authentifizierungsmodus auf `Windows` festgelegt, und die Schutzebene wird auf `Sign` gesetzt.</span><span class="sxs-lookup"><span data-stu-id="af52a-191">By default the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="af52a-192">Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es ein Teil einer Domäne sein.</span><span class="sxs-lookup"><span data-stu-id="af52a-192">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="af52a-193">Wenn Sie dieses Beispiel auf einem Computer ausführen, der nicht Teil einer Domäne ist, wird folgende Fehlermeldung ausgegeben: "Das interne Message Queuing-Zertifikat für diesen Benutzer ist nicht vorhanden".</span><span class="sxs-lookup"><span data-stu-id="af52a-193">If you run this sample on a computer that is not part of a domain, you receive the following error: "User's internal message queuing certificate does not exist".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af52a-194">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="af52a-194">The samples may already be installed on your computer.</span></span> <span data-ttu-id="af52a-195">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="af52a-195">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="af52a-196">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="af52a-196">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="af52a-197">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="af52a-197">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\DeadLetter`  
