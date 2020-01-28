---
title: Message Queuing zu Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 6d718eb0-9f61-4653-8a75-d2dac8fb3520
ms.openlocfilehash: 541ea23e6748242db57661ceda8e1fedecb66884
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747117"
---
# <a name="message-queuing-to-windows-communication-foundation"></a><span data-ttu-id="96556-102">Message Queuing zu Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="96556-102">Message Queuing to Windows Communication Foundation</span></span>

<span data-ttu-id="96556-103">Dieses Beispiel veranschaulicht, wie eine Message Queuing (MSMQ)-Anwendung eine MSMQ-Nachricht an einen Windows Communication Foundation (WCF)-Dienst senden kann.</span><span class="sxs-lookup"><span data-stu-id="96556-103">This sample demonstrates how a Message Queuing (MSMQ) application can send an MSMQ message to a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="96556-104">Der Dienst ist eine selbst gehostete Konsolenanwendung, die es Ihnen ermöglicht, den Dienst beim Empfang von Nachrichten in der Warteschlange zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="96556-104">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

 <span data-ttu-id="96556-105">Der Dienstvertrag ist `IOrderProcessor`, der einen unidirektionalen Dienst definiert, der für die Verwendung mit Warteschlangen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="96556-105">The service contract is `IOrderProcessor`, which defines a one-way service that is suitable for use with queues.</span></span> <span data-ttu-id="96556-106">Eine MSMQ-Nachricht verfügt über keinen Aktionsheader, d h. es ist nicht möglich, verschiedene MSMQ-Nachrichten Vorgangsverträgen automatisch zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="96556-106">An MSMQ message does not have an Action header, so it is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="96556-107">Deshalb kann es nur einen Vorgangsvertrag geben.</span><span class="sxs-lookup"><span data-stu-id="96556-107">Therefore, there can be only one operation contract.</span></span> <span data-ttu-id="96556-108">Wenn Sie mehr als einen Vorgangsvertrag für den Dienst definieren möchten, muss die Anwendung Informationen darüber bereitstellen, welcher Header in der MSMQ-Nachricht (z. B. die Bezeichnung oder CorrelationID) für die Entscheidung, welcher Vorgangsvertrag erteilt werden soll, verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="96556-108">If you want to define more than one operation contract for the service, the application must provide information as to which header in the MSMQ message (for example, the label or correlationID) can be used to decide which operation contract to dispatch.</span></span>

 <span data-ttu-id="96556-109">Die MSMQ-Nachricht enthält keine Informationen darüber, welche Header den verschiedenen Parametern des Vorgangsvertrags zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="96556-109">The MSMQ message does not contain information as to which headers are mapped to the different parameters of the operation contract.</span></span> <span data-ttu-id="96556-110">Der Parameter ist vom Typ <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`), der die zugrunde liegende MSMQ-Nachricht enthält.</span><span class="sxs-lookup"><span data-stu-id="96556-110">The parameter is of type <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`), which contains the underlying MSMQ message.</span></span> <span data-ttu-id="96556-111">Der Typ "T" in der Klasse <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`) steht für die Daten, die zum MSMQ-Nachrichtentext serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="96556-111">The type "T" in the <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`) class represents the data that is serialized into the MSMQ message body.</span></span> <span data-ttu-id="96556-112">In diesem Beispiel wird der `PurchaseOrder`-Typ zum MSMQ-Nachrichtentext serialisiert.</span><span class="sxs-lookup"><span data-stu-id="96556-112">In this sample, the `PurchaseOrder` type is serialized into the MSMQ message body.</span></span>

 <span data-ttu-id="96556-113">Im folgenden Beispielcode wird der Dienstvertrag des Diensts für die Auftragsverarbeitung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="96556-113">The following sample code shows the service contract of the order processing service.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
[ServiceKnownType(typeof(PurchaseOrder))]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}
```

 <span data-ttu-id="96556-114">Der Dienst ist selbst gehostet.</span><span class="sxs-lookup"><span data-stu-id="96556-114">The service is self hosted.</span></span> <span data-ttu-id="96556-115">Bei Verwendung von MSMQ muss die Warteschlange im Voraus erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="96556-115">When using MSMQ, the queue used must be created in advance.</span></span> <span data-ttu-id="96556-116">Dies kann manuell erfolgen oder mithilfe eines Codes.</span><span class="sxs-lookup"><span data-stu-id="96556-116">This can be done manually or through code.</span></span> <span data-ttu-id="96556-117">In diesem Beispiel prüft der Dienst, ob die Warteschlange vorhanden ist, und erstellt sie gegebenenfalls.</span><span class="sxs-lookup"><span data-stu-id="96556-117">In this sample, the service checks for the existence of the queue and creates it if required.</span></span> <span data-ttu-id="96556-118">Der Warteschlangenname wird aus der Konfigurationsdatei gelesen.</span><span class="sxs-lookup"><span data-stu-id="96556-118">The queue name is read from the configuration file.</span></span>

```csharp
public static void Main()
{
    // Get the MSMQ queue name from the application settings in
    // configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];
    // Create the MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName, true);
    …
}
```

 <span data-ttu-id="96556-119">Der Dienst erstellt und öffnet einen <xref:System.ServiceModel.ServiceHost> für den `OrderProcessorService`, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="96556-119">The service creates and opens a <xref:System.ServiceModel.ServiceHost> for the `OrderProcessorService`, as shown in the following sample code.</span></span>

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
{
    serviceHost.Open();
    Console.WriteLine("The service is ready.");
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.ReadLine();
    serviceHost.Close();
}
```

 <span data-ttu-id="96556-120">Der Name der MSMQ-Warteschlange wird im appSettings-Abschnitt der Konfigurationsdatei angegeben, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="96556-120">The MSMQ queue name is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="96556-121">Im Warteschlangennamen wird ein Punkt (.) für den lokalen Computer verwendet, und in der Pfadangabe werden umgekehrte Schrägstriche als Trennzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="96556-121">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="96556-122">Die WCF-Endpunkt Adresse gibt ein MSMQ. Format Name-Schema an und verwendet "localhost" für den lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="96556-122">The WCF endpoint address specifies a msmq.formatname scheme, and uses localhost for the local computer.</span></span> <span data-ttu-id="96556-123">Die Adresse der Warteschlange für jeden MSMQ-Formatnamen, der sich auf Richtlinien bezieht, folgt dem msmq.formatname-Schema.</span><span class="sxs-lookup"><span data-stu-id="96556-123">The address of the queue for each MSMQ Format Name addressing guidelines follows the msmq.formatname scheme.</span></span>

