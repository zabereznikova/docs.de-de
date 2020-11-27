---
title: Datenstrom
ms.date: 03/30/2017
ms.assetid: 58a3db81-20ab-4627-bf31-39d30b70b4fe
ms.openlocfilehash: 04bc5db4172d9052b45f63a2f7ed0fb997dc4c6c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257196"
---
# <a name="stream"></a><span data-ttu-id="0b31c-102">STREAM</span><span class="sxs-lookup"><span data-stu-id="0b31c-102">Stream</span></span>

<span data-ttu-id="0b31c-103">Das Streambeispiel zeigt die Verwendung des Kommunikationsstream-Übertragungsmodus.</span><span class="sxs-lookup"><span data-stu-id="0b31c-103">The Stream sample demonstrates the use of streaming transfer mode communication.</span></span> <span data-ttu-id="0b31c-104">Der Dienst macht mehrere Vorgänge verfügbar, die Streams senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="0b31c-104">The service exposes several operations that send and receive streams.</span></span> <span data-ttu-id="0b31c-105">Dieses Beispiel ist selbst gehostet.</span><span class="sxs-lookup"><span data-stu-id="0b31c-105">This sample is self-hosted.</span></span> <span data-ttu-id="0b31c-106">Sowohl der Client als auch der Dienst sind Konsolenprogramme.</span><span class="sxs-lookup"><span data-stu-id="0b31c-106">Both the client and service are console programs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b31c-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="0b31c-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="0b31c-108">Windows Communication Foundation (WCF) kann in zwei Übertragungsmodi kommunizieren – gepuffert oder Streaming.</span><span class="sxs-lookup"><span data-stu-id="0b31c-108">Windows Communication Foundation (WCF) can communicate in two transfer modes—buffered or streaming.</span></span> <span data-ttu-id="0b31c-109">Im standardmäßigen gepufferten Übertragungsmodus müssen Nachrichten vollständig übertragen worden sein, bevor sie vom Empfänger gelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="0b31c-109">In the default buffered transfer mode, a message must be completely delivered before a receiver can read it.</span></span> <span data-ttu-id="0b31c-110">Im Streaming-Übertragungsmodus kann der Empfänger mit der Verarbeitung der Nachricht beginnen, bevor diese vollständig übertragen wurde.</span><span class="sxs-lookup"><span data-stu-id="0b31c-110">In the streaming transfer mode, the receiver can begin to process the message before it is completely delivered.</span></span> <span data-ttu-id="0b31c-111">Der Streamingmodus ist hilfreich, wenn die zu übergebenden Informationen sehr umfangreich sind und hintereinander verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="0b31c-111">The streaming mode is useful when the information that is passed is lengthy and can be processed serially.</span></span> <span data-ttu-id="0b31c-112">Der Streamingmodus ist auch dann nützlich, wenn eine Nachricht zu groß ist, um als Ganzes gepuffert zu werden.</span><span class="sxs-lookup"><span data-stu-id="0b31c-112">Streaming mode is also useful when the message is too large to be entirely buffered.</span></span>  
  
