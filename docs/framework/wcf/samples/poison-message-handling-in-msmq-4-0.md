---
title: Behandlung nicht verarbeitbarer Nachrichten in MSMQ 4,0
ms.date: 03/30/2017
ms.assetid: ec8d59e3-9937-4391-bb8c-fdaaf2cbb73e
ms.openlocfilehash: 4b662094923c85e825edcc9025a73f1a1b42cb9b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144239"
---
# <a name="poison-message-handling-in-msmq-40"></a><span data-ttu-id="504f3-102">Behandlung nicht verarbeitbarer Nachrichten in MSMQ 4,0</span><span class="sxs-lookup"><span data-stu-id="504f3-102">Poison Message Handling in MSMQ 4.0</span></span>
<span data-ttu-id="504f3-103">In diesem Beispiel wird veranschaulicht, wie die Handhabung nicht verarbeitbarer Nachrichten in einem Dienst erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="504f3-103">This sample demonstrates how to perform poison message handling in a service.</span></span> <span data-ttu-id="504f3-104">Dieses Beispiel basiert auf dem [Beispiel für die TRANSacted MSMQ-Bindung.](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)</span><span class="sxs-lookup"><span data-stu-id="504f3-104">This sample is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="504f3-105">In diesem Beispiel wird der `netMsmqBinding` verwendet.</span><span class="sxs-lookup"><span data-stu-id="504f3-105">This sample uses the `netMsmqBinding`.</span></span> <span data-ttu-id="504f3-106">Der Dienst ist eine selbst gehostete Konsolenanwendung, die es Ihnen ermöglicht, den Dienst beim Empfang von Nachrichten in der Warteschlange zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="504f3-106">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

 <span data-ttu-id="504f3-107">In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="504f3-107">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="504f3-108">Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet.</span><span class="sxs-lookup"><span data-stu-id="504f3-108">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="504f3-109">Der Dienst empfängt Nachrichten aus der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="504f3-109">The service receives messages from the queue.</span></span> <span data-ttu-id="504f3-110">Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="504f3-110">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>

 <span data-ttu-id="504f3-111">Eine nicht verarbeitbare Nachricht ist eine Nachricht, die wiederholt aus einer Warteschlange eingelesen wird, wenn der Dienst, der die Nachricht liest, diese nicht verarbeiten kann und daher die Transaktion abbricht, unter der die Nachricht gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="504f3-111">A poison message is a message that is repeatedly read from a queue when the service reading the message cannot process the message and therefore terminates the transaction under which the message is read.</span></span> <span data-ttu-id="504f3-112">In solchen Fällen wird erneut versucht, die Nachricht zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="504f3-112">In such cases, the message is retried again.</span></span> <span data-ttu-id="504f3-113">Dies kann theoretisch ewig so weitergehen, wenn ein Problem mit der Nachricht vorliegt.</span><span class="sxs-lookup"><span data-stu-id="504f3-113">This can theoretically go on forever if there is a problem with the message.</span></span> <span data-ttu-id="504f3-114">Dies kann nur auftreten, wenn Sie Transaktionen verwenden, um aus der Warteschlange zu lesen und den Dienstvorgang aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="504f3-114">This can only occur when you use transactions to read from the queue and invoke the service operation.</span></span>

 <span data-ttu-id="504f3-115">Je nach MSMQ-Version unterstützt NetMsmqBinding eingeschränkte bis vollständige Erkennung von nicht verarbeitbaren Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="504f3-115">Based on the version of MSMQ, the NetMsmqBinding supports limited detection to full detection of poison messages.</span></span> <span data-ttu-id="504f3-116">Nachdem die Nachricht als nicht verarbeitbar erkannt wurde, kann sie auf verschiedene Weisen gehandhabt werden.</span><span class="sxs-lookup"><span data-stu-id="504f3-116">After the message has been detected as poisoned, then it can be handled in several ways.</span></span> <span data-ttu-id="504f3-117">Wiederum in Abhängigkeit von der MSMQ-Version unterstützt NetMsmqBinding die eingeschränkte bis vollständige Handhabung von nicht verarbeitbaren Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="504f3-117">Again, based on the version of MSMQ, the NetMsmqBinding supports limited handling to full handling of poison messages.</span></span>

 <span data-ttu-id="504f3-118">In diesem Beispiel werden die begrenzten Giftfunktionen auf Windows Server 2003 und Windows XP-Plattformen sowie die vollständigen Giftfunktionen unter Windows Vista veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="504f3-118">This sample illustrates the limited poison facilities provided on Windows Server 2003 and Windows XP platform and the full poison facilities provided on Windows Vista.</span></span> <span data-ttu-id="504f3-119">In beiden Beispielen besteht das Ziel darin, die Giftnachricht aus der Warteschlange in eine andere Warteschlange zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="504f3-119">In both samples, the objective is to move the poison message out of the queue to another queue.</span></span> <span data-ttu-id="504f3-120">Diese Warteschlange kann dann von einem Giftnachrichtendienst bedient werden.</span><span class="sxs-lookup"><span data-stu-id="504f3-120">That queue can then be serviced by a poison message service.</span></span>

