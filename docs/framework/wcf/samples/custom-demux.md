---
title: Benutzerdefinierter Demux
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc54065c-518e-4146-b24a-0fe00038bfa7
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 45184c2d884347baef4090ed496e22e77aab5423
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="custom-demux"></a><span data-ttu-id="a3863-102">Benutzerdefinierter Demux</span><span class="sxs-lookup"><span data-stu-id="a3863-102">Custom Demux</span></span>
<span data-ttu-id="a3863-103">In diesem Beispiel wird veranschaulicht, wie MSMQ-Nachrichtenheader unterschiedlichen Dienstvorgängen zugeordnet werden können, damit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Dienste, bei denen <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> besteht keine Einschränkung auf die Verwendung eines einzigen Dienstvorgangs aus, wie in der [Message Queuing Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) und [Windows Communication Foundation zu Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) Beispiele.</span><span class="sxs-lookup"><span data-stu-id="a3863-103">This sample demonstrates how MSMQ message headers can be mapped to different service operations so that [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services that use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> are not limited to using one service operation as demonstrated in the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) and [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) samples.</span></span>  
  
 <span data-ttu-id="a3863-104">Der Dienst ist in diesem Beispiel eine selbst gehostete Konsolenanwendung, sodass Sie den Dienst beobachten können, der Nachrichten in Warteschlangen empfängt.</span><span class="sxs-lookup"><span data-stu-id="a3863-104">The service in this sample is a self-hosted console application to enable you to observe the service that receives queued messages.</span></span>  
  
 <span data-ttu-id="a3863-105">Der Dienstvertrag ist `IOrderProcessor` und definiert einen unidirektionalen Dienst, der für die Verwendung mit Warteschlangen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="a3863-105">The service contract is `IOrderProcessor`, and defines a one-way service that is suitable for use with queues.</span></span>  

```csharp
[ServiceContract]  
[KnownType(typeof(PurchaseOrder))]  
[KnownType(typeof(String))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Name = "SubmitPurchaseOrder")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
  
    [OperationContract(IsOneWay = true, Name = "CancelPurchaseOrder")]  
    void CancelPurchaseOrder(MsmqMessage<string> ponumber);  
}  
```

 <span data-ttu-id="a3863-106">Eine MSMQ-Nachricht besitzt keinen Aktionsheader.</span><span class="sxs-lookup"><span data-stu-id="a3863-106">An MSMQ message does not have an Action header.</span></span> <span data-ttu-id="a3863-107">Es ist nicht möglich, Vorgangsverträgen unterschiedliche MSMQ-Nachrichten automatisch zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a3863-107">It is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="a3863-108">Deshalb kann es nur einen Vorgangsvertrag geben.</span><span class="sxs-lookup"><span data-stu-id="a3863-108">Therefore, there can be only one operation contract.</span></span> <span data-ttu-id="a3863-109">Um diese Einschränkung zu umgehen, implementiert der Dienst die <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>-Methode der <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a3863-109">To overcome this limitation, the service implements the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method of the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface.</span></span> <span data-ttu-id="a3863-110">Die <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>-Methode ermöglicht dem Dienst, einem bestimmten Dienstvorgang einen bestimmten Nachrichtenheader zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a3863-110">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method enables the service to map a given header of the message to a particular service operation.</span></span> <span data-ttu-id="a3863-111">In diesem Beispiel wird den Dienstvorgängen der Bezeichnungsheader der Nachricht zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a3863-111">In this sample, the message's label header is mapped to the service operations.</span></span> <span data-ttu-id="a3863-112">Der `Name`-Parameter des Vorgangsvertrags legt fest, welcher Dienstvorgang für eine bestimmte Nachrichtenbezeichnung weitergeleitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="a3863-112">The `Name` parameter of the operation contract determines which service operation must be dispatched for a given message label.</span></span> <span data-ttu-id="a3863-113">Wenn der Bezeichnungsheader der Nachricht z. B. "SubmitPurchaseOrder" enthält, wird der "SubmitPurchaseOrder"-Dienstvorgang aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a3863-113">For example, if the message's label header contains "SubmitPurchaseOrder", the "SubmitPurchaseOrder" service operation is invoked.</span></span>  

