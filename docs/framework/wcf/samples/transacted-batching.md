---
title: 'Transaktive Batchverarbeitung:'
ms.date: 03/30/2017
ms.assetid: ecd328ed-332e-479c-a894-489609bcddd2
ms.openlocfilehash: 7df65b8f3f149deac841010e392f3919b24506b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33508877"
---
# <a name="transacted-batching"></a><span data-ttu-id="8754e-102">Transaktive Batchverarbeitung:</span><span class="sxs-lookup"><span data-stu-id="8754e-102">Transacted Batching</span></span>
<span data-ttu-id="8754e-103">In diesem Beispiel wird die Batchverarbeitung durchgeführter Lesevorgänge mithilfe von Message Queuing (MSMQ) veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8754e-103">This sample demonstrates how to batch transacted reads by using Message Queuing (MSMQ).</span></span> <span data-ttu-id="8754e-104">Transaktive Batchverarbeitung ist eine Leistungsoptimierungsfunktion für durchgeführte Lesevorgänge in Kommunikation unter Verwendung von Warteschlangen.</span><span class="sxs-lookup"><span data-stu-id="8754e-104">Transacted Batching is a performance optimization feature for transacted reads in queued communication.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8754e-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="8754e-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8754e-106">In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="8754e-106">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="8754e-107">Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet.</span><span class="sxs-lookup"><span data-stu-id="8754e-107">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="8754e-108">Der Dienst empfängt Nachrichten aus der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="8754e-108">The service receives messages from the queue.</span></span> <span data-ttu-id="8754e-109">Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="8754e-109">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="8754e-110">Dieses Beispiel veranschaulicht transaktive Batchverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="8754e-110">This sample demonstrates transacted batching.</span></span> <span data-ttu-id="8754e-111">Die transaktive Batchverarbeitung ist ein Verhalten, das beim Lesen und Verarbeiten einer großen Anzahl an Nachrichten in der Warteschlange die Verwendung einer einzelnen Transaktion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8754e-111">Transacted batching is a behavior that enables the use of a single transaction when reading many messages in the queue and processing them.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8754e-112">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="8754e-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8754e-113">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8754e-113">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8754e-114">Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8754e-114">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="8754e-115">Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="8754e-115">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="8754e-116">Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen.</span><span class="sxs-lookup"><span data-stu-id="8754e-116">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="8754e-117">Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8754e-117">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="8754e-118">Öffnen Sie Server-Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8754e-118">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="8754e-119">Erweitern Sie die **Funktionen** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="8754e-119">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="8754e-120">Mit der rechten Maustaste **Private Meldungswarteschlangen**, und wählen Sie **neu**, **Private Warteschlange**.</span><span class="sxs-lookup"><span data-stu-id="8754e-120">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="8754e-121">Überprüfen Sie die **transaktional** Feld.</span><span class="sxs-lookup"><span data-stu-id="8754e-121">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="8754e-122">Geben Sie `ServiceModelSamplesTransacted` als Namen für die neue Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="8754e-122">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8754e-123">In diesem Beispiel sendet der Client Hunderte von Nachrichten als Teil des Batches.</span><span class="sxs-lookup"><span data-stu-id="8754e-123">In this sample the client sends hundreds of messages as part of the batch.</span></span> <span data-ttu-id="8754e-124">Es ist normal, dass die Verarbeitung durch die Dienstanwendung eine gewisse Zeit dauert.</span><span class="sxs-lookup"><span data-stu-id="8754e-124">It is normal for the service application to take some time to process these.</span></span>  
  
