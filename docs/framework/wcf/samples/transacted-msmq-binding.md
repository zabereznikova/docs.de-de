---
title: Abgewickelte MSMQ-Bindung
ms.date: 03/30/2017
ms.assetid: 71f5cb8d-f1df-4e1e-b8a2-98e734a75c37
ms.openlocfilehash: a3592195f853dd97bf8e4351526bf0fff9ce78fd
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715633"
---
# <a name="transacted-msmq-binding"></a><span data-ttu-id="e5875-102">Abgewickelte MSMQ-Bindung</span><span class="sxs-lookup"><span data-stu-id="e5875-102">Transacted MSMQ Binding</span></span>

<span data-ttu-id="e5875-103">In diesem Beispiel wird veranschaulicht, wie eine abgewickelte Warteschlangenkommunikation mithilfe von Message Queuing (MSMQ) durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e5875-103">This sample demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ).</span></span>

> [!NOTE]
> <span data-ttu-id="e5875-104">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="e5875-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="e5875-105">In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="e5875-105">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="e5875-106">Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet.</span><span class="sxs-lookup"><span data-stu-id="e5875-106">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="e5875-107">Der Dienst empfängt Nachrichten aus der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="e5875-107">The service receives messages from the queue.</span></span> <span data-ttu-id="e5875-108">Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="e5875-108">The service and client, therefore, do not have to be running at the same time to communicate using a queue.</span></span>

<span data-ttu-id="e5875-109">Wenn Transaktionen verwendet werden, um Nachrichten zu senden und zu empfangen, gibt es genau genommen zwei separate Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="e5875-109">When transactions are used to send and receive messages, there are actually two separate transactions.</span></span> <span data-ttu-id="e5875-110">Wenn der Client innerhalb des Geltungsbereichs einer Transaktion Nachrichten sendet, gilt die Transaktion lokal für den Client und den Warteschlangen-Manager des Clients.</span><span class="sxs-lookup"><span data-stu-id="e5875-110">When the client sends messages within the scope of a transaction, the transaction is local to the client and the client queue manager.</span></span> <span data-ttu-id="e5875-111">Wenn der Dienst innerhalb des Geltungsbereichs der Transaktion Nachrichten empfängt, gilt die Transaktion lokal für den Dienst und den empfangenden Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="e5875-111">When the service receives messages within the scope of the transaction, the transaction is local to the service and the receiving queue manager.</span></span> <span data-ttu-id="e5875-112">Es ist wichtig, daran zu denken, dass der Client und der Dienst nicht an derselben Transaktion beteiligt sind, sondern zur Durchführung ihrer Vorgänge (wie Senden und Empfangen) über die Warteschlange verschiedene Transaktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5875-112">It is very important to remember that the client and the service are not participating in the same transaction; rather, they are using different transactions when performing their operations (such as send and receive) with the queue.</span></span>

<span data-ttu-id="e5875-113">In diesem Beispiel sendet der Client einen Nachrichtenbatch aus dem Geltungsbereich einer Transaktion an den Dienst.</span><span class="sxs-lookup"><span data-stu-id="e5875-113">In this sample, the client sends a batch of messages to the service from within the scope of a transaction.</span></span> <span data-ttu-id="e5875-114">Die an die Warteschlange gesendeten Nachrichten werden dann vom Dienst innerhalb des vom Dienst definierten Geltungsbereichs der Transaktion empfangen.</span><span class="sxs-lookup"><span data-stu-id="e5875-114">The messages sent to the queue are then received by the service within the transaction scope defined by the service.</span></span>

<span data-ttu-id="e5875-115">Der Dienstvertrag lautet `IOrderProcessor`, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5875-115">The service contract is `IOrderProcessor`, as shown in the following sample code.</span></span> <span data-ttu-id="e5875-116">Die Schnittstelle definiert einen unidirektionalen Dienst, der für die Verwendung mit Warteschlangen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="e5875-116">The interface defines a one-way service that is suitable for use with queues.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