```csharp
public class OperationSelector : IDispatchOperationSelector  
{  
    public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
    {  
        MsmqIntegrationMessageProperty property = MsmqIntegrationMessageProperty.Get(message);  
        return property.Label;  
    }  
}  
```

 <span data-ttu-id="a3863-114">Der Dienst muss die <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29>-Methode der <xref:System.ServiceModel.Description.IContractBehavior>-Schnittstelle implementieren, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a3863-114">The service must implement the <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> method of the <xref:System.ServiceModel.Description.IContractBehavior> interface as shown in the following sample code.</span></span> <span data-ttu-id="a3863-115">Diese wendet den benutzerdefinierten `OperationSelector` auf die Dienstframework-Dispatchlaufzeit an.</span><span class="sxs-lookup"><span data-stu-id="a3863-115">This applies the custom `OperationSelector` to the service framework dispatch runtime.</span></span>  

```csharp
void IContractBehavior.ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
{  
    dispatch.OperationSelector = new OperationSelector();  
}  
```

 <span data-ttu-id="a3863-116">Eine Nachricht muss den <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> des Verteilers durchlaufen, bevor die Vorgangsauswahl erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="a3863-116">A message must pass through the dispatcher's <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> before getting to the OperationSelector.</span></span> <span data-ttu-id="a3863-117">Standardmäßig wird eine Nachricht zurückgewiesen, wenn ihre Aktion auf keinem der vom Dienst implementierten Verträge gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="a3863-117">By default a message is rejected if its action cannot be found on any contract implemented by the service.</span></span> <span data-ttu-id="a3863-118">Um diese Prüfung zu vermeiden, implementieren wir ein <xref:System.ServiceModel.Description.IEndpointBehavior> namens `MatchAllFilterBehavior`, das es allen Nachrichten ermöglicht, den `ContractFilter` zu passieren, indem der <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> folgendermaßen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="a3863-118">To avoid this check, we implement an <xref:System.ServiceModel.Description.IEndpointBehavior> named `MatchAllFilterBehavior`, which allows any message to pass through the `ContractFilter` by applying the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> as follows.</span></span>  

```csharp
public void ApplyDispatchBehavior(ServiceEndpoint serviceEndpoint, EndpointDispatcher endpointDispatcher)  
{  
    endpointDispatcher.ContractFilter = new MatchAllMessageFilter();  
}  
```
  
 <span data-ttu-id="a3863-119">Wenn der Dienst eine Nachricht empfängt, wird der entsprechende Dienstvorgang mithilfe der Informationen im Bezeichnungsheader verteilt.</span><span class="sxs-lookup"><span data-stu-id="a3863-119">When a message is received by the service, the appropriate service operation is dispatched using the information provided by the label header.</span></span> <span data-ttu-id="a3863-120">Der Nachrichtentext wird in ein `PurchaseOrder`-Objekt deserialisiert, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a3863-120">The body of the message is deserialized into a `PurchaseOrder` object, as shown in the following sample code.</span></span>  

```csharp
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
{  
    PurchaseOrder po = (PurchaseOrder)msg.Body;  
    Random statusIndexer = new Random();  
    po.Status = (OrderStates)statusIndexer.Next(3);  
    Console.WriteLine("Processing {0} ", po);  
}  
```

 <span data-ttu-id="a3863-121">Der Dienst ist selbst gehostet.</span><span class="sxs-lookup"><span data-stu-id="a3863-121">The service is self-hosted.</span></span> <span data-ttu-id="a3863-122">Bei der Verwendung von MSMQ muss die Warteschlange im Voraus erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a3863-122">When using the MSMQ, the queue that is used must be created in advance.</span></span> <span data-ttu-id="a3863-123">Dies kann manuell erfolgen oder mithilfe eines Codes.</span><span class="sxs-lookup"><span data-stu-id="a3863-123">This can be done manually or through code.</span></span> <span data-ttu-id="a3863-124">In diesem Beispiel enthält der Dienst einen Code, um zu überprüfen, ob die Warteschlange bereits vorhanden ist und um die Warteschlange gegebenenfalls zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a3863-124">In this sample, the service contains code to check for the existence of the queue and creates it if the queue does not exist.</span></span> <span data-ttu-id="a3863-125">Der Warteschlangenname wird aus der Konfigurationsdatei gelesen.</span><span class="sxs-lookup"><span data-stu-id="a3863-125">The queue name is read from the configuration file.</span></span>  

