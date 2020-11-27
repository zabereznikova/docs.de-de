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
# <a name="stream"></a>STREAM

Das Streambeispiel zeigt die Verwendung des Kommunikationsstream-Übertragungsmodus. Der Dienst macht mehrere Vorgänge verfügbar, die Streams senden und empfangen. Dieses Beispiel ist selbst gehostet. Sowohl der Client als auch der Dienst sind Konsolenprogramme.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Windows Communication Foundation (WCF) kann in zwei Übertragungsmodi kommunizieren – gepuffert oder Streaming. Im standardmäßigen gepufferten Übertragungsmodus müssen Nachrichten vollständig übertragen worden sein, bevor sie vom Empfänger gelesen werden können. Im Streaming-Übertragungsmodus kann der Empfänger mit der Verarbeitung der Nachricht beginnen, bevor diese vollständig übertragen wurde. Der Streamingmodus ist hilfreich, wenn die zu übergebenden Informationen sehr umfangreich sind und hintereinander verarbeitet werden können. Der Streamingmodus ist auch dann nützlich, wenn eine Nachricht zu groß ist, um als Ganzes gepuffert zu werden.  
  
## <a name="streaming-and-service-contracts"></a>Streaming und Dienstverträge  

 Streaming ist es wert, beim Entwerfen eines Dienstvertrags in Betracht gezogen zu werden. Wenn ein Vorgang Daten in großem Umfang empfängt oder zurückgibt, sollte man in Betracht ziehen, diese Daten zu streamen, um eine übermäßige Auslastung des Arbeitsspeichers durch das Puffern ein- oder ausgehender Nachrichten zu vermeiden. Zum Übertragen von Daten im Streamingmodus muss der Parameter, der die Daten enthält, der einzige Parameter in der Nachricht sein. Wenn beispielsweise die Eingabenachricht im Streamingmodus übertragen werden soll, muss der Vorgang genau einen Eingabeparameter haben. Ebenso gilt, wenn die Ausgabenachricht im Streamingmodus übertragen werden soll, muss der Vorgang entweder genau einen Ausgabeparameter oder einen Rückgabewert haben. In beiden Fällen muss der Parameter- oder Rückgabewerttyp `Stream`, `Message` oder `IXmlSerializable` sein. Nachfolgend ist der in diesem Streamingbeispiel verwendete Dienstvertrag aufgeführt.  
  
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
  
 Der `GetStream`-Vorgang empfängt Eingabedaten als Zeichenfolge, die gepuffert wird, und gibt einen `Stream` zurück, der im Streamingmodus übertragen wird. Umgekehrt nimmt `UploadStream` einen (per Streaming übertragenen) `Stream` entgegen und gibt einen (gepufferten) `bool` zurück. `EchoStream` akzeptiert und gibt einen Wert des Typs `Stream` zurück und ist ein Beispiel für einen Vorgang, dessen Eingabe- und Ausgabenachrichten per Streaming übertragen werden. `GetReversedStream` akzeptiert keine Eingaben und gibt einen `Stream`-Wert (im Streamingmodus) zurück.  
  