3.  <span data-ttu-id="8754e-125">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="8754e-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="8754e-126">Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8754e-126">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="8754e-127">So führen Sie das Beispiel auf einem Computer aus, der sich in einer Arbeitsgruppe befindet oder über keine Active Directory-Integration verfügt</span><span class="sxs-lookup"><span data-stu-id="8754e-127">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1.  <span data-ttu-id="8754e-128">Standardmäßig wird mit <xref:System.ServiceModel.NetMsmqBinding> die Transportsicherheit aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8754e-128">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="8754e-129">Es gibt zwei relevante Eigenschaften für MSMQ-transportsicherheit <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> und <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` standardmäßig der Authentifizierungsmodus festgelegt ist, um `Windows` und die Schutzebene festgelegt ist, um `Sign`.</span><span class="sxs-lookup"><span data-stu-id="8754e-129">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="8754e-130">Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es Teil einer Domäne sein, und die Active Directory-Integrationsoption für MSMQ muss installiert sein.</span><span class="sxs-lookup"><span data-stu-id="8754e-130">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="8754e-131">Wenn Sie dieses Beispiel auf einem Computer ausführen, der diese Kriterien nicht erfüllt, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="8754e-131">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
2.  <span data-ttu-id="8754e-132">Wenn Ihr Computer nicht zu einer Domäne gehört oder auf ihm keine Active Directory-Integration installiert ist, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf `None` setzen, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8754e-132">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <behaviors>  
        <serviceBehaviors>  
          <behavior name="ThrottlingBehavior">  
            <serviceMetadata httpGetEnabled="true"/>  
            <serviceThrottling maxConcurrentCalls="5"/>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="BatchingBehavior">  
            <transactedBatching maxBatchSize="100"/>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <services>  
        <service   
            behaviorConfiguration="ThrottlingBehavior"   
            name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
          <host>  
            <baseAddresses>  
              <add baseAddress="http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                    binding="netMsmqBinding"  
                    bindingConfiguration="Binding1"   
                    behaviorConfiguration="BatchingBehavior"   
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
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
  
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="8754e-133">Ändern Sie die Konfiguration sowohl auf dem Server als auch auf dem Client, bevor Sie das Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="8754e-133">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8754e-134">Das Festlegen von `security``mode` auf `None` entspricht dem Festlegen von <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> und der `Message`-Sicherheit auf `None`.</span><span class="sxs-lookup"><span data-stu-id="8754e-134">Setting `security``mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>  
  