<span data-ttu-id="e5875-117">Das Dienstverhalten definiert ein Vorgangsverhalten, wobei `TransactionScopeRequired` auf `true` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="e5875-117">The service behavior defines an operation behavior with `TransactionScopeRequired` set to `true`.</span></span> <span data-ttu-id="e5875-118">Auf diese Weise wird sichergestellt, dass alle Ressourcen-Manager, auf die diese Methode zugreift, denselben Geltungsbereich einer Transaktion verwenden, der auch zum Abrufen der Nachricht aus der Warteschlange verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e5875-118">This ensures that the same transaction scope that is used to retrieve the message from the queue is used by any resource managers accessed by the method.</span></span> <span data-ttu-id="e5875-119">Des Weiteren wird gewährleistet, dass die Nachricht an die Warteschlange zurückgegeben wird, wenn die Methode eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="e5875-119">It also guarantees that if the method throws an exception, the message is returned to the queue.</span></span> <span data-ttu-id="e5875-120">Ohne Festlegung dieses Vorgangsverhaltens erstellt ein in der Warteschlange stehender Kanal eine Transaktion, um die Nachricht aus der Warteschlange zu lesen, und führt dafür automatisch vor der Verteilung einen Commit aus, sodass die Nachricht verloren geht, falls der Vorgang fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="e5875-120">Without setting this operation behavior, a queued channel creates a transaction to read the message from the queue and commits it automatically before dispatch such that if the operation fails, the message is lost.</span></span> <span data-ttu-id="e5875-121">Das häufigste Szenario betrifft Dienstvorgänge, die sich in der Transaktion zum Lesen der Nachricht aus der Warteschlange eintragen, wie im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e5875-121">The most common scenario is for service operations to enlist in the transaction that is used to read the message from the queue, as demonstrated in the following code.</span></span>

```csharp
 // This service class that implements the service contract.
 // This added code writes output to the console window.
 public class OrderProcessorService : IOrderProcessor
 {
     [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
     public void SubmitPurchaseOrder(PurchaseOrder po)
     {
         Orders.Add(po);
         Console.WriteLine("Processing {0} ", po);
     }
  …
}
```

<span data-ttu-id="e5875-122">Der Dienst ist selbst gehostet.</span><span class="sxs-lookup"><span data-stu-id="e5875-122">The service is self hosted.</span></span> <span data-ttu-id="e5875-123">Bei Verwendung des MSMQ-Transports muss die Warteschlange im Voraus erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e5875-123">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="e5875-124">Dies kann manuell erfolgen oder mithilfe eines Codes.</span><span class="sxs-lookup"><span data-stu-id="e5875-124">This can be done manually or through code.</span></span> <span data-ttu-id="e5875-125">In diesem Beispiel enthält der Dienst einen Code, um zu überprüfen, ob die Warteschlange bereits vorhanden ist, und um die Warteschlange gegebenenfalls zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e5875-125">In this sample, the service contains code to check for the existence of the queue and create the queue if it does not exist.</span></span> <span data-ttu-id="e5875-126">Der Warteschlangenname wird aus der Konfigurationsdatei gelesen.</span><span class="sxs-lookup"><span data-stu-id="e5875-126">The queue name is read from the configuration file.</span></span> <span data-ttu-id="e5875-127">Die Basisadresse wird vom [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) verwendet, um den Proxy für den Dienst zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e5875-127">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy to the service.</span></span>

```csharp
// Host the service within this EXE console application.
public static void Main()
{
    // Get the MSMQ queue name from appSettings in configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];

    // Create the transacted MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName, true);

    // Create a ServiceHost for the OrderProcessorService type.
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
    {
        // Open the ServiceHost to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        // Close the ServiceHost to shut down the service.
        serviceHost.Close();
    }
}
```

<span data-ttu-id="e5875-128">Der Name der MSMQ-Warteschlange wird im appSettings-Abschnitt der Konfigurationsdatei angegeben, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5875-128">The MSMQ queue name is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

```xml
<appSettings>
    <add key="queueName" value=".\private$\ServiceModelSamplesTransacted" />
</appSettings>
```