## <a name="streaming-and-service-contracts"></a><span data-ttu-id="0b31c-113">Streaming und Dienstverträge</span><span class="sxs-lookup"><span data-stu-id="0b31c-113">Streaming and Service Contracts</span></span>  

 <span data-ttu-id="0b31c-114">Streaming ist es wert, beim Entwerfen eines Dienstvertrags in Betracht gezogen zu werden.</span><span class="sxs-lookup"><span data-stu-id="0b31c-114">Streaming is something to be considered when designing a service contract.</span></span> <span data-ttu-id="0b31c-115">Wenn ein Vorgang Daten in großem Umfang empfängt oder zurückgibt, sollte man in Betracht ziehen, diese Daten zu streamen, um eine übermäßige Auslastung des Arbeitsspeichers durch das Puffern ein- oder ausgehender Nachrichten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="0b31c-115">If an operation receives or returns large amounts of data, you should consider streaming this data to avoid high memory utilization due to buffering of input or output messages.</span></span> <span data-ttu-id="0b31c-116">Zum Übertragen von Daten im Streamingmodus muss der Parameter, der die Daten enthält, der einzige Parameter in der Nachricht sein.</span><span class="sxs-lookup"><span data-stu-id="0b31c-116">To stream data, the parameter that holds that data must be the only parameter in the message.</span></span> <span data-ttu-id="0b31c-117">Wenn beispielsweise die Eingabenachricht im Streamingmodus übertragen werden soll, muss der Vorgang genau einen Eingabeparameter haben.</span><span class="sxs-lookup"><span data-stu-id="0b31c-117">For example, if the input message is the one to be streamed, the operation must have exactly one input parameter.</span></span> <span data-ttu-id="0b31c-118">Ebenso gilt, wenn die Ausgabenachricht im Streamingmodus übertragen werden soll, muss der Vorgang entweder genau einen Ausgabeparameter oder einen Rückgabewert haben.</span><span class="sxs-lookup"><span data-stu-id="0b31c-118">Similarly, if the output message is to be streamed, the operation must have either exactly one output parameter or a return value.</span></span> <span data-ttu-id="0b31c-119">In beiden Fällen muss der Parameter- oder Rückgabewerttyp `Stream`, `Message` oder `IXmlSerializable` sein.</span><span class="sxs-lookup"><span data-stu-id="0b31c-119">In either case, the parameter or return value type must be either `Stream`, `Message`, or `IXmlSerializable`.</span></span> <span data-ttu-id="0b31c-120">Nachfolgend ist der in diesem Streamingbeispiel verwendete Dienstvertrag aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0b31c-120">The following is the service contract used in this streaming sample.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IStreamingSample  
{  
    [OperationContract]  
    Stream GetStream(string data);  
    [OperationContract]  
    bool UploadStream(Stream stream);  
    [OperationContract]  
    Stream EchoStream(Stream stream);  
    [OperationContract]  
    Stream GetReversedStream();  
  
}  
```  
  
 <span data-ttu-id="0b31c-121">Der `GetStream`-Vorgang empfängt Eingabedaten als Zeichenfolge, die gepuffert wird, und gibt einen `Stream` zurück, der im Streamingmodus übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="0b31c-121">The `GetStream` operation receives some input data as a string, which is buffered, and returns a `Stream`, which is streamed.</span></span> <span data-ttu-id="0b31c-122">Umgekehrt nimmt `UploadStream` einen (per Streaming übertragenen) `Stream` entgegen und gibt einen (gepufferten) `bool` zurück.</span><span class="sxs-lookup"><span data-stu-id="0b31c-122">Conversely, `UploadStream` takes in a `Stream` (streamed) and returns a `bool` (buffered).</span></span> <span data-ttu-id="0b31c-123">`EchoStream` akzeptiert und gibt einen Wert des Typs `Stream` zurück und ist ein Beispiel für einen Vorgang, dessen Eingabe- und Ausgabenachrichten per Streaming übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="0b31c-123">`EchoStream` takes and returns `Stream` and is an example of an operation whose input and output messages are both streamed.</span></span> <span data-ttu-id="0b31c-124">`GetReversedStream` akzeptiert keine Eingaben und gibt einen `Stream`-Wert (im Streamingmodus) zurück.</span><span class="sxs-lookup"><span data-stu-id="0b31c-124">Finally, `GetReversedStream` takes no inputs and returns a `Stream` (streamed).</span></span>  
  
## <a name="enabling-streamed-transfers"></a><span data-ttu-id="0b31c-125">Aktivieren von Streamübertragungen</span><span class="sxs-lookup"><span data-stu-id="0b31c-125">Enabling Streamed Transfers</span></span>  

 <span data-ttu-id="0b31c-126">Wenn Sie Vorgangsverträge wie oben beschrieben definieren, können Sie Streaming auf Programmiermodellebene durchführen.</span><span class="sxs-lookup"><span data-stu-id="0b31c-126">Defining operation contracts as previously described provides streaming at the programming model level.</span></span> <span data-ttu-id="0b31c-127">Wenn Sie an dieser Stelle aufhören, wird immer noch der gesamte Nachrichteninhalt vom Transport gepuffert.</span><span class="sxs-lookup"><span data-stu-id="0b31c-127">If you stop there, the transport still buffers the entire message content.</span></span> <span data-ttu-id="0b31c-128">Zum Aktivieren von Transportstreaming müssen Sie im Bindungselement des Transports einen Übertragungsmodus auswählen.</span><span class="sxs-lookup"><span data-stu-id="0b31c-128">To enable transport streaming, select a transfer mode on the binding element of the transport.</span></span> <span data-ttu-id="0b31c-129">Das Bindungselement weist eine `TransferMode`-Eigenschaft auf, die auf `Buffered`, `Streamed`, `StreamedRequest` oder `StreamedResponse` festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0b31c-129">The binding element has a `TransferMode` property that can be set to `Buffered`, `Streamed`, `StreamedRequest`, or `StreamedResponse`.</span></span> <span data-ttu-id="0b31c-130">Wenn Sie den Übertragungsmodus auf `Streamed` festlegen, wird ein Kommunikationsstream in beide Richtungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="0b31c-130">Setting the transfer mode to `Streamed` enables streaming communication in both directions.</span></span> <span data-ttu-id="0b31c-131">Wenn Sie den Übertragungsmodus auf `StreamedRequest` oder `StreamedResponse` festlegen, wird ein Kommunikationsstream nur in der jeweiligen Richtung (Anforderung bzw. Antwort) ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="0b31c-131">Setting the transfer mode to `StreamedRequest` or `StreamedResponse` enables streaming communication in only the request or response, respectively.</span></span>  
  
 <span data-ttu-id="0b31c-132">Die `basicHttpBinding` macht die `TransferMode`-Eigenschaft für die Bindung verfügbar, wie dies ebenso bei `NetTcpBinding` und `NetNamedPipeBinding` der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="0b31c-132">The `basicHttpBinding` exposes the `TransferMode` property on the binding as does `NetTcpBinding` and `NetNamedPipeBinding`.</span></span> <span data-ttu-id="0b31c-133">Für andere Transporte müssen Sie eine benutzerdefinierte Bindung erstellen, um den Übertragungsmodus festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0b31c-133">For other transports, you must create a custom binding to set the transfer mode.</span></span>  
  
 <span data-ttu-id="0b31c-134">Der folgende Konfigurationscode aus dem Beispiel zeigt, wie die `TransferMode`-Eigenschaft in der `basicHttpBinding` und eine benutzerdefinierte HTTP-Bindung auf den Streamingmodus festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="0b31c-134">The following configuration code from the sample shows setting the `TransferMode` property to streaming on the `basicHttpBinding` and a custom HTTP binding:</span></span>  
  
```xml  
<!-- An example basicHttpBinding using streaming. -->  
<basicHttpBinding>  
  <binding name="HttpStreaming" maxReceivedMessageSize="67108864"  
           transferMode="Streamed"/>  
