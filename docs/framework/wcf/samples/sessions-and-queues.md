---
title: Sitzungen und Warteschlangen
ms.date: 03/30/2017
ms.assetid: 47d7c5c2-1e6f-4619-8003-a0ff67dcfbd6
ms.openlocfilehash: 489a8f5e782faca679991809e575e98153de95e0
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140606"
---
# <a name="sessions-and-queues"></a><span data-ttu-id="0cac5-102">Sitzungen und Warteschlangen</span><span class="sxs-lookup"><span data-stu-id="0cac5-102">Sessions and Queues</span></span>
<span data-ttu-id="0cac5-103">Dieses Beispiel veranschaulicht, wie ein Satz zusammengehöriger Nachrichten bei der Kommunikation unter Verwendung von Warteschlangen über den MSMQ-Transport (Message Queuing) gesendet und empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="0cac5-103">This sample demonstrates how to send and receive a set of related messages in queued communication over the Message Queuing (MSMQ) transport.</span></span> <span data-ttu-id="0cac5-104">In diesem Beispiel wird die `netMsmqBinding`-Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0cac5-104">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="0cac5-105">Der Dienst ist eine selbst gehostete Konsolenanwendung, die es Ihnen ermöglicht, den Dienst beim Empfang von Nachrichten in der Warteschlange zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="0cac5-105">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0cac5-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="0cac5-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0cac5-107">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="0cac5-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0cac5-108">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0cac5-108">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="0cac5-109">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="0cac5-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0cac5-110">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0cac5-110">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Session`  
  
 <span data-ttu-id="0cac5-111">In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="0cac5-111">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="0cac5-112">Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet.</span><span class="sxs-lookup"><span data-stu-id="0cac5-112">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="0cac5-113">Der Dienst empfängt Nachrichten aus der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="0cac5-113">The service receives messages from the queue.</span></span> <span data-ttu-id="0cac5-114">Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="0cac5-114">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="0cac5-115">Manchmal sendet ein Client eine Reihe von Nachrichten, die in einer Gruppe zusammengehören.</span><span class="sxs-lookup"><span data-stu-id="0cac5-115">Sometimes, a client sends a set of messages that are related to each other in a group.</span></span> <span data-ttu-id="0cac5-116">Wenn Nachrichten zusammen oder in einer angegebenen Reihenfolge verarbeitet werden müssen, können Sie mithilfe einer Warteschlange zwecks Verarbeitung durch eine einzige Empfangsanwendung zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="0cac5-116">When messages must be processed together or in a specified order, a queue can be used to group them together, for processing by a single receiving application.</span></span> <span data-ttu-id="0cac5-117">Dies ist besonders wichtig, wenn in einer Gruppe von Servern mehrere Empfangsanwendungen vorhanden sind und sichergestellt werden muss, dass eine Gruppe von Nachrichten von derselben empfangenden Anwendung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="0cac5-117">This is particularly important when there are several receiving applications on a group of servers and it is necessary to ensure that a group of messages is processed by the same receiving application.</span></span> <span data-ttu-id="0cac5-118">Warteschlangensitzungen sind ein Mechanismus zum Senden und Empfangen eines Satzes zusammengehöriger Nachrichten, die alle zusammen verarbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0cac5-118">Queued sessions are a mechanism used to send and receive a related set of messages that must get processed all at once.</span></span> <span data-ttu-id="0cac5-119">Damit Warteschlangensitzungen dieses Muster bieten, ist eine Transaktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0cac5-119">Queued sessions require a transaction to exhibit this pattern.</span></span>  
  
 <span data-ttu-id="0cac5-120">Im vorliegenden Beispiel sendet der Client im Rahmen einer Sitzung innerhalb des Bereichs einer einzigen Transaktion eine Reihe von Nachrichten an den Dienst.</span><span class="sxs-lookup"><span data-stu-id="0cac5-120">In the sample, the client sends a number of messages to the service as part of a session within the scope of a single transaction.</span></span>  
  
 <span data-ttu-id="0cac5-121">Der Dienstvertrag ist `IOrderTaker`, der einen unidirektionalen Dienst definiert, der für die Verwendung mit Warteschlangen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="0cac5-121">The service contract is `IOrderTaker`, which defines a one-way service that is suitable for use with queues.</span></span> <span data-ttu-id="0cac5-122">Der in dem Vertrag im folgenden Beispielcode verwendete <xref:System.ServiceModel.SessionMode> zeigt an, dass die Nachrichten zu der Sitzung gehören.</span><span class="sxs-lookup"><span data-stu-id="0cac5-122">The <xref:System.ServiceModel.SessionMode> used in the contract shown in the following sample code indicates that the messages are part of the session.</span></span>  

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface IOrderTaker  
{  
    [OperationContract(IsOneWay = true)]  
    void OpenPurchaseOrder(string customerId);  
  
    [OperationContract(IsOneWay = true)]  
    void AddProductLineItem(string productId, int quantity);  
  
    [OperationContract(IsOneWay = true)]  
    void EndPurchaseOrder();  
}  
```

 <span data-ttu-id="0cac5-123">Der Dienst definiert Dienstvorgänge so, dass der erste Vorgang in einer Transaktion eingetragen, diese jedoch nicht automatisch abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="0cac5-123">The service defines service operations in such a way that the first operation enlists in a transaction but does not automatically complete the transaction.</span></span> <span data-ttu-id="0cac5-124">Auch die nachfolgenden Vorgänge werden in derselben Transaktion eingetragen, die aber nicht automatisch abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="0cac5-124">Subsequent operations also enlist in the same transaction but do not automatically complete.</span></span> <span data-ttu-id="0cac5-125">Der letzte Vorgang in der Sitzung schließt die Transaktion automatisch ab.</span><span class="sxs-lookup"><span data-stu-id="0cac5-125">The last operation in the session automatically completes the transaction.</span></span> <span data-ttu-id="0cac5-126">So wird die gleiche Transaktion für mehrere Vorgangsaufrufe im Dienstvertrag verwendet.</span><span class="sxs-lookup"><span data-stu-id="0cac5-126">Thus, the same transaction is used for several operation invocations in the service contract.</span></span> <span data-ttu-id="0cac5-127">Wenn einer der Vorgänge eine Ausnahme auslöst, wird ein Rollback der Transaktion ausgeführt und die Sitzung zurück in die Warteschlange gelegt.</span><span class="sxs-lookup"><span data-stu-id="0cac5-127">If any of the operations throw an exception, then the transaction rolls back and the session is put back into the queue.</span></span> <span data-ttu-id="0cac5-128">Nach erfolgreichem Abschluss des letzten Vorgangs wird ein Commit für die Transaktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0cac5-128">Upon successful completion of the last operation, the transaction is committed.</span></span> <span data-ttu-id="0cac5-129">Der Dienst verwendet `PerSession` als <xref:System.ServiceModel.InstanceContextMode>, um sämtliche Nachrichten in einer Sitzung in derselben Instanz des Diensts zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="0cac5-129">The service uses `PerSession` as the <xref:System.ServiceModel.InstanceContextMode> to receive all messages in a session on the same instance of the service.</span></span>  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class OrderTakerService : IOrderTaker  
{  
    PurchaseOrder po;  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                 TransactionAutoComplete = false)]  
    public void OpenPurchaseOrder(string customerId)  
    {  
        Console.WriteLine("Creating purchase order");  
        po = new PurchaseOrder(customerId);  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                  TransactionAutoComplete = false)]  
    public void AddProductLineItem(string productId, int quantity)  
    {  
        po.AddProductLineItem(productId, quantity);  
        Console.WriteLine("Product " + productId + " quantity " +
                            quantity + " added to purchase order");  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                  TransactionAutoComplete = true)]  
    public void EndPurchaseOrder()  
    {  
       Console.WriteLine("Purchase Order Completed");  
       Console.WriteLine();  
       Console.WriteLine(po.ToString());  
    }  
}  
```

 <span data-ttu-id="0cac5-130">Der Dienst ist selbst gehostet.</span><span class="sxs-lookup"><span data-stu-id="0cac5-130">The service is self hosted.</span></span> <span data-ttu-id="0cac5-131">Bei Verwendung des MSMQ-Transports muss die Warteschlange im Voraus erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0cac5-131">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="0cac5-132">Dies kann manuell erfolgen oder mithilfe eines Codes.</span><span class="sxs-lookup"><span data-stu-id="0cac5-132">This can be done manually or through code.</span></span> <span data-ttu-id="0cac5-133">In diesem Beispiel enthält der Dienst <xref:System.Messaging>-Code, um zu überprüfen, ob die Warteschlange bereits vorhanden ist, und um sie andernfalls zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0cac5-133">In this sample, the service contains <xref:System.Messaging> code to check for the existence of the queue and creates it, if necessary.</span></span> <span data-ttu-id="0cac5-134">Der Warteschlangenname wird mithilfe der <xref:System.Configuration.ConfigurationManager.AppSettings%2A>-Klasse aus der Konfigurationsdatei gelesen.</span><span class="sxs-lookup"><span data-stu-id="0cac5-134">The queue name is read from the configuration file using the <xref:System.Configuration.ConfigurationManager.AppSettings%2A> class.</span></span>  