## <a name="msmq-v40-poison-handling-sample"></a><span data-ttu-id="504f3-121">MSMQ v4.0 &#8211; Beispiel für Handhabung nicht verarbeitbarer Nachrichten</span><span class="sxs-lookup"><span data-stu-id="504f3-121">MSMQ v4.0 Poison Handling Sample</span></span>
 <span data-ttu-id="504f3-122">In Windows Vista bietet MSMQ eine Gift-Subqueue-Funktion, die zum Speichern von Giftnachrichten verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="504f3-122">In Windows Vista, MSMQ provides a poison subqueue facility that can be used to store poison messages.</span></span> <span data-ttu-id="504f3-123">In diesem Beispiel wird die bewährte Methode für den Umgang mit Giftnachrichten unter Windows Vista veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="504f3-123">This sample demonstrates the best practice of dealing with poison messages using Windows Vista.</span></span>

 <span data-ttu-id="504f3-124">Die Giftnachrichtenerkennung in Windows Vista ist ausgeklügelt.</span><span class="sxs-lookup"><span data-stu-id="504f3-124">The poison message detection in Windows Vista is sophisticated.</span></span> <span data-ttu-id="504f3-125">Es gibt 3 Eigenschaften, die bei der Erkennung behilflich sind.</span><span class="sxs-lookup"><span data-stu-id="504f3-125">There are 3 properties that help with detection.</span></span> <span data-ttu-id="504f3-126"><xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> gibt an, wie oft eine bestimmte Nachricht erneut aus der Warteschlange gelesen und zur Verarbeitung an die Anwendung übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="504f3-126">The <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is number of times a given message is re-read from the queue and dispatched to the application for processing.</span></span> <span data-ttu-id="504f3-127">Eine Nachricht wird erneut aus der Warteschlange eingelesen, wenn sie wieder in die Warteschlange eingestellt wurde, weil sie nicht an die Anwendung übergeben werden konnte oder weil die Anwendung die Transaktion im Dienstvorgang zurücksetzt.</span><span class="sxs-lookup"><span data-stu-id="504f3-127">A message is re-read from the queue when it is put back into the queue because the message cannot be dispatched to the application or the application rolls back the transaction in the service operation.</span></span> <span data-ttu-id="504f3-128"><xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> gibt an, wie oft die Nachricht in die Wiederholungswarteschlange verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="504f3-128"><xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> is the number of times the message is moved to the retry queue.</span></span> <span data-ttu-id="504f3-129">Wenn <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> erreicht wird, wird die Nachricht in die Wiederholungswarteschlange verschoben.</span><span class="sxs-lookup"><span data-stu-id="504f3-129">When <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is reached, the message is moved to the retry queue.</span></span> <span data-ttu-id="504f3-130">Die Eigenschaft <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> ist die Zeitverzögerung, nach der die Nachricht aus der Wiederholungswarteschlange zurück in die Hauptwarteschlange verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="504f3-130">The property <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> is the time delay after which the message is moved from the retry queue back to the main queue.</span></span> <span data-ttu-id="504f3-131"><xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> wird auf 0 zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="504f3-131">The <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is reset to 0.</span></span> <span data-ttu-id="504f3-132">Es wird ein erneuter Versuch gestartet.</span><span class="sxs-lookup"><span data-stu-id="504f3-132">The message is tried again.</span></span> <span data-ttu-id="504f3-133">Wenn alle Versuche, die Nachricht zu lesen, fehlgeschlagen sind, wird die Nachricht als nicht verarbeitbar markiert.</span><span class="sxs-lookup"><span data-stu-id="504f3-133">If all attempts to read the message have failed, then the message is marked as poisoned.</span></span>

 <span data-ttu-id="504f3-134">Sobald eine Nachricht als nicht verarbeitbar markiert wurde, wird damit gemäß den Einstellungen in der <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A>-Enumeration verfahren.</span><span class="sxs-lookup"><span data-stu-id="504f3-134">Once the message is marked as poisoned, the message is dealt with according to the settings in the <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A> enumeration.</span></span> <span data-ttu-id="504f3-135">So können Sie die möglichen Werte erneut durchlaufen:</span><span class="sxs-lookup"><span data-stu-id="504f3-135">To reiterate the possible values:</span></span>