## <a name="enabling-streamed-transfers"></a>Aktivieren von Streamübertragungen  

 Wenn Sie Vorgangsverträge wie oben beschrieben definieren, können Sie Streaming auf Programmiermodellebene durchführen. Wenn Sie an dieser Stelle aufhören, wird immer noch der gesamte Nachrichteninhalt vom Transport gepuffert. Zum Aktivieren von Transportstreaming müssen Sie im Bindungselement des Transports einen Übertragungsmodus auswählen. Das Bindungselement weist eine `TransferMode`-Eigenschaft auf, die auf `Buffered`, `Streamed`, `StreamedRequest` oder `StreamedResponse` festgelegt werden kann. Wenn Sie den Übertragungsmodus auf `Streamed` festlegen, wird ein Kommunikationsstream in beide Richtungen ermöglicht. Wenn Sie den Übertragungsmodus auf `StreamedRequest` oder `StreamedResponse` festlegen, wird ein Kommunikationsstream nur in der jeweiligen Richtung (Anforderung bzw. Antwort) ermöglicht.  
  
 Die `basicHttpBinding` macht die `TransferMode`-Eigenschaft für die Bindung verfügbar, wie dies ebenso bei `NetTcpBinding` und `NetNamedPipeBinding` der Fall ist. Für andere Transporte müssen Sie eine benutzerdefinierte Bindung erstellen, um den Übertragungsmodus festzulegen.  
  
 Der folgende Konfigurationscode aus dem Beispiel zeigt, wie die `TransferMode`-Eigenschaft in der `basicHttpBinding` und eine benutzerdefinierte HTTP-Bindung auf den Streamingmodus festgelegt wird.  
  
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
  
 Zusätzlich zum Festlegen des `transferMode` auf `Streamed` legt der oben aufgeführte Konfigurationscode die `maxReceivedMessageSize` auf 64 MB fest. Als Schutzmechanismus legt `maxReceivedMessageSize` einen Höchstwert für die maximal zulässige Größe von Nachrichten beim Empfang fest. Die Standardeinstellung von `maxReceivedMessageSize` ist 64&#160;KB, was normalerweise zu niedrig für die Verwendung des Streamingmodus ist.  
  
## <a name="processing-data-as-it-is-streamed"></a>Verarbeiten von Daten bei deren Streamingübertragung  

 Bei den Vorgängen `GetStream`, `UploadStream` und `EchoStream` werden Daten direkt aus einer Datei gesendet oder empfangene Daten direkt in einer Datei gespeichert. In manchen Fällen ist es jedoch erforderlich, große Mengen von Daten zu senden oder zu empfangen und Teile dieser Daten dabei zu verarbeiten. Eine Möglichkeit in solchen Situationen wäre, einen benutzerdefinierten Stream (eine Klasse, die sich von <xref:System.IO.Stream> ableitet) zu schreiben, der Daten verarbeitet, während diese gelesen oder geschrieben werden. Der `GetReversedStream`-Vorgang und die `ReverseStream`-Klasse sind ein Beispiel für ein solches Vorgehen.  
  
 `GetReversedStream` erstellt eine neue Instanz der `ReverseStream`-Klasse und gibt eine Instanz dieser Klasse zurück. Die tatsächliche Verarbeitung erfolgt, wenn das System Daten aus diesem `ReverseStream`-Objekt liest. Die `ReverseStream.Read`-Implementierung liest eine Gruppe von Bytes aus der zugrunde liegenden Datei, invertiert die Reihenfolge der Bytes und gibt die invertierten Bytes zurück. Sie invertiert nicht den gesamten Dateiinhalt, sondern immer nur eine Gruppe von Bytes auf einmal. Dieses Beispiel zeigt, wie Sie das Verarbeiten eines Streams durchführen können, wenn der Inhalt aus dem Stream gelesen oder in den Stream geschrieben wird.  
  
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
  
## <a name="running-the-sample"></a>Ausführen des Beispiels  

 Zum Ausführen des Beispiels müssen Sie zuerst den Dienst und den Client nach den am Ende dieses Dokuments aufgeführten Anweisungen erstellen. Starten Sie dann den Dienst und den Client in zwei verschiedenen Konsolenfenstern. Beim Starten wartet der Client, dass Sie die EINGABETASTE drücken, wenn der Dienst bereit ist. Dann ruft der Client die Methoden `GetStream()`, `UploadStream()` und `GetReversedStream()` erst über HTTP und dann über TCP auf. Nachfolgend sehen Sie eine Beispielausgabe aus dem Dienst und dann eine Beispielausgabe aus dem Client:  
  
 Dienstausgabe:  
  
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
  
 Clientausgabe:  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
> [!NOTE]
> Wenn Sie zur Neugenerierung der Konfiguration für dieses Beispiel die Datei Svcutil.exe verwenden, müssen Sie den Endpunktnamen in der Clientkonfiguration so ändern, dass er mit dem Clientcode übereinstimmt.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Stream`  