</basicHttpBinding>  
<!-- An example customBinding using HTTP and streaming.-->  
<customBinding>  
  <binding name="Soap12">  
    <textMessageEncoding messageVersion="Soap12WSAddressing10" />  
    <httpTransport transferMode="Streamed"  
                   maxReceivedMessageSize="67108864"/>  
  </binding>  
</customBinding>  
```  
  
 <span data-ttu-id="0b31c-135">Zusätzlich zum Festlegen des `transferMode` auf `Streamed` legt der oben aufgeführte Konfigurationscode die `maxReceivedMessageSize` auf 64 MB fest.</span><span class="sxs-lookup"><span data-stu-id="0b31c-135">In addition to setting the `transferMode` to `Streamed`, the previous configuration code sets the `maxReceivedMessageSize` to 64MB.</span></span> <span data-ttu-id="0b31c-136">Als Schutzmechanismus legt `maxReceivedMessageSize` einen Höchstwert für die maximal zulässige Größe von Nachrichten beim Empfang fest.</span><span class="sxs-lookup"><span data-stu-id="0b31c-136">As a defense mechanism, `maxReceivedMessageSize` places a cap on the maximum allowable size of messages on receive.</span></span> <span data-ttu-id="0b31c-137">Die Standardeinstellung von `maxReceivedMessageSize` ist 64&#160;KB, was normalerweise zu niedrig für die Verwendung des Streamingmodus ist.</span><span class="sxs-lookup"><span data-stu-id="0b31c-137">The default `maxReceivedMessageSize` is 64 KB, which is usually too low for streaming scenarios.</span></span>  
  
## <a name="processing-data-as-it-is-streamed"></a><span data-ttu-id="0b31c-138">Verarbeiten von Daten bei deren Streamingübertragung</span><span class="sxs-lookup"><span data-stu-id="0b31c-138">Processing Data As It Is Streamed</span></span>  

 <span data-ttu-id="0b31c-139">Bei den Vorgängen `GetStream`, `UploadStream` und `EchoStream` werden Daten direkt aus einer Datei gesendet oder empfangene Daten direkt in einer Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0b31c-139">The operations `GetStream`, `UploadStream` and `EchoStream` all deal with sending data directly from a file or saving received data directly to a file.</span></span> <span data-ttu-id="0b31c-140">In manchen Fällen ist es jedoch erforderlich, große Mengen von Daten zu senden oder zu empfangen und Teile dieser Daten dabei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0b31c-140">However in some cases, there is a requirement to send or receive large amounts of data and perform some processing on chunks of the data as it is being sent or received.</span></span> <span data-ttu-id="0b31c-141">Eine Möglichkeit in solchen Situationen wäre, einen benutzerdefinierten Stream (eine Klasse, die sich von <xref:System.IO.Stream> ableitet) zu schreiben, der Daten verarbeitet, während diese gelesen oder geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0b31c-141">One way to address such scenarios is to write a custom stream (a class that derives from <xref:System.IO.Stream>) that processes data as it is read or written.</span></span> <span data-ttu-id="0b31c-142">Der `GetReversedStream`-Vorgang und die `ReverseStream`-Klasse sind ein Beispiel für ein solches Vorgehen.</span><span class="sxs-lookup"><span data-stu-id="0b31c-142">The `GetReversedStream` operation and `ReverseStream` class are an example of this.</span></span>  
  
 <span data-ttu-id="0b31c-143">`GetReversedStream` erstellt eine neue Instanz der `ReverseStream`-Klasse und gibt eine Instanz dieser Klasse zurück.</span><span class="sxs-lookup"><span data-stu-id="0b31c-143">`GetReversedStream` creates and returns a new instance of `ReverseStream`.</span></span> <span data-ttu-id="0b31c-144">Die tatsächliche Verarbeitung erfolgt, wenn das System Daten aus diesem `ReverseStream`-Objekt liest.</span><span class="sxs-lookup"><span data-stu-id="0b31c-144">The actual processing happens as the system reads from that `ReverseStream` object.</span></span> <span data-ttu-id="0b31c-145">Die `ReverseStream.Read`-Implementierung liest eine Gruppe von Bytes aus der zugrunde liegenden Datei, invertiert die Reihenfolge der Bytes und gibt die invertierten Bytes zurück.</span><span class="sxs-lookup"><span data-stu-id="0b31c-145">The `ReverseStream.Read` implementation reads a chunk of bytes from the underlying file, reverses them, then returns the reversed bytes.</span></span> <span data-ttu-id="0b31c-146">Sie invertiert nicht den gesamten Dateiinhalt, sondern immer nur eine Gruppe von Bytes auf einmal.</span><span class="sxs-lookup"><span data-stu-id="0b31c-146">This does not reverse the entire file content; it reverses one chunk of bytes at a time.</span></span> <span data-ttu-id="0b31c-147">Dieses Beispiel zeigt, wie Sie das Verarbeiten eines Streams durchführen können, wenn der Inhalt aus dem Stream gelesen oder in den Stream geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="0b31c-147">This is an example to show how you can perform stream processing as the content is being read or written from and to the stream.</span></span>  
  
```csharp
class ReverseStream : Stream  
{  
  
