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
# <a name="transport-custom-transactions-over-udp-sample"></a>Transport: Beispiel für benutzerdefinierte Transaktionen über UDP
Dieses Beispiel basiert auf der [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel in der Windows Communication Foundation (WCF)[Transporterweiterbarkeit](../../../../docs/framework/wcf/samples/transport-extensibility.md). Es erweitert das Beispiel für den UDP-Transport, um einen benutzerdefinierten Transaktionsfluss zu unterstützen, und veranschaulicht die Verwendung der <xref:System.ServiceModel.Channels.TransactionMessageProperty>-Eigenschaft.  
  
## <a name="code-changes-in-the-udp-transport-sample"></a>Codeänderungen im Beispiel für den UDP-Transport  
 Zur Veranschaulichung des Transaktionsflusses wird der Dienstvertrag für `ICalculatorContract` im Beispiel geändert, sodass für `CalculatorService.Add()` ein Transaktionsbereich erforderlich ist. Im Beispiel wird dem Vertrag des `System.Guid`-Vorgangs außerdem ein zusätzlicher `Add`-Parameter hinzugefügt. Dieser Parameter wird dazu verwendet, den Bezeichner der Clienttransaktion an den Dienst zu übergeben.  
  
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
  
 Die [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel UDP-Pakete verwendet, um Nachrichten zwischen einem Client und einem Dienst zu übergeben. Die [Transport: benutzerdefinierte Transportbeispiel](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) verwendet den gleichen Mechanismus zur Übertragung von Nachrichten, aber wenn eine Transaktion übergeben wird, wird es in UDP-Paket zusammen mit der codierten Nachricht eingefügt.  
  
```  
byte[] txmsgBuffer =                TransactionMessageBuffer.WriteTransactionMessageBuffer(txPropToken, messageBuffer);  
  
int bytesSent = this.socket.SendTo(txmsgBuffer, 0, txmsgBuffer.Length, SocketFlags.None, this.remoteEndPoint);  
```  
  
 Bei `TransactionMessageBuffer.WriteTransactionMessageBuffer` handelt es sich um eine Hilfsmethode mit einer neuen Funktionalität, mit der das Weitergabetoken für die aktuelle Transaktion mit der Nachrichtenentität zusammengeführt und in einem Puffer platziert wird.  
  
 Für die Übertragung über einen benutzerdefinierten Transaktionsfluss muss die Clientimplementierung wissen, welche Dienstvorgänge einen Transaktionsfluss erfordern, und übergeben diese Informationen zu WCF. Es sollte auch ein Mechanismus zum Senden der Benutzertransaktion an die Transportebene vorhanden sein. In diesem Beispiel wird "WCF-nachrichteninspektoren" verwendet, um diese Informationen abzurufen. Der hier implementierte Clientnachrichteninspektor mit der Bezeichnung `TransactionFlowInspector` führt die folgenden Aufgaben aus:  
  
-   Bestimmt, ob für eine bestimmte Nachrichtenaktion ein Transaktionsfluss erfolgen muss (dies geschieht in `IsTxFlowRequiredForThisOperation()`).  
  
-   Fügt die aktuelle Ambient-Transaktion mithilfe von `TransactionFlowProperty` an die Nachricht an, falls ein Transaktionsfluss erfolgen muss (dies geschieht in `BeforeSendRequest()`).  
  
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
  
 Der `TransactionFlowInspector` selbst wird mithilfe eines benutzerdefinierten Verhaltens (`TransactionFlowBehavior`) ans Framework übergeben.  
  
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
  
 Wenn der vorangehende Mechanismus vorhanden ist, erstellt der Benutzercode vor dem Aufrufen des Dienstvorgangs einen `TransactionScope`. Der Nachrichteninspektor stellt sicher, dass die Transaktion an den Transport übergeben wird, falls sie an den Dienstvorgang übergeben werden muss.  
  
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
  
 Nach dem Empfang eines UDP-Pakets vom Client wird dieses vom Dienst deserialisiert, um die Nachricht und möglicherweise eine Transaktion zu extrahieren.  
  
```  
count = listenSocket.EndReceiveFrom(result, ref dummy);  
  
// read the transaction and message                       TransactionMessageBuffer.ReadTransactionMessageBuffer(buffer, count, out transaction, out msg);  
```  
  
 `TransactionMessageBuffer.ReadTransactionMessageBuffer()` ist die Hilfsmethode, die den von `TransactionMessageBuffer.WriteTransactionMessageBuffer()` ausgeführten Serialisierungsprozess umkehrt.  
  
 Wenn ein Transaktionsfluss erfolgte, wird die Transaktion an die Nachricht in `TransactionMessageProperty` angehängt.  
  
```  
message = MessageEncoderFactory.Encoder.ReadMessage(msg, bufferManager);  
  
if (transaction != null)  
{  
       TransactionMessageProperty.Set(transaction, message);  
}  
```  
  
 Auf diese Weise wird sichergestellt, dass der Verteiler die Transaktion zum Versandzeitpunkt aufnimmt und sie beim Aufrufen des Dienstvorgangs verwendet, an den die Nachricht adressiert ist.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Um die Projektmappe zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Das aktuelle Beispiel sollte ähnlich wie bei ausgeführt werden, die [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel. Starten Sie den Dienst mit UdpTestService.exe, um das Beispiel auszuführen. Wenn Sie [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] ausführen, müssen Sie den Dienst mit erhöhten Rechten starten. Dazu, mit der Maustaste UdpTestService.exe in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] , und klicken Sie auf **als Administrator ausführen**.  
  
3.  Hierdurch wird die folgende Ausgabe generiert.  
  
    ```  
    Testing Udp From Code.  
    Service is started from code...  
    Press <ENTER> to terminate the service and start service from config...  
    ```  
  
4.  Zu diesem Zeitpunkt können Sie den Client durch Ausführen von UdpTestClient.exe starten. Die vom Client erzeugte Ausgabe lautet wie folgt.  
  
    ```  
    0  
    3  
    6  
    9  
    12  
    Press <ENTER> to complete test.  
    ```  
  
5.  Die Ausgabe des Diensts lautet wie folgt.  
  
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
  
6.  Die Dienstanwendung zeigt die Nachricht `The client transaction has flowed to the service` an, wenn die vom Client gesendete Transaktions-ID (im `clientTransactionId`-Parameter des Vorgangs `CalculatorService.Add()`) mit der ID der Diensttransaktion übereinstimmt. Eine Übereinstimmung liegt nur dann vor, wenn die Clienttransaktion an den Dienst übergeben wurde.  
  
7.  Um die Clientanwendung für Endpunkte auszuführen, die mithilfe einer Konfiguration veröffentlicht wurden, drücken Sie die EINGABETASTE im Dienstanwendungsfenster, und führen Sie den Testclient erneut aus. Auf dem Dienst sollten Sie die folgende Ausgabe erhalten:  
  
    ```  
    Testing Udp From Config.  
    Service is started from config...  
    Press <ENTER> to terminate the service and exit...  
    ```  
  
8.  Das Ausführen des Clients für den Dienst erzeugt nun eine ähnliche Ausgabe wie zuvor.  
  
9. Um den Clientcode und die Konfiguration mithilfe von Svcutil.exe neu zu generieren, starten Sie die Dienstanwendung, und führen Sie dann den folgenden Svcutil.exe-Befehl aus dem Stammverzeichnis des Beispiels aus.  
  
    ```  
    svcutil http://localhost:8000/udpsample/ /reference:UdpTranport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
    ```  
  
10. Beachten Sie, dass Svcutil.exe nicht die Bindungserweiterungskonfiguration für `sampleProfileUdpBinding` generiert. Sie müssen diese manuell hinzufügen.  
  
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
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transactions\TransactionMessagePropertyUDPTransport`  
  
## <a name="see-also"></a>Siehe auch  
 [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md)