```csharp
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration  
    string queueName = ConfigurationManager.AppSettings["orderQueueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {                 
        ServiceEndpoint endpoint = serviceHost.Description.Endpoints[0];  
        endpoint.Behaviors.Add(new MatchAllFilterBehavior());  
  
        //Open the ServiceHost to create listeners and start listening for messages.  
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

 <span data-ttu-id="a3863-126">Der MSMQ-Warteschlangenname wird im appSettings-Abschnitt der Konfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="a3863-126">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3863-127">Im Warteschlangennamen wird ein Punkt (.) für den lokalen Computer verwendet, und in der Pfadangabe werden umgekehrte Schrägstriche als Trennzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3863-127">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="a3863-128">Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunktadresse gibt ein msmq.formatname-Schema an, und für den lokalen Computer wird localhost verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3863-128">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint address specifies a msmq.formatname scheme, and uses localhost for the local computer.</span></span> <span data-ttu-id="a3863-129">Dem Schema folgt eine ordnungsgemäß entsprechend den Namens- und Adressierungsrichtlinien des MSMQ-Formats formatierte Warteschlangenadresse.</span><span class="sxs-lookup"><span data-stu-id="a3863-129">What follows the scheme is a properly formatted queue address according to the MSMQ Format name addressing guidelines.</span></span>  
  
```xml  
<appSettings>  
    <!-- Use appSetting to configure the MSMQ queue name. -->  
    <add key="queueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="a3863-130">Dieses Beispiel erfordert die Installation von [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=95143).</span><span class="sxs-lookup"><span data-stu-id="a3863-130">This sample requires the installation of [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=95143).</span></span>  
  
 <span data-ttu-id="a3863-131">Starten Sie den Dienst, und führen Sie den Client aus.</span><span class="sxs-lookup"><span data-stu-id="a3863-131">Start the service and run the client.</span></span>  
  
 <span data-ttu-id="a3863-132">Auf dem Client wird die folgende Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3863-132">The following output is seen on the client.</span></span>  
  
```  
Placed the order:Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
Canceled the Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="a3863-133">Auf dem Dienst muss die folgende Ausgabe angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a3863-133">The following output must be seen on the service.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
Processing Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Shipped  
Purchase Order 28fc457a-1a56-4fe0-9dde-156965c21ed6 is canceled  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a3863-134">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="a3863-134">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a3863-135">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a3863-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="a3863-136">Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a3863-136">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="a3863-137">Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="a3863-137">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="a3863-138">Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen.</span><span class="sxs-lookup"><span data-stu-id="a3863-138">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="a3863-139">Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a3863-139">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="a3863-140">Öffnen Sie Server-Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3863-140">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="a3863-141">Erweitern Sie die **Funktionen** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="a3863-141">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="a3863-142">Mit der rechten Maustaste **Private Meldungswarteschlangen**, und wählen Sie **neu**, **Private Warteschlange**.</span><span class="sxs-lookup"><span data-stu-id="a3863-142">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="a3863-143">Überprüfen Sie die **transaktional** Feld.</span><span class="sxs-lookup"><span data-stu-id="a3863-143">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="a3863-144">Geben Sie `ServiceModelSamplesTransacted` als Namen für die neue Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="a3863-144">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="a3863-145">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="a3863-145">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="a3863-146">Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a3863-146">To run the sample in a single- or cross- computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="a3863-147">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="a3863-147">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="a3863-148">Kopieren Sie die Dienstprogrammdateien aus dem Ordner \service\bin\ (unterhalb des sprachspezifischen Ordners) auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="a3863-148">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>  
  
2.  <span data-ttu-id="a3863-149">Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="a3863-149">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
3.  <span data-ttu-id="a3863-150">Ändern Sie in der Datei Client.exe.config den Wert von orderQueueName, und geben Sie anstelle von "." den Namen des Dienstcomputers an.</span><span class="sxs-lookup"><span data-stu-id="a3863-150">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>  
  
4.  <span data-ttu-id="a3863-151">Starten Sie auf dem Dienstcomputer Service.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="a3863-151">On the service computer, launch Service.exe from a command prompt.</span></span>  
  
5.  <span data-ttu-id="a3863-152">Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="a3863-152">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a3863-153">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="a3863-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a3863-154">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a3863-154">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a3863-155">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="a3863-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a3863-156">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a3863-156">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\CustomDemux`  
  
## <a name="see-also"></a><span data-ttu-id="a3863-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3863-157">See Also</span></span>  
 [<span data-ttu-id="a3863-158">Queuing in WCF</span><span class="sxs-lookup"><span data-stu-id="a3863-158">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="a3863-159">Message Queuing</span><span class="sxs-lookup"><span data-stu-id="a3863-159">Message Queuing</span></span>](http://go.microsoft.com/fwlink/?LinkId=95143)
