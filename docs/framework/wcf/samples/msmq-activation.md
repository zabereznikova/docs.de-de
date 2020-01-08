---
title: MSMQ-Aktivierung
ms.date: 03/30/2017
ms.assetid: e3834149-7b8c-4a54-806b-b4296720f31d
ms.openlocfilehash: 2afcfbee69f8257e4ed0b1c352ef29e4af9ddb84
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544715"
---
# <a name="msmq-activation"></a><span data-ttu-id="a4df4-102">MSMQ-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="a4df4-102">MSMQ Activation</span></span>

<span data-ttu-id="a4df4-103">Dieses Beispiel veranschaulicht das Hosten von Anwendungen in Windows Process Activation Service (WAS), die von einer Nachrichtenwarteschlange gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="a4df4-103">This sample demonstrates how to host applications in Windows Process Activation Service (WAS) that are read from a message queue.</span></span> <span data-ttu-id="a4df4-104">Dieses Beispiel verwendet die `netMsmqBinding` und basiert auf dem Beispiel für die bidirektionale [Kommunikation](../../../../docs/framework/wcf/samples/two-way-communication.md) .</span><span class="sxs-lookup"><span data-stu-id="a4df4-104">This sample uses the `netMsmqBinding` and is based on the [Two-Way Communication](../../../../docs/framework/wcf/samples/two-way-communication.md) sample.</span></span> <span data-ttu-id="a4df4-105">In diesem Fall handelt es sich bei dem Dienst um eine im Internet gehostete Anwendung. Der Client ist selbst gehostet und gibt an die Konsole aus, um den Status eingereichter Bestellungen zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="a4df4-105">The service in this case is a Web-hosted application and the client is self-hosted and outputs to the console to observe the status of purchase orders submitted.</span></span>

> [!NOTE]
> <span data-ttu-id="a4df4-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="a4df4-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="a4df4-107">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="a4df4-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a4df4-108">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a4df4-108">Check for the following (default) directory before continuing.</span></span>
>
> <span data-ttu-id="a4df4-109">\<InstallDrive>:\WF_WCF_Samples</span><span class="sxs-lookup"><span data-stu-id="a4df4-109">\<InstallDrive>:\WF_WCF_Samples</span></span>
>
> <span data-ttu-id="a4df4-110">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle WCF-und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all WCF and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a4df4-111">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a4df4-111">This sample is located in the following directory.</span></span>
>
> <span data-ttu-id="a4df4-112">\<InstallDrive>:\Samples\WCFWFCardSpace\WCF\Basic\Services\Hosting\WASHost\MsmqActivation.</span><span class="sxs-lookup"><span data-stu-id="a4df4-112">\<InstallDrive>:\Samples\WCFWFCardSpace\WCF\Basic\Services\Hosting\WASHost\MsmqActivation.</span></span>

<span data-ttu-id="a4df4-113">Windows Process Activation Service (was), der neue Prozess Aktivierungsmechanismus für Windows Server 2008, bietet IIS-ähnliche Funktionen, die zuvor nur für HTTP-basierte Anwendungen für Anwendungen verfügbar waren, die nicht-HTTP-Protokolle verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4df4-113">Windows Process Activation Service (WAS), the new process activation mechanism for Windows Server 2008, provides IIS-like features that were previously only available to HTTP-based applications to applications that use non-HTTP protocols.</span></span> <span data-ttu-id="a4df4-114">Windows Communication Foundation (WCF) verwendet die Listeneradapter-Schnittstelle zum Übermitteln von Aktivierungs Anforderungen, die über die von WCF unterstützten nicht-HTTP-Protokolle, wie z. b. TCP, Named Pipes und MSMQ, empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="a4df4-114">Windows Communication Foundation (WCF) uses the Listener Adapter interface to communicate activation requests that are received over the non-HTTP protocols supported by WCF, such as TCP, Named Pipes, and MSMQ.</span></span> <span data-ttu-id="a4df4-115">Die Funktionalität für den Empfang von Anforderungen über Nicht-HTTP-Protokolle wird von verwalteten Windows-Diensten gehostet, die in "SMSvcHost.exe" ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a4df4-115">The functionality for receiving requests over non-HTTP protocols is hosted by managed Windows services running in SMSvcHost.exe.</span></span>

