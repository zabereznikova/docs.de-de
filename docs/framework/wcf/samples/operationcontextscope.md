---
title: "OperationContextScope | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11c11108-8eb4-4d49-95a0-83285a812262
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# OperationContextScope
Im OperationContextScope\-Beispiel wird veranschaulicht, wie zusätzliche Informationen über einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Aufruf mit Headern gesendet werden.In diesem Beispiel sind Server und Client Konsolenanwendungen.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Im Beispiel wird veranschaulicht, wie ein Client weitere Informationen als <xref:System.ServiceModel.Channels.MessageHeader> mit <xref:System.ServiceModel.OperationContextScope> senden kann.Ein <xref:System.ServiceModel.OperationContextScope>\-Objekt wird erstellt, indem es einem Kanal zugeordnet wird.Der <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A>\-Auflistung können Header hinzugefügt werden, die zum Remotedienst übersetzt werden müssen.Dieser Auflistung hinzugefügte Header können im Dienst durch den Zugriff auf <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> abgerufen werden.Die Aufrufe erfolgen auf mehreren Kanälen. Danach werden die dem Client hinzugefügten Header nur auf den Kanal angewendet, mit dem <xref:System.ServiceModel.OperationContextScope> erstellt wurde.  
  
## MessageHeaderReader  
 Dies ist der Beispieldienst, der eine Nachricht vom Client empfängt und den Header in der <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>\-Auflistung sucht.Der Client übergibt die im Header gesendete GUID, und der Dienst ruft den benutzerdefinierten Header ab und vergleicht ihn, falls vorhanden, mit der vom Client als Argument übergebenen GUID.  
  
```  
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
  
## MessageHeaderClient  
 Dies ist die Clientimplementierung, die den von [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generierten Proxy für die Kommunikation mit dem Remotedienst verwendet.Zuerst werden zwei Proxyobjekte von `MessageHeaderReaderClient` erstellt.  
  
```  
//Create two clients to the remote service.  
MessageHeaderReaderClient client1 = new MessageHeaderReaderClient();  
MessageHeaderReaderClient client2 = new MessageHeaderReaderClient();  
```  
  
 Der Client erstellt dann OperationContextScope und bewertet ihn zu `client1`.<xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> wird ein <xref:System.ServiceModel.Channels.MessageHeader> hinzugefügt, und es wird ein Aufruf auf beiden Clients aufgerufen.Es wird sichergestellt, dass der Header nur auf `client1` und nicht auf `client2` gesendet wird, indem der Rückgabewert des `RetrieveHeader`\-Aufrufs überprüft wird.  
  
```  
using (new OperationContextScope(client1.InnerChannel))  
{  
    //Create a new GUID that is sent as the header.  
    String guid = Guid.NewGuid().ToString();  
  
    //Create a MessageHeader for the GUID we just created.  
    MessageHeader customHeader = MessageHeader.CreateHeader(CustomHeader.HeaderName, CustomHeader.HeaderNamespace, guid);  
  
    //Add the header to the OutgoingMessageHeader collection.  
    OperationContext.Current.OutgoingMessageHeaders.Add(customHeader);  
  
    //Now call RetreieveHeader on both the proxies. Since the OperationContextScope is tied to   
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
  
 Dieses Beispiel ist selbst gehostet.Es wird die folgende Beispielausgabe vom Ausgeben des Beispiels bereitgestellt:  
  
```  
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
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\OperationContextScope`  
  
## Siehe auch