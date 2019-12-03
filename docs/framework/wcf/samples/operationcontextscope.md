---
title: OperationContextScope
ms.date: 03/30/2017
ms.assetid: 11c11108-8eb4-4d49-95a0-83285a812262
ms.openlocfilehash: 581f75ece1a601b3baf590c1923a17a353de1ff1
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714613"
---
# <a name="operationcontextscope"></a>OperationContextScope
Das OperationContextScope-Beispiel veranschaulicht, wie zusätzliche Informationen über einen Windows Communication Foundation (WCF)-Aufrufe mithilfe von Headern gesendet werden. In diesem Beispiel sind Server und Client Konsolenanwendungen.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Im Beispiel wird veranschaulicht, wie ein Client weitere Informationen als <xref:System.ServiceModel.Channels.MessageHeader> mit <xref:System.ServiceModel.OperationContextScope> senden kann. Ein <xref:System.ServiceModel.OperationContextScope>-Objekt wird erstellt, indem es einem Kanal zugeordnet wird. Der <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A>-Auflistung können Header hinzugefügt werden, die zum Remotedienst übersetzt werden müssen. Dieser Auflistung hinzugefügte Header können im Dienst durch den Zugriff auf <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> abgerufen werden. Die Aufrufe erfolgen auf mehreren Kanälen. Danach werden die dem Client hinzugefügten Header nur auf den Kanal angewendet, mit dem <xref:System.ServiceModel.OperationContextScope> erstellt wurde.  
  
## <a name="messageheaderreader"></a>MessageHeaderReader  
 Dies ist der Beispieldienst, der eine Nachricht vom Client empfängt und den Header in der <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>-Auflistung sucht. Der Client übergibt die im Header gesendete GUID, und der Dienst ruft den benutzerdefinierten Header ab und vergleicht ihn, falls vorhanden, mit der vom Client als Argument übergebenen GUID.  
  
```csharp
public bool RetrieveHeader(string guid)  
{  
     MessageHeaders messageHeaderCollection =   
             OperationContext.Current.IncomingMessageHeaders;  
     String guidHeader = null;  
  
     Console.WriteLine("Trying to check if IncomingMessageHeader " +  
               " collection contains header with value {0}", guid);  
     if (messageHeaderCollection.FindHeader(  
                       CustomHeader.HeaderName,   
                       CustomHeader.HeaderNamespace) != -1)  
     {  
          guidHeader = messageHeaderCollection.GetHeader<String>(  
           CustomHeader.HeaderName, CustomHeader.HeaderNamespace);  
     }  
     else  
     {  
          Console.WriteLine("No header was found");  
     }  
     if (guidHeader != null)  
     {  
          Console.WriteLine("Found header with value {0}. "+   
         "Does it match with GUID sent as parameter: {1}",   
          guidHeader, guidHeader.Equals(guid));  
      }  
  
      Console.WriteLine();  
      //Return true if header is present and equals the guid sent by  
      // client as argument  
      return (guidHeader != null && guidHeader.Equals(guid));  
}  
```  
  
## <a name="messageheaderclient"></a>MessageHeaderClient  
 Dies ist die Client Implementierung, die den vom [Service Model Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generierten Proxy verwendet, um mit dem Remote Dienst zu kommunizieren. Zuerst werden zwei Proxyobjekte von `MessageHeaderReaderClient` erstellt.  
  
```csharp
//Create two clients to the remote service.  
MessageHeaderReaderClient client1 = new MessageHeaderReaderClient();  
MessageHeaderReaderClient client2 = new MessageHeaderReaderClient();  
```  
  
 Der Client erstellt dann OperationContextScope und bewertet ihn zu `client1`. <xref:System.ServiceModel.Channels.MessageHeader> wird ein <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> hinzugefügt, und es wird ein Aufruf auf beiden Clients aufgerufen. Dadurch wird sichergestellt, dass der-Header nur auf `client1` und nicht auf `client2` gesendet wird, indem der Rückgabewert des `RetrieveHeader`-Aufrufes aufgerufen wird.  
  
```csharp
using (new OperationContextScope(client1.InnerChannel))  
{  
    //Create a new GUID that is sent as the header.  
    String guid = Guid.NewGuid().ToString();  
  
    //Create a MessageHeader for the GUID we just created.  
    MessageHeader customHeader = MessageHeader.CreateHeader(CustomHeader.HeaderName, CustomHeader.HeaderNamespace, guid);  
  
    //Add the header to the OutgoingMessageHeader collection.  
    OperationContext.Current.OutgoingMessageHeaders.Add(customHeader);  
  
    //Now call RetrieveHeader on both the proxies. Since the OperationContextScope is tied to   
    //client1's InnerChannel, the header should only be added to calls made on that client.  
    //Calls made on client2 should not be sending the header across even though the call  
    //is made in the same OperationContextScope.  
    Console.WriteLine("Using client1 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: True", client1.RetrieveHeader(guid));  
  
    Console.WriteLine();  
    Console.WriteLine("Using client2 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: False", client2.RetrieveHeader(guid));  
}  
```  
  
 Dieses Beispiel ist selbst gehostet. Es wird die folgende Beispielausgabe vom Ausgeben des Beispiels bereitgestellt:  
  
```console  
Prompt> Service.exe  
The service is ready.  
Press <ENTER> to terminate service.  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
Found header with value 2239da67-546f-42d4-89dc-8eb3c06215d8. Does it match with GUID sent as parameter: True  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
No header was found  
  
Prompt>Client.exe  
Using client1 to send message  
Did server retrieve the header? : Actual: True, Expected: True  
  
Using client2 to send message  
Did server retrieve the header? : Actual: False, Expected: False  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\OperationContextScope`  