<span data-ttu-id="a4df4-116">Der Net.Msmq-Listeneradapterdienst (NetMsmqActivator) aktiviert in der Warteschlange befindliche Anwendungen auf der Grundlage von Nachrichten in der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="a4df4-116">The Net.Msmq Listener Adapter service (NetMsmqActivator) activates queued applications based on messages in the queue.</span></span>

<span data-ttu-id="a4df4-117">Der Client sendet Bestellungen aus dem Bereich einer Transaktion an den Dienst.</span><span class="sxs-lookup"><span data-stu-id="a4df4-117">The client sends purchase orders to the service from within the scope of a transaction.</span></span> <span data-ttu-id="a4df4-118">Der Dienst empfängt die Bestellungen in einer Transaktion und verarbeitet sie.</span><span class="sxs-lookup"><span data-stu-id="a4df4-118">The service receives the orders in a transaction and processes them.</span></span> <span data-ttu-id="a4df4-119">Der Dienst führt dann einen Rückruf an den Client mit dem Status der Bestellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4df4-119">The service then calls back the client with the status of the order.</span></span> <span data-ttu-id="a4df4-120">Zur Vereinfachung der bidirektionalen Kommunikation verwenden sowohl der Client als auch der Dienst Warteschlangen für Bestellungen und den Auftragsstatus.</span><span class="sxs-lookup"><span data-stu-id="a4df4-120">To facilitate two-way communication the client and service both use queues to enqueue purchase orders and order status.</span></span>