4.  <span data-ttu-id="8754e-135">Um die Datenbank auf einem Remotecomputer auszuführen, ändern Sie die Verbindungszeichenfolge so, dass sie auf den Computer verweist, auf dem sich die Datenbank befindet.</span><span class="sxs-lookup"><span data-stu-id="8754e-135">To run the database on a remote computer, change the connection string to point to the computer on which the database resides.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8754e-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8754e-136">Requirements</span></span>  
 <span data-ttu-id="8754e-137">Um dieses Beispiel auszuführen, muss MSMQ installiert sein, und SQL oder SQL Express ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8754e-137">To run this sample, MSMQ must be installed and SQL or SQL Express is required.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="8754e-138">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="8754e-138">Demonstrates</span></span>  
 <span data-ttu-id="8754e-139">Das Beispiel veranschaulicht transaktives Batchverarbeitungsverhalten.</span><span class="sxs-lookup"><span data-stu-id="8754e-139">The sample demonstrates transacted batching behavior.</span></span> <span data-ttu-id="8754e-140">Transaktive Batchverarbeitung ist eine Leistungsoptimierungsfunktion, die zusammen mit MSMQ-Wartenschlangentransport bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8754e-140">Transacted batching is a performance optimization feature provided with MSMQ queued transport.</span></span>  
  
 <span data-ttu-id="8754e-141">Wenn Transaktionen verwendet werden, um Nachrichten zu senden und zu empfangen, gibt es genau genommen 2 separate Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="8754e-141">When transactions are used to send and receive messages there are actually 2 separate transactions.</span></span> <span data-ttu-id="8754e-142">Wenn der Client innerhalb des Geltungsbereichs einer Transaktion Nachrichten sendet, gilt die Transaktion lokal für den Client und den Warteschlangen-Manager des Clients.</span><span class="sxs-lookup"><span data-stu-id="8754e-142">When the client sends messages within the scope of a transaction, the transaction is local to the client and the client queue manager.</span></span> <span data-ttu-id="8754e-143">Wenn der Dienst innerhalb des Geltungsbereichs der Transaktion Nachrichten empfängt, gilt die Transaktion lokal für den Dienst und den empfangenden Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="8754e-143">When the service receives messages within the scope of the transaction, the transaction is local to the service and the receiving queue manager.</span></span> <span data-ttu-id="8754e-144">Es ist wichtig, daran zu denken, dass der Client und der Dienst nicht an derselben Transaktion beteiligt sind, sondern zur Durchführung ihrer Vorgänge (wie Senden und Empfangen) über die Warteschlange verschiedene Transaktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8754e-144">It is very important to remember that the client and the service are not participating in the same transaction; rather they are using different transactions when performing their operations (such as send and receive) with the queue.</span></span>  
  
 <span data-ttu-id="8754e-145">Im Beispiel wird eine einzelne Transaktion zur Ausführung mehrerer Dienstvorgänge verwendet.</span><span class="sxs-lookup"><span data-stu-id="8754e-145">In the sample we use a single transaction for the execution of multiple service operations.</span></span> <span data-ttu-id="8754e-146">Diese dient lediglich als Leistungsoptimierungsfunktion und hat keine Auswirkungen auf die Semantik der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8754e-146">This is used only as a performance optimization feature and does not impact the semantics of the application.</span></span> <span data-ttu-id="8754e-147">Das Beispiel basiert auf [Binden von MSMQ transaktive](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span><span class="sxs-lookup"><span data-stu-id="8754e-147">The sample is based on [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="8754e-148">Kommentare</span><span class="sxs-lookup"><span data-stu-id="8754e-148">Comments</span></span>  
 <span data-ttu-id="8754e-149">In diesem Beispiel sendet der Client einen Nachrichtenbatch aus dem Geltungsbereich einer Transaktion an den Dienst.</span><span class="sxs-lookup"><span data-stu-id="8754e-149">In this sample, the client sends a batch of messages to the service from within the scope of a transaction.</span></span> <span data-ttu-id="8754e-150">Um die Leistungsoptimierung zu zeigen, wird eine große Anzahl von Nachrichten gesendet; in diesem Fall bis zu 2.500 Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="8754e-150">To show the performance optimization, we send a large number of messages; in this case, up to 2500 messages.</span></span>  
  
 <span data-ttu-id="8754e-151">Die an die Warteschlange gesendeten Nachrichten werden dann vom Dienst innerhalb des vom Dienst definierten Geltungsbereichs der Transaktion empfangen.</span><span class="sxs-lookup"><span data-stu-id="8754e-151">The messages sent to the queue are then received by the service within the transaction scope defined by the service.</span></span> <span data-ttu-id="8754e-152">Ohne Batchverarbeitung führt dies zu 2.500 Transaktionen für jeden Aufruf des Dienstvorgangs.</span><span class="sxs-lookup"><span data-stu-id="8754e-152">Without batching, this results in 2500 transactions for each invocation of the service operation.</span></span> <span data-ttu-id="8754e-153">Dadurch wird die Leistung des Systems beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="8754e-153">This impacts performance of the system.</span></span> <span data-ttu-id="8754e-154">Da zwei Ressourcen-Manager beteiligt sind – die MSMQ-Warteschlange und die `Orders`-Datenbank – ist jede dieser Transaktionen eine DTC-Transaktion.</span><span class="sxs-lookup"><span data-stu-id="8754e-154">Because two resource managers are involved -the MSMQ queue and the `Orders` database- each such transaction is a DTC transaction.</span></span> <span data-ttu-id="8754e-155">Dieser Vorgang wurde wie folgt optimiert: Es wird eine wesentlich kleinere Anzahl an Transaktionen verwendet, indem sichergestellt wird, dass ein Batch an Nachrichten und Dienstvorgangsaufrufen in einer einzelnen Transaktion erfolgt.</span><span class="sxs-lookup"><span data-stu-id="8754e-155">We optimize this by using a much smaller number of transactions by ensuring that a batch of messages and service operation invocations happen in a single transaction.</span></span>  
  
 <span data-ttu-id="8754e-156">Die Batchverarbeitungsfunktion wird wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="8754e-156">We use the batching feature by:</span></span>  
  