> [!NOTE]
> <span data-ttu-id="e5875-129">Im Warteschlangennamen werden ein Punkt (.) für den lokalen Computer und umgekehrte Schrägstriche als Trennzeichen in der Pfadangabe verwendet, wenn die Warteschlange mithilfe von <xref:System.Messaging> erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e5875-129">The queue name uses a dot (.) for the local computer and backslash separators in its path when creating the queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="e5875-130">Der Windows Communication Foundation (WCF)-Endpunkt verwendet die Warteschlangen Adresse mit dem Schema "net. MSMQ", verwendet "localhost", um den lokalen Computer anzugeben, und verwendet Schrägstriche im Pfad.</span><span class="sxs-lookup"><span data-stu-id="e5875-130">The Windows Communication Foundation (WCF) endpoint uses the queue address with net.msmq scheme, uses "localhost" to denote the local computer, and uses forward slashes in its path.</span></span>

<span data-ttu-id="e5875-131">Der Client erstellt einen Geltungsbereich für die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="e5875-131">The client creates a transaction scope.</span></span> <span data-ttu-id="e5875-132">Die Kommunikation mit der Warteschlange findet innerhalb des Geltungsbereichs der Transaktion statt, sodass diese in der Folge als unteilbare Einheit behandelt wird, in der entweder alle oder keine Nachrichten an die Warteschlange gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5875-132">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages are sent to the queue or none of the messages are sent to the queue.</span></span> <span data-ttu-id="e5875-133">Für die Transaktion wird ein Commit ausgeführt, indem <xref:System.Transactions.TransactionScope.Complete%2A> im Geltungsbereich der Transaktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e5875-133">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A> on the transaction scope.</span></span>