<span data-ttu-id="a4df4-121">Der `IOrderProcessor`-Dienstvertrag definiert die unidirektionalen Dienstvorgänge, die mit Warteschlangen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a4df4-121">The service contract `IOrderProcessor` defines the one-way service operations that work with queuing.</span></span> <span data-ttu-id="a4df4-122">Der Dienstvorgang nutzt den Antwortendpunkt, um Bestellstatus an den Client zu senden.</span><span class="sxs-lookup"><span data-stu-id="a4df4-122">The service operation uses the reply endpoint to send order statuses to the client.</span></span> <span data-ttu-id="a4df4-123">Die Adresse des Antwortendpunkts ist der URI der Warteschlange, die für die Rücksendung des Auftragsstatus an den Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a4df4-123">The reply endpoint's address is the URI of the queue used to send the order status back to the client.</span></span> <span data-ttu-id="a4df4-124">Die Anwendung für die Auftragsverarbeitung implementiert diesen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="a4df4-124">The order processing application implements this contract.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po,
                                           string reportOrderStatusTo);
}
```

<span data-ttu-id="a4df4-125">Der Antwortvertrag, an den der Bestellstatus gesendet wird, wird vom Client angegeben.</span><span class="sxs-lookup"><span data-stu-id="a4df4-125">The reply contract to send order status to is specified by the client.</span></span> <span data-ttu-id="a4df4-126">Der Client implementiert den Auftragsstatusvertrag.</span><span class="sxs-lookup"><span data-stu-id="a4df4-126">The client implements the order status contract.</span></span> <span data-ttu-id="a4df4-127">Der Dienst verwendet den generierten Client dieses Vertrags, um den Bestellstatus an den Client zurückzusenden.</span><span class="sxs-lookup"><span data-stu-id="a4df4-127">The service uses the generated client of this contract to send order status back to the client.</span></span>

```csharp
[ServiceContract]
public interface IOrderStatus
{
    [OperationContract(IsOneWay = true)]
    void OrderStatus(string poNumber, string status);
}
```

<span data-ttu-id="a4df4-128">Der Dienstvorgang verarbeitet die übermittelte Bestellung.</span><span class="sxs-lookup"><span data-stu-id="a4df4-128">The service operation processes the submitted purchase order.</span></span> <span data-ttu-id="a4df4-129"><xref:System.ServiceModel.OperationBehaviorAttribute> wird auf den Dienstvorgang angewendet, um die automatische Eintragung in die Transaktion, die für den Empfang der Nachricht aus der Warteschlange verwendet wird, und die automatische Fertigstellung der Transaktion bei Abschluss des Dienstvorgangs festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-129">The <xref:System.ServiceModel.OperationBehaviorAttribute> is applied to the service operation to specify automatic enlistment in the transaction that is used to receive the message from the queue and automatic completion of the transaction on completion of the service operation.</span></span> <span data-ttu-id="a4df4-130">Die `Orders`-Klasse kapselt die Auftragsverarbeitungsfunktion.</span><span class="sxs-lookup"><span data-stu-id="a4df4-130">The `Orders` class encapsulates order processing functionality.</span></span> <span data-ttu-id="a4df4-131">In diesem Fall fügt sie die Bestellung einem Wörterbuch hinzu.</span><span class="sxs-lookup"><span data-stu-id="a4df4-131">In this case, it adds the purchase order to a dictionary.</span></span> <span data-ttu-id="a4df4-132">Die Transaktion, in der der Dienstvorgang eingetragen wurde, steht den Vorgängen in der `Orders`-Klasse zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a4df4-132">The transaction that the service operation enlisted in is available to the operations in the `Orders` class.</span></span>

<span data-ttu-id="a4df4-133">Der Dienstvorgang verarbeitet die übermittelte Bestellung und meldet dem Client den Status der Bestellung.</span><span class="sxs-lookup"><span data-stu-id="a4df4-133">The service operation, in addition to processing the submitted purchase order, replies back to the client about the status of the order.</span></span>

```csharp
public class OrderProcessorService : IOrderProcessor
{
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)
    {
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
        Console.WriteLine("Sending back order status information");
        NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();
        msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;
        OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));
        // please note that the same transaction that is used to dequeue purchase order is used
        // to send back order status
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            client.OrderStatus(po.PONumber, po.Status);
            scope.Complete();
        }
    }
}
```

<span data-ttu-id="a4df4-134">Die zu verwendende Clientbindung wird mithilfe einer Konfigurationsdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a4df4-134">The client binding to use is specified using a configuration file.</span></span>

<span data-ttu-id="a4df4-135">Der MSMQ-Warteschlangenname wird im appSettings-Abschnitt der Konfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="a4df4-135">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="a4df4-136">Der Endpunkt für den Dienst wird im Abschnitt "System.serviceModel" der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="a4df4-136">The endpoint for the service is defined in the System.serviceModel section of the configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="a4df4-137">Der Name der MSMQ-Warteschlange und die Endpunktadresse verwenden geringfügig abweichende Adressierungskonventionen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-137">The MSMQ queue name and endpoint address use slightly different addressing conventions.</span></span> <span data-ttu-id="a4df4-138">Im MSQM-Warteschlangennamen wird ein Punkt (.) für den lokalen Computer verwendet, und in der Pfadangabe werden umgekehrte Schrägstriche als Trennzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4df4-138">The MSMQ queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="a4df4-139">Die WCF-Endpunkt Adresse gibt ein net. MSMQ:-Schema an, verwendet "localhost" für den lokalen Computer und verwendet Schrägstriche im Pfad.</span><span class="sxs-lookup"><span data-stu-id="a4df4-139">The WCF endpoint address specifies a net.msmq: scheme, uses "localhost" for the local computer, and uses forward slashes in its path.</span></span> <span data-ttu-id="a4df4-140">Um aus einer Warteschlange zu lesen, die auf einem Remotecomputer gehostet wird, ersetzen Sie "." und localhost durch den Namen des Remotecomputers.</span><span class="sxs-lookup"><span data-stu-id="a4df4-140">To read from a queue that is hosted on the remote computer, replace the "." and "localhost" to the remote computer name.</span></span>

<span data-ttu-id="a4df4-141">Um den Dienstcode in WAS zu hosten, wird eine SVC-Datei mit dem Namen der Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4df4-141">A .svc file with the name of the class is used to host the service code in WAS.</span></span>

<span data-ttu-id="a4df4-142">Die Datei "Service.svc" selbst enthält eine Anweisung zur Erstellung von `OrderProcessorService`.</span><span class="sxs-lookup"><span data-stu-id="a4df4-142">The Service.svc file itself contains a directive to create the `OrderProcessorService`.</span></span>

`<%@ServiceHost language="c#" Debug="true" Service="Microsoft.ServiceModel.Samples.OrderProcessorService"%>`

<span data-ttu-id="a4df4-143">Die Datei „Service.svc“ enthält darüber hinaus eine Assemblyanweisung, um sicherzustellen, dass „System.Transactions.dll“ geladen wird.</span><span class="sxs-lookup"><span data-stu-id="a4df4-143">The Service.svc file also contains an assembly directive to ensure that System.Transactions.dll is loaded.</span></span>

`<%@Assembly name="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"%>`

<span data-ttu-id="a4df4-144">Der Client erstellt einen Geltungsbereich für die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="a4df4-144">The client creates a transaction scope.</span></span> <span data-ttu-id="a4df4-145">Die Kommunikation mit dem Dienst findet innerhalb des Geltungsbereichs der Transaktion statt, sodass diese in der Folge als unteilbare Einheit behandelt wird, in der alle Nachrichten entweder erfolgreich sind oder fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-145">Communication with the service takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span> <span data-ttu-id="a4df4-146">Für die Transaktion wird ein Commit ausgeführt, indem `Complete` im Geltungsbereich der Transaktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a4df4-146">The transaction is committed by calling `Complete` on the transaction scope.</span></span>

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))
{
    // Open the ServiceHostBase to create listeners and start listening
    // for order status messages.
    serviceHost.Open();

    // Create a proxy with given client endpoint configuration
    OrderProcessorClient client = new OrderProcessorClient();

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
    using (TransactionScope scope = new
        TransactionScope(TransactionScopeOption.Required))
    {
        // Make a queued call to submit the purchase order
        client.SubmitPurchaseOrder(po,
       "net.msmq://localhost/private/ServiceModelSamplesOrder/OrderStatus");
        // Complete the transaction.
        scope.Complete();
    }

    //Closing the client gracefully closes the connection and cleans up
    //resources
    client.Close();

    Console.WriteLine();
    Console.WriteLine("Press <ENTER> to terminate client.");
    Console.ReadLine();

    // Close the ServiceHostBase to shutdown the service.
    serviceHost.Close();
    }
```

