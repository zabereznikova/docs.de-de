---
title: Flüchtige Kommunikation unter Verwendung von Warteschlangen
ms.date: 03/30/2017
ms.assetid: 0d012f64-51c7-41d0-8e18-c756f658ee3d
ms.openlocfilehash: 8ed10262d319664d404e6beb630593cb93748a7d
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715282"
---
# <a name="volatile-queued-communication"></a><span data-ttu-id="9ae91-102">Flüchtige Kommunikation unter Verwendung von Warteschlangen</span><span class="sxs-lookup"><span data-stu-id="9ae91-102">Volatile Queued Communication</span></span>

<span data-ttu-id="9ae91-103">In diesem Beispiel wird veranschaulicht, wie eine flüchtige Kommunikation unter Verwendung von Warteschlangen über Message Queuing (MSMQ)-Transport durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9ae91-103">This sample demonstrates how to perform volatile queued communication over the Message Queuing (MSMQ) transport.</span></span> <span data-ttu-id="9ae91-104">In diesem Beispiel wird <xref:System.ServiceModel.NetMsmqBinding> verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ae91-104">This sample uses <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="9ae91-105">Der Dienst ist in diesem Fall eine selbst gehostete Konsolenanwendung, die es Ihnen ermöglicht, den Dienst beim Empfang von Nachrichten in der Warteschlange zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="9ae91-105">The service in this case is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

> [!NOTE]
> <span data-ttu-id="9ae91-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="9ae91-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="9ae91-107">In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="9ae91-107">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="9ae91-108">Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet.</span><span class="sxs-lookup"><span data-stu-id="9ae91-108">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="9ae91-109">Der Dienst empfängt Nachrichten aus der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="9ae91-109">The service receives messages from the queue.</span></span> <span data-ttu-id="9ae91-110">Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="9ae91-110">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>

<span data-ttu-id="9ae91-111">Wenn Sie eine Nachricht ohne Zusicherungen senden, sendet MSMQ nur nach dem Best-Effort-Prinzip, im Gegensatz zu Exactly Once-Zusicherungen, bei denen MSMQ sicherstellt, dass die Nachricht zugestellt wird, oder Sie benachrichtigt werden, falls sie nicht zugestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9ae91-111">When you send a message with no assurances, MSMQ only makes a best effort to deliver the message, unlike with Exactly Once assurances where MSMQ ensures that the message gets delivered or, if it cannot be delivered, lets you know that the message cannot be delivered.</span></span>

<span data-ttu-id="9ae91-112">In bestimmten Szenarios senden Sie eventuell eine flüchtige Nachricht ohne Zusicherungen über eine Warteschlange, wenn eine schnelle Zustellung wichtiger ist, als Nachrichten zu verlieren.</span><span class="sxs-lookup"><span data-stu-id="9ae91-112">In certain scenarios, you may want to send a volatile message with no assurances over a queue, when timely delivery is more important than losing messages.</span></span> <span data-ttu-id="9ae91-113">Flüchtige Nachrichten bleiben nach einem Absturz des Warteschlangen-Managers nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="9ae91-113">Volatile messages do not survive queue manager crashes.</span></span> <span data-ttu-id="9ae91-114">Wenn es daher zu einem Absturz des Warteschlangen-Managers kommt, bleibt die nicht transaktionale Warteschlange zum Speichern von flüchtigen Nachrichten erhalten, die Nachrichten selbst jedoch nicht, da sie nicht auf dem Datenträger gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9ae91-114">Therefore if the queue manager crashes, the non-transactional queue used to store volatile messages survives but the messages themselves do not because the messages are not stored on the disk.</span></span>

> [!NOTE]
> <span data-ttu-id="9ae91-115">Sie können keine flüchtigen Nachrichten ohne Zusicherungen innerhalb des Bereichs einer Transaktion mit MSMQ senden.</span><span class="sxs-lookup"><span data-stu-id="9ae91-115">You cannot send volatile messages with no assurances within the scope of a transaction using MSMQ.</span></span> <span data-ttu-id="9ae91-116">Sie müssen außerdem eine nicht transaktionale Warteschlange erstellen, um flüchtige Nachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="9ae91-116">You also must create a non-transactional queue to send volatile messages.</span></span>

