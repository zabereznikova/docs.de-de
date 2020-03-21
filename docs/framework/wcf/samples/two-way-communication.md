---
title: Bidirektionale Kommunikation
ms.date: 03/30/2017
ms.assetid: fb64192d-b3ea-4e02-9fb3-46a508d26c60
ms.openlocfilehash: 56f789fe185cb2885c215e9512e82ae2fbb64a36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143758"
---
# <a name="two-way-communication"></a><span data-ttu-id="32515-102">Bidirektionale Kommunikation</span><span class="sxs-lookup"><span data-stu-id="32515-102">Two-Way Communication</span></span>
<span data-ttu-id="32515-103">Dieses Beispiel veranschaulicht das Ausführen der transaktiven bidirektionalen Warteschlangenkommunikation über MSMQ.</span><span class="sxs-lookup"><span data-stu-id="32515-103">This sample demonstrates how to perform transacted two-way queued communication over MSMQ.</span></span> <span data-ttu-id="32515-104">In diesem Beispiel wird die `netMsmqBinding`-Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="32515-104">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="32515-105">Der Dienst ist in diesem Fall eine selbst gehostete Konsolenanwendung, die es Ihnen ermöglicht, den Dienst beim Empfang von Nachrichten in der Warteschlange zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="32515-105">In this case, the service is a self-hosted console application that allows you to observe the service receiving queued messages.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="32515-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="32515-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="32515-107">Dieses Beispiel basiert auf der [Transacted MSMQ-Bindung](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span><span class="sxs-lookup"><span data-stu-id="32515-107">This sample is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span></span>  
  
 <span data-ttu-id="32515-108">In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="32515-108">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="32515-109">Der Client sendet Nachrichten an eine Warteschlange, und der Dienst empfängt Nachrichten von der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="32515-109">The client sends messages to a queue, and the service receives messages from the queue.</span></span> <span data-ttu-id="32515-110">Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="32515-110">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="32515-111">In diesem Beispiel wird die bidirektionale Kommunikation mit Warteschlangen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="32515-111">This sample demonstrates 2-way communication using queues.</span></span> <span data-ttu-id="32515-112">Der Client sendet Bestellungen aus dem Bereich einer Transaktion an die Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="32515-112">The client sends purchase orders to the queue from within the scope of a transaction.</span></span> <span data-ttu-id="32515-113">Der Dienst empfängt die Bestellungen, verarbeitet die Bestellungen und meldet an den Client den Status der Bestellung aus der Warteschlange innerhalb des Bereichs der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="32515-113">The service receives the orders, processes the order and then calls back the client with the status of the order from the queue within the scope of a transaction.</span></span> <span data-ttu-id="32515-114">Zur Vereinfachung der bidirektionalen Kommunikation verwenden sowohl der Client als auch der Dienst Warteschlangen für Bestellungen und den Auftragsstatus.</span><span class="sxs-lookup"><span data-stu-id="32515-114">To facilitate two-way communication the client and service both use queues to enqueue purchase orders and order status.</span></span>  
  
 <span data-ttu-id="32515-115">Der `IOrderProcessor`-Dienstvertrag definiert einen unidirektionalen Dienstvorgang, der für die Verwendung mit Warteschlangen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="32515-115">The service contract `IOrderProcessor` defines one-way service operations that suit the use of queuing.</span></span> <span data-ttu-id="32515-116">Der Dienstvorgang beinhaltet den Antwortendpunkt, an den der Auftragsstatus gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="32515-116">The service operation includes the reply endpoint to use to send the order statuses to.</span></span> <span data-ttu-id="32515-117">Der Antwortendpunkt ist der URI der Warteschlange für die Rücksendung des Auftragsstatus an den Client.</span><span class="sxs-lookup"><span data-stu-id="32515-117">The reply endpoint is the URI of the queue to send the order status back to the client.</span></span> <span data-ttu-id="32515-118">Die Anwendung für die Auftragsverarbeitung implementiert diesen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="32515-118">The order processing application implements this contract.</span></span>  

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true)]  
    void SubmitPurchaseOrder(PurchaseOrder po, string
                                  reportOrderStatusTo);  
}
```
  
 <span data-ttu-id="32515-119">Der Antwortvertrag für die Sendung des Auftragsstatus wird vom Client angegeben.</span><span class="sxs-lookup"><span data-stu-id="32515-119">The reply contract to send order status is specified by the client.</span></span> <span data-ttu-id="32515-120">Der Client implementiert den Auftragsstatusvertrag.</span><span class="sxs-lookup"><span data-stu-id="32515-120">The client implements the order status contract.</span></span> <span data-ttu-id="32515-121">Der Dienst verwendet den generierten Proxy dieses Vertrags, um den Auftragsstatus an den Client zurückzusenden.</span><span class="sxs-lookup"><span data-stu-id="32515-121">The service uses the generated proxy of this contract to send order status back to the client.</span></span>  

```csharp
[ServiceContract]  
public interface IOrderStatus  
{  
    [OperationContract(IsOneWay = true)]  
    void OrderStatus(string poNumber, string status);  
}  
```

 <span data-ttu-id="32515-122">Der Dienstvorgang verarbeitet die übermittelte Bestellung.</span><span class="sxs-lookup"><span data-stu-id="32515-122">The service operation processes the submitted purchase order.</span></span> <span data-ttu-id="32515-123">Das <xref:System.ServiceModel.OperationBehaviorAttribute> wird auf den Dienstvorgang angewendet, um die automatische Eintragung für eine Transaktion festzulegen, die für den Empfang der Nachricht aus der Warteschlange verwendet wird, und für die automatische Fertigstellung von Transaktionen, wenn der Dienstvorgang fertig gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="32515-123">The <xref:System.ServiceModel.OperationBehaviorAttribute> is applied to the service operation to specify automatic enlistment in a transaction that is used to receive the message from the queue and automatic completion of transactions on completion of the service operation.</span></span> <span data-ttu-id="32515-124">Die `Orders`-Klasse kapselt die Auftragsverarbeitungsfunktion.</span><span class="sxs-lookup"><span data-stu-id="32515-124">The `Orders` class encapsulates order processing functionality.</span></span> <span data-ttu-id="32515-125">In diesem Fall fügt sie die Bestellung einem Wörterbuch hinzu.</span><span class="sxs-lookup"><span data-stu-id="32515-125">In this case, it adds the purchase order to a dictionary.</span></span> <span data-ttu-id="32515-126">Die Transaktion, in der der Dienstvorgang eingetragen wurde, steht den Vorgängen in der `Orders`-Klasse zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="32515-126">The transaction that the service operation enlisted in is available to the operations in the `Orders` class.</span></span>  
  
 <span data-ttu-id="32515-127">Der Dienstvorgang verarbeitet die übermittelte Bestellung und meldet dem Client den Status des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="32515-127">The service operation, in addition to processing the submitted purchase order, replies back to the client on the status of the order.</span></span>  

```csharp
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)  
{  
    Orders.Add(po);  
    Console.WriteLine("Processing {0} ", po);  
    Console.WriteLine("Sending back order status information");  
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding("ClientCallbackBinding");  
    OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));  
  
    // Please note that the same transaction that is used to dequeue the purchase order is used  
    // to send back order status.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        client.OrderStatus(po.PONumber, po.Status);  
        scope.Complete();  
    }  
    //Close the client.  
    client.Close();  
}  
```

 <span data-ttu-id="32515-128">Der MSMQ-Warteschlangenname wird im appSettings-Abschnitt der Konfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="32515-128">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="32515-129">Der Endpunkt für den Dienst wird im Abschnitt System.ServiceModel der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="32515-129">The endpoint for the service is defined in the System.ServiceModel section of the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="32515-130">Der Name der MSMQ-Warteschlange und die Endpunktadresse verwenden geringfügig abweichende Adressierungskonventionen.</span><span class="sxs-lookup"><span data-stu-id="32515-130">The MSMQ queue name and endpoint address use slightly different addressing conventions.</span></span> <span data-ttu-id="32515-131">Im MSMQ-Warteschlangennamen wird ein Punkt (.) für den lokalen Computer verwendet, und in der Pfadangabe werden umgekehrte Schrägstriche als Trennzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="32515-131">The MSMQ queue name uses a dot (.) for the local machine and backslash separators in its path.</span></span> <span data-ttu-id="32515-132">Die WCF-Endpunktadresse (Windows Communication Foundation) gibt ein net.msmq:-Schema an, verwendet "localhost" für den lokalen Computer und verwendet Schrägstriche in seinem Pfad.</span><span class="sxs-lookup"><span data-stu-id="32515-132">The Windows Communication Foundation (WCF) endpoint address specifies a net.msmq: scheme, uses "localhost" for the local machine, and uses forward slashes in its path.</span></span> <span data-ttu-id="32515-133">Um in einer Warteschlange zu lesen, die auf einem Remotecomputer gehostet wird, ersetzen Sie "." und "localhost" durch den Namen des Remotecomputers.</span><span class="sxs-lookup"><span data-stu-id="32515-133">To read from a queue that is hosted on the remote machine, replace the "." and "localhost" to the remote machine name.</span></span>  
  
 <span data-ttu-id="32515-134">Der Dienst ist selbst gehostet.</span><span class="sxs-lookup"><span data-stu-id="32515-134">The service is self hosted.</span></span> <span data-ttu-id="32515-135">Bei Verwendung des MSMQ-Transports muss die Warteschlange im Voraus erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="32515-135">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="32515-136">Dies kann manuell erfolgen oder mithilfe eines Codes.</span><span class="sxs-lookup"><span data-stu-id="32515-136">This can be done manually or through code.</span></span> <span data-ttu-id="32515-137">In diesem Beispiel prüft der Dienst, ob die Warteschlange vorhanden ist, und erstellt sie gegebenenfalls.</span><span class="sxs-lookup"><span data-stu-id="32515-137">In this sample, the service checks for the existence of the queue and creates it, if necessary.</span></span> <span data-ttu-id="32515-138">Der Warteschlangenname wird aus der Konfigurationsdatei gelesen.</span><span class="sxs-lookup"><span data-stu-id="32515-138">The queue name is read from the configuration file.</span></span> <span data-ttu-id="32515-139">Die Basisadresse wird vom [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) verwendet, um den Proxy für den Dienst zu generieren.</span><span class="sxs-lookup"><span data-stu-id="32515-139">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy to the service.</span></span>  

```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from appSettings in configuration.  
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
    }  
}  
```

 <span data-ttu-id="32515-140">Der Client erstellt eine Transaktion.</span><span class="sxs-lookup"><span data-stu-id="32515-140">The client creates a transaction.</span></span> <span data-ttu-id="32515-141">Die Kommunikation mit der Warteschlange findet innerhalb des Geltungsbereichs der Transaktion statt, sodass diese in der Folge als unteilbare Einheit behandelt wird, in der alle Nachrichten entweder erfolgreich sind oder fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="32515-141">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span>  

```csharp
// Create a ServiceHost for the OrderStatus service type.  
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))  
{  
  
    // Open the ServiceHostBase to create listeners and start listening for order status messages.  
    serviceHost.Open();  
  
    // Create the purchase order.  
    ...  
  
    // Create a client with given client endpoint configuration.  
    OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
    //Create a transaction scope.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        string hostName = Dns.GetHostName();  
  
        // Make a queued call to submit the purchase order.  
        client.SubmitPurchaseOrder(po, "net.msmq://" + hostName + "/private/ServiceModelSamplesTwo-way/OrderStatus");  
  
        // Complete the transaction.  
        scope.Complete();  
    }  
  
    //Close down the client.  
    client.Close();  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
  
    // Close the ServiceHost to shutdown the service.  
    serviceHost.Close();  
}  
```

 <span data-ttu-id="32515-142">Der Clientcode implementiert den `IOrderStatus`-Vertrag, um den Auftragsstatus vom Dienst zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="32515-142">The client code implements the `IOrderStatus` contract to receive order status from the service.</span></span> <span data-ttu-id="32515-143">In diesem Fall druckt er den Auftragsstatus aus.</span><span class="sxs-lookup"><span data-stu-id="32515-143">In this case, it prints out the order status.</span></span>  

```csharp
[ServiceBehavior]  
public class OrderStatusService : IOrderStatus  
{  
    [OperationBehavior(TransactionAutoComplete = true,
                        TransactionScopeRequired = true)]  
    public void OrderStatus(string poNumber, string status)  
    {  
        Console.WriteLine("Status of order {0}:{1} ", poNumber ,
                                                           status);  
    }  
}  
```

 <span data-ttu-id="32515-144">Die Auftragsstatuswarteschlange wird in der `Main`-Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="32515-144">The order status queue is created in the `Main` method.</span></span> <span data-ttu-id="32515-145">Die Clientkonfiguration beinhaltet die Dienstkonfiguration für den Auftragsstatus, um den Auftragsstatusdienst zu hosten, wie in der folgenden Beispielkonfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="32515-145">The client configuration includes the order status service configuration to host the order status service, as shown in the following sample configuration.</span></span>  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
</appSettings>  
  
<system.serviceModel>  
  
  <services>  
    <service
       name="Microsoft.ServiceModel.Samples.OrderStatusService">  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
    </service>  
  </services>  
  
  <client>  
    <!-- Define NetMsmqEndpoint -->  
    <endpoint name="OrderProcessorEndpoint"  
              address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"
              binding="netMsmqBinding"
              contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
  </client>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="32515-146">Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="32515-146">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="32515-147">Sie können sehen, wie der Dienst Nachrichten vom Client empfängt.</span><span class="sxs-lookup"><span data-stu-id="32515-147">You can see the service receive messages from the client.</span></span> <span data-ttu-id="32515-148">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="32515-148">Press ENTER in each console window to shut down the service and client.</span></span>  
  
 <span data-ttu-id="32515-149">Der Dienst zeigt die Bestellungsinformationen an und sendet sie für die Rücksendung an den Auftragsstatus an die Auftragsstatuswarteschlage.</span><span class="sxs-lookup"><span data-stu-id="32515-149">The service displays the purchase order information and indicates it is sending back the order status to the order status queue.</span></span>  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 124a1f69-3699-4b16-9bcc-43147a8756fc  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
  
Sending back order status information  
```  
  
 <span data-ttu-id="32515-150">Der Client zeigt die vom Dienst gesendeten Auftragsstatusinformationen an.</span><span class="sxs-lookup"><span data-stu-id="32515-150">The client displays the order status information sent by the service.</span></span>  
  