-   <span data-ttu-id="8754e-157">Durch die Angabe von transaktivem Batchverarbeitungsverhalten in der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="8754e-157">Specifying transacted batching behavior in configuration.</span></span>  
  
-   <span data-ttu-id="8754e-158">Durch die Angabe einer Batchgröße hinsichtlich der Anzahl der Nachrichten, die in einer einzelnen Transaktion gelesen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8754e-158">Specifying a batch size in terms of number of messages to be read using a single transaction.</span></span>  
  
-   <span data-ttu-id="8754e-159">Durch die Angabe der maximalen Anzahl gleichzeitig auszuführender Batches.</span><span class="sxs-lookup"><span data-stu-id="8754e-159">Specifying the maximum number of concurrent batches to run.</span></span>  
  
 <span data-ttu-id="8754e-160">In diesem Beispiel werden Leistungssteigerungen durch die Verringerung von Transaktionen gezeigt, die dadurch erreicht werden kann, dass erst 100 Dienstvorgänge in einer einzelnen Transaktion aufgerufen werden, bevor der Commit für die Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8754e-160">In this example, we show performance gains by reducing the number of transactions by ensuring that 100 service operations are invoked in a single transaction before committing the transaction.</span></span>  
  
 <span data-ttu-id="8754e-161">Das Dienstverhalten definiert ein Vorgangsverhalten, wobei `TransactionScopeRequired` auf `true` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="8754e-161">The service behavior defines an operation behavior with `TransactionScopeRequired` set to `true`.</span></span> <span data-ttu-id="8754e-162">Auf diese Weise wird sichergestellt, dass alle Ressourcen-Manager, auf die diese Methode zugreift, denselben Geltungsbereich einer Transaktion verwenden, der auch zum Abrufen der Nachricht aus der Warteschlange verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8754e-162">This ensures that the same transaction scope that is used to retrieve the message from the queue is used by any resource managers accessed by the method.</span></span> <span data-ttu-id="8754e-163">In diesem Beispiel wird eine einfache Datenbank zum Speichern der in der Nachricht enthaltenen Bestellinformation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8754e-163">In this example, we use a basic database to store the purchase order information contained in the message.</span></span> <span data-ttu-id="8754e-164">Des Weiteren wird durch den Transaktionsbereich gewährleistet, dass die Nachricht an die Warteschlange zurückgegeben wird, wenn die Methode eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="8754e-164">The transaction scope also guarantees that if the method throws an exception, the message is returned to the queue.</span></span> <span data-ttu-id="8754e-165">Ohne Festlegung dieses Vorgangsverhaltens erstellt ein in der Warteschlange stehender Kanal eine Transaktion, um die Nachricht aus der Warteschlange zu lesen, und führt automatisch vor der Verteilung der Nachricht dafür einen Commit aus, sodass die Nachricht verloren geht, falls der Vorgang fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="8754e-165">Without setting this operation behavior, a queued channel creates a transaction to read the message from the queue and commits it automatically before it is dispatched so that if the operation fails, the message is lost.</span></span> <span data-ttu-id="8754e-166">Das häufigste Szenario betrifft Dienstvorgänge, die sich in der Transaktion eintragen, die zum Lesen der Nachricht aus der Warteschlange dient, wie im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8754e-166">The most common scenario is for service operations to enlist in the transaction that is used to read the message from the queue as demonstrated in the following code.</span></span>  
  
 <span data-ttu-id="8754e-167">Beachten Sie, dass `ReleaseServiceInstanceOnTransactionComplete` auf `false` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="8754e-167">Note that `ReleaseServiceInstanceOnTransactionComplete` is set to `false`.</span></span> <span data-ttu-id="8754e-168">Dies ist eine wichtige Anforderung für die Batchverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="8754e-168">This is an important requirement for batching.</span></span> <span data-ttu-id="8754e-169">Die Eigenschaft `ReleaseServiceInstanceOnTransactionComplete` für `ServiceBehaviorAttribute`gibt an, was nach Abschluss der Transaktion mit der Dienstinstanz geschehen soll.</span><span class="sxs-lookup"><span data-stu-id="8754e-169">The property `ReleaseServiceInstanceOnTransactionComplete` on `ServiceBehaviorAttribute` indicates what to do with the service instance once the transaction is completed.</span></span> <span data-ttu-id="8754e-170">Standardmäßig wird die Dienstinstanz nach Abschluss der Transaktion freigegeben.</span><span class="sxs-lookup"><span data-stu-id="8754e-170">By default, the service instance is released upon completing the transaction.</span></span> <span data-ttu-id="8754e-171">Der wichtigste Aspekt bei der Batchverarbeitung ist die Verwendung einer einzelnen Transaktion zum Lesen und Verteilen einer großen Anazahl an Nachrichten in der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="8754e-171">The core aspect to batching is the use of a single transaction for reading and dispatching many messages in the queue.</span></span> <span data-ttu-id="8754e-172">Die Freigabe des Diensts führt also zum Vorzeitigen Abschluss der Transaktion, wodurch der ganze Nutzen der Stapelverarbeitung hinfällig wird.</span><span class="sxs-lookup"><span data-stu-id="8754e-172">Therefore releasing the service instance ends up completing the transaction prematurely negating the very use of batching.</span></span> <span data-ttu-id="8754e-173">Wenn diese Eigenschaft auf `true` gesetzt und transaktive Batchverarbeitung zum Endpunkt hinzugefügt wird, löst das Batchverarbeitungsverhalten eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="8754e-173">If this property is set to `true` and transacted batching behavior is added to the endpoint, the batching validation behavior throws an exception.</span></span>  