<span data-ttu-id="a4df4-147">Der Clientcode implementiert den `IOrderStatus`-Vertrag, um den Auftragsstatus vom Dienst zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-147">The client code implements the `IOrderStatus` contract to receive order status from the service.</span></span> <span data-ttu-id="a4df4-148">In diesem Fall druckt er den Auftragsstatus aus.</span><span class="sxs-lookup"><span data-stu-id="a4df4-148">In this case, it prints out the order status.</span></span>

```csharp
[ServiceBehavior]
public class OrderStatusService : IOrderStatus
{
    [OperationBehavior(TransactionAutoComplete = true,
                        TransactionScopeRequired = true)]
    public void OrderStatus(string poNumber, string status)
    {
        Console.WriteLine("Status of order {0}:{1} ",
                                         poNumber , status);
    }
}
```

<span data-ttu-id="a4df4-149">Die Auftragsstatuswarteschlange wird in der `Main`-Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="a4df4-149">The order status queue is created in the `Main` method.</span></span> <span data-ttu-id="a4df4-150">Die Clientkonfiguration beinhaltet die Dienstkonfiguration für den Auftragsstatus, um den Auftragsstatusdienst zu hosten, wie in der folgenden Beispielkonfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a4df4-150">The client configuration includes the order status service configuration to host the order status service, as shown in the following sample configuration.</span></span>

```xml
<appSettings>
    <!-- use appSetting to configure MSMQ queue name -->
    <add key="targetQueueName" value=".\private$\ServiceModelSamples/service.svc" />
    <add key="responseQueueName" value=".\private$\ServiceModelSamples/OrderStatus" />
  </appSettings>

<system.serviceModel>

    <services>
      <service
         name="Microsoft.ServiceModel.Samples.OrderStatusService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamples/OrderStatus"
                  binding="netMsmqBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderStatus" />
      </service>
    </services>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                address="net.msmq://localhost/private/ServiceModelSamples/service.svc"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
    </client>

  </system.serviceModel>
```

<span data-ttu-id="a4df4-151">Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Server- als auch im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4df4-151">When you run the sample, the client and service activities are displayed in both the server and client console windows.</span></span> <span data-ttu-id="a4df4-152">Sie können sehen, wie der Server Nachrichten vom Client empfängt.</span><span class="sxs-lookup"><span data-stu-id="a4df4-152">You can see the server receive messages from the client.</span></span> <span data-ttu-id="a4df4-153">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Server und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-153">Press ENTER in each console window to shut down the server and client.</span></span>

<span data-ttu-id="a4df4-154">Der Client zeigt die vom Server gesendeten Bestellstatusinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4df4-154">The client displays the order status information sent by the server:</span></span>