```csharp
// Create a client.
OrderProcessorClient client = new OrderProcessorClient();

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

// Create a transaction scope.
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{
    // Make a queued call to submit the purchase order.
    client.SubmitPurchaseOrder(po);
    // Complete the transaction.
    scope.Complete();
}

// Closing the client gracefully closes the connection and cleans up resources.
client.Close();

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

<span data-ttu-id="e5875-134">Um zu überprüfen, dass Transaktionen funktionieren, ändern Sie den Client, indem Sie den Geltungsbereich einer Transaktion, wie im folgenden Beispielcode gezeigt, kommentieren, die Projektmappe neu erstellen und den Client ausführen.</span><span class="sxs-lookup"><span data-stu-id="e5875-134">To verify that transactions are working, modify the client by commenting the transaction scope as shown in the following sample code, rebuild the solution, and run the client.</span></span>

```csharp
//scope.Complete();
```

<span data-ttu-id="e5875-135">Da die Transaktion nicht abgeschlossen wird, werden die Nachrichten nicht an die Warteschlange gesendet.</span><span class="sxs-lookup"><span data-stu-id="e5875-135">Because the transaction is not completed, the messages are not sent to the queue.</span></span>

<span data-ttu-id="e5875-136">Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5875-136">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="e5875-137">Sie können sehen, wie der Dienst Nachrichten vom Client empfängt.</span><span class="sxs-lookup"><span data-stu-id="e5875-137">You can see the service receive messages from the client.</span></span> <span data-ttu-id="e5875-138">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e5875-138">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="e5875-139">Beachten Sie, dass aufgrund der Verwendung einer Warteschlange der Client und der Dienst nicht gleichzeitig ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e5875-139">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="e5875-140">Sie können den Client ausführen, ihn schließen und anschließend den Dienst starten, der dann trotzdem noch die Nachrichten des Clients empfängt.</span><span class="sxs-lookup"><span data-stu-id="e5875-140">You can run the client, shut it down, and then start up the service and it still receives the messages.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 7b31ce51-ae7c-4def-9b8b-617e4288eafd
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e5875-141">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="e5875-141">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="e5875-142">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="e5875-142">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="e5875-143">Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e5875-143">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="e5875-144">Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="e5875-144">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="e5875-145">Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen.</span><span class="sxs-lookup"><span data-stu-id="e5875-145">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="e5875-146">Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e5875-146">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="e5875-147">Öffnen Sie Server-Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="e5875-147">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="e5875-148">Erweitern Sie die Registerkarte **Features** .</span><span class="sxs-lookup"><span data-stu-id="e5875-148">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="e5875-149">Klicken Sie mit der rechten Maustaste auf private Meldungs **Warteschlangen**, und wählen Sie **neu**, **private**</span><span class="sxs-lookup"><span data-stu-id="e5875-149">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="e5875-150">Aktivieren Sie das Kontrollkästchen **transaktional** .</span><span class="sxs-lookup"><span data-stu-id="e5875-150">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="e5875-151">Geben Sie `ServiceModelSamplesTransacted` als Namen für die neue Warteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="e5875-151">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="e5875-152">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e5875-152">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="e5875-153">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e5875-153">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

<span data-ttu-id="e5875-154">Standardmäßig wird mit <xref:System.ServiceModel.NetMsmqBinding> die Transportsicherheit aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e5875-154">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="e5875-155">Es gibt zwei relevante Eigenschaften für die MSMQ-Transportsicherheit, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> und <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="e5875-155">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>.</span></span> <span data-ttu-id="e5875-156">Standardmäßig wird der Authentifizierungsmodus als `Windows` festgelegt, und die Schutzebene wird auf `Sign` gesetzt.</span><span class="sxs-lookup"><span data-stu-id="e5875-156">By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="e5875-157">Damit MSMQ die Authentifizierungs- und Signierungsfunktion zur Verfügung stellt, muss es Teil einer Domäne sein, und die Option zur Active Directory-Integration muss für MSMQ installiert sein.</span><span class="sxs-lookup"><span data-stu-id="e5875-157">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the Active Directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="e5875-158">Wenn Sie dieses Beispiel auf einem Computer ausführen, der diese Kriterien nicht erfüllt, erhalten Sie eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="e5875-158">If you run this sample on a computer that does not satisfy these criteria, you receive an error.</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="e5875-159">So führen Sie das Beispiel auf einem Computer aus, der sich in einer Arbeitsgruppe befindet oder über keine Active Directory-Integration verfügt</span><span class="sxs-lookup"><span data-stu-id="e5875-159">To run the sample on a computer joined to a workgroup or without Active Directory integration</span></span>

1. <span data-ttu-id="e5875-160">Wenn Ihr Computer nicht zu einer Domäne gehört oder auf ihm keine Active Directory-Integration installiert ist, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf `None` setzen, wie im folgenden Beispiel für einen Konfigurationscode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5875-160">If your computer is not part of a domain or does not have Active Directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration code.</span></span>

    ```xml
    <system.serviceModel>
      <services>
        <service name="Microsoft.ServiceModel.Samples.OrderProcessorService"
                 behaviorConfiguration="OrderProcessorServiceBehavior">
          <host>
            <baseAddresses>
              <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
            </baseAddresses>
          </host>
          <!-- Define NetMsmqEndpoint. -->
          <endpoint
              address="net.msmq://localhost/private/ServiceModelSamplesTransacted"
              binding="netMsmqBinding"
              bindingConfiguration="Binding1"
           contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
          <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->
          <endpoint address="mex"
                    binding="mexHttpBinding"
                    contract="IMetadataExchange" />
        </service>
      </services>

      <bindings>
        <netMsmqBinding>
          <binding name="Binding1">
            <security mode="None" />
          </binding>
        </netMsmqBinding>
      </bindings>

        <behaviors>
          <serviceBehaviors>
            <behavior name="OrderProcessorServiceBehavior">
              <serviceMetadata httpGetEnabled="True"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>

      </system.serviceModel>
    ```

2. <span data-ttu-id="e5875-161">Ändern Sie die Konfiguration sowohl auf dem Server als auch auf dem Client, bevor Sie das Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="e5875-161">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e5875-162">Das Festlegen von `security mode` auf `None` entspricht dem Festlegen von <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> und der `Message`-Sicherheit auf `None`.</span><span class="sxs-lookup"><span data-stu-id="e5875-162">Setting `security mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5875-163">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e5875-163">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e5875-164">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e5875-164">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="e5875-165">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="e5875-165">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e5875-166">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e5875-166">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Transacted`