```csharp
// Service class that implements the service contract.  
// Added code to write output to the console window.  
[ServiceBehavior(ReleaseServiceInstanceOnTransactionComplete=false,   
TransactionIsolationLevel=  
System.Transactions.IsolationLevel.Serializable, ConcurrencyMode=ConcurrencyMode.Multiple)]  
public class OrderProcessorService : IOrderProcessor  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                       TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Orders.Add(po);  
        Console.WriteLine("Processing {0} ", po);  
    }  
    …  
}  
```

 <span data-ttu-id="8754e-174">Die `Orders`-Klasse kapselt die Verarbeitung des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="8754e-174">The `Orders` class encapsulates the processing of the order.</span></span> <span data-ttu-id="8754e-175">Im Beispiel aktualisiert sie die Datenbank mit Bestellinformationen.</span><span class="sxs-lookup"><span data-stu-id="8754e-175">In the sample, it updates the database with purchase order information.</span></span>  

```csharp
// Order Processing Logic  
public class Orders  
{  
    public static void Add(PurchaseOrder po)  
    {  
        // Insert purchase order.  
        SqlCommand insertPurchaseOrderCommand =   
        new SqlCommand(  
        "insert into PurchaseOrders(poNumber, customerId)   
                               values(@poNumber, @customerId)");  
        insertPurchaseOrderCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        insertPurchaseOrderCommand.Parameters.Add("@customerId",   
                                         SqlDbType.VarChar, 50);  
  
        // Insert product line item.  
        SqlCommand insertProductLineItemCommand =   
             new SqlCommand("insert into ProductLineItems(productId,   
                    unitCost, quantity, poNumber) values(@productId,   
                    @unitCost, @quantity, @poNumber)");  
        insertProductLineItemCommand.Parameters.Add("@productId",   
                                           SqlDbType.VarChar, 50);  
        insertProductLineItemCommand.Parameters.Add("@unitCost",   
                                                  SqlDbType.Float);  
        insertProductLineItemCommand.Parameters.Add("@quantity",   
                                                     SqlDbType.Int);  
        insertProductLineItemCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        int rowsAffected = 0;  
        using (TransactionScope scope =   
              new TransactionScope(TransactionScopeOption.Required))  
        {  
             using (SqlConnection conn = new   
                 SqlConnection(  
                 ConfigurationManager.AppSettings["connectionString"]))  
             {  
                 conn.Open();  
  
                // Insert into purchase order table.  
               insertPurchaseOrderCommand.Connection = conn;  
               insertPurchaseOrderCommand.Parameters["@poNumber"].Value   
                                                       = po.PONumber;  
             insertPurchaseOrderCommand.Parameters["@customerId"].Value   
                                                    =po.CustomerId;  
             insertPurchaseOrderCommand.ExecuteNonQuery();  
  
            // Insert into product line item table.  
            insertProductLineItemCommand.Connection = conn;  
            foreach (PurchaseOrderLineItem orderLineItem in   
                                        po.orderLineItems) {  
            insertProductLineItemCommand.Parameters["@poNumber"].Value   
                                                          =po.PONumber;  
            insertProductLineItemCommand.Parameters["@productId"].Value   
                                             = orderLineItem.ProductId;  
            insertProductLineItemCommand.Parameters["@unitCost"].Value   
                                             = orderLineItem.UnitCost;  
            insertProductLineItemCommand.Parameters["@quantity"].Value   
                                             = orderLineItem.Quantity;  
            rowsAffected +=   
            insertProductLineItemCommand.ExecuteNonQuery();  
            }  
            scope.Complete();  
        }  
     }  
     Console.WriteLine(  
     "Updated database with {0} product line items  for purchase order   
                                     {1} ", rowsAffected, po.PONumber);  
    }  
}  
```

 <span data-ttu-id="8754e-176">Das Batchverarbeitungsverhalten und seine Konfiguration werden in der Dienstanwendungskonfiguration angegeben.</span><span class="sxs-lookup"><span data-stu-id="8754e-176">The batching behavior and its configuration are specified in the service application configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName"   
     value=".\private$\ServiceModelSamplesTransactedBatching" />  
    <add key="baseAddress"   
     value=  
     "http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
    <add key="connectionString" value="Data Source=.\SQLEXPRESS;AttachDbFilename=|DataDirectory|orders.mdf;Integrated Security=True;User Instance=True;" />  
  </appSettings>  
  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ThrottlingBehavior">  
          <serviceThrottling maxConcurrentCalls="5"/>  
        </behavior>  
      </serviceBehaviors>  
  
      <endpointBehaviors>  
        <behavior name="BatchingBehavior">  
          <transactedBatching maxBatchSize="100"/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service   
          behaviorConfiguration="ThrottlingBehavior"   
          name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address=  
