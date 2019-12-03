---
title: MTOM-Codierung
ms.date: 03/30/2017
ms.assetid: 820e316f-4ee1-4eb5-ae38-b6a536e8a14f
ms.openlocfilehash: 4156ebed22dc775aa69cf473dc89a26d7e2070d7
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714756"
---
# <a name="mtom-encoding"></a><span data-ttu-id="e3909-102">MTOM-Codierung</span><span class="sxs-lookup"><span data-stu-id="e3909-102">MTOM Encoding</span></span>
<span data-ttu-id="e3909-103">Dieses Beispiel veranschaulicht die Verwendung der MTOM-Nachrichtencodierung (Message Transmission Optimization Mechanism) mit einer WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="e3909-103">This sample demonstrates the use of the Message Transmission Optimization Mechanism (MTOM) message encoding with a WSHttpBinding.</span></span> <span data-ttu-id="e3909-104">MTOM ist ein Mechanismus zum Übertragen großer Binäranhänge mit SOAP-Nachrichten als unformatierte Bytes, was kleinere Nachrichten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e3909-104">MTOM is a mechanism for transmitting large binary attachments with SOAP messages as raw bytes, allowing for smaller messages.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e3909-105">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e3909-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e3909-106">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e3909-106">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="e3909-107">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="e3909-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e3909-108">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e3909-108">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MTOM`  
  
 <span data-ttu-id="e3909-109">Standardmäßig sendet und empfängt "WSHttpBinding" Nachrichten als normales Text-XML.</span><span class="sxs-lookup"><span data-stu-id="e3909-109">By default, the WSHttpBinding sends and received messages as normal text XML.</span></span> <span data-ttu-id="e3909-110">Wenn Sie das Senden und Empfangen von MTOM-Nachrichten aktivieren möchten, legen Sie das `messageEncoding`-Attribut in der Bindungskonfiguration (wie im folgenden Beispielcode) oder direkt in der Bindung mithilfe der `MessageEncoding`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="e3909-110">To enable sending and receiving MTOM messages, set the `messageEncoding` attribute on the binding's configuration (as in the following example code), or directly on the binding using the `MessageEncoding` property.</span></span> <span data-ttu-id="e3909-111">Der Dienst oder Client kann nun MTOM-Nachrichten senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="e3909-111">The service or client can now send and receive MTOM messages.</span></span>  
  
```xml  
<wsHttpBinding>  
  <binding name="WSHttpBinding_IUpload" messageEncoding="Mtom" />  
</wsHttpBinding>  
```  
  
 <span data-ttu-id="e3909-112">Der MTOM-Encoder kann Arrays von Bytes und Streams optimieren.</span><span class="sxs-lookup"><span data-stu-id="e3909-112">The MTOM encoder can optimize arrays of bytes and streams.</span></span> <span data-ttu-id="e3909-113">In diesem Beispiel verwendet der Vorgang einen `Stream`-Parameter und kann deshalb optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="e3909-113">In this sample, the operation uses a `Stream` parameter and can therefore be optimized.</span></span>  

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
  public interface IUpload  
  {  
      [OperationContract]  
      int Upload(Stream data);  
  }  
```
  
 <span data-ttu-id="e3909-114">Der für dieses Beispiel gewählte Vertrag überträgt Binärdaten an den Dienst und empfängt die Anzahl der hochgeladenen Bytes als Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="e3909-114">The contract chosen for this sample transmits binary data to the service and receives the number of bytes uploaded as the return value.</span></span> <span data-ttu-id="e3909-115">Wenn der Dienst installiert ist und der Client ausgeführt wird, gibt er die Zahl 1000 aus. Damit wird angezeigt, dass alle 1000 Bytes empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="e3909-115">When the service is installed and the client is run, it prints out the number 1000, which indicates that all 1000 bytes were received.</span></span> <span data-ttu-id="e3909-116">Der Rest der Ausgabe führt optimierte und nicht optimierte Nachrichtengrößen für verschiedene Nutzlasten auf.</span><span class="sxs-lookup"><span data-stu-id="e3909-116">The remainder of the output lists optimized and non-optimized message sizes for various payloads.</span></span>  
  
```console
Output:  
1000  
  
Text encoding with a 100 byte payload: 433  
MTOM encoding with a 100 byte payload: 912  
  
Text encoding with a 1000 byte payload: 1633  
MTOM encoding with a 1000 byte payload: 2080  
  
Text encoding with a 10000 byte payload: 13633  
MTOM encoding with a 10000 byte payload: 11080  
  
Text encoding with a 100000 byte payload: 133633  
MTOM encoding with a 100000 byte payload: 101080  
  
Text encoding with a 1000000 byte payload: 1333633  
MTOM encoding with a 1000000 byte payload: 1001080  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="e3909-117">Der Zweck der Verwendung von MTOM besteht in der Optimierung der Übertragung großer binärer Nutzlasten.</span><span class="sxs-lookup"><span data-stu-id="e3909-117">The purpose for using MTOM is to optimize the transmission of large binary payloads.</span></span> <span data-ttu-id="e3909-118">Das Senden einer SOAP-Nachricht mit MTOM bedeutet zwar einen deutlichen Mehraufwand bei kleinen binären Nutzlasten, ist jedoch bei Datenmengen von mehr als einigen Tausend Bytes eine große Ersparnis.</span><span class="sxs-lookup"><span data-stu-id="e3909-118">Sending a SOAP message using MTOM has a noticeable overhead for small binary payloads, but becomes a great savings when they grow over a few thousand bytes.</span></span> <span data-ttu-id="e3909-119">Der Grund dafür liegt darin, dass normales Text-XML Binärdaten mit Base64 codiert. Dabei sind vier Zeichen für drei Bytes erforderlich, wodurch die Datenmenge um ein Drittel vergrößert wird.</span><span class="sxs-lookup"><span data-stu-id="e3909-119">The reason for this is that normal text XML encodes binary data using Base64, which requires four characters for every three bytes, and increases the size of the data by one third.</span></span> <span data-ttu-id="e3909-120">MTOM kann Binärdaten als unformatierte Bytes übertragen, spart dadurch die Zeit zum Codieren/Decodieren und erzeugt kleinere Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="e3909-120">MTOM is able to transmit binary data as raw bytes, saving the encoding/decoding time and resulting is smaller messages.</span></span> <span data-ttu-id="e3909-121">Der Schwellenwert von einigen Tausend Bytes ist verglichen mit heutigen Geschäftsdokumenten und Digitalfotos klein.</span><span class="sxs-lookup"><span data-stu-id="e3909-121">The threshold of a few thousand bytes is small when compared to today's business documents and digital photographs.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e3909-122">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="e3909-122">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e3909-123">Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="e3909-123">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="e3909-124">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="e3909-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="e3909-125">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e3909-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="e3909-126">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e3909-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