- <span data-ttu-id="504f3-136">"Fault" (Standard): Versetzt den Listener und auch den Diensthost in den Fehlerzustand.</span><span class="sxs-lookup"><span data-stu-id="504f3-136">Fault (default): To fault the listener and also the service host.</span></span>

- <span data-ttu-id="504f3-137">„Drop“: Verwirft die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="504f3-137">Drop: To drop the message.</span></span>

- <span data-ttu-id="504f3-138">Verschieben: Um die Nachricht in die Unterwarteschlange der Giftnachricht zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="504f3-138">Move: To move the message to the poison message subqueue.</span></span> <span data-ttu-id="504f3-139">Dieser Wert ist nur unter Windows Vista verfügbar.</span><span class="sxs-lookup"><span data-stu-id="504f3-139">This value is available only on Windows Vista.</span></span>

- <span data-ttu-id="504f3-140">"Reject": Lehnt die Nachricht ab und sendet sie zurück in die Warteschlange für unzustellbare Nachrichten des Absenders.</span><span class="sxs-lookup"><span data-stu-id="504f3-140">Reject: To reject the message, sending the message back to the sender's dead-letter queue.</span></span> <span data-ttu-id="504f3-141">Dieser Wert ist nur unter Windows Vista verfügbar.</span><span class="sxs-lookup"><span data-stu-id="504f3-141">This value is available only on Windows Vista.</span></span>

 <span data-ttu-id="504f3-142">Im Beispiel wird die Verwendung der `Move`-Disposition für die nicht verarbeitbare Nachricht veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="504f3-142">The sample demonstrates using the `Move` disposition for the poison message.</span></span> <span data-ttu-id="504f3-143">`Move`bewirkt, dass die Nachricht in die Gift-Subwarteschlange verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="504f3-143">`Move` causes the message to move to the poison subqueue.</span></span>

 <span data-ttu-id="504f3-144">Der Dienstvertrag ist `IOrderProcessor`, der einen unidirektionalen Dienst definiert, der für die Verwendung mit Warteschlangen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="504f3-144">The service contract is `IOrderProcessor`, which defines a one-way service that is suitable for use with queues.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 <span data-ttu-id="504f3-145">Der Dienstvorgang zeigt eine Nachricht an, die angibt, dass der Auftrag verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="504f3-145">The service operation displays a message stating it is processing the order.</span></span> <span data-ttu-id="504f3-146">Um die Giftnachrichtenfunktionalität `SubmitPurchaseOrder` zu demonstrieren, löst der Dienstvorgang eine Ausnahme aus, um die Transaktion bei einem zufälligen Aufruf des Dienstes zurückzuschlagen.</span><span class="sxs-lookup"><span data-stu-id="504f3-146">To demonstrate the poison message functionality, the `SubmitPurchaseOrder` service operation throws an exception to roll back the transaction on a random invocation of the service.</span></span> <span data-ttu-id="504f3-147">Dadurch wird die Nachricht in die Warteschlange zurückgestellt.</span><span class="sxs-lookup"><span data-stu-id="504f3-147">This causes the message to be put back in the queue.</span></span> <span data-ttu-id="504f3-148">Schließlich wird die Nachricht als nicht verarbeitbar markiert.</span><span class="sxs-lookup"><span data-stu-id="504f3-148">Eventually the message is marked as poison.</span></span> <span data-ttu-id="504f3-149">Die Konfiguration ist so eingestellt, dass die Giftnachricht in die Gift-Subwarteschlange verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="504f3-149">The configuration is set to move the poison message to the poison subqueue.</span></span>

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

 <span data-ttu-id="504f3-150">Die Dienstkonfiguration beinhaltet folgende Eigenschaften für nicht verarbeitbare Nachrichten: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay` und `receiveErrorHandling`, wie in der folgenden Konfigurationsdatei gezeigt.</span><span class="sxs-lookup"><span data-stu-id="504f3-150">The service configuration includes the following poison message properties: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay`, and `receiveErrorHandling` as shown in the following configuration file.</span></span>

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

