---
title: Behandlung nicht verarbeitbarer Nachrichten in MSMQ 4,0
ms.date: 03/30/2017
ms.assetid: ec8d59e3-9937-4391-bb8c-fdaaf2cbb73e
ms.openlocfilehash: eb0801a3df0f6f384dd646598e43fe1c20b6eda0
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716523"
---
# <a name="poison-message-handling-in-msmq-40"></a><span data-ttu-id="3d851-102">Behandlung nicht verarbeitbarer Nachrichten in MSMQ 4,0</span><span class="sxs-lookup"><span data-stu-id="3d851-102">Poison Message Handling in MSMQ 4.0</span></span>
<span data-ttu-id="3d851-103">In diesem Beispiel wird veranschaulicht, wie die Handhabung nicht verarbeitbarer Nachrichten in einem Dienst erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="3d851-103">This sample demonstrates how to perform poison message handling in a service.</span></span> <span data-ttu-id="3d851-104">Dieses Beispiel basiert auf dem [transaktiven MSMQ-Bindungs](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="3d851-104">This sample is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="3d851-105">In diesem Beispiel wird der `netMsmqBinding` verwendet.</span><span class="sxs-lookup"><span data-stu-id="3d851-105">This sample uses the `netMsmqBinding`.</span></span> <span data-ttu-id="3d851-106">Der Dienst ist eine selbst gehostete Konsolenanwendung, die es Ihnen ermöglicht, den Dienst beim Empfang von Nachrichten in der Warteschlange zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="3d851-106">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

 <span data-ttu-id="3d851-107">In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="3d851-107">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="3d851-108">Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet.</span><span class="sxs-lookup"><span data-stu-id="3d851-108">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="3d851-109">Der Dienst empfängt Nachrichten aus der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="3d851-109">The service receives messages from the queue.</span></span> <span data-ttu-id="3d851-110">Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="3d851-110">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>

 <span data-ttu-id="3d851-111">Eine nicht verarbeitbare Nachricht ist eine Nachricht, die wiederholt aus einer Warteschlange eingelesen wird, wenn der Dienst, der die Nachricht liest, diese nicht verarbeiten kann und daher die Transaktion abbricht, unter der die Nachricht gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="3d851-111">A poison message is a message that is repeatedly read from a queue when the service reading the message cannot process the message and therefore terminates the transaction under which the message is read.</span></span> <span data-ttu-id="3d851-112">In solchen Fällen wird erneut versucht, die Nachricht zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3d851-112">In such cases, the message is retried again.</span></span> <span data-ttu-id="3d851-113">Dies kann theoretisch ewig so weitergehen, wenn ein Problem mit der Nachricht vorliegt.</span><span class="sxs-lookup"><span data-stu-id="3d851-113">This can theoretically go on forever if there is a problem with the message.</span></span> <span data-ttu-id="3d851-114">Beachten Sie, dass dieser Fall nur eintreten kann, wenn zum Lesen aus der Warteschlange und zum Aufrufen des Dienstvorgangs Transaktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3d851-114">Note that this can only occur when you use transactions to read from the queue and invoke the service operation.</span></span>

 <span data-ttu-id="3d851-115">Je nach MSMQ-Version unterstützt NetMsmqBinding eingeschränkte bis vollständige Erkennung von nicht verarbeitbaren Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="3d851-115">Based on the version of MSMQ, the NetMsmqBinding supports limited detection to full detection of poison messages.</span></span> <span data-ttu-id="3d851-116">Nachdem die Nachricht als nicht verarbeitbar erkannt wurde, kann sie auf verschiedene Weisen gehandhabt werden.</span><span class="sxs-lookup"><span data-stu-id="3d851-116">After the message has been detected as poisoned, then it can be handled in several ways.</span></span> <span data-ttu-id="3d851-117">Wiederum in Abhängigkeit von der MSMQ-Version unterstützt NetMsmqBinding die eingeschränkte bis vollständige Handhabung von nicht verarbeitbaren Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="3d851-117">Again, based on the version of MSMQ, the NetMsmqBinding supports limited handling to full handling of poison messages.</span></span>

 <span data-ttu-id="3d851-118">In diesem Beispiel sehen Sie die eingeschränkten Funktionen für die Handhabung nicht verarbeiteter Nachrichten auf den Plattformen [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] und die vollständigen Funktionen, die [!INCLUDE[wv](../../../../includes/wv-md.md)] bietet.</span><span class="sxs-lookup"><span data-stu-id="3d851-118">This sample illustrates the limited poison facilities provided on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../../includes/wxp-md.md)] platform and the full poison facilities provided on [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span> <span data-ttu-id="3d851-119">In beiden Beispielen besteht das Ziel darin, die nicht verarbeitbare Nachricht aus der Warteschlange in eine andere Warteschlange zu verschieben, in der dann ein Dienst für nicht verarbeitbare Nachrichten darauf angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3d851-119">In both samples, the objective is move the poison message out of the queue to another queue which then can be serviced by a poison message service.</span></span>

## <a name="msmq-v40-poison-handling-sample"></a><span data-ttu-id="3d851-120">MSMQ v4.0 &#8211; Beispiel für Handhabung nicht verarbeitbarer Nachrichten</span><span class="sxs-lookup"><span data-stu-id="3d851-120">MSMQ v4.0 Poison Handling Sample</span></span>
 <span data-ttu-id="3d851-121">In [!INCLUDE[wv](../../../../includes/wv-md.md)] stellt MSMQ eine Funktion mit einer Unterwarteschlange zur Verfügung, in der nicht verarbeitbare Nachrichten gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="3d851-121">In [!INCLUDE[wv](../../../../includes/wv-md.md)], MSMQ provides a poison sub-queue facility that can be used to store poison messages.</span></span> <span data-ttu-id="3d851-122">In diesem Beispiel wird die empfohlene Vorgehensweise für den Umgang mit nicht verarbeitbaren Nachrichten unter [!INCLUDE[wv](../../../../includes/wv-md.md)] veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3d851-122">This sample demonstrates the best practice of dealing with poison messages using [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span>

 <span data-ttu-id="3d851-123">Die Erkennung nicht verarbeitbarer Nachrichten in [!INCLUDE[wv](../../../../includes/wv-md.md)] ist ziemlich ausgereift.</span><span class="sxs-lookup"><span data-stu-id="3d851-123">The poison message detection in [!INCLUDE[wv](../../../../includes/wv-md.md)] is quite sophisticated.</span></span> <span data-ttu-id="3d851-124">Es gibt 3 Eigenschaften, die bei der Erkennung behilflich sind.</span><span class="sxs-lookup"><span data-stu-id="3d851-124">There are 3 properties that help with detection.</span></span> <span data-ttu-id="3d851-125"><xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> gibt an, wie oft eine bestimmte Nachricht erneut aus der Warteschlange gelesen und zur Verarbeitung an die Anwendung übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="3d851-125">The <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is number of times a given message is re-read from the queue and dispatched to the application for processing.</span></span> <span data-ttu-id="3d851-126">Eine Nachricht wird erneut aus der Warteschlange eingelesen, wenn sie wieder in die Warteschlange eingestellt wurde, weil sie nicht an die Anwendung übergeben werden konnte oder weil die Anwendung die Transaktion im Dienstvorgang zurücksetzt.</span><span class="sxs-lookup"><span data-stu-id="3d851-126">A message is re-read from the queue when it is put back into the queue because the message cannot be dispatched to the application or the application rolls back the transaction in the service operation.</span></span> <span data-ttu-id="3d851-127"><xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> gibt an, wie oft die Nachricht in die Wiederholungswarteschlange verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="3d851-127"><xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> is the number of times the message is moved to the retry queue.</span></span> <span data-ttu-id="3d851-128">Wenn <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> erreicht wird, wird die Nachricht in die Wiederholungswarteschlange verschoben.</span><span class="sxs-lookup"><span data-stu-id="3d851-128">When <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is reached, the message is moved to the retry queue.</span></span> <span data-ttu-id="3d851-129">Die Eigenschaft <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> ist die Zeitverzögerung, nach der die Nachricht aus der Wiederholungswarteschlange zurück in die Hauptwarteschlange verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="3d851-129">The property <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> is the time delay after which the message is moved from the retry queue back to the main queue.</span></span> <span data-ttu-id="3d851-130"><xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> wird auf 0 zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="3d851-130">The <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is reset to 0.</span></span> <span data-ttu-id="3d851-131">Es wird ein erneuter Versuch gestartet.</span><span class="sxs-lookup"><span data-stu-id="3d851-131">The message is tried again.</span></span> <span data-ttu-id="3d851-132">Wenn alle Versuche, die Nachricht zu lesen, fehlgeschlagen sind, wird die Nachricht als nicht verarbeitbar markiert.</span><span class="sxs-lookup"><span data-stu-id="3d851-132">If all attempts to read the message have failed, then the message is marked as poisoned.</span></span>

 <span data-ttu-id="3d851-133">Sobald eine Nachricht als nicht verarbeitbar markiert wurde, wird damit gemäß den Einstellungen in der <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A>-Enumeration verfahren.</span><span class="sxs-lookup"><span data-stu-id="3d851-133">Once the message is marked as poisoned, the message is dealt with according to the settings in the <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A> enumeration.</span></span> <span data-ttu-id="3d851-134">So können Sie die möglichen Werte erneut durchlaufen:</span><span class="sxs-lookup"><span data-stu-id="3d851-134">To reiterate the possible values:</span></span>

- <span data-ttu-id="3d851-135">"Fault" (Standard): Versetzt den Listener und auch den Diensthost in den Fehlerzustand.</span><span class="sxs-lookup"><span data-stu-id="3d851-135">Fault (default): To fault the listener and also the service host.</span></span>

- <span data-ttu-id="3d851-136">„Drop“: Verwirft die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="3d851-136">Drop: To drop the message.</span></span>

- <span data-ttu-id="3d851-137">"Move": Verschiebt die Nachricht in die Unterwarteschlange für potenziell schädliche Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="3d851-137">Move: To move the message to the poison message sub-queue.</span></span> <span data-ttu-id="3d851-138">Dieser Wert ist nur unter [!INCLUDE[wv](../../../../includes/wv-md.md)] verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3d851-138">This value is available only on [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span>

- <span data-ttu-id="3d851-139">"Reject": Lehnt die Nachricht ab und sendet sie zurück in die Warteschlange für unzustellbare Nachrichten des Absenders.</span><span class="sxs-lookup"><span data-stu-id="3d851-139">Reject: To reject the message, sending the message back to the sender's dead-letter queue.</span></span> <span data-ttu-id="3d851-140">Dieser Wert ist nur unter [!INCLUDE[wv](../../../../includes/wv-md.md)] verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3d851-140">This value is available only on [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span>

 <span data-ttu-id="3d851-141">Im Beispiel wird die Verwendung der `Move`-Disposition für die nicht verarbeitbare Nachricht veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3d851-141">The sample demonstrates using the `Move` disposition for the poison message.</span></span> <span data-ttu-id="3d851-142">`Move` führt dazu, dass die Nachricht in die Unterwarteschlange für potenziell schädliche Nachrichten verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="3d851-142">`Move` causes the message to move to the poison sub-queue.</span></span>

 <span data-ttu-id="3d851-143">Der Dienstvertrag ist `IOrderProcessor`, der einen unidirektionalen Dienst definiert, der für die Verwendung mit Warteschlangen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="3d851-143">The service contract is `IOrderProcessor`, which defines a one-way service that is suitable for use with queues.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 <span data-ttu-id="3d851-144">Der Dienstvorgang zeigt eine Nachricht an, die angibt, dass der Auftrag verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="3d851-144">The service operation displays a message stating it is processing the order.</span></span> <span data-ttu-id="3d851-145">Zur Demonstration der Funktion für nicht verarbeitbare Nachrichten löst der Dienst `SubmitPurchaseOrder` eine Ausnahme auf, um die Transaktion bei einem zufälligen Aufruf des Diensts zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="3d851-145">To demonstrate the poison message functionality, the `SubmitPurchaseOrder` service operation throws an exception to rollback the transaction on a random invocation of the service.</span></span> <span data-ttu-id="3d851-146">Dadurch wird die Nachricht in die Warteschlange zurückgestellt.</span><span class="sxs-lookup"><span data-stu-id="3d851-146">This causes the message to be put back in the queue.</span></span> <span data-ttu-id="3d851-147">Schließlich wird die Nachricht als nicht verarbeitbar markiert.</span><span class="sxs-lookup"><span data-stu-id="3d851-147">Eventually the message is marked as poison.</span></span> <span data-ttu-id="3d851-148">Die Konfiguration wird so festgelegt, dass die nicht verarbeitbare Nachricht in die Unterwarteschlange für potenziell schädliche Nachrichten verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="3d851-148">The configuration is set to move the poison message to the poison sub-queue.</span></span>

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
public class OrderProcessorService : IOrderProcessor
{
    static Random r = new Random(137);

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {

        int randomNumber = r.Next(10);

        if (randomNumber % 2 == 0)
        {
            Orders.Add(po);
            Console.WriteLine("Processing {0} ", po);
        }
        else
        {
            Console.WriteLine("Aborting transaction, cannot process purchase order: " + po.PONumber);
            Console.WriteLine();
            throw new Exception("Cannot process purchase order: " + po.PONumber);
        }
    }

    public static void OnServiceFaulted(object sender, EventArgs e)
    {
        Console.WriteLine("Service Faulted");
    }

    // Host the service within this EXE console application.
    public static void Main()
    {
        // Get MSMQ queue name from app settings in configuration.
        string queueName = ConfigurationManager.AppSettings["queueName"];

        // Create the transacted MSMQ queue if necessary.
        if (!System.Messaging.MessageQueue.Exists(queueName))
            System.Messaging.MessageQueue.Create(queueName, true);

        // Get the base address that is used to listen for WS-MetaDataExchange requests.
        // This is useful to generate a proxy for the client.
        string baseAddress = ConfigurationManager.AppSettings["baseAddress"];

        // Create a ServiceHost for the OrderProcessorService type.
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService), new Uri(baseAddress));

        // Hook on to the service host faulted events.
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);

        // Open the ServiceHostBase to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        if(serviceHost.State != CommunicationState.Faulted) {
            serviceHost.Close();
        }

    }
}
```

 <span data-ttu-id="3d851-149">Die Dienstkonfiguration beinhaltet folgende Eigenschaften für nicht verarbeitbare Nachrichten: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay` und `receiveErrorHandling`, wie in der folgenden Konfigurationsdatei gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d851-149">The service configuration includes the following poison message properties: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay`, and `receiveErrorHandling` as shown in the following configuration file.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
    <!-- Use appSetting to configure MSMQ queue name. -->
    <add key="queueName" value=".\private$\ServiceModelSamplesPoison" />
    <add key="baseAddress" value="http://localhost:8000/orderProcessor/poisonSample"/>
  </appSettings>
  <system.serviceModel>
    <services>
      <service
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison"
                  binding="netMsmqBinding"
                  bindingConfiguration="PoisonBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
      </service>
    </services>

    <bindings>
      <netMsmqBinding>
        <binding name="PoisonBinding"
                 receiveRetryCount="0"
                 maxRetryCycles="1"
                 retryCycleDelay="00:00:05"
                 receiveErrorHandling="Move">
        </binding>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

