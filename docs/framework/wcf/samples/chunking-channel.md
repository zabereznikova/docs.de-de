---
title: Segmentierungskanal
ms.date: 03/30/2017
ms.assetid: e4d53379-b37c-4b19-8726-9cc914d5d39f
ms.openlocfilehash: 7a5e5292bcb37e83de21458716e34887a0557d91
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585544"
---
# <a name="chunking-channel"></a>Segmentierungskanal

Beim Senden großer Nachrichten mit Windows Communication Foundation (WCF) ist es häufig wünschenswert, die Menge an Arbeitsspeicher einzuschränken, die zum Puffern dieser Nachrichten verwendet wird. Eine mögliche Lösung besteht im Streamen des Nachrichtentexts (vorausgesetzt, der größte Teil der Daten befindet sich dort). Einige Protokolle erfordern jedoch die Pufferung der Nachricht als Ganzes. Zuverlässiges Messaging und Sicherheit sind zwei solche Beispiele. Eine weitere mögliche Lösung besteht darin, die große Nachricht in kleinere Nachrichten zu teilen, so genannte Segmente, diese Segmente jeweils einzeln zu senden und dann auf der Empfängerseite die große Nachricht wiederherzustellen. Die Anwendung selbst könnte diese Segmentierung und Desegmentierung vornehmen, oder es könnte alternativ ein benutzerdefinierter Kanal dafür verwendet werden. Das Beispiel für den Segmentierungskanal zeigt, wie mit einem benutzerdefinierten Protokollkanal oder Mehrschicht-Kanal das Segmentieren und Desegmentieren beliebig großer Nachrichten vorgenommen werden kann.

Die Segmentierung sollte stets nur dann eingesetzt werden, wenn die gesamte Nachricht, die gesendet werden soll, erstellt wurde. Ein Segmentierungskanal sollte immer unter einem Sicherheitskanal und einem zuverlässigen Sitzungskanal angeordnet sein.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ChunkingChannel`

## <a name="chunking-channel-assumptions-and-limitations"></a>Segmentierungskanal &#160; Voraussetzungen und Einschränkungen

### <a name="message-structure"></a>Nachrichtenstruktur

Der Segmentierungskanal geht bei zu segmentierenden Nachrichten von folgender Nachrichtenstruktur aus:

```xml
<soap:Envelope>
  <!-- headers -->
  <soap:Body>
    <operationElement>
      <paramElement>data to be chunked</paramElement>
    </operationElement>
  </soap:Body>
</soap:Envelope>
```

Bei Verwendung von ServiceModel erfüllen Vertragsvorgänge mit 1 Eingabeparameter diese Nachrichtenform bei ihrer Eingabenachricht. Ebenso erfüllen Vertragsvorgänge mit 1 Ausgabeparameter bzw. Rückgabewert diese Nachrichtenform bei ihrer Ausgabenachricht. Es folgen Beispiele für solche Vorgänge:

```csharp
[ServiceContract]
interface ITestService
{
    [OperationContract]
    Stream EchoStream(Stream stream);

    [OperationContract]
    Stream DownloadStream();

    [OperationContract(IsOneWay = true)]
    void UploadStream(Stream stream);
}
```

### <a name="sessions"></a>Sitzungen

Der Segmentierungskanal erfordert, dass Nachrichten genau einmal zugestellt werden, und zwar in geordneter Zustellung von Einzelnachrichten (Segmenten). Dies bedeutet, dass der zugrunde liegende Kanalstapel sitzungsbasiert sein muss. Sitzungen können vom Transport bereitgestellt werden (z.&#160;B. TCP-Transport) oder durch einen sitzungsbasierten Protokollkanal (z.&#160;B. ReliableSession-Kanal).

### <a name="asynchronous-send-and-receive"></a>Asynchrones Senden und Empfangen

Asynchrone Methoden zum Senden und Empfangen sind in dieser Version des Segmentierungskanalbeispiels nicht implementiert.

## <a name="chunking-protocol"></a>Segmentierungsprotokoll

Der Segmentierungskanal definiert ein Protokoll, das den Start und das Ende einer Segmentreihe sowie die laufende Nummer jedes Segments angibt. Die folgenden drei Beispielnachrichten veranschaulichen die Start-, Segmentierungs- und Endnachricht mit Kommentaren, in denen jeweils die wichtigsten Aspekte der einzelnen Elemente beschrieben werden.

### <a name="start-message"></a>Startnachricht

```xml
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
<!--Original message action is replaced with a chunking-specific action. -->
    <a:Action s:mustUnderstand="1">http://samples.microsoft.com/chunkingAction</a:Action>