```console
Press <ENTER> to terminate client.
Status of order 70cf9d63-3dfa-4e69-81c2-23aa4478ebed :Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a4df4-155">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="a4df4-155">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="a4df4-156">Stellen Sie sicher, dass IIS 7,0 installiert ist, da es für die was-Aktivierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a4df4-156">Ensure that IIS 7.0 is installed, as it is required for WAS activation.</span></span>

2. <span data-ttu-id="a4df4-157">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="a4df4-157">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span> <span data-ttu-id="a4df4-158">Außerdem müssen Sie die WCF-nicht-http-Aktivierungs Komponenten installieren:</span><span class="sxs-lookup"><span data-stu-id="a4df4-158">In addition, you must install the WCF non-HTTP activation components:</span></span>

    1. <span data-ttu-id="a4df4-159">Wählen Sie im Menü **Start** die **Systemsteuerung** aus.</span><span class="sxs-lookup"><span data-stu-id="a4df4-159">From the **Start** menu, choose **Control Panel**.</span></span>

    2. <span data-ttu-id="a4df4-160">Wählen Sie **Programme und Funktionen**aus.</span><span class="sxs-lookup"><span data-stu-id="a4df4-160">Select **Programs and Features**.</span></span>

    3. <span data-ttu-id="a4df4-161">Klicken Sie **auf Windows-Funktionen ein-oder ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="a4df4-161">Click **Turn Windows Features on or off**.</span></span>

    4. <span data-ttu-id="a4df4-162">Klicken Sie unter **featurezusammenfassung**auf **Features hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a4df4-162">Under **Features Summary**, click **Add Features**.</span></span>

    5. <span data-ttu-id="a4df4-163">Erweitern Sie den Knoten **Microsoft .NET Framework 3,0** , und überprüfen Sie die Funktion **Windows Communication Foundation nicht-HTTP-Aktivierung** .</span><span class="sxs-lookup"><span data-stu-id="a4df4-163">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>

3. <span data-ttu-id="a4df4-164">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-164">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="a4df4-165">Führen Sie den Client aus, indem Sie "client.exe" von einem Befehlsfenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-165">Run the client by executing client.exe from a command window.</span></span> <span data-ttu-id="a4df4-166">Auf diese Weise wird die Warteschlange erstellt und eine Nachricht an sie gesendet.</span><span class="sxs-lookup"><span data-stu-id="a4df4-166">This creates the queue and sends a message to it.</span></span> <span data-ttu-id="a4df4-167">Der Client verbleibt in der Ausführung, um das Ergebnis des Lesens der Nachricht durch den Dienst zu sehen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-167">Leave the client running to see the result of the service reading the message</span></span>

5. <span data-ttu-id="a4df4-168">Der MSMQ-Aktivierungsdienst wird standardmäßig als Netzwerkdienst ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a4df4-168">The MSMQ activation service runs as Network Service by default.</span></span> <span data-ttu-id="a4df4-169">Daher muss die Warteschlange, die zur Aktivierung der Anwendung verwendet wird, über Empfangs- und Einsehberechtigungen für den Netzwerkdienst verfügen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-169">Therefore, the queue that is used to activate the application must have receive and peek permissions for Network Service.</span></span> <span data-ttu-id="a4df4-170">Diese können durch Verwendung von Message Queuing MMC hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="a4df4-170">This can be added by using the Message Queuing MMC:</span></span>

    1. <span data-ttu-id="a4df4-171">Klicken Sie im **Startmenü** auf **Ausführen**, geben Sie `Compmgmt.msc` ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="a4df4-171">From the **Start** menu, click **Run**, then type `Compmgmt.msc` and press ENTER.</span></span>

    2. <span data-ttu-id="a4df4-172">Erweitern Sie unter **Dienste und Anwendungen** **Message Queuing**.</span><span class="sxs-lookup"><span data-stu-id="a4df4-172">Under **Services and Applications**, expand **Message Queuing**.</span></span>

    3. <span data-ttu-id="a4df4-173">Klicken Sie auf **private Warteschlangen**.</span><span class="sxs-lookup"><span data-stu-id="a4df4-173">Click **Private Queues**.</span></span>

    4. <span data-ttu-id="a4df4-174">Klicken Sie mit der rechten Maustaste auf die Warteschlange (Service Model Samples/Service. svc), und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="a4df4-174">Right-click the queue (servicemodelsamples/Service.svc) and choose **Properties**.</span></span>

    5. <span data-ttu-id="a4df4-175">Klicken Sie auf der Registerkarte **Sicherheit** auf **Hinzufügen** , und geben Sie dem Netzwerkdienst die Berechtigungen Peek und Receive.</span><span class="sxs-lookup"><span data-stu-id="a4df4-175">On the **Security** tab, click **Add** and give peek and receive permissions to Network Service.</span></span>

6. <span data-ttu-id="a4df4-176">Konfigurieren Sie den Windows Process Activation Service (WAS), um die MSMQ-Aktivierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-176">Configure the Windows Process Activation Service (WAS) to support MSMQ activation.</span></span>

    <span data-ttu-id="a4df4-177">Zur Vereinfachung sind die folgenden beiden Schritte in der Batchdatei AddMsmqSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="a4df4-177">As a convenience, the following steps are implemented in a batch file called AddMsmqSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="a4df4-178">Zur Unterstützung der net.msmq-Aktivierung muss die Standardwebsite zuerst an das net.msmq-Protokoll gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="a4df4-178">To support net.msmq activation, the default Web site must first be bound to the net.msmq protocol.</span></span> <span data-ttu-id="a4df4-179">Sie können hierzu das Tool "appcmd.exe" verwenden, das mit dem IIS 7.0-Verwaltungstoolset installiert wird.</span><span class="sxs-lookup"><span data-stu-id="a4df4-179">This can be done using appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="a4df4-180">Führen Sie an einer Eingabeaufforderung auf höherer Ebene (Administrator) den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="a4df4-180">From an elevated (administrator) command prompt, run the following command.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        -+bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > <span data-ttu-id="a4df4-181">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="a4df4-181">This command is a single line of text.</span></span>

        <span data-ttu-id="a4df4-182">Dieser Befehl fügt der Standardwebsite eine net.msmq-Sitebindung hinzu.</span><span class="sxs-lookup"><span data-stu-id="a4df4-182">This command adds a net.msmq site binding to the default Web site.</span></span>

    2. <span data-ttu-id="a4df4-183">Alle Anwendungen innerhalb einer Site nutzen zwar eine gemeinsame net.msmq-Bindung, aber jede Anwendung kann die net.msmq-Unterstützung unabhängig von den anderen Anwendungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a4df4-183">Although all applications within a site share a common net.msmq binding, each application can enable net.msmq support individually.</span></span> <span data-ttu-id="a4df4-184">Um net.msmq für die Anwendung /servicemodelsamples zu aktivieren, führen Sie den folgenden Befehl in einer Eingabeaufforderung auf höherer Ebene (Administrator) aus.</span><span class="sxs-lookup"><span data-stu-id="a4df4-184">To enable net.msmq for the /servicemodelsamples application, run the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.msmq
        ```

        > [!NOTE]
        > <span data-ttu-id="a4df4-185">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="a4df4-185">This command is a single line of text.</span></span>

        <span data-ttu-id="a4df4-186">Dieser Befehl ermöglicht den Zugriff auf die Anwendung/ServiceModelSamples-Anwendung mithilfe von `http://localhost/servicemodelsamples` und `net.msmq://localhost/servicemodelsamples`.</span><span class="sxs-lookup"><span data-stu-id="a4df4-186">This command enables the /servicemodelsamples application to be accessed using `http://localhost/servicemodelsamples` and `net.msmq://localhost/servicemodelsamples`.</span></span>

