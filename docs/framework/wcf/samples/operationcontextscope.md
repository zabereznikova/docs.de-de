---
title: OperationContextScope
ms.date: 03/30/2017
ms.assetid: 11c11108-8eb4-4d49-95a0-83285a812262
ms.openlocfilehash: 0b2b4d9b22f654fa433c7473160444b41a5adfa4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575151"
---
# <a name="operationcontextscope"></a><span data-ttu-id="e982e-102">OperationContextScope</span><span class="sxs-lookup"><span data-stu-id="e982e-102">OperationContextScope</span></span>
<span data-ttu-id="e982e-103">Das OperationContextScope-Beispiel veranschaulicht, wie zusätzliche Informationen über einen Windows Communication Foundation (WCF)-Aufrufe mithilfe von Headern gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="e982e-103">The OperationContextScope sample demonstrates how to send extra information on a Windows Communication Foundation (WCF) call using headers.</span></span> <span data-ttu-id="e982e-104">In diesem Beispiel sind Server und Client Konsolenanwendungen.</span><span class="sxs-lookup"><span data-stu-id="e982e-104">In this sample, both the server and client are console applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e982e-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="e982e-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e982e-106">Im Beispiel wird veranschaulicht, wie ein Client weitere Informationen als <xref:System.ServiceModel.Channels.MessageHeader> mit <xref:System.ServiceModel.OperationContextScope> senden kann.</span><span class="sxs-lookup"><span data-stu-id="e982e-106">The sample demonstrates how a client can send additional information as a <xref:System.ServiceModel.Channels.MessageHeader> using <xref:System.ServiceModel.OperationContextScope>.</span></span> <span data-ttu-id="e982e-107">Ein <xref:System.ServiceModel.OperationContextScope>-Objekt wird erstellt, indem es einem Kanal zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="e982e-107">An <xref:System.ServiceModel.OperationContextScope> object is created by scoping it to a channel.</span></span> <span data-ttu-id="e982e-108">Der <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A>-Auflistung können Header hinzugefügt werden, die zum Remotedienst übersetzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e982e-108">Headers that must be translated to the remote service can be added to the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="e982e-109">Dieser Auflistung hinzugefügte Header können im Dienst durch den Zugriff auf <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e982e-109">Headers added to this collection can be retrieved on the service by accessing <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span></span> <span data-ttu-id="e982e-110">Die Aufrufe erfolgen auf mehreren Kanälen. Danach werden die dem Client hinzugefügten Header nur auf den Kanal angewendet, mit dem <xref:System.ServiceModel.OperationContextScope> erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e982e-110">Its calls are made on multiple channels and then the headers added to the client only apply to the channel that was used to create the <xref:System.ServiceModel.OperationContextScope>.</span></span>  
  
## <a name="messageheaderreader"></a><span data-ttu-id="e982e-111">MessageHeaderReader</span><span class="sxs-lookup"><span data-stu-id="e982e-111">MessageHeaderReader</span></span>  
 <span data-ttu-id="e982e-112">Dies ist der Beispieldienst, der eine Nachricht vom Client empfängt und den Header in der <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>-Auflistung sucht.</span><span class="sxs-lookup"><span data-stu-id="e982e-112">This is the sample service that receives a message from the client and tries to look up the header in the <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="e982e-113">Der Client übergibt die im Header gesendete GUID, und der Dienst ruft den benutzerdefinierten Header ab und vergleicht ihn, falls vorhanden, mit der vom Client als Argument übergebenen GUID.</span><span class="sxs-lookup"><span data-stu-id="e982e-113">The client passes the GUID that it sent in the header and the service retrieves the custom header and, if present, compares it with the GUID passed as the argument by the client.</span></span>  
  
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
  
## <a name="messageheaderclient"></a><span data-ttu-id="e982e-114">MessageHeaderClient</span><span class="sxs-lookup"><span data-stu-id="e982e-114">MessageHeaderClient</span></span>  
 <span data-ttu-id="e982e-115">Dies ist die Client Implementierung, die den vom [Service Model Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) generierten Proxy verwendet, um mit dem Remote Dienst zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="e982e-115">This is the client implementation that uses the proxy generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to communicate with the remote service.</span></span> <span data-ttu-id="e982e-116">Zuerst werden zwei Proxyobjekte von `MessageHeaderReaderClient` erstellt.</span><span class="sxs-lookup"><span data-stu-id="e982e-116">It first creates two proxy objects of `MessageHeaderReaderClient`.</span></span>  
  
```csharp
//Create two clients to the remote service.  
MessageHeaderReaderClient client1 = new MessageHeaderReaderClient();  
MessageHeaderReaderClient client2 = new MessageHeaderReaderClient();  
```  
  
 <span data-ttu-id="e982e-117">Der Client erstellt dann OperationContextScope und bewertet ihn zu `client1`.</span><span class="sxs-lookup"><span data-stu-id="e982e-117">Client then creates an OperationContextScope and scopes it to `client1`.</span></span> <span data-ttu-id="e982e-118"><xref:System.ServiceModel.Channels.MessageHeader> wird ein <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> hinzugefügt, und es wird ein Aufruf auf beiden Clients aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e982e-118">It adds a <xref:System.ServiceModel.Channels.MessageHeader> to <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> and invokes one call on both clients.</span></span> <span data-ttu-id="e982e-119">Dadurch wird sichergestellt, dass der Header nur ein `client1` -und nicht ein-Wert gesendet wird, `client2` indem der Rückgabewert des `RetrieveHeader` Aufrufes überprüft wird</span><span class="sxs-lookup"><span data-stu-id="e982e-119">It ensures that the header is sent only on `client1` and not on `client2` by checking the return value from the `RetrieveHeader` call.</span></span>  
  
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
  
 <span data-ttu-id="e982e-120">Dieses Beispiel ist selbst gehostet.</span><span class="sxs-lookup"><span data-stu-id="e982e-120">This sample is self-hosted.</span></span> <span data-ttu-id="e982e-121">Es wird die folgende Beispielausgabe vom Ausgeben des Beispiels bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="e982e-121">The following sample output from running the sample is provided:</span></span>  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e982e-122">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="e982e-122">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e982e-123">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="e982e-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="e982e-124">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e982e-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="e982e-125">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e982e-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e982e-126">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e982e-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e982e-127">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e982e-127">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e982e-128">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e982e-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e982e-129">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e982e-129">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\OperationContextScope`  