```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the OrderTakerService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderTakerService)))  
    {  
        // Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();
    }  
}  
```

 <span data-ttu-id="0cac5-135">Der MSMQ-Warteschlangenname wird im appSettings-Abschnitt der Konfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="0cac5-135">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="0cac5-136">Der Endpunkt für den Dienst wird im Abschnitt „system.serviceModel“ der Konfigurationsdatei definiert und gibt die `netMsmqBinding`-Bindung an.</span><span class="sxs-lookup"><span data-stu-id="0cac5-136">The endpoint for the service is defined in the system.serviceModel section of the configuration file and specifies the `netMsmqBinding` binding.</span></span>  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesSession" />  
</appSettings>  
  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
      ...  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesSession"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
      ...  
    </service>  
  </services>  
  ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="0cac5-137">Der Client erstellt einen Geltungsbereich für die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="0cac5-137">The client creates a transaction scope.</span></span> <span data-ttu-id="0cac5-138">Alle Nachrichten in der Sitzung werden an die Warteschlange innerhalb des Transaktionsbereichs gesendet, wo sie als eine unteilbare Einheit behandelt werden, so dass sämtliche Nachrichten entweder erfolgreich sind oder fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="0cac5-138">All messages in the session are sent to the queue within the transaction scope, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span> <span data-ttu-id="0cac5-139">Das Commit für die Transaktion wird durch Aufrufen von <xref:System.Transactions.TransactionScope.Complete%2A> ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0cac5-139">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A>.</span></span>  