<!--
Original message is assigned a unique id that is transmitted
in a MessageId header. Note that this is different from the WS-Addressing MessageId header.
-->
    <MessageId s:mustUnderstand="1" xmlns="http://samples.microsoft.com/chunking">
53f183ee-04aa-44a0-b8d3-e45224563109
</MessageId>
<!--
ChunkingStart header signals the start of a chunked message.
-->
    <ChunkingStart s:mustUnderstand="1" i:nil="true" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://samples.microsoft.com/chunking" />
<!--
Original message action is transmitted in OriginalAction.
This is required to re-create the original message on the other side.
-->
    <OriginalAction xmlns="http://samples.microsoft.com/chunking">
http://tempuri.org/ITestService/EchoStream
    </OriginalAction>
   <!--
    All original message headers are included here.
   -->
  </s:Header>
  <s:Body>
<!--
Chunking assumes this structure of Body content:
<element>
  <childelement>large data to be chunked<childelement>
</element>
The start message contains just <element> and <childelement> without
the data to be chunked.
-->
    <EchoStream xmlns="http://tempuri.org/">
      <stream />
    </EchoStream>
  </s:Body>
</s:Envelope>
```

### <a name="chunk-message"></a>Segmentierungsnachricht

```xml
<s:Envelope
  xmlns:a="http://www.w3.org/2005/08/addressing"
  xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
   <!--
    All chunking protocol messages have this action.
   -->
    <a:Action s:mustUnderstand="1">
      http://samples.microsoft.com/chunkingAction
    </a:Action>
<!--
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.
-->
    <MessageId s:mustUnderstand="1"
               xmlns="http://samples.microsoft.com/chunking">
      53f183ee-04aa-44a0-b8d3-e45224563109
    </MessageId>
<!--
The sequence number of the chunk.
This number restarts at 1 with each new sequence of chunks.
-->
    <ChunkNumber s:mustUnderstand="1"
                 xmlns="http://samples.microsoft.com/chunking">
      1096
    </ChunkNumber>
  </s:Header>
  <s:Body>
<!--
The chunked data is wrapped in a chunk element.
The encoding of this data (and the entire message)
depends on the encoder used. The chunking channel does not mandate an encoding.
-->
    <chunk xmlns="http://samples.microsoft.com/chunking">
kfSr2QcBlkHTvQ==
    </chunk>
  </s:Body>
</s:Envelope>
```

### <a name="end-message"></a>Endnachricht

```xml
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
    <a:Action s:mustUnderstand="1">
      http://samples.microsoft.com/chunkingAction
    </a:Action>
<!--
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.
-->
    <MessageId s:mustUnderstand="1"
               xmlns="http://samples.microsoft.com/chunking">
      53f183ee-04aa-44a0-b8d3-e45224563109
    </MessageId>
<!--
ChunkingEnd header signals the end of a chunk sequence.
-->
    <ChunkingEnd s:mustUnderstand="1" i:nil="true"
                 xmlns:i="http://www.w3.org/2001/XMLSchema-instance"
                 xmlns="http://samples.microsoft.com/chunking" />
<!--
ChunkingEnd messages have a sequence number.
-->
    <ChunkNumber s:mustUnderstand="1"
                 xmlns="http://samples.microsoft.com/chunking">
      79
    </ChunkNumber>
  </s:Header>
  <s:Body>
<!--
The ChunkingEnd message has the same <element><childelement> structure
as the ChunkingStart message.
-->
    <EchoStream xmlns="http://tempuri.org/">
      <stream />
    </EchoStream>
  </s:Body>