## <a name="processing-messages-from-the-poison-message-queue"></a><span data-ttu-id="3d851-150">Verarbeiten von Nachrichten aus der Warteschlange für potenziell schädliche Nachrichten</span><span class="sxs-lookup"><span data-stu-id="3d851-150">Processing messages from the poison message queue</span></span>
 <span data-ttu-id="3d851-151">Der Dienst für nicht verarbeitbare Nachrichten liest Nachrichten aus der endgültigen Warteschlange für potenziell schädliche Nachrichten und verarbeitet sie.</span><span class="sxs-lookup"><span data-stu-id="3d851-151">The poison message service reads messages from the final poison message queue and processes them.</span></span>

 <span data-ttu-id="3d851-152">Nachrichten in der Warteschlange für potenziell schädliche Nachrichten sind Nachrichten, die an den Dienst adressiert sind, der die Nachricht verarbeitet; dieser kann vom Dienst-Endpunkt für nicht verarbeitbare Nachrichten abweichen.</span><span class="sxs-lookup"><span data-stu-id="3d851-152">Messages in the poison message queue are messages that are addressed to the service that is processing the message, which could be different from the poison message service endpoint.</span></span> <span data-ttu-id="3d851-153">Wenn der Dienst für nicht verarbeitbare Nachrichten Nachrichten aus der Warteschlange liest, findet die WCF-Kanal Schicht daher die nicht Übereinstimmung in Endpunkten und versendet die Nachricht nicht.</span><span class="sxs-lookup"><span data-stu-id="3d851-153">Therefore, when the poison message service reads messages from the queue, the WCF channel layer finds the mismatch in endpoints and does not dispatch the message.</span></span> <span data-ttu-id="3d851-154">In diesem Fall ist die Nachricht an den Auftragsverarbeitungsdienst adressiert, wird jedoch vom Dienst für nicht verarbeitete Nachrichten empfangen.</span><span class="sxs-lookup"><span data-stu-id="3d851-154">In this case, the message is addressed to the order processing service but is being received by the poison message service.</span></span> <span data-ttu-id="3d851-155">Damit die Nachricht empfangen wird, selbst wenn sie an einen anderen Endpunkt adressiert ist, muss `ServiceBehavior` zum Filtern von Adressen hinzugefügt werden, wobei das Übereinstimmungskriterium darin besteht, mit jedem Dienst-Endpunkt übereinzustimmen, an den die Nachricht adressiert ist.</span><span class="sxs-lookup"><span data-stu-id="3d851-155">To continue to receive the message even if the message is addressed to a different endpoint, we must add a `ServiceBehavior` to filter addresses where the match criterion is to match any service endpoint the message is addressed to.</span></span> <span data-ttu-id="3d851-156">Dies ist erforderlich, um Nachrichten, die aus der Warteschlange für potenziell schädliche Nachrichten gelesen werden, erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3d851-156">This is required to successfully process messages that you read from the poison message queue.</span></span>

 <span data-ttu-id="3d851-157">Die Implementierung des Diensts für nicht verarbeitbare Nachrichten selbst weist große Ähnlichkeiten mit der Dienstimplementierung auf.</span><span class="sxs-lookup"><span data-stu-id="3d851-157">The poison message service implementation itself is very similar to the service implementation.</span></span> <span data-ttu-id="3d851-158">Sie implementiert den Vertrag und verarbeitet die Aufträge.</span><span class="sxs-lookup"><span data-stu-id="3d851-158">It implements the contract and processes the orders.</span></span> <span data-ttu-id="3d851-159">Hier das Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="3d851-159">The code example is as follows.</span></span>

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
[ServiceBehavior(AddressFilterMode=AddressFilterMode.Any)]
public class OrderProcessorService : IOrderProcessor
{
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
    }

    public static void OnServiceFaulted(object sender, EventArgs e)
    {
        Console.WriteLine("Service Faulted...exiting app");
        Environment.Exit(1);
    }

    // Host the service within this EXE console application.
    public static void Main()
    {

        // Create a ServiceHost for the OrderProcessorService type.
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService));

        // Hook on to the service host faulted events.
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);

        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The poison message service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        // Close the ServiceHostBase to shutdown the service.
        if(serviceHost.State != CommunicationState.Faulted)
        {
            serviceHost.Close();
        }
    }