```console  
Press <ENTER> to terminate client.  
Status of order 124a1f69-3699-4b16-9bcc-43147a8756fc:Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="32515-151">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="32515-151">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="32515-152">Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="32515-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="32515-153">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="32515-153">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="32515-154">Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="32515-154">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="32515-155">Wenn Sie zur Neugenerierung der Konfiguration für dieses Beispiel die Datei "Svcutil.exe" verwenden, müssen Sie die Endpunktnamen in der Clientkonfiguration ändern, sodass sie mit dem Clientcode übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="32515-155">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint names in the client configuration to match the client code.</span></span>  
  
 <span data-ttu-id="32515-156">Standardmäßig wird mit <xref:System.ServiceModel.NetMsmqBinding> die Transportsicherheit aktiviert.</span><span class="sxs-lookup"><span data-stu-id="32515-156">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="32515-157">Es gibt zwei relevante Eigenschaften für <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> die <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` MSMQ-Transportsicherheit, `Windows` und standardmäßig ist der `Sign`Authentifizierungsmodus auf und die Schutzebene auf festgelegt.</span><span class="sxs-lookup"><span data-stu-id="32515-157">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="32515-158">Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es Teil einer Domäne sein, und die Active Directory-Integrationsoption für MSMQ muss installiert sein.</span><span class="sxs-lookup"><span data-stu-id="32515-158">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="32515-159">Wenn Sie dieses Beispiel auf einem Computer ausführen, der diese Kriterien nicht erfüllt, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="32515-159">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="32515-160">So führen Sie das Beispiel auf einem Computer aus, der sich in einer Arbeitsgruppe befindet oder über keine Active Directory-Integration verfügt</span><span class="sxs-lookup"><span data-stu-id="32515-160">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1. <span data-ttu-id="32515-161">Wenn Ihr Computer nicht zu einer Domäne gehört oder auf ihm keine Active Directory-Integration installiert ist, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf `None` setzen, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="32515-161">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>  
  
    ```xml  
    <configuration>  
  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderProcessor" />  
      </appSettings>  
  
      <system.serviceModel>  
        <services>  
          <service
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding"
                      contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          </service>  
        </services>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
2. <span data-ttu-id="32515-162">Wenn die Sicherheit für eine Clientkonfiguration deaktiviert wird, wird Folgendes generiert:</span><span class="sxs-lookup"><span data-stu-id="32515-162">Turning off security for a client configuration generates the following:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
      </appSettings>  
  
      <system.serviceModel>  
  
        <services>  
          <service
             name="Microsoft.ServiceModel.Samples.OrderStatusService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding" contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
          </service>  
        </services>  
  
        <client>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint name="OrderProcessorEndpoint"  
                    address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"
                    binding="netMsmqBinding"
                    bindingConfiguration="TransactedBinding"  
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
        </client>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
3. <span data-ttu-id="32515-163">Der Dienst für dieses Beispiel erstellt eine Bindung im `OrderProcessorService`.</span><span class="sxs-lookup"><span data-stu-id="32515-163">The service for this sample creates a binding in the `OrderProcessorService`.</span></span> <span data-ttu-id="32515-164">Fügen Sie eine Codezeile hinzu, nachdem die Bindung instanziiert wurde, um den Sicherheitsmodus auf `None` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="32515-164">Add a line of code after the binding is instantiated to set the security mode to `None`.</span></span>  
  
    ```csharp
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();  
    msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;  
    ```  
  
4. <span data-ttu-id="32515-165">Ändern Sie die Konfiguration sowohl auf dem Server als auch auf dem Client, bevor Sie das Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="32515-165">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="32515-166">Das Festlegen von `security mode` auf `None` entspricht dem Festlegen von <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> oder der `Message`-Sicherheit auf `None`.</span><span class="sxs-lookup"><span data-stu-id="32515-166">Setting `security mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> or `Message` security to `None`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="32515-167">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="32515-167">The samples may already be installed on your machine.</span></span> <span data-ttu-id="32515-168">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="32515-168">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="32515-169">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="32515-169">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="32515-170">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="32515-170">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\Net\MSMQ\Two-Way`  