</s:Envelope>
```

## <a name="chunking-channel-architecture"></a>Segmentierungskanalarchitektur

Der Segmentierungskanal ist ein `IDuplexSessionChannel`, der im Allgemeinen der typischen Kanalarchitektur folgt. Es gibt ein `ChunkingBindingElement`, das eine `ChunkingChannelFactory` und einen `ChunkingChannelListener` erstellen kann. `ChunkingChannelFactory` erstellt auf Anforderung Instanzen von `ChunkingChannel`. `ChunkingChannelListener` erstellt Instanzen von `ChunkingChannel`, wenn ein neuer innerer Kanal akzeptiert wird. Der `ChunkingChannel` selbst ist für das Senden und Empfangen von Nachrichten verantwortlich.

Eine Ebene tiefer beruht `ChunkingChannel` für die Implementierung des Segmentierungsprotokolls auf mehreren Komponenten. Auf der Senderseite verwendet der Kanal einen benutzerdefinierten <xref:System.Xml.XmlDictionaryWriter>, den so genannten `ChunkingWriter`, der die eigentliche Segmentierung durchführt. `ChunkingWriter` verwendet den inneren Kanal direkt zum Senden von Segmenten. Durch die Verwendung eines benutzerdefinierten `XmlDictionaryWriter` können Segmente versendet werden, während der große Text der ursprünglichen Nachricht geschrieben wird. Dies bedeutet, dass nicht die gesamte ursprüngliche Nachricht gepuffert wird.

![Diagramm, das die Architektur des Segmentierungs Kanals anzeigt.](./media/chunking-channel/chunking-channel-send.gif)

Auf der Empfängerseite ruft `ChunkingChannel` Nachrichten aus dem inneren Kanal ab und gibt sie an einen benutzerdefinierten <xref:System.Xml.XmlDictionaryReader>, den so genannten `ChunkingReader` weiter, der die ursprüngliche Nachricht wieder aus den eingehenden Segmenten zusammensetzt. `ChunkingChannel` bindet diesen `ChunkingReader` in einer benutzerdefinierten `Message`-Implementierung, der so genannten `ChunkingMessage`, ein und gibt diese Nachricht an die darüberliegende Schicht zurück. Diese Kombination aus `ChunkingReader` und `ChunkingMessage` ermöglicht die Desegmentierung des ursprünglichen Nachrichtentexts, während dieser von der darüberliegenden Schicht gelesen wird. Es ist also nicht erforderlich, den gesamten Text der ursprünglichen Nachricht zu puffern. `ChunkingReader` enthält eine Warteschlange, in der die eingehenden Segmente bis zu der maximal konfigurierbaren Anzahl gepufferter Segmente gepuffert werden. Wenn diese Obergrenze erreicht ist, wartet der Leser, bis Nachrichten durch die darüberliegende Schicht aus der Warteschlange abfließen (d.&#160;h. einfach durch Lesen aus dem ursprünglichen Nachrichtentext) oder bis das maximale Empfangs-Timeout erreicht ist.

![Diagramm, das die Architektur des Segmentierungs Kanals anzeigt.](./media/chunking-channel/chunking-channel-receive.gif)

## <a name="chunking-programming-model"></a>Programmierungsmodell für die Segmentierung

Dienstentwickler können angeben, welche Nachrichten segmentiert werden sollen, indem sie das Attribut `ChunkingBehavior` auf Vorgänge innerhalb des Vertrags anwenden. Das Attribut macht eine `AppliesTo`-Eigenschaft verfügbar, mit der der Entwickler angeben kann, ob sich die Segmentierung auf die Eingabenachricht, die Ausgabenachricht oder auf beides bezieht. Im folgenden Beispiel wird die Verwendung des `ChunkingBehavior`-Attributs veranschaulicht.

```csharp
[ServiceContract]
interface ITestService
{
    [OperationContract]
    [ChunkingBehavior(ChunkingAppliesTo.Both)]
    Stream EchoStream(Stream stream);

    [OperationContract]
    [ChunkingBehavior(ChunkingAppliesTo.OutMessage)]
    Stream DownloadStream();