"net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                  binding="netMsmqBinding"  
                  behaviorConfiguration="BatchingBehavior"   
                  contract=  
                    "Microsoft.ServiceModel.Samples.IOrderProcessor" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  <span data-ttu-id="8754e-177">Die Batchgröße ist ein Hinweis für das System.</span><span class="sxs-lookup"><span data-stu-id="8754e-177">The batch size is a hint to the system.</span></span> <span data-ttu-id="8754e-178">Wenn Sie beispielsweise die Batchgröße 20 angaben, werden 20 Nachrichten in einer einzelnen Transaktion gelesen und verteilt, und anschließend wird ein Commit für die Transaktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8754e-178">For example, if you specify a batch size of 20, then 20 messages would be read and dispatched using a single transaction and then the transaction is committed.</span></span> <span data-ttu-id="8754e-179">Aber es gibt Fälle, in denen die Transaktion möglicherweise einen Commit für den Batch ausführt, bevor die Batchgröße erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="8754e-179">But there are cases where the transaction may commit the batch before the batch size is reached.</span></span>  
>   
>  <span data-ttu-id="8754e-180">Jeder Transaktion ist ein Timeout zugeordnet, das zu laufen beginnt, sobald die Transaktion erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="8754e-180">Associated with every transaction is a timeout that starts ticking once the transaction is created.</span></span> <span data-ttu-id="8754e-181">Wenn dieses Timeout abläuft, wird die Transaktion abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="8754e-181">When this timeout expires the transaction is aborted.</span></span> <span data-ttu-id="8754e-182">Es ist sogar möglich, dass dieses Timeout abläuft, bevor die Batchgröße erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="8754e-182">It is possible for this timeout to expire even before the batch size is reached.</span></span> <span data-ttu-id="8754e-183">Um zu vermeiden, dass der Batch aufgrund des Abbruchs erneut verarbeitet werden muss, überprüft `TransactedBatchingBehavior`, wie viel Zeit für die Transaktion noch übrig ist.</span><span class="sxs-lookup"><span data-stu-id="8754e-183">To avoid re-working the batch because of the abort, the `TransactedBatchingBehavior` checks to see how much time is left on the transaction.</span></span> <span data-ttu-id="8754e-184">Wenn 80 % des Transaktionstimeouts abgelaufen sind, wird ein Commit für die Transaktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8754e-184">If 80% of the transaction timeout is used up, then the transaction is committed.</span></span>  
>   
>  <span data-ttu-id="8754e-185">Falls die Warteschlange keine weiteren Nachrichten mehr enthält, wird nicht weiter auf das Erreichen der Batchgröße gewartet, sondern <xref:System.ServiceModel.Description.TransactedBatchingBehavior> führt einen Commit für die Transaktion durch.</span><span class="sxs-lookup"><span data-stu-id="8754e-185">If there are no more messages in the queue then instead of waiting for the fulfillment of the batch size the <xref:System.ServiceModel.Description.TransactedBatchingBehavior> commits the transaction.</span></span>  
>   
>  <span data-ttu-id="8754e-186">Die Auswahl der Batchgröße hängt von Ihrer Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="8754e-186">The choice of the batch size is dependent on your application.</span></span> <span data-ttu-id="8754e-187">Wenn die Batchgröße zu klein ist, wird möglicherweise nicht die gewünschte Leistung erreicht.</span><span class="sxs-lookup"><span data-stu-id="8754e-187">If the batch size is too small, you may not get the desired performance.</span></span> <span data-ttu-id="8754e-188">Andererseits kann auch eine zu große Batchgröße zu Leistungseinbußen führen.</span><span class="sxs-lookup"><span data-stu-id="8754e-188">On the other hand if the batch size is too big, it may deteriorate performance.</span></span> <span data-ttu-id="8754e-189">Beispielsweise könnte die Transaktion länger erhalten bleiben und die Datenbank sperren, oder die Transaktion könnte blockiert werden, was dazu führen könnte, dass der Batch zurückgesetzt wird und die Arbeit wiederholt werden muss.</span><span class="sxs-lookup"><span data-stu-id="8754e-189">For example, your transaction could live longer and hold locks on your database or your transaction could become dead locked, which could cause the batch to get rolled back and to redo the work.</span></span>  
  
 <span data-ttu-id="8754e-190">Der Client erstellt einen Geltungsbereich für die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="8754e-190">The client creates a transaction scope.</span></span> <span data-ttu-id="8754e-191">Die Kommunikation mit der Warteschlange findet innerhalb des Geltungsbereichs der Transaktion statt, sodass diese in der Folge als unteilbare Einheit behandelt wird, in der entweder alle oder keine Nachrichten an die Warteschlange gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="8754e-191">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages are sent to the queue or none of the messages are sent to the queue.</span></span> <span data-ttu-id="8754e-192">Für die Transaktion wird ein Commit ausgeführt, indem <xref:System.Transactions.TransactionScope.Complete%2A> im Geltungsbereich der Transaktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8754e-192">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A> on the transaction scope.</span></span>  