## <a name="processing-messages-from-the-poison-message-queue"></a><span data-ttu-id="504f3-151">Verarbeiten von Nachrichten aus der Warteschlange für potenziell schädliche Nachrichten</span><span class="sxs-lookup"><span data-stu-id="504f3-151">Processing messages from the poison message queue</span></span>
 <span data-ttu-id="504f3-152">Der Dienst für nicht verarbeitbare Nachrichten liest Nachrichten aus der endgültigen Warteschlange für potenziell schädliche Nachrichten und verarbeitet sie.</span><span class="sxs-lookup"><span data-stu-id="504f3-152">The poison message service reads messages from the final poison message queue and processes them.</span></span>

 <span data-ttu-id="504f3-153">Nachrichten in der Warteschlange für potenziell schädliche Nachrichten sind Nachrichten, die an den Dienst adressiert sind, der die Nachricht verarbeitet; dieser kann vom Dienst-Endpunkt für nicht verarbeitbare Nachrichten abweichen.</span><span class="sxs-lookup"><span data-stu-id="504f3-153">Messages in the poison message queue are messages that are addressed to the service that is processing the message, which could be different from the poison message service endpoint.</span></span> <span data-ttu-id="504f3-154">Wenn der Giftnachrichtendienst Nachrichten aus der Warteschlange liest, findet die WCF-Kanalschicht die Nichtübereinstimmung in Endpunkten und sendet die Nachricht nicht aus.</span><span class="sxs-lookup"><span data-stu-id="504f3-154">Therefore, when the poison message service reads messages from the queue, the WCF channel layer finds the mismatch in endpoints and does not dispatch the message.</span></span> <span data-ttu-id="504f3-155">In diesem Fall ist die Nachricht an den Auftragsverarbeitungsdienst adressiert, wird jedoch vom Dienst für nicht verarbeitete Nachrichten empfangen.</span><span class="sxs-lookup"><span data-stu-id="504f3-155">In this case, the message is addressed to the order processing service but is being received by the poison message service.</span></span> <span data-ttu-id="504f3-156">Damit die Nachricht empfangen wird, selbst wenn sie an einen anderen Endpunkt adressiert ist, muss `ServiceBehavior` zum Filtern von Adressen hinzugefügt werden, wobei das Übereinstimmungskriterium darin besteht, mit jedem Dienst-Endpunkt übereinzustimmen, an den die Nachricht adressiert ist.</span><span class="sxs-lookup"><span data-stu-id="504f3-156">To continue to receive the message even if the message is addressed to a different endpoint, we must add a `ServiceBehavior` to filter addresses where the match criterion is to match any service endpoint the message is addressed to.</span></span> <span data-ttu-id="504f3-157">Dies ist erforderlich, um Nachrichten, die aus der Warteschlange für potenziell schädliche Nachrichten gelesen werden, erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="504f3-157">This is required to successfully process messages that you read from the poison message queue.</span></span>

 <span data-ttu-id="504f3-158">Die Implementierung des Diensts für nicht verarbeitbare Nachrichten selbst weist große Ähnlichkeiten mit der Dienstimplementierung auf.</span><span class="sxs-lookup"><span data-stu-id="504f3-158">The poison message service implementation itself is very similar to the service implementation.</span></span> <span data-ttu-id="504f3-159">Sie implementiert den Vertrag und verarbeitet die Aufträge.</span><span class="sxs-lookup"><span data-stu-id="504f3-159">It implements the contract and processes the orders.</span></span> <span data-ttu-id="504f3-160">Hier das Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="504f3-160">The code example is as follows.</span></span>

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

 <span data-ttu-id="504f3-161">Im Gegensatz zum Auftragsverarbeitungsdienst, der Nachrichten aus der Auftragswarteschlange liest, liest der Giftnachrichtendienst Nachrichten aus der Giftunterwarteschlange.</span><span class="sxs-lookup"><span data-stu-id="504f3-161">Unlike the order processing service that reads messages from the order queue, the poison message service reads messages from the poison subqueue.</span></span> <span data-ttu-id="504f3-162">Die Giftwarteschlange ist eine Unterwarteschlange der Hauptwarteschlange, heißt "Gift" und wird automatisch von MSMQ generiert.</span><span class="sxs-lookup"><span data-stu-id="504f3-162">The poison queue is a subqueue of the main queue, is named "poison" and is automatically generated by MSMQ.</span></span> <span data-ttu-id="504f3-163">Um darauf zuzugreifen, geben Sie den Hauptwarteschlangennamen gefolgt von einem ";" und dem Subqueue-Namen, in diesem Fall -"poison", an, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="504f3-163">To access it, provide the main queue name followed by a ";" and the subqueue name, in this case -"poison", as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="504f3-164">Im Beispiel für MSMQ v3.0 handelt es sich beim Namen der Warteschlange für potenziell schädliche Nachrichten ("poison") nicht um eine Unterwarteschlange, sondern vielmehr um die Warteschlange, in die die Nachricht verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="504f3-164">In the sample for MSMQ v3.0, the poison queue name is not a sub-queue, rather the queue that we moved the message to.</span></span>

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

 <span data-ttu-id="504f3-165">Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowie die Dienstaktivitäten für nicht verarbeitbare Nachrichten in Konsolenfenstern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="504f3-165">When you run the sample, the client, service, and poison message service activities are displayed in console windows.</span></span> <span data-ttu-id="504f3-166">Sie können sehen, wie der Dienst Nachrichten vom Client empfängt.</span><span class="sxs-lookup"><span data-stu-id="504f3-166">You can see the service receive messages from the client.</span></span> <span data-ttu-id="504f3-167">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um die Dienste herunterzufahren.</span><span class="sxs-lookup"><span data-stu-id="504f3-167">Press ENTER in each console window to shut down the services.</span></span>

 <span data-ttu-id="504f3-168">Der Dienst beginnt mit der Ausführung, verarbeitet Aufträge und beginnt zu einem nach dem Zufallsprinzip ausgewählten Zeitpunkt, die Verarbeitung abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="504f3-168">The service starts running, processing orders and at random starts to terminate processing.</span></span> <span data-ttu-id="504f3-169">Wenn die Nachricht angibt, dass der Auftrag verarbeitet wurde, können Sie den Client erneut ausführen, um eine weitere Nachricht zu senden, bis Sie feststellen, dass der Dienst die Verarbeitung einer Nachricht tatsächlich abgebrochen hat.</span><span class="sxs-lookup"><span data-stu-id="504f3-169">If the message indicates it has processed the order, you can run the client again to send another message until you see the service has actually terminated a message.</span></span> <span data-ttu-id="504f3-170">Gemäß den konfigurierten Einstellungen für nicht verarbeitbare Nachrichten wird noch einmal versucht, die Nachricht zu verarbeiten, bevor sie in die endgültige Warteschlange für potenziell schädliche Nachrichten ("poison") verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="504f3-170">Based on the configured poison settings, the message is tried once for processing before moving it to the final poison queue.</span></span>

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

 <span data-ttu-id="504f3-171">Starten Sie den Dienst für nicht verarbeitbare Nachrichten, um die nicht verarbeitbare Nachricht aus der Warteschlange für potenziell schädliche Nachrichten zu lesen.</span><span class="sxs-lookup"><span data-stu-id="504f3-171">Start up the poison message service to read the poisoned message from the poison queue.</span></span> <span data-ttu-id="504f3-172">In diesem Beispiel liest der Dienst für nicht verarbeitbare Nachrichten die Nachricht und verarbeitet sie.</span><span class="sxs-lookup"><span data-stu-id="504f3-172">In this example, the poison message service reads the message and processes it.</span></span> <span data-ttu-id="504f3-173">Sie können sehen, dass die Bestellung, die abgebrochen und als nicht verarbeitbar gekennzeichnet wurde, vom Dienst für nicht verarbeitbare Nachrichten gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="504f3-173">You could see that the purchase order that was terminated and poisoned is read by the poison message service.</span></span>

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

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="504f3-174">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="504f3-174">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="504f3-175">Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="504f3-175">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="504f3-176">Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="504f3-176">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="504f3-177">Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="504f3-177">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="504f3-178">Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen.</span><span class="sxs-lookup"><span data-stu-id="504f3-178">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="504f3-179">Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="504f3-179">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="504f3-180">Öffnen Sie den Server-Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="504f3-180">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="504f3-181">Erweitern Sie die Registerkarte **Features.**</span><span class="sxs-lookup"><span data-stu-id="504f3-181">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="504f3-182">Klicken Sie mit der rechten Maustaste auf **Private Message Queues**, und wählen Sie **Neue**, **Private Warteschlange**aus.</span><span class="sxs-lookup"><span data-stu-id="504f3-182">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="504f3-183">Aktivieren Sie das Kontrollkästchen **Transaktional.**</span><span class="sxs-lookup"><span data-stu-id="504f3-183">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="504f3-184">Geben `ServiceModelSamplesTransacted` Sie den Namen der neuen Warteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="504f3-184">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="504f3-185">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="504f3-185">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="504f3-186">Um das Beispiel in einer Einzel- oder Computerübergreifenden Konfiguration auszuführen, ändern Sie die Warteschlangennamen so, dass sie den tatsächlichen Hostnamen anstelle von localhost widerspiegeln, und befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="504f3-186">To run the sample in a single- or cross-computer configuration, change the queue names to reflect the actual hostname instead of localhost and follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

 <span data-ttu-id="504f3-187">Standardmäßig wird mit der `netMsmqBinding`-Bindung die Transportsicherheit aktiviert.</span><span class="sxs-lookup"><span data-stu-id="504f3-187">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="504f3-188">Der Typ der Transportsicherheit wird durch zwei Eigenschaften festgelegt: `MsmqAuthenticationMode` und `MsmqProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="504f3-188">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="504f3-189">Standardmäßig wird der Authentifizierungsmodus als `Windows` festgelegt, und die Schutzebene wird auf `Sign` gesetzt.</span><span class="sxs-lookup"><span data-stu-id="504f3-189">By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="504f3-190">Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es ein Teil einer Domäne sein.</span><span class="sxs-lookup"><span data-stu-id="504f3-190">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="504f3-191">Wenn Sie dieses Beispiel auf einem Computer ausführen, der nicht Teil einer Domäne ist, wird folgende Fehlermeldung ausgegeben: "Das interne Message Queuing-Zertifikat für diesen Benutzer ist nicht vorhanden".</span><span class="sxs-lookup"><span data-stu-id="504f3-191">If you run this sample on a computer that is not part of a domain, you receive the following error: "User's internal message queuing certificate does not exist".</span></span>

#### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="504f3-192">So führen Sie das Beispiel auf einem Computer aus, der zu einer Arbeitsgruppe gehört</span><span class="sxs-lookup"><span data-stu-id="504f3-192">To run the sample on a computer joined to a workgroup</span></span>

1. <span data-ttu-id="504f3-193">Wenn Ihr Computer nicht zu einer Domäne gehört, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf `None` festlegen, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="504f3-193">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding name="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

     <span data-ttu-id="504f3-194">Stellen Sie sicher, dass der Endpunkt der Bindung zugeordnet wird, indem Sie das bindingConfiguration-Attribut des Endpunkts entsprechend festlegen.</span><span class="sxs-lookup"><span data-stu-id="504f3-194">Ensure the endpoint is associated with the binding by setting the endpoint's bindingConfiguration attribute.</span></span>

2. <span data-ttu-id="504f3-195">Stellen Sie sicher, dass Sie die Konfiguration auf dem PoisonMessageServer, dem Server und dem Client ändern, bevor Sie das Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="504f3-195">Ensure that you change the configuration on the PoisonMessageServer, server, and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="504f3-196">Das Festlegen von `security mode` auf `None` entspricht dem Festlegen von `MsmqAuthenticationMode`, `MsmqProtectionLevel` und der `Message`-Sicherheit auf `None`.</span><span class="sxs-lookup"><span data-stu-id="504f3-196">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel`, and `Message` security to `None`.</span></span>  
  