    FileStream inStream;  
    internal ReverseStream(string filePath)  
    {  
        //Opens the file and places a StreamReader around it.  
        inStream = File.OpenRead(filePath);  
    }  
  
    // Other methods removed for brevity.  
  
    public override int Read(byte[] buffer, int offset, int count)  
    {  
        int countRead=inStream.Read(buffer, offset,count);  
        ReverseBuffer(buffer, offset, countRead);  
        return countRead;  
    }  
  
    public override void Close()  
    {  
        inStream.Close();  
        base.Close();  
    }  
    protected override void Dispose(bool disposing)  
    {  
        inStream.Dispose();  
        base.Dispose(disposing);  
    }  
    void ReverseBuffer(byte[] buffer, int offset, int count)  
    {  
        int i, j;  
        for (i = offset, j = offset + count - 1; i < j; i++, j--)  
        {  
            byte currenti = buffer[i];  
            buffer[i] = buffer[j];  
            buffer[j] = currenti;  
        }  
  
    }  
}  
```  
  
## <a name="running-the-sample"></a><span data-ttu-id="0b31c-148">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="0b31c-148">Running the Sample</span></span>  

 <span data-ttu-id="0b31c-149">Zum Ausführen des Beispiels müssen Sie zuerst den Dienst und den Client nach den am Ende dieses Dokuments aufgeführten Anweisungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="0b31c-149">To run the sample, first build both the service and the client by following the directions at the end of this document.</span></span> <span data-ttu-id="0b31c-150">Starten Sie dann den Dienst und den Client in zwei verschiedenen Konsolenfenstern.</span><span class="sxs-lookup"><span data-stu-id="0b31c-150">Then start the service and the client in two different console windows.</span></span> <span data-ttu-id="0b31c-151">Beim Starten wartet der Client, dass Sie die EINGABETASTE drücken, wenn der Dienst bereit ist.</span><span class="sxs-lookup"><span data-stu-id="0b31c-151">When the client starts, it waits for you to press ENTER when the service is ready.</span></span> <span data-ttu-id="0b31c-152">Dann ruft der Client die Methoden `GetStream()`, `UploadStream()` und `GetReversedStream()` erst über HTTP und dann über TCP auf.</span><span class="sxs-lookup"><span data-stu-id="0b31c-152">The client then calls the methods `GetStream()`, `UploadStream()` and `GetReversedStream()` first over HTTP and then over TCP.</span></span> <span data-ttu-id="0b31c-153">Nachfolgend sehen Sie eine Beispielausgabe aus dem Dienst und dann eine Beispielausgabe aus dem Client:</span><span class="sxs-lookup"><span data-stu-id="0b31c-153">Here is an example output from the service followed by example output from the client:</span></span>  
  
 <span data-ttu-id="0b31c-154">Dienstausgabe:</span><span class="sxs-lookup"><span data-stu-id="0b31c-154">Service Output:</span></span>  
  
```console  
The streaming service is ready.  
Press <ENTER> to terminate service.  
  