```csharp
//Create a transaction scope.  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
    // Create a client with given client endpoint configuration.  
    OrderTakerClient client = new OrderTakerClient("OrderTakerEndpoint");  
    // Open a purchase order.  
    client.OpenPurchaseOrder("somecustomer.com");  
    Console.WriteLine("Purchase Order created");  
  
    // Add product line items.  
    Console.WriteLine("Adding 10 quantities of blue widget");  
    client.AddProductLineItem("Blue Widget", 10);  
  
    Console.WriteLine("Adding 23 quantities of red widget");  
    client.AddProductLineItem("Red Widget", 23);  
  
    // Close the purchase order.  
    Console.WriteLine("Closing the purchase order");  
    client.EndPurchaseOrder();  
  
    //Closing the client gracefully closes the connection and cleans up resources.  
    client.Close();
  
    // Complete the transaction.  
    scope.Complete();  
}  
```

> [!NOTE]
> <span data-ttu-id="0cac5-140">Sie können für sämtliche Nachrichten in der Sitzung nur eine einzige Transaktion verwenden, und alle Nachrichten in der Sitzung müssen vor deren Commit gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cac5-140">You can use only a single transaction for all messages in the session and all messages in the session must be sent before committing the transaction.</span></span> <span data-ttu-id="0cac5-141">Wenn der Client geschlossen wird, wird auch die Sitzung geschlossen.</span><span class="sxs-lookup"><span data-stu-id="0cac5-141">Closing the client closes the session.</span></span> <span data-ttu-id="0cac5-142">Daher muss der Client geschlossen werden, bevor die Transaktion abgeschlossen ist, um alle Nachrichten in der Sitzung an die Warteschlange zu senden.</span><span class="sxs-lookup"><span data-stu-id="0cac5-142">Therefore, the client has to be closed before the transaction is completed to send all messages in the session to the queue.</span></span>  
  
 <span data-ttu-id="0cac5-143">Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0cac5-143">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="0cac5-144">Sie können sehen, wie der Dienst Nachrichten vom Client empfängt.</span><span class="sxs-lookup"><span data-stu-id="0cac5-144">You can see the service receive messages from the client.</span></span> <span data-ttu-id="0cac5-145">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0cac5-145">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="0cac5-146">Beachten Sie, dass aufgrund der Verwendung einer Warteschlange der Client und der Dienst nicht gleichzeitig ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0cac5-146">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="0cac5-147">Sie können den Client ausführen, ihn schließen und anschließend den Dienst starten, der dann trotzdem noch die Nachrichten des Clients empfängt.</span><span class="sxs-lookup"><span data-stu-id="0cac5-147">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span>  
  
 <span data-ttu-id="0cac5-148">Auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="0cac5-148">On the client.</span></span>  
  
