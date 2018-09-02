---
title: 'Transport: Beispiel für benutzerdefinierte Transaktionen über UDP'
ms.date: 03/30/2017
ms.assetid: 6cebf975-41bd-443e-9540-fd2463c3eb23
ms.openlocfilehash: b3a105194ceef9d9091dfbc9521fd47978517f89
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43452715"
---
# <a name="transport-custom-transactions-over-udp-sample"></a><span data-ttu-id="d4b77-102">Transport: Beispiel für benutzerdefinierte Transaktionen über UDP</span><span class="sxs-lookup"><span data-stu-id="d4b77-102">Transport: Custom Transactions over UDP Sample</span></span>
<span data-ttu-id="d4b77-103">Dieses Beispiel basiert auf der [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel in der Windows Communication Foundation (WCF)[Transporterweiterbarkeit](../../../../docs/framework/wcf/samples/transport-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="d4b77-103">This sample is based on the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample in the Windows Communication Foundation (WCF)[Transport Extensibility](../../../../docs/framework/wcf/samples/transport-extensibility.md).</span></span> <span data-ttu-id="d4b77-104">Es erweitert das Beispiel für den UDP-Transport, um einen benutzerdefinierten Transaktionsfluss zu unterstützen, und veranschaulicht die Verwendung der <xref:System.ServiceModel.Channels.TransactionMessageProperty>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d4b77-104">It extends the UDP Transport sample to support custom transaction flow and demonstrates the use of the <xref:System.ServiceModel.Channels.TransactionMessageProperty> property.</span></span>  
  
## <a name="code-changes-in-the-udp-transport-sample"></a><span data-ttu-id="d4b77-105">Codeänderungen im Beispiel für den UDP-Transport</span><span class="sxs-lookup"><span data-stu-id="d4b77-105">Code Changes in the UDP Transport Sample</span></span>  
 <span data-ttu-id="d4b77-106">Zur Veranschaulichung des Transaktionsflusses wird der Dienstvertrag für `ICalculatorContract` im Beispiel geändert, sodass für `CalculatorService.Add()` ein Transaktionsbereich erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d4b77-106">To demonstrate transaction flow, the sample changes the service contract for `ICalculatorContract` to require a transaction scope for `CalculatorService.Add()`.</span></span> <span data-ttu-id="d4b77-107">Im Beispiel wird dem Vertrag des `System.Guid`-Vorgangs außerdem ein zusätzlicher `Add`-Parameter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d4b77-107">The sample also adds an extra `System.Guid` parameter to the contract of the `Add` operation.</span></span> <span data-ttu-id="d4b77-108">Dieser Parameter wird dazu verwendet, den Bezeichner der Clienttransaktion an den Dienst zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="d4b77-108">This parameter is used to pass the identifier of the client transaction to the service.</span></span>  
  
```  
class CalculatorService : IDatagramContract, ICalculatorContract  
{  
    [OperationBehavior(TransactionScopeRequired=true)]  
    public int Add(int x, int y, Guid clientTransactionId)  
    {  
        if(Transaction.Current.TransactionInformation.DistributedIdentifier == clientTransactionId)  
    {  
        Console.WriteLine("The client transaction has flowed to the service");  
    }  
    else  
    {  
     Console.WriteLine("The client transaction has NOT flowed to the service");  
    }  
  
    Console.WriteLine("   adding {0} + {1}", x, y);              
    return (x + y);  
    }  
  
    [...]  
}  
```  
  
 <span data-ttu-id="d4b77-109">Die [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel UDP-Pakete verwendet, um Nachrichten zwischen einem Client und einem Dienst zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="d4b77-109">The [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample uses UDP packets to pass messages between a client and a service.</span></span> <span data-ttu-id="d4b77-110">Die [Transport: benutzerdefinierte Transportbeispiel](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) verwendet den gleichen Mechanismus zur Übertragung von Nachrichten, aber wenn eine Transaktion übergeben wird, wird es in UDP-Paket zusammen mit der codierten Nachricht eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d4b77-110">The [Transport: Custom Transport Sample](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) uses the same mechanism to transport messages, but when a transaction is flowed, it is inserted into the UDP packet along with the encoded message.</span></span>  
  
```  
byte[] txmsgBuffer =                TransactionMessageBuffer.WriteTransactionMessageBuffer(txPropToken, messageBuffer);  
  
int bytesSent = this.socket.SendTo(txmsgBuffer, 0, txmsgBuffer.Length, SocketFlags.None, this.remoteEndPoint);  
```  
  
 <span data-ttu-id="d4b77-111">Bei `TransactionMessageBuffer.WriteTransactionMessageBuffer` handelt es sich um eine Hilfsmethode mit einer neuen Funktionalität, mit der das Weitergabetoken für die aktuelle Transaktion mit der Nachrichtenentität zusammengeführt und in einem Puffer platziert wird.</span><span class="sxs-lookup"><span data-stu-id="d4b77-111">`TransactionMessageBuffer.WriteTransactionMessageBuffer` is a helper method that contains new functionality to merge the propagation token for the current transaction with the message entity and place it into a buffer.</span></span>  
  
 <span data-ttu-id="d4b77-112">Für die Übertragung über einen benutzerdefinierten Transaktionsfluss muss die Clientimplementierung wissen, welche Dienstvorgänge einen Transaktionsfluss erfordern, und übergeben diese Informationen zu WCF.</span><span class="sxs-lookup"><span data-stu-id="d4b77-112">For custom transaction flow transport, the client implementation must know what service operations require transaction flow and to pass this information to WCF.</span></span> <span data-ttu-id="d4b77-113">Es sollte auch ein Mechanismus zum Senden der Benutzertransaktion an die Transportebene vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d4b77-113">There should also be a mechanism for transmitting the user transaction to the transport layer.</span></span> <span data-ttu-id="d4b77-114">In diesem Beispiel wird "WCF-nachrichteninspektoren" verwendet, um diese Informationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d4b77-114">This sample uses "WCF message inspectors" to obtain this information.</span></span> <span data-ttu-id="d4b77-115">Der hier implementierte Clientnachrichteninspektor mit der Bezeichnung `TransactionFlowInspector` führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="d4b77-115">The client message inspector implemented here, which is called `TransactionFlowInspector`, performs the following tasks:</span></span>  
  
-   <span data-ttu-id="d4b77-116">Bestimmt, ob für eine bestimmte Nachrichtenaktion ein Transaktionsfluss erfolgen muss (dies geschieht in `IsTxFlowRequiredForThisOperation()`).</span><span class="sxs-lookup"><span data-stu-id="d4b77-116">Determines whether a transaction must be flowed for a given message action (this takes place in `IsTxFlowRequiredForThisOperation()`).</span></span>  
  
-   <span data-ttu-id="d4b77-117">Fügt die aktuelle Ambient-Transaktion mithilfe von `TransactionFlowProperty` an die Nachricht an, falls ein Transaktionsfluss erfolgen muss (dies geschieht in `BeforeSendRequest()`).</span><span class="sxs-lookup"><span data-stu-id="d4b77-117">Attaches the current ambient transaction to the message using `TransactionFlowProperty`, if a transaction is required to be flowed (this is done in `BeforeSendRequest()`).</span></span>  
  
```  
public class TransactionFlowInspector : IClientMessageInspector  
{  
   void IClientMessageInspector.AfterReceiveReply(ref           System.ServiceModel.Channels.Message reply, object correlationState)  
  {  
  }  
  
   public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
   {  
       // obtain the tx propagation token  
       byte[] propToken = null;             
       if (Transaction.Current != null && IsTxFlowRequiredForThisOperation(request.Headers.Action))  
       {  
           try  
           {  
               propToken = TransactionInterop.GetTransmitterPropagationToken(Transaction.Current);  
           }  
           catch (TransactionException e)  
           {  
              throw new CommunicationException("TransactionInterop.GetTransmitterPropagationToken failed.", e);  
           }  
       }  
  
      // set the propToken on the message in a TransactionFlowProperty  
       TransactionFlowProperty.Set(propToken, request);  
  
       return null;              
    }  
  }  
  
  static bool IsTxFlowRequiredForThisOperation(String action)  
 {  
       // In general, this should contain logic to identify which operations (actions)      require transaction flow.  
      [...]  
 }  
}  
```  
  
 <span data-ttu-id="d4b77-118">Der `TransactionFlowInspector` selbst wird mithilfe eines benutzerdefinierten Verhaltens (`TransactionFlowBehavior`) ans Framework übergeben.</span><span class="sxs-lookup"><span data-stu-id="d4b77-118">The `TransactionFlowInspector` itself is passed to the framework using a custom behavior: the `TransactionFlowBehavior`.</span></span>  
  
```  
public class TransactionFlowBehavior : IEndpointBehavior  
{  
       public void AddBindingParameters(ServiceEndpoint endpoint,            System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
      {  
      }  
  
       public void ApplyClientBehavior(ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.ClientRuntime clientRuntime)  
      {  
            TransactionFlowInspector inspector = new TransactionFlowInspector();  
            clientRuntime.MessageInspectors.Add(inspector);  
      }  
  
      public void ApplyDispatchBehavior(ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.EndpointDispatcher endpointDispatcher)  
     {  
     }  
  
      public void Validate(ServiceEndpoint endpoint)  
      {  
      }  
}  
```  
  
 <span data-ttu-id="d4b77-119">Wenn der vorangehende Mechanismus vorhanden ist, erstellt der Benutzercode vor dem Aufrufen des Dienstvorgangs einen `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="d4b77-119">With the preceding mechanism in place, the user code creates a `TransactionScope` before calling the service operation.</span></span> <span data-ttu-id="d4b77-120">Der Nachrichteninspektor stellt sicher, dass die Transaktion an den Transport übergeben wird, falls sie an den Dienstvorgang übergeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="d4b77-120">The message inspector ensures that the transaction is passed to the transport in case it is required to be flowed to the service operation.</span></span>  
  
```  
CalculatorContractClient calculatorClient = new CalculatorContractClient("SampleProfileUdpBinding_ICalculatorContract");  
calculatorClient.Endpoint.Behaviors.Add(new TransactionFlowBehavior());               
  
try  
{  
       for (int i = 0; i < 5; ++i)  
      {  
              // call the 'Add' service operation under a transaction scope  
             using (TransactionScope ts = new TransactionScope())  
             {  
        [...]  
        Console.WriteLine(calculatorClient.Add(i, i * 2));  
         }  
      }               
       calculatorClient.Close();  
}  
catch (TimeoutException)  
{  
    calculatorClient.Abort();  
}  
catch (CommunicationException)  
{  
    calculatorClient.Abort();  
}  
catch (Exception)  
{  
    calculatorClient.Abort();  
    throw;  
}  
```  
  
 <span data-ttu-id="d4b77-121">Nach dem Empfang eines UDP-Pakets vom Client wird dieses vom Dienst deserialisiert, um die Nachricht und möglicherweise eine Transaktion zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="d4b77-121">Upon receiving a UDP packet from the client, the service deserializes it to extract the message and possibly a transaction.</span></span>  
  
```  
count = listenSocket.EndReceiveFrom(result, ref dummy);  
  
// read the transaction and message                       TransactionMessageBuffer.ReadTransactionMessageBuffer(buffer, count, out transaction, out msg);  
```  
  
 <span data-ttu-id="d4b77-122">`TransactionMessageBuffer.ReadTransactionMessageBuffer()` ist die Hilfsmethode, die den von `TransactionMessageBuffer.WriteTransactionMessageBuffer()` ausgeführten Serialisierungsprozess umkehrt.</span><span class="sxs-lookup"><span data-stu-id="d4b77-122">`TransactionMessageBuffer.ReadTransactionMessageBuffer()` is the helper method that reverses the serialization process performed by `TransactionMessageBuffer.WriteTransactionMessageBuffer()`.</span></span>  
  
 <span data-ttu-id="d4b77-123">Wenn ein Transaktionsfluss erfolgte, wird die Transaktion an die Nachricht in `TransactionMessageProperty` angehängt.</span><span class="sxs-lookup"><span data-stu-id="d4b77-123">If a transaction was flowed in, it is appended to the message in the `TransactionMessageProperty`.</span></span>  
  
```  
message = MessageEncoderFactory.Encoder.ReadMessage(msg, bufferManager);  
  
if (transaction != null)  
{  
       TransactionMessageProperty.Set(transaction, message);  
}  
```  
  
 <span data-ttu-id="d4b77-124">Auf diese Weise wird sichergestellt, dass der Verteiler die Transaktion zum Versandzeitpunkt aufnimmt und sie beim Aufrufen des Dienstvorgangs verwendet, an den die Nachricht adressiert ist.</span><span class="sxs-lookup"><span data-stu-id="d4b77-124">This ensures that the dispatcher picks up the transaction at dispatch time and uses it when calling the service operation addressed by the message.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d4b77-125">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="d4b77-125">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d4b77-126">Um die Projektmappe zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d4b77-126">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="d4b77-127">Das aktuelle Beispiel sollte ähnlich wie bei ausgeführt werden, die [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d4b77-127">The current sample should be run similarly to the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span> <span data-ttu-id="d4b77-128">Starten Sie den Dienst mit UdpTestService.exe, um das Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d4b77-128">To run it, start the service with UdpTestService.exe.</span></span> <span data-ttu-id="d4b77-129">Wenn Sie [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] ausführen, müssen Sie den Dienst mit erhöhten Rechten starten.</span><span class="sxs-lookup"><span data-stu-id="d4b77-129">If you are running [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], you must start the service with elevated privileges.</span></span> <span data-ttu-id="d4b77-130">Dazu, mit der Maustaste UdpTestService.exe in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] , und klicken Sie auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d4b77-130">To do so, right-click UdpTestService.exe in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and click **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="d4b77-131">Hierdurch wird die folgende Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="d4b77-131">This produces the following output.</span></span>  
  
    ```  
    Testing Udp From Code.  
    Service is started from code...  
    Press <ENTER> to terminate the service and start service from config...  
    ```  
  
4.  <span data-ttu-id="d4b77-132">Zu diesem Zeitpunkt können Sie den Client durch Ausführen von UdpTestClient.exe starten.</span><span class="sxs-lookup"><span data-stu-id="d4b77-132">At this time, you can start the client by running UdpTestClient.exe.</span></span> <span data-ttu-id="d4b77-133">Die vom Client erzeugte Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="d4b77-133">The output produced by the client is as follows.</span></span>  
  
    ```  
    0  
    3  
    6  
    9  
    12  
    Press <ENTER> to complete test.  
    ```  
  
5.  <span data-ttu-id="d4b77-134">Die Ausgabe des Diensts lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="d4b77-134">The service output is as follows.</span></span>  
  
    ```  
    Hello, world!  
    Hello, world!  
    Hello, world!  
    Hello, world!  
    Hello, world!  
    The client transaction has flowed to the service  
       adding 0 + 0  
    The client transaction has flowed to the service  
       adding 1 + 2  
    The client transaction has flowed to the service  
       adding 2 + 4  
    The client transaction has flowed to the service  
       adding 3 + 6  
    The client transaction has flowed to the service  
       adding 4 + 8  
    ```  
  
6.  <span data-ttu-id="d4b77-135">Die Dienstanwendung zeigt die Nachricht `The client transaction has flowed to the service` an, wenn die vom Client gesendete Transaktions-ID (im `clientTransactionId`-Parameter des Vorgangs `CalculatorService.Add()`) mit der ID der Diensttransaktion übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="d4b77-135">The service application displays the message `The client transaction has flowed to the service` if it can match the transaction identifier sent by the client, in the `clientTransactionId` parameter of the `CalculatorService.Add()` operation, to the identifier of the service transaction.</span></span> <span data-ttu-id="d4b77-136">Eine Übereinstimmung liegt nur dann vor, wenn die Clienttransaktion an den Dienst übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d4b77-136">A match is obtained only if the client transaction has flowed to the service.</span></span>  
  
7.  <span data-ttu-id="d4b77-137">Um die Clientanwendung für Endpunkte auszuführen, die mithilfe einer Konfiguration veröffentlicht wurden, drücken Sie die EINGABETASTE im Dienstanwendungsfenster, und führen Sie den Testclient erneut aus.</span><span class="sxs-lookup"><span data-stu-id="d4b77-137">To run the client application against endpoints published using configuration, press ENTER on the service application window and then run the test client again.</span></span> <span data-ttu-id="d4b77-138">Auf dem Dienst sollten Sie die folgende Ausgabe erhalten:</span><span class="sxs-lookup"><span data-stu-id="d4b77-138">You should see the following output on the service.</span></span>  
  
    ```  
    Testing Udp From Config.  
    Service is started from config...  
    Press <ENTER> to terminate the service and exit...  
    ```  
  
8.  <span data-ttu-id="d4b77-139">Das Ausführen des Clients für den Dienst erzeugt nun eine ähnliche Ausgabe wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="d4b77-139">Running the client against the service now produces similar output as before.</span></span>  
  
9. <span data-ttu-id="d4b77-140">Um den Clientcode und die Konfiguration mithilfe von Svcutil.exe neu zu generieren, starten Sie die Dienstanwendung, und führen Sie dann den folgenden Svcutil.exe-Befehl aus dem Stammverzeichnis des Beispiels aus.</span><span class="sxs-lookup"><span data-stu-id="d4b77-140">To regenerate the client code and configuration using Svcutil.exe, start the service application and then run the following Svcutil.exe command from the root directory of the sample.</span></span>  
  
    ```  
    svcutil http://localhost:8000/udpsample/ /reference:UdpTranport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
    ```  
  
10. <span data-ttu-id="d4b77-141">Beachten Sie, dass Svcutil.exe nicht die Bindungserweiterungskonfiguration für `sampleProfileUdpBinding` generiert. Sie müssen diese manuell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d4b77-141">Note that Svcutil.exe does not generate the binding extension configuration for the `sampleProfileUdpBinding`; you must add it manually.</span></span>  
  
    ```xml  
    <configuration>  
        <system.serviceModel>      
            …  
            <extensions>  
                <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
                <bindingExtensions>  
                    <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
                </bindingExtensions>  
            </extensions>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="d4b77-142">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d4b77-142">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d4b77-143">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d4b77-143">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d4b77-144">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="d4b77-144">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d4b77-145">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d4b77-145">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transactions\TransactionMessagePropertyUDPTransport`  
  
## <a name="see-also"></a><span data-ttu-id="d4b77-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4b77-146">See Also</span></span>  
 [<span data-ttu-id="d4b77-147">Transport: UDP</span><span class="sxs-lookup"><span data-stu-id="d4b77-147">Transport: UDP</span></span>](../../../../docs/framework/wcf/samples/transport-udp.md)