```

 <span data-ttu-id="3d851-160">Im Gegensatz zum Auftragsverarbeitungsdienst, der Nachrichten aus der Auftragswarteschlange liest, liest der Dienst für nicht verarbeitbare Nachrichten Nachrichten aus der Unterwarteschlange für potenziell schädliche Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="3d851-160">Unlike the order processing service that reads messages from the order queue, the poison message service reads messages from the poison sub-queue.</span></span> <span data-ttu-id="3d851-161">Die Warteschlange für potenziell schädliche Nachrichten ist eine Unterwarteschlange der Hauptwarteschlange, trägt den Namen "poison" und wird automatisch von MSMQ generiert.</span><span class="sxs-lookup"><span data-stu-id="3d851-161">The poison queue is a sub-queue of the main queue, is named "poison" and is automatically generated by MSMQ.</span></span> <span data-ttu-id="3d851-162">Um darauf zuzugreifen, geben Sie den Namen der Hauptwarteschlange, gefolgt von ";" und dem Namen der Unterwarteschlange (in diesem Fall -"poison") an, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d851-162">To access it, provide the main queue name followed by a ";" and the sub-queue name, in this case -"poison", as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="3d851-163">Im Beispiel für MSMQ v3.0 handelt es sich beim Namen der Warteschlange für potenziell schädliche Nachrichten ("poison") nicht um eine Unterwarteschlange, sondern vielmehr um die Warteschlange, in die die Nachricht verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="3d851-163">In the sample for MSMQ v3.0, the poison queue name is not a sub-queue, rather the queue that we moved the message to.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.OrderProcessorService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison;poison"
                  binding="netMsmqBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" >
        </endpoint>
      </service>
    </services>

  </system.serviceModel>
</configuration>
```

 <span data-ttu-id="3d851-164">Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowie die Dienstaktivitäten für nicht verarbeitbare Nachrichten in Konsolenfenstern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d851-164">When you run the sample, the client, service, and poison message service activities are displayed in console windows.</span></span> <span data-ttu-id="3d851-165">Sie können sehen, wie der Dienst Nachrichten vom Client empfängt.</span><span class="sxs-lookup"><span data-stu-id="3d851-165">You can see the service receive messages from the client.</span></span> <span data-ttu-id="3d851-166">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um die Dienste herunterzufahren.</span><span class="sxs-lookup"><span data-stu-id="3d851-166">Press ENTER in each console window to shut down the services.</span></span>

 <span data-ttu-id="3d851-167">Der Dienst beginnt mit der Ausführung, verarbeitet Aufträge und beginnt zu einem nach dem Zufallsprinzip ausgewählten Zeitpunkt, die Verarbeitung abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="3d851-167">The service starts running, processing orders and at random starts to terminate processing.</span></span> <span data-ttu-id="3d851-168">Wenn die Nachricht angibt, dass der Auftrag verarbeitet wurde, können Sie den Client erneut ausführen, um eine weitere Nachricht zu senden, bis Sie feststellen, dass der Dienst die Verarbeitung einer Nachricht tatsächlich abgebrochen hat.</span><span class="sxs-lookup"><span data-stu-id="3d851-168">If the message indicates it has processed the order, you can run the client again to send another message until you see the service has actually terminated a message.</span></span> <span data-ttu-id="3d851-169">Gemäß den konfigurierten Einstellungen für nicht verarbeitbare Nachrichten wird noch einmal versucht, die Nachricht zu verarbeiten, bevor sie in die endgültige Warteschlange für potenziell schädliche Nachrichten ("poison") verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="3d851-169">Based on the configured poison settings, the message is tried once for processing before moving it to the final poison queue.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 0f063b71-93e0-42a1-aa3b-bca6c7a89546
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending

Processing Purchase Order: 5ef9a4fa-5a30-4175-b455-2fb1396095fa
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending

Aborting transaction, cannot process purchase order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89
```

 <span data-ttu-id="3d851-170">Starten Sie den Dienst für nicht verarbeitbare Nachrichten, um die nicht verarbeitbare Nachricht aus der Warteschlange für potenziell schädliche Nachrichten zu lesen.</span><span class="sxs-lookup"><span data-stu-id="3d851-170">Start up the poison message service to read the poisoned message from the poison queue.</span></span> <span data-ttu-id="3d851-171">In diesem Beispiel liest der Dienst für nicht verarbeitbare Nachrichten die Nachricht und verarbeitet sie.</span><span class="sxs-lookup"><span data-stu-id="3d851-171">In this example, the poison message service reads the message and processes it.</span></span> <span data-ttu-id="3d851-172">Sie können sehen, dass die Bestellung, die abgebrochen und als nicht verarbeitbar gekennzeichnet wurde, vom Dienst für nicht verarbeitbare Nachrichten gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="3d851-172">You could see that the purchase order that was terminated and poisoned is read by the poison message service.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3d851-173">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="3d851-173">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="3d851-174">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="3d851-174">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="3d851-175">Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3d851-175">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="3d851-176">Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="3d851-176">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="3d851-177">Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen.</span><span class="sxs-lookup"><span data-stu-id="3d851-177">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="3d851-178">Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3d851-178">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="3d851-179">Öffnen Sie Server-Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="3d851-179">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="3d851-180">Erweitern Sie die Registerkarte **Features** .</span><span class="sxs-lookup"><span data-stu-id="3d851-180">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="3d851-181">Klicken Sie mit der rechten Maustaste auf private Meldungs **Warteschlangen**, und wählen Sie **neu**, **private**</span><span class="sxs-lookup"><span data-stu-id="3d851-181">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="3d851-182">Aktivieren Sie das Kontrollkästchen **transaktional** .</span><span class="sxs-lookup"><span data-stu-id="3d851-182">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="3d851-183">Geben Sie `ServiceModelSamplesTransacted` als Namen für die neue Warteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="3d851-183">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="3d851-184">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="3d851-184">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="3d851-185">Wenn Sie das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend ausführen möchten, ändern Sie die Warteschlangen Namen so, dass Sie den tatsächlichen Hostnamen anstelle von "localhost" widerspiegeln, und befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3d851-185">To run the sample in a single- or cross-computer configuration, change the queue names to reflect the actual hostname instead of localhost and follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

 <span data-ttu-id="3d851-186">Standardmäßig wird mit der `netMsmqBinding`-Bindung die Transportsicherheit aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3d851-186">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="3d851-187">Der Typ der Transportsicherheit wird durch zwei Eigenschaften festgelegt: `MsmqAuthenticationMode` und `MsmqProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="3d851-187">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="3d851-188">Standardmäßig wird der Authentifizierungsmodus als `Windows` festgelegt, und die Schutzebene wird auf `Sign` gesetzt.</span><span class="sxs-lookup"><span data-stu-id="3d851-188">By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="3d851-189">Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es ein Teil einer Domäne sein.</span><span class="sxs-lookup"><span data-stu-id="3d851-189">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="3d851-190">Wenn Sie dieses Beispiel auf einem Computer ausführen, der nicht Teil einer Domäne ist, wird folgende Fehlermeldung ausgegeben: "Das interne Message Queuing-Zertifikat für diesen Benutzer ist nicht vorhanden".</span><span class="sxs-lookup"><span data-stu-id="3d851-190">If you run this sample on a computer that is not part of a domain, you receive the following error: "User's internal message queuing certificate does not exist".</span></span>

#### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="3d851-191">So führen Sie das Beispiel auf einem Computer aus, der zu einer Arbeitsgruppe gehört</span><span class="sxs-lookup"><span data-stu-id="3d851-191">To run the sample on a computer joined to a workgroup</span></span>

1. <span data-ttu-id="3d851-192">Wenn Ihr Computer nicht zu einer Domäne gehört, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf `None` festlegen, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d851-192">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding name="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

     <span data-ttu-id="3d851-193">Stellen Sie sicher, dass der Endpunkt der Bindung zugeordnet wird, indem Sie das bindingConfiguration-Attribut des Endpunkts entsprechend festlegen.</span><span class="sxs-lookup"><span data-stu-id="3d851-193">Ensure the endpoint is associated with the binding by setting the endpoint's bindingConfiguration attribute.</span></span>

2. <span data-ttu-id="3d851-194">Ändern Sie die Konfiguration auf dem PoisonMessageServer, dem Server und dem Client, bevor Sie das Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="3d851-194">Ensure that you change the configuration on the PoisonMessageServer, server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3d851-195">Das Festlegen von `security mode` auf `None` entspricht dem Festlegen von `MsmqAuthenticationMode`, `MsmqProtectionLevel` und der `Message`-Sicherheit auf `None`.</span><span class="sxs-lookup"><span data-stu-id="3d851-195">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel`, and `Message` security to `None`.</span></span>  
  