```csharp
//Client implementation code.  
class Client  
{  
    static void Main()  
    {  
        Random randomGen = new Random();  
        for (int i = 0; i < 2500; i++)  
        {  
            // Create a client with given client endpoint configuration.  
            OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
            // Create the purchase order.  
            PurchaseOrder po = new PurchaseOrder();  
            po.CustomerId = "somecustomer" + i + ".com";  
            po.PONumber = Guid.NewGuid().ToString();  
  
            PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
            lineItem1.ProductId = "Blue Widget";  
            lineItem1.Quantity = randomGen.Next(1, 100);  
            lineItem1.UnitCost = (float)randomGen.NextDouble() * 10;  
  
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
                // Make a queued call to submit the purchase order.  
                client.SubmitPurchaseOrder(po);  
                // Complete the transaction.  
                scope.Complete();  
            }  
  
            client.Close();  
        }  
        Console.WriteLine();  
        Console.WriteLine("Press <ENTER> to terminate client.");  
        Console.ReadLine();  
    }  
}  
```

 <span data-ttu-id="8754e-193">Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8754e-193">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="8754e-194">Sie können sehen, wie der Dienst Nachrichten vom Client empfängt.</span><span class="sxs-lookup"><span data-stu-id="8754e-194">You can see the service receive messages from the client.</span></span> <span data-ttu-id="8754e-195">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="8754e-195">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="8754e-196">Beachten Sie, dass aufgrund der Verwendung einer Warteschlange der Client und der Dienst nicht gleichzeitig ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8754e-196">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="8754e-197">Sie können den Client ausführen, ihn schließen und anschließend den Dienst starten, der dann trotzdem noch die Nachrichten des Clients empfängt.</span><span class="sxs-lookup"><span data-stu-id="8754e-197">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span> <span data-ttu-id="8754e-198">Sie können eine rollende Ausgabe sehen, während Nachrichten in einen Batch eingelesen und verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="8754e-198">You can see a rolling output as messages are read in a batch and processed.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Updated database with 2 product line items for purchase order 493ac832-d216-4e94-b2a5-d7f492fb5e39  
Processing Purchase Order: 8b567f5b-0661-4662-aae2-6cef1bd6d278  
        Customer: somecustomer849.com  
        OrderDetails  
               Order LineItem: 80 of Blue Widget @unit price: $9.751623  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41622.23  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 41130b95-4ea8-40a9-91c3-2e129117fcb8  
Processing Purchase Order: 5ce2699d-9a31-4cc2-a8c5-64cda614b3c7  
        Customer: somecustomer850.com  
        OrderDetails  
               Order LineItem: 89 of Blue Widget @unit price: $6.369128  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41408.95  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 8b567f5b-0661-4662-aae2-6cef1bd6d278  
Processing Purchase Order: ea94486b-7c86-4309-a42d-2f06c00656cd  
        Customer: somecustomer851.com  
        OrderDetails  
             Order LineItem: 47 of Blue Widget @unit price: $0.9391424  
             Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $40886.24  
        Order status: Pending  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="8754e-199">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="8754e-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8754e-200">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="8754e-200">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8754e-201">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="8754e-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8754e-202">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8754e-202">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Batching`  
  
## <a name="see-also"></a><span data-ttu-id="8754e-203">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8754e-203">See Also</span></span>