7. <span data-ttu-id="a4df4-187">Falls noch nicht geschehen, stellen Sie sicher, dass der MSMQ-Aktivierungsdienst aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a4df4-187">If you have not done so previously, ensure that the MSMQ activation service is enabled.</span></span> <span data-ttu-id="a4df4-188">Klicken Sie im **Startmenü** auf **Ausführen**, und geben Sie `Services.msc`ein.</span><span class="sxs-lookup"><span data-stu-id="a4df4-188">From the **Start** menu, click **Run**, and type `Services.msc`.</span></span> <span data-ttu-id="a4df4-189">Durchsuchen Sie die Liste der Dienste für den **net. MSMQ-Listeneradapter**.</span><span class="sxs-lookup"><span data-stu-id="a4df4-189">Search the list of services for the **Net.Msmq Listener Adapter**.</span></span> <span data-ttu-id="a4df4-190">Klicken Sie mit der rechten Maustaste, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="a4df4-190">Right-click and select **Properties**.</span></span> <span data-ttu-id="a4df4-191">Legen Sie den **Starttyp** auf **automatisch**fest, klicken Sie auf übernehmen und **dann** auf **Start** .</span><span class="sxs-lookup"><span data-stu-id="a4df4-191">Set the **Startup Type** to **Automatic**, click **Apply** and click the **Start** button.</span></span> <span data-ttu-id="a4df4-192">Dieser Schritt muss nur einmal vor der ersten Verwendung des Net.Msmq-Listeneradapterdiensts durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a4df4-192">This step must only be done once prior to the first usage of the Net.Msmq Listener Adapter service.</span></span>