3. <span data-ttu-id="504f3-197">Damit Meta Data Exchange funktionieren kann, registrieren Sie eine URL mit http-Bindung.</span><span class="sxs-lookup"><span data-stu-id="504f3-197">In order for Meta Data Exchange to work, we register a URL with http binding.</span></span> <span data-ttu-id="504f3-198">Dazu muss der Dienst in einem Befehlsfenster auf Administratorebene ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="504f3-198">This requires that the service run in an elevated command window.</span></span> <span data-ttu-id="504f3-199">Andernfalls erhalten Sie eine Ausnahme `Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8000/ServiceModelSamples/service/. Your process does not have access rights to this namespace (see https://go.microsoft.com/fwlink/?LinkId=70353 for details). ---> System.Net.HttpListenerException: Access is denied`wie: .</span><span class="sxs-lookup"><span data-stu-id="504f3-199">Otherwise, you get an exception such as: `Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8000/ServiceModelSamples/service/. Your process does not have access rights to this namespace (see https://go.microsoft.com/fwlink/?LinkId=70353 for details). ---> System.Net.HttpListenerException: Access is denied`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="504f3-200">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="504f3-200">The samples may already be installed on your computer.</span></span> <span data-ttu-id="504f3-201">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="504f3-201">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="504f3-202">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="504f3-202">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="504f3-203">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="504f3-203">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Poison\MSMQ4`