<span data-ttu-id="9ae91-117">Bei dem Dienstvertrag in diesem Beispiel handelt es sich um `IStockTicker`. Hier werden unidirektionale Dienste definiert, die für die Verwendung mit Warteschlangen am besten geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="9ae91-117">The service contract in this sample is `IStockTicker` that defines one-way services that are best suited for use with queuing.</span></span>

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IStockTicker
{
    [OperationContract(IsOneWay = true)]
    void StockTick(string symbol, float price);
}
```

<span data-ttu-id="9ae91-118">Der Dienstvorgang zeigt das Aktientickersymbol und den Preis an, wie im folgenden Beispielcode dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9ae91-118">The service operation displays the stock ticker symbol and price, as shown in the following sample code:</span></span>

```csharp
public class StockTickerService : IStockTicker
{
    public void StockTick(string symbol, float price)
    {
        Console.WriteLine("Stock Tick {0}:{1} ", symbol, price);
     }
     …
}
```

<span data-ttu-id="9ae91-119">Der Dienst ist selbst gehostet.</span><span class="sxs-lookup"><span data-stu-id="9ae91-119">The service is self hosted.</span></span> <span data-ttu-id="9ae91-120">Bei Verwendung des MSMQ-Transports muss die Warteschlange im Voraus erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9ae91-120">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="9ae91-121">Dies kann manuell erfolgen oder mithilfe eines Codes.</span><span class="sxs-lookup"><span data-stu-id="9ae91-121">This can be done manually or through code.</span></span> <span data-ttu-id="9ae91-122">In diesem Beispiel enthält der Dienst Code, um zu überprüfen, ob die Warteschlange bereits vorhanden ist, und um die Warteschlange gegebenenfalls zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ae91-122">In this sample, the service contains code to check for the existence of the queue and create it if required.</span></span> <span data-ttu-id="9ae91-123">Der Warteschlangenname wird aus der Konfigurationsdatei gelesen.</span><span class="sxs-lookup"><span data-stu-id="9ae91-123">The queue name is read from the configuration file.</span></span> <span data-ttu-id="9ae91-124">Die Basisadresse wird vom [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) verwendet, um den Proxy für den Dienst zu generieren.</span><span class="sxs-lookup"><span data-stu-id="9ae91-124">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy for the service.</span></span>

```csharp
// Host the service within this EXE console application.
public static void Main()
{
    // Get MSMQ queue name from app settings in configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];

    // Create the transacted MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName);

    // Create a ServiceHost for the StockTickerService type.
    using (ServiceHost serviceHost = new ServiceHost(typeof(StockTickerService)))
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

<span data-ttu-id="9ae91-125">Der MSMQ-Warteschlangenname wird im appSettings-Abschnitt der Konfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="9ae91-125">The MSMQ queue name is specified in the appSettings section of the configuration file.</span></span> <span data-ttu-id="9ae91-126">Der Endpunkt für den Dienst wird im Abschnitt „system.serviceModel“ der Konfigurationsdatei definiert und gibt die `netMsmqBinding`-Bindung an.</span><span class="sxs-lookup"><span data-stu-id="9ae91-126">The endpoint for the service is defined in the system.serviceModel section of the configuration file and specifies the `netMsmqBinding` binding.</span></span>

> [!NOTE]
> <span data-ttu-id="9ae91-127">Im Warteschlangennamen wird ein Punkt (.) für den lokalen Computer verwendet, und in der Pfadangabe werden umgekehrte Schrägstriche als Trennzeichen verwendet, wenn eine Warteschlange mithilfe von <xref:System.Messaging> erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9ae91-127">The queue name uses a dot (.) for the local machine and backslash separators in its path when creating a queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="9ae91-128">Die Windows Communication Foundation (WCF)-Endpunkt Adresse gibt ein net. MSMQ:-Schema an und verwendet "localhost" für den lokalen Computer und Schrägstriche im Pfad.</span><span class="sxs-lookup"><span data-stu-id="9ae91-128">The Windows Communication Foundation (WCF) endpoint address specifies a net.msmq: scheme, uses "localhost" for the local machine and forward slashes in its path.</span></span>

<span data-ttu-id="9ae91-129">Die Zusicherungen und die Dauerhaftigkeit oder Flüchtigkeit von Nachrichten werden ebenfalls in der Konfiguration angegeben.</span><span class="sxs-lookup"><span data-stu-id="9ae91-129">The assurances and durability or volatility of messages are also specified in the configuration.</span></span>

```xml
<appSettings>
  <!-- use appSetting to configure MSMQ queue name -->
  <add key="queueName" value=".\private$\ServiceModelSamplesVolatile" />
</appSettings>

<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.StockTickerService"
             behaviorConfiguration="CalculatorServiceBehavior">
    ...
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesVolatile"
                binding="netMsmqBinding"
                bindingConfiguration="volatileBinding"
                contract="Microsoft.ServiceModel.Samples.IStockTicker" />
    ...
    </service>
  </services>

  <bindings>
    <netMsmqBinding>
      <binding name="volatileBinding"
             durable="false"
           exactlyOnce="false"/>
    </netMsmqBinding>
  </bindings>
  ...
</system.serviceModel>
```

<span data-ttu-id="9ae91-130">Da im Beispiel Nachrichten in der Warteschlange mithilfe einer nicht transaktionalen Warteschlange gesendet werden, können keine transaktiven Nachrichten an die Warteschlagen gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ae91-130">Because the sample sends queued messages by using a non-transactional queue, transacted messages cannot be sent to the queue.</span></span>

```csharp
// Create a client.
Random r = new Random(137);

StockTickerClient client = new StockTickerClient();

float price = 43.23F;
for (int i = 0; i < 10; i++)
{
    float increment = 0.01f * (r.Next(10));
    client.StockTick("zzz" + i, price + increment);
}

//Closing the client gracefully cleans up resources.
client.Close();
```

<span data-ttu-id="9ae91-131">Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ae91-131">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="9ae91-132">Sie können sehen, wie der Dienst Nachrichten vom Client empfängt.</span><span class="sxs-lookup"><span data-stu-id="9ae91-132">You can see the service receive messages from the client.</span></span> <span data-ttu-id="9ae91-133">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="9ae91-133">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="9ae91-134">Beachten Sie, dass aufgrund der Verwendung einer Warteschlange der Client und der Dienst nicht gleichzeitig ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9ae91-134">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="9ae91-135">Sie können den Client ausführen, ihn schließen und anschließend den Dienst starten, der dann trotzdem noch die Nachrichten des Clients empfängt.</span><span class="sxs-lookup"><span data-stu-id="9ae91-135">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Stock Tick zzz0:43.25
Stock Tick zzz1:43.23
Stock Tick zzz2:43.28
Stock Tick zzz3:43.3
Stock Tick zzz4:43.23
Stock Tick zzz5:43.25
Stock Tick zzz6:43.25
Stock Tick zzz7:43.24
Stock Tick zzz8:43.32
Stock Tick zzz9:43.3
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9ae91-136">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="9ae91-136">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="9ae91-137">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="9ae91-137">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="9ae91-138">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="9ae91-138">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="9ae91-139">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9ae91-139">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

<span data-ttu-id="9ae91-140">Standardmäßig wird mit <xref:System.ServiceModel.NetMsmqBinding> die Transportsicherheit aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9ae91-140">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="9ae91-141">Es gibt zwei relevante Eigenschaften für die MSMQ-Transportsicherheit, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> und <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` standardmäßig ist der Authentifizierungsmodus auf `Windows` festgelegt, und die Schutz Ebene ist auf `Sign`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9ae91-141">There are two pertinent properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="9ae91-142">Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es Teil einer Domäne sein, und die Active Directory-Integrationsoption für MSMQ muss installiert sein.</span><span class="sxs-lookup"><span data-stu-id="9ae91-142">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="9ae91-143">Wenn Sie dieses Beispiel auf einem Computer ausführen, der diese Kriterien nicht erfüllt, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="9ae91-143">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="9ae91-144">So führen Sie das Beispiel auf einem Computer aus, der sich in einer Arbeitsgruppe befindet oder über keine Active Directory-Integration verfügt</span><span class="sxs-lookup"><span data-stu-id="9ae91-144">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>

1. <span data-ttu-id="9ae91-145">Wenn Ihr Computer nicht zu einer Domäne gehört oder auf ihm keine Active Directory-Integration installiert ist, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf `None` festlegen, wie im folgenden Beispiel für einen Konfigurationscode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ae91-145">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration code:</span></span>

    ```xml
    <system.serviceModel>
        <services>
          <service name="Microsoft.ServiceModel.Samples.StockTickerService"
                   behaviorConfiguration="StockTickerServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>

            <!-- Define NetMsmqEndpoint -->
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesVolatile"
                      binding="netMsmqBinding"
                      bindingConfiguration="volatileBinding"
                      contract="Microsoft.ServiceModel.Samples.IStockTicker" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />

          </service>
        </services>

        <bindings>
          <netMsmqBinding>
            <binding name="volatileBinding"
                  durable="false"
                  exactlyOnce="false">
              <security mode="None" />
            </binding>
          </netMsmqBinding>
        </bindings>

        <behaviors>
          <serviceBehaviors>
            <behavior name="StockTickerServiceBehavior">
              <serviceMetadata httpGetEnabled="True"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>

      </system.serviceModel>
    ```

2. <span data-ttu-id="9ae91-146">Ändern Sie die Konfiguration sowohl auf dem Server als auch auf dem Client, bevor Sie das Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="9ae91-146">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9ae91-147">Das Festlegen von `security mode` auf `None` entspricht dem Festlegen von <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> und der `Message`-Sicherheit auf `None`.</span><span class="sxs-lookup"><span data-stu-id="9ae91-147">Setting `security mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ae91-148">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="9ae91-148">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9ae91-149">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9ae91-149">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="9ae91-150">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="9ae91-150">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9ae91-151">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ae91-151">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Volatile`