```console  
Purchase Order created  
Adding 10 quantities of blue widget  
Adding 23 quantities of red widget  
Closing the purchase order  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="0cac5-149">Beim Dienst.</span><span class="sxs-lookup"><span data-stu-id="0cac5-149">On the service.</span></span>  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Creating purchase order  
Product Blue Widget quantity 10 added to purchase order  
Product Red Widget quantity 23 added to purchase order  
Purchase Order Completed  
  
Purchase Order: 7c86fef0-2306-4c51-80e6-bcabcc1a6e5e  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 10 of Blue Widget @unit price: $2985  
                Order LineItem: 23 of Red Widget @unit price: $156  
        Total cost of this order: $33438  
        Order status: Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0cac5-150">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="0cac5-150">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0cac5-151">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="0cac5-151">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0cac5-152">Um die c#-, C++-oder Visual Basic .NET-Edition der Projekt Mappe zu erstellen, befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0cac5-152">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="0cac5-153">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0cac5-153">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
 <span data-ttu-id="0cac5-154">Standardmäßig wird mit <xref:System.ServiceModel.NetMsmqBinding> die Transportsicherheit aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0cac5-154">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="0cac5-155">Es gibt zwei relevante Eigenschaften für die MSMQ <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> - <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` Transportsicherheit: Standardmäßig wird der Authentifizierungsmodus auf `Windows` und die Schutz Ebene auf `Sign`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0cac5-155">There are two relevant properties for MSMQ transport security namely, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="0cac5-156">Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es Teil einer Domäne sein, und die Active Directory-Integrationsoption für MSMQ muss installiert sein.</span><span class="sxs-lookup"><span data-stu-id="0cac5-156">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="0cac5-157">Wenn Sie dieses Beispiel auf einem Computer ausführen, der diese Kriterien nicht erfüllt, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="0cac5-157">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="0cac5-158">So führen Sie das Beispiel auf einem Computer aus, der sich in einer Arbeitsgruppe befindet oder über keine Active Directory-Integration verfügt</span><span class="sxs-lookup"><span data-stu-id="0cac5-158">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1. <span data-ttu-id="0cac5-159">Wenn Ihr Computer nicht zu einer Domäne gehört oder auf ihm keine Active Directory-Integration installiert ist, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf `None` setzen, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0cac5-159">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <services>  
        <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
                 behaviorConfiguration="OrderTakerServiceBehavior">  
          <host>  
            <baseAddresses>  
              <add baseAddress=  
             "http://localhost:8000/ServiceModelSamples/service"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint  
              address=  
            "net.msmq://localhost/private/ServiceModelSamplesSession"  
              binding="netMsmqBinding"  
              bindingConfiguration="Binding1"  
           contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
          <!-- The mex endpoint is exposed at-->
          <!--http://localhost:8000/ServiceModelSamples/service/mex. -->  
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
            <behavior name="OrderTakerServiceBehavior">  
              <serviceMetadata httpGetEnabled="True"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    ```  
  
2. <span data-ttu-id="0cac5-160">Ändern Sie die Konfiguration sowohl auf dem Server als auch auf dem Client, bevor Sie das Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="0cac5-160">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0cac5-161">Das Einstellen des Sicherheitsmodus auf `None` ist dasselbe, wie <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> und `Message`-Sicherheit auf `None` zu setzen.</span><span class="sxs-lookup"><span data-stu-id="0cac5-161">Setting security mode to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>  