```xml
<appSettings>
    <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>
```

 <span data-ttu-id="96556-124">Die Clientanwendung ist eine MSMQ-Anwendung, die sich der <xref:System.Messaging.MessageQueue.Send%2A>-Methode bedient, um eine permanente Transaktionsnachricht an die Warteschlange zu senden, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="96556-124">The client application is an MSMQ application that uses the <xref:System.Messaging.MessageQueue.Send%2A> method to send a durable and transactional message to the queue, as shown in the following sample code.</span></span>

```csharp
//Connect to the queue.
MessageQueue orderQueue = new MessageQueue(ConfigurationManager.AppSettings["orderQueueName"]);

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

// Submit the purchase order.
Message msg = new Message();
msg.Body = po;
//Create a transaction scope.
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{

    orderQueue.Send(msg, MessageQueueTransactionType.Automatic);
    // Complete the transaction.
    scope.Complete();

}
Console.WriteLine("Placed the order:{0}", po);
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

 <span data-ttu-id="96556-125">Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="96556-125">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="96556-126">Sie können sehen, wie der Dienst Nachrichten vom Client empfängt.</span><span class="sxs-lookup"><span data-stu-id="96556-126">You can see the service receive messages from the client.</span></span> <span data-ttu-id="96556-127">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="96556-127">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="96556-128">Beachten Sie, dass aufgrund der Verwendung einer Warteschlange der Client und der Dienst nicht gleichzeitig ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="96556-128">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="96556-129">Sie können beispielsweise den Client ausführen, ihn schließen und anschließend den Dienst starten, der dann trotzdem noch die Nachrichten des Clients empfängt.</span><span class="sxs-lookup"><span data-stu-id="96556-129">For example, you could run the client, shut it down, and then start up the service and it would still receive its messages.</span></span>

## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="96556-130">Einrichten, erstellen und Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="96556-130">Set up, build, and run the sample</span></span>

1. <span data-ttu-id="96556-131">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="96556-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="96556-132">Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="96556-132">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="96556-133">Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="96556-133">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="96556-134">Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen.</span><span class="sxs-lookup"><span data-stu-id="96556-134">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="96556-135">Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="96556-135">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="96556-136">Öffnen Sie Server-Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="96556-136">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="96556-137">Erweitern Sie die Registerkarte **Features** .</span><span class="sxs-lookup"><span data-stu-id="96556-137">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="96556-138">Klicken Sie mit der rechten Maustaste auf private Meldungs **Warteschlangen**, und wählen Sie **neu**, **private**</span><span class="sxs-lookup"><span data-stu-id="96556-138">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="96556-139">Aktivieren Sie das Kontrollkästchen **transaktional** .</span><span class="sxs-lookup"><span data-stu-id="96556-139">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="96556-140">Geben Sie `ServiceModelSamplesTransacted` als Namen für die neue Warteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="96556-140">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="96556-141">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="96556-141">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="96556-142">Um das Beispiel in einer Konfiguration mit einem einzelnen Computer auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="96556-142">To run the sample in a single- computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

## <a name="run-the-sample-across-computers"></a><span data-ttu-id="96556-143">Führen Sie das Beispiel Computer übergreifend aus.</span><span class="sxs-lookup"><span data-stu-id="96556-143">Run the sample across computers</span></span>

1. <span data-ttu-id="96556-144">Kopieren Sie die Dienstprogrammdateien aus dem Ordner \service\bin\ (unterhalb des sprachspezifischen Ordners) auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="96556-144">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>

2. <span data-ttu-id="96556-145">Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="96556-145">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>

3. <span data-ttu-id="96556-146">Ändern Sie in der Datei Client.exe.config den Wert von orderQueueName, und geben Sie anstelle von "." den Namen des Dienstcomputers an.</span><span class="sxs-lookup"><span data-stu-id="96556-146">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>

4. <span data-ttu-id="96556-147">Starten Sie auf dem Dienstcomputer Service.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="96556-147">On the service computer, launch Service.exe from a command prompt.</span></span>

5. <span data-ttu-id="96556-148">Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="96556-148">On the client computer, launch Client.exe from a command prompt.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96556-149">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="96556-149">The samples may already be installed on your computer.</span></span> <span data-ttu-id="96556-150">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="96556-150">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="96556-151">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="96556-151">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="96556-152">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="96556-152">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MsmqToWcf`

## <a name="see-also"></a><span data-ttu-id="96556-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96556-153">See also</span></span>

- [<span data-ttu-id="96556-154">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="96556-154">Queues in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="96556-155">Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="96556-155">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- <span data-ttu-id="96556-156">[Message Queuing](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="96556-156">[Message Queuing](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span></span>