Saving to file D:\...\uploadedfile  
......................  
File D:\...\uploadedfile saved  
Saving to file D:\...\uploadedfile  
...............  
File D:\...\uploadedfile saved  
```  
  
 <span data-ttu-id="0b31c-155">Clientausgabe:</span><span class="sxs-lookup"><span data-stu-id="0b31c-155">Client Output:</span></span>  
  
```console  
Press <ENTER> when service is ready  
------ Using HTTP ------
Calling GetStream()  
Saving to file D:\...\clientfile  
......................  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
Calling UploadStream()  
Calling GetReversedStream()  
Saving to file D:\...\clientfile  
......................  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
------ Using Custom HTTP ------  
Calling GetStream()  
Saving to file D:\...\clientfile  
...............  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
Calling UploadStream()  
Calling GetReversedStream()  
Saving to file D:\...\clientfile  
...............  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0b31c-156">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="0b31c-156">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0b31c-157">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="0b31c-157">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0b31c-158">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="0b31c-158">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="0b31c-159">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0b31c-159">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b31c-160">Wenn Sie zur Neugenerierung der Konfiguration für dieses Beispiel die Datei Svcutil.exe verwenden, müssen Sie den Endpunktnamen in der Clientkonfiguration so ändern, dass er mit dem Clientcode übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="0b31c-160">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0b31c-161">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="0b31c-161">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0b31c-162">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0b31c-162">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="0b31c-163">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0b31c-163">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0b31c-164">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0b31c-164">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Stream`  