    [OperationContract(IsOneWay=true)]
    [ChunkingBehavior(ChunkingAppliesTo.InMessage)]
    void UploadStream(Stream stream);

}
```

Aus diesem Programmierungsmodell kompiliert `ChunkingBindingElement` eine Liste von Aktions-URIs, die die zu segmentierenden Nachrichten identifizieren. Die Aktion der einzelnen ausgehenden Nachrichten wird mit dieser Liste verglichen, um zu bestimmen, ob die Nachricht segmentiert oder direkt gesendet werden soll.

## <a name="implementing-the-send-operation"></a>Implementieren des Sendevorgangs

Allgemein gesagt überprüft der Sendevorgang zunächst, ob die ausgehende Nachricht segmentiert werden muss, und falls nicht, sendet sie die Nachricht direkt über den inneren Kanal.

Wenn die Nachricht segmentiert werden muss, erstellt Send einen neuen `ChunkingWriter` und ruft `WriteBodyContents` in der ausgehenden Nachricht auf, der sie diesen `ChunkingWriter` übergibt. Der `ChunkingWriter` nimmt dann die Nachrichtensegmentierung vor (dazu gehört das Kopieren der ursprünglichen Nachrichtenheaders in die Startsegmentnachricht) und sendet Segmente über den inneren Kanal.

Hier einige Details, die beachtet werden sollten:

- Send ruft zunächst `ThrowIfDisposedOrNotOpened` auf, um sicherzustellen, dass `CommunicationState` geöffnet ist.

- Das Senden wird synchronisiert, sodass für die einzelnen Sitzungen jeweils nicht mehrere Nachrichten gleichzeitig gesendet werden können. Es gibt einen `ManualResetEvent` namens `sendingDone`, der zurückgesetzt wird, wenn eine segmentierte Nachricht gesendet wird. Sobald die Endsegmentnachricht gesendet wurde, ist dieses Ereignis festgelegt. Die Send-Methode wartet, bis dieses Ereignis festgelegt ist, bevor sie versucht, die ausgehende Nachricht zu senden.

- Send sperrt `CommunicationObject.ThisLock`, um Änderungen am synchronisierten Zustand während des Sendens zu vermeiden. Weitere Informationen zu <xref:System.ServiceModel.Channels.CommunicationObject>-Zuständen und den Zustandsautomaten finden Sie in der <xref:System.ServiceModel.Channels.CommunicationObject>-Dokumentation.

- Der an Send übergebene Timeout dient als Timeout für den gesamten Sendevorgang, der das Senden aller Segmente umfasst.

- Der benutzerdefinierte <xref:System.Xml.XmlDictionaryWriter>-Entwurf wurde ausgewählt, um zu vermeiden, dass der gesamte Text der ursprünglichen Nachricht gepuffert wird. Wenn mithilfe von <xref:System.Xml.XmlDictionaryReader> ein `message.GetReaderAtBodyContents` für den Text verwendet würde, würde der gesamte Nachrichtentext gepuffert. Stattdessen verfügen wir über ein benutzerdefiniertes <xref:System.Xml.XmlDictionaryWriter> , das an die Übergabe erfolgt `message.WriteBodyContents` . Wenn die Nachricht WriteBase64 beim Writer aufruft, fasst der Writer Segmente zu Nachrichten zusammen und sendet sie über den inneren Kanal. WriteBase64 blockiert, bis das Segment gesendet wurde.

## <a name="implementing-the-receive-operation"></a>Implementieren des Empfangsvorgangs (Receive)

Allgemein gesagt stellt der Empfangsvorgang (Receive) zunächst sicher, dass die eingehende Nachricht nicht `null` und dass ihre Aktion `ChunkingAction` lautet. Wenn sie nicht beide Kriterien erfüllt, wird die Nachricht unverändert von Receive zurückgegeben. Andernfalls erstellt Receive einen neuen `ChunkingReader` und eine neue `ChunkingMessage`, die ihn umgibt (durch Aufrufen von `GetNewChunkingMessage`). Vor der Rückgabe dieser neuen `ChunkingMessage` führt Receive mithilfe eines Threadpool-Threads `ReceiveChunkLoop` aus, wodurch wiederum `innerChannel.Receive` in einer Schleife aufgerufen wird und Segmente an `ChunkingReader` übergeben werden, bis die Endsegmentnachricht empfangen oder der Receive-Timeout erreicht wird.

Hier einige Details, die beachtet werden sollten:

- Wie Send ruft auch Receive zunächst `ThrowIfDisposedOrNotOepned` auf, um sicherzustellen, dass `CommunicationState` geöffnet ist.

- Auch Receive wird synchronisiert, sodass aus der Sitzung nicht mehrere Nachrichten gleichzeitig empfangen werden können. Dies ist besonders wichtig, da nach dem Empfang einer Startsegmentnachricht davon ausgegangen wird, dass alle anschließend empfangenen Nachrichten Segmente innerhalb dieser neuen Segmentsequenz sind, bis eine Endsegmentnachricht empfangen wird. Receive kann so lange keine Nachrichten mithilfe von Pull aus dem inneren Kanal übertragen, bis alle Segmente, die zu der Nachricht gehören, die momentan wieder aus ihren Segmenten zusammengesetzt wird, empfangen wurden. Um dies zu erreichen, verwendet Receive ein `ManualResetEvent` namens `currentMessageCompleted`, das beim Empfang der Endsegmentnachricht festgelegt und beim Empfang einer neuen Startsegmentnachricht zurückgesetzt wird.

- Im Gegensatz zu Send verhindert Receive während des Empfangs keine Zustandsübergänge bei synchronisierten Zuständen. So kann beispielsweise Close während des Empfangs aufgerufen werden. Der Vorgang wartet dann, bis der ausstehende Empfang der ursprünglichen Nachricht abgeschlossen bzw. der angegebene Timeoutwert erreicht ist.

- Der an Receive übergebene Timeout dient als Timeout für den gesamten Empfangsvorgang, der den Empfang aller Segmente umfasst.

- Wenn die Schicht, die die Nachricht verwendet, den Nachrichtentext langsamer verwendet als Segmentnachrichten eintreffen, puffert `ChunkingReader` die eingehenden Segmente bis zu der von `ChunkingBindingElement.MaxBufferedChunks` angegebenen Obergrenze. Nachdem dieser Grenzwert erreicht wurde, werden erst dann wieder Segmente mithilfe von Pull aus der unteren Schicht übertragen, wenn entweder ein gepuffertes Segment verwendet oder der Empfangs-Timeout erreicht wurde.

## <a name="communicationobject-overrides"></a>CommunicationObject-Überschreibungen

### <a name="onopen"></a>OnOpen

`OnOpen` ruft `innerChannel.Open` auf, um den inneren Kanal zu öffnen.

### <a name="onclose"></a>OnClose

`OnClose` legt zuerst `stopReceive` auf `true` fest, um zu signalisieren, dass der ausstehende`ReceiveChunkLoop` beendet werden soll. Er wartet dann auf das `receiveStopped` <xref:System.Threading.ManualResetEvent> , das festgelegt wird, wenn `ReceiveChunkLoop` beendet wird. Angenommen, `ReceiveChunkLoop` wird innerhalb des angegebenen Timeouts beendet, dann ruft `OnClose` mit dem restlichen Timeout `innerChannel.Close` auf.

### <a name="onabort"></a>OnAbort

`OnAbort` ruft `innerChannel.Abort` auf, um den inneren Kanal abzubrechen. Wenn es einen ausstehenden `ReceiveChunkLoop` gibt, erhält diese eine Ausnahme vom ausstehenden `innerChannel.Receive`-Aufruf.

### <a name="onfaulted"></a>OnFaulted

Der `ChunkingChannel` erfordert kein besonderes Verhalten, wenn der Kanal einen Fehler verursacht hat, sodass `OnFaulted` nicht überschrieben wird.

## <a name="implementing-channel-factory"></a>Implementieren einer Kanalfactory

Der `ChunkingChannelFactory` ist dafür zuständig, Instanzen von `ChunkingDuplexSessionChannel` zu erstellen und Zustandsübergänge an die innere Kanalfactory weiterzugeben.

`OnCreateChannel` verwendet die innere Kanalfactory zur Erstellung eines inneren `IDuplexSessionChannel`-Kanals. Anschließend erstellt es einen neuen `ChunkingDuplexSessionChannel`, dem sie beim Empfang diesen inneren Kanal sowie die Liste der zu segmentierenden Nachrichtenaktionen und die maximale Anzahl der zu puffernden Segmente übergibt. Die Liste der zu segmentierenden Nachrichtenaktionen und die maximale Anzahl der zu puffernden Segmente sind zwei Parameter, die im Konstruktor an `ChunkingChannelFactory` weitergegeben werden. Im Abschnitt über `ChunkingBindingElement` wird beschrieben, woher diese Werte kommen.

`OnOpen`, `OnClose`, `OnAbort` und ihre asynchronen Entsprechungen rufen die entsprechende Zustandsübergangsmethode in der inneren Kanalfactory auf.

## <a name="implementing-channel-listener"></a>Implementieren eines Kanallisteners

Der `ChunkingChannelListener` ist ein Wrapper um einen inneren Kanallistener. Neben dem Delegieren von Aufrufen an diesen inneren Kanallistener besteht seine Hauptaufgabe darin, neue `ChunkingDuplexSessionChannels` um Kanäle zu legen, die aus dem inneren Kanallistener akzeptiert wurden. Dies erfolgt in `OnAcceptChannel` und `OnEndAcceptChannel`. Dem neu erstellten `ChunkingDuplexSessionChannel` wird der innere Kanal, zusammen mit den anderen, bereits beschriebenen Parametern, übergeben.

## <a name="implementing-binding-element-and-binding"></a>Implementieren von Bindungselement und Bindung

`ChunkingBindingElement` ist für das Erstellen der `ChunkingChannelFactory` und des `ChunkingChannelListener` verantwortlich. Der `ChunkingBindingElement` überprüft, ob T in `CanBuildChannelFactory` \<T> und `CanBuildChannelListener` \<T> vom Typ ist `IDuplexSessionChannel` (der einzige Kanal, der vom Segmentierungs Kanal unterstützt wird) und ob die anderen Bindungs Elemente der Bindung diesen Kanaltyp unterstützen.

`BuildChannelFactory`\<T>prüft zunächst, ob der angeforderte Kanaltyp erstellt werden kann, und ruft anschließend eine Liste der zu segmentierenden Nachrichten Aktionen ab. Weitere Informationen finden Sie im folgenden Abschnitt. Anschließend erstellt es einen neuen `ChunkingChannelFactory`, dem es die innere Kanalfactory (wie aus `context.BuildInnerChannelFactory<IDuplexSessionChannel>` zurückgegeben), die Liste der Nachrichtenaktionen und die maximale Anzahl der beim Empfang zu puffernden Segmente übergibt. Die maximale Anzahl an Segmenten stammt aus einer Eigenschaft namens `MaxBufferedChunks`, die vom `ChunkingBindingElement` verfügbar gemacht wird.

`BuildChannelListener<T>` hat zum Erstellen von `ChunkingChannelListener` und zur Übergabe an den inneren Kanallistener eine ähnliche Implementierung.

In diesem Beispiel ist eine Beispielbindung namens `TcpChunkingBinding` enthalten. Diese Bindung besteht aus zwei Bindungselementen: `TcpTransportBindingElement` und `ChunkingBindingElement`. Die Bindung macht nicht nur die Eigenschaft `MaxBufferedChunks` verfügbar, sondern legt auch einige der `TcpTransportBindingElement`-Eigenschaften fest, wie beispielsweise `MaxReceivedMessageSize` (wird auf `ChunkingUtils.ChunkSize` + 100 KB für Header festgelegt).

`TcpChunkingBinding` implementiert außerdem `IBindingRuntimePreferences` und gibt den Wert true aus der `ReceiveSynchronously`-Methode zurück, was anzeigt, dass nur die synchronen Receive-Aufrufe implementiert werden.

### <a name="determining-which-messages-to-chunk"></a>Bestimmen der zu segmentierenden Nachrichten

Der Segmentierungskanal segmentiert nur die Nachrichten, die über das `ChunkingBehavior`-Attribut identifiziert wurden. Die `ChunkingBehavior`-Klasse implementiert `IOperationBehavior` und wird durch Aufrufen der `AddBindingParameter`-Methode implementiert. In dieser Methode untersucht `ChunkingBehavior` den Wert dieser `AppliesTo`-Eigenschaft (`InMessage`, `OutMessage` oder beides), um zu bestimmen, welche Nachrichten segmentiert werden sollen. Anschließend ruft es die Aktion jeder diese Nachrichten ab (aus der Nachrichtenauflistung unter `OperationDescription`) und fügt sie einer Zeichenfolgenauflistung hinzu, die in einer Instanz von `ChunkingBindingParameter` enthalten ist. Anschließend wird dieser `ChunkingBindingParameter` der angegebenen `BindingParameterCollection` hinzugefügt.

Diese `BindingParameterCollection` wird innerhalb von `BindingContext` an die einzelnen Bindungselemente in der Bindung übergeben, wenn das betreffende Bindungselement die Kanalfactory oder den Kanallistener erstellt. Die `ChunkingBindingElement` -Implementierung von `BuildChannelFactory<T>` und `BuildChannelListener<T>` ruft diese `ChunkingBindingParameter` aus den `BindingContext’` s ab `BindingParameterCollection` . Die Auflistung der in `ChunkingBindingParameter` enthaltenen Aktionen wird anschließend an `ChunkingChannelFactory` oder `ChunkingChannelListener` übergeben, von wo aus sie wiederum an `ChunkingDuplexSessionChannel` übergeben wird.

## <a name="running-the-sample"></a>Ausführen des Beispiels

#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

3. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.

4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).

5. Führen Sie zuerst Service.exe und dann Client.exe aus, und sehen Sie sich die Ausgabe in beiden Konsolenfenstern an.

Beim Ausführen des Beispiels sollte die Ausgabe wie folgt aussehen.

Client:

```console
Press enter when service is available

 > Sent chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd
```

Server: 

```console
Service started, press enter to exit
 < Received chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd
```