3. <span data-ttu-id="3d851-196">Damit Meta Data Exchange funktionieren kann, registrieren Sie eine URL mit http-Bindung.</span><span class="sxs-lookup"><span data-stu-id="3d851-196">In order for Meta Data Exchange to work, we register a URL with http binding.</span></span> <span data-ttu-id="3d851-197">Dazu muss der Dienst in einem Befehlsfenster auf Administratorebene ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3d851-197">This requires that the service run in an elevated command window.</span></span> <span data-ttu-id="3d851-198">Andernfalls erhalten Sie eine Ausnahme, z. b.: `Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8000/ServiceModelSamples/service/. Your process does not have access rights to this namespace (see https://go.microsoft.com/fwlink/?LinkId=70353 for details). ---> System.Net.HttpListenerException: Access is denied`.</span><span class="sxs-lookup"><span data-stu-id="3d851-198">Otherwise, you get an exception such as: `Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8000/ServiceModelSamples/service/. Your process does not have access rights to this namespace (see https://go.microsoft.com/fwlink/?LinkId=70353 for details). ---> System.Net.HttpListenerException: Access is denied`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3d851-199">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="3d851-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3d851-200">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3d851-200">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="3d851-201">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="3d851-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3d851-202">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="3d851-202">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Poison\MSMQ4`
