---
title: OperationContextScope
ms.date: 03/30/2017
ms.assetid: 11c11108-8eb4-4d49-95a0-83285a812262
ms.openlocfilehash: 46180c47512fd4bdb5955ed0febb63892fc27b19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656790"
---
# <a name="operationcontextscope"></a><span data-ttu-id="fa672-102">OperationContextScope</span><span class="sxs-lookup"><span data-stu-id="fa672-102">OperationContextScope</span></span>
<span data-ttu-id="fa672-103">Im OperationContextScope-Beispiel wird veranschaulicht, wie zusätzliche Informationen für einen Windows Communication Foundation (WCF)-Aufruf verwenden von Headern gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fa672-103">The OperationContextScope sample demonstrates how to send extra information on a Windows Communication Foundation (WCF) call using headers.</span></span> <span data-ttu-id="fa672-104">In diesem Beispiel sind Server und Client Konsolenanwendungen.</span><span class="sxs-lookup"><span data-stu-id="fa672-104">In this sample, both the server and client are console applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa672-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="fa672-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="fa672-106">Im Beispiel wird veranschaulicht, wie ein Client weitere Informationen als <xref:System.ServiceModel.Channels.MessageHeader> mit <xref:System.ServiceModel.OperationContextScope> senden kann.</span><span class="sxs-lookup"><span data-stu-id="fa672-106">The sample demonstrates how a client can send additional information as a <xref:System.ServiceModel.Channels.MessageHeader> using <xref:System.ServiceModel.OperationContextScope>.</span></span> <span data-ttu-id="fa672-107">Ein <xref:System.ServiceModel.OperationContextScope>-Objekt wird erstellt, indem es einem Kanal zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="fa672-107">An <xref:System.ServiceModel.OperationContextScope> object is created by scoping it to a channel.</span></span> <span data-ttu-id="fa672-108">Der <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A>-Auflistung können Header hinzugefügt werden, die zum Remotedienst übersetzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="fa672-108">Headers that must be translated to the remote service can be added to the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="fa672-109">Dieser Auflistung hinzugefügte Header können im Dienst durch den Zugriff auf <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fa672-109">Headers added to this collection can be retrieved on the service by accessing <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span></span> <span data-ttu-id="fa672-110">Die Aufrufe erfolgen auf mehreren Kanälen. Danach werden die dem Client hinzugefügten Header nur auf den Kanal angewendet, mit dem <xref:System.ServiceModel.OperationContextScope> erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fa672-110">Its calls are made on multiple channels and then the headers added to the client only apply to the channel that was used to create the <xref:System.ServiceModel.OperationContextScope>.</span></span>  
  
## <a name="messageheaderreader"></a><span data-ttu-id="fa672-111">MessageHeaderReader</span><span class="sxs-lookup"><span data-stu-id="fa672-111">MessageHeaderReader</span></span>  
 <span data-ttu-id="fa672-112">Dies ist der Beispieldienst, der eine Nachricht vom Client empfängt und den Header in der <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>-Auflistung sucht.</span><span class="sxs-lookup"><span data-stu-id="fa672-112">This is the sample service that receives a message from the client and tries to look up the header in the <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="fa672-113">Der Client übergibt die im Header gesendete GUID, und der Dienst ruft den benutzerdefinierten Header ab und vergleicht ihn, falls vorhanden, mit der vom Client als Argument übergebenen GUID.</span><span class="sxs-lookup"><span data-stu-id="fa672-113">The client passes the GUID that it sent in the header and the service retrieves the custom header and, if present, compares it with the GUID passed as the argument by the client.</span></span>  
  
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
  
## <a name="messageheaderclient"></a><span data-ttu-id="fa672-114">MessageHeaderClient</span><span class="sxs-lookup"><span data-stu-id="fa672-114">MessageHeaderClient</span></span>  
 <span data-ttu-id="fa672-115">Dies ist die Clientimplementierung, die die vom generierten Proxy verwendet [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) für die Kommunikation mit dem Remotedienst.</span><span class="sxs-lookup"><span data-stu-id="fa672-115">This is the client implementation that uses the proxy generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to communicate with the remote service.</span></span> <span data-ttu-id="fa672-116">Zuerst werden zwei Proxyobjekte von `MessageHeaderReaderClient` erstellt.</span><span class="sxs-lookup"><span data-stu-id="fa672-116">It first creates two proxy objects of `MessageHeaderReaderClient`.</span></span>  
  
```csharp
//Create two clients to the remote service.  
MessageHeaderReaderClient client1 = new MessageHeaderReaderClient();  
MessageHeaderReaderClient client2 = new MessageHeaderReaderClient();  
```  
  
 <span data-ttu-id="fa672-117">Der Client erstellt dann OperationContextScope und bewertet ihn zu `client1`.</span><span class="sxs-lookup"><span data-stu-id="fa672-117">Client then creates an OperationContextScope and scopes it to `client1`.</span></span> <span data-ttu-id="fa672-118"><xref:System.ServiceModel.Channels.MessageHeader> wird ein <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> hinzugefügt, und es wird ein Aufruf auf beiden Clients aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fa672-118">It adds a <xref:System.ServiceModel.Channels.MessageHeader> to <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> and invokes one call on both clients.</span></span> <span data-ttu-id="fa672-119">Wird sichergestellt, dass die Header gesendet wird, nur auf `client1` und nicht in `client2` durch Überprüfen des Rückgabewerts aus den `RetrieveHeader` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fa672-119">It ensures that the header is sent only on `client1` and not on `client2` by checking the return value from the `RetrieveHeader` call.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="fa672-120">Dieses Beispiel ist selbst gehostet.</span><span class="sxs-lookup"><span data-stu-id="fa672-120">This sample is self-hosted.</span></span> <span data-ttu-id="fa672-121">Es wird die folgende Beispielausgabe vom Ausgeben des Beispiels bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="fa672-121">The following sample output from running the sample is provided:</span></span>  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fa672-122">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="fa672-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="fa672-123">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fa672-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="fa672-124">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="fa672-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="fa672-125">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fa672-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fa672-126">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="fa672-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fa672-127">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fa672-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fa672-128">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="fa672-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fa672-129">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fa672-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\OperationContextScope`  
  
## <a name="see-also"></a><span data-ttu-id="fa672-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa672-130">See also</span></span>