8. <span data-ttu-id="a4df4-193">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a4df4-193">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="a4df4-194">Ändern Sie zusätzlich den Code auf dem Client, der die Bestellung einsendet, sodass beim Einsenden der Bestellung der Computername im URI der Warteschlange angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a4df4-194">Additionally, change the code on the client that submits the purchase order to reflect the computer name in the URI of the queue when submitting the purchase order.</span></span> <span data-ttu-id="a4df4-195">Verwenden Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="a4df4-195">Use the following code:</span></span>

    ```csharp
    client.SubmitPurchaseOrder(po, "net.msmq://localhost/private/ServiceModelSamples/OrderStatus");
    ```

9. <span data-ttu-id="a4df4-196">Entfernen Sie die net.msmq-Sitebindung, die Sie für dieses Beispiel hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="a4df4-196">Remove the net.msmq site binding you added for this sample.</span></span>

    <span data-ttu-id="a4df4-197">Zur Vereinfachung sind die folgenden beiden Schritte in einer Batchdatei namens RemoveMsmqSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet:</span><span class="sxs-lookup"><span data-stu-id="a4df4-197">As a convenience, the following steps are implemented in a batch file called RemoveMsmqSiteBinding.cmd located in the sample directory:</span></span>

    1. <span data-ttu-id="a4df4-198">Entfernen Sie net.msmq aus der Liste der aktivierten Protokolle, indem Sie den folgenden Befehl an einer Eingabeaufforderung auf höherer Ebene (Administrator) ausführen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-198">Remove net.msmq from the list of enabled protocols by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="a4df4-199">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="a4df4-199">This command is a single line of text.</span></span>

    2. <span data-ttu-id="a4df4-200">Entfernen Sie die net.msmq-Sitebindung, indem Sie den folgenden Befehl in einer Eingabeaufforderung auf höher Ebene ausführen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-200">Remove the net.msmq site binding by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > <span data-ttu-id="a4df4-201">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="a4df4-201">This command is a single line of text.</span></span>

    > [!WARNING]
    > <span data-ttu-id="a4df4-202">Durch die Ausführung der Batchdatei wird der DefaultAppPool zurückgesetzt und mit .NET Framework, Version 2.0, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a4df4-202">Running the batch file will reset the DefaultAppPool to run using .NET Framework version 2.0.</span></span>

<span data-ttu-id="a4df4-203">Standardmäßig wird mit der `netMsmqBinding`-Bindung die Transportsicherheit aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a4df4-203">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="a4df4-204">Der Typ der Transportsicherheit wird durch zwei Eigenschaften festgelegt: `MsmqAuthenticationMode` und `MsmqProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="a4df4-204">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="a4df4-205">Standardmäßig wird der Authentifizierungsmodus auf `Windows` festgelegt, und die Schutzebene wird auf `Sign` gesetzt.</span><span class="sxs-lookup"><span data-stu-id="a4df4-205">By default the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="a4df4-206">Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es ein Teil einer Domäne sein.</span><span class="sxs-lookup"><span data-stu-id="a4df4-206">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="a4df4-207">Wenn Sie dieses Beispiel auf einem Computer ausführen, der nicht Teil einer Domäne ist, wird folgende Fehlermeldung ausgegeben: "Das interne Message Queuing-Zertifikat für diesen Benutzer ist nicht vorhanden."</span><span class="sxs-lookup"><span data-stu-id="a4df4-207">If you run this sample on a computer that is not part of a domain, the following error is received: "User's internal message queuing certificate does not exist".</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="a4df4-208">So führen Sie das Beispiel auf einem Computer aus, der zu einer Arbeitsgruppe gehört</span><span class="sxs-lookup"><span data-stu-id="a4df4-208">To run the sample on a computer joined to a workgroup</span></span>

1. <span data-ttu-id="a4df4-209">Wenn Ihr Computer nicht zu einer Domäne gehört, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf "None" festlegen, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4df4-209">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to none as shown in the following sample configuration.</span></span>

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding configurationName="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

2. <span data-ttu-id="a4df4-210">Ändern Sie die Konfiguration sowohl auf dem Server als auch auf dem Client, bevor Sie das Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-210">Change the configuration on both the server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a4df4-211">Das Festlegen von `security mode` auf `None` entspricht dem Festlegen von `MsmqAuthenticationMode`, `MsmqProtectionLevel` und der `Message`-Sicherheit auf `None`.</span><span class="sxs-lookup"><span data-stu-id="a4df4-211">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel` and `Message` security to `None`.</span></span>

3. <span data-ttu-id="a4df4-212">Um die Aktivierung auf einem Computer zu ermöglichen, der zu einer Arbeitsgruppe gehört, müssen sowohl der Aktivierungsdienst als auch der Arbeitsprozess mit einem spezifischen Benutzerkonto ausgeführt werden (das gleiche Konto für beide), und die Warteschlange muss über ACLs für das spezifische Benutzerkonto verfügen.</span><span class="sxs-lookup"><span data-stu-id="a4df4-212">To enable activation in a computer joined to a workgroup, both the activation service and the worker process must be run with a specific user account (must be same for both) and the queue must have ACLs for the specific user account.</span></span>

     <span data-ttu-id="a4df4-213">So ändern Sie die Identität, unter der der Arbeitsprozess ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="a4df4-213">To change the identity that the worker process runs under:</span></span>

    1. <span data-ttu-id="a4df4-214">Führen Sie "Inetmgr.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="a4df4-214">Run Inetmgr.exe.</span></span>

    2. <span data-ttu-id="a4df4-215">Klicken Sie unter **Anwendungs Pools**mit der rechten Maustaste auf den **AppPool** (normalerweise **DefaultAppPool**), und wählen Sie **Anwendungs Pool Standardwerte festlegen**... aus.</span><span class="sxs-lookup"><span data-stu-id="a4df4-215">Under **Application Pools**, right-click the **AppPool** (typically **DefaultAppPool**) and choose **Set Application Pool Defaults…**.</span></span>

    3. <span data-ttu-id="a4df4-216">Ändern Sie die Identitätseigenschaften, um das bestimmte Benutzerkonto zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4df4-216">Change the Identity properties to use the specific user account.</span></span>

     <span data-ttu-id="a4df4-217">So ändern Sie die Identität, unter der der Aktivierungsdienst ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="a4df4-217">To change the identity that the Activation Service runs under:</span></span>

    1. <span data-ttu-id="a4df4-218">Führen Sie "Services.msc" aus.</span><span class="sxs-lookup"><span data-stu-id="a4df4-218">Run Services.msc.</span></span>

    2. <span data-ttu-id="a4df4-219">Klicken Sie mit der rechten Maustaste auf **net. MsmqListener**, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="a4df4-219">Right-click the **Net.MsmqListener Adapter**, and choose **Properties**.</span></span>

4. <span data-ttu-id="a4df4-220">Ändern Sie das Konto auf der Registerkarte **Anmeldung** .</span><span class="sxs-lookup"><span data-stu-id="a4df4-220">Change the account in the **LogOn** tab.</span></span>

5. <span data-ttu-id="a4df4-221">In der Arbeitsgruppe muss der Dienst auch mit einem uneingeschränkten Token ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a4df4-221">In workgroup, the service must also run using an unrestricted token.</span></span> <span data-ttu-id="a4df4-222">Führen Sie hierzu in einem Befehlsfenster Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="a4df4-222">To do this, run the following in a command window:</span></span>

    ```console
    sc sidtype netmsmqactivator unrestricted
    ```

## <a name="see-also"></a><span data-ttu-id="a4df4-223">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4df4-223">See also</span></span>

- [<span data-ttu-id="a4df4-224">AppFabric-Hosting-und persistenzbeispiele</span><span class="sxs-lookup"><span data-stu-id="a4df4-224">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
