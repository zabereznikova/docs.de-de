---
title: 'Vorgehensweise: Aktivieren des Streamingmodus'
description: Erfahren Sie, wie Sie per Streaming übertragene Nachrichten in WCF anstelle der standardmäßigen gepufferten Übertragungen aktivieren, die vor der Verarbeitung vollständig empfangen werden müssen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6ca2cf4b-c7a1-49d8-a79b-843a90556ba4
ms.openlocfilehash: 7f77c406e1cfd4def116a1abe24aa92be74c6abe
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237741"
---
# <a name="how-to-enable-streaming"></a>Vorgehensweise: Aktivieren des Streamingmodus

Windows Communication Foundation (WCF) kann Nachrichten mit gepufferten oder Streamingübertragungen senden. Im voreingestellten gepufferten Übertragungsmodus müssen Nachrichten vollständig übertragen worden sein, bevor sie vom Empfänger gelesen werden können. Im Streamingmodus kann der Empfänger mit der Verarbeitung der Nachricht beginnen, bevor diese vollständig übertragen wurde. Der Streamingmodus ist hilfreich, wenn die zu übergebenden Informationen sehr umfangreich sind und hintereinander verarbeitet werden können. Der Streamingmodus ist auch dann nützlich, wenn eine Nachricht zu groß ist, um als Ganzes gepuffert zu werden.  
  
 Um den Streamingmodus zu aktivieren, definieren Sie den `OperationContract` angemessen, und aktivieren Sie den Streamingmodus auf Transportebene.  
  
### <a name="to-stream-data"></a>So werden Daten im Streamingmodus übertragen  
  
1. Damit Daten im Streamingmodus übermittelt werden können, muss der `OperationContract` für den Dienst zwei Anforderungen erfüllen:  
  
    1. Der Parameter, der die zu übermittelten Daten enthält, muss der einzige Parameter der Methode sein. Wenn beispielsweise die Eingabenachricht im Streamingmodus übertragen werden soll, muss der Vorgang genau einen Eingabeparameter haben. Ebenso gilt, wenn die Ausgabenachricht im Streamingmodus übertragen werden soll, muss der Vorgang entweder genau einen Ausgabeparameter oder einen Rückgabewert haben.  
  
    2. Mindestens einer der Parameter bzw. der Rückgabewert muss vom Typ <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message> oder <xref:System.Xml.Serialization.IXmlSerializable> sein  
  
     Das folgende Beispiel enthält einen Vertrag für im Streamingmodus zu übertragende Daten.  
  
     [!code-csharp[c_HowTo_EnableStreaming#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#1)]
     [!code-vb[c_HowTo_EnableStreaming#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#1)]  
  
     Der `GetStream`-Vorgang muss gepufferte Eingabedaten des Typs `string` erhalten, die dann gepuffert werden, und er gibt einen `Stream`-Wert zurück, der im Streamingmodus übertragen wird. Umgekehrt akzeptiert `UploadStream` einen (per Streaming übertragenen) `Stream` und gibt einen (gepufferten) `bool` zurück. `EchoStream` akzeptiert und gibt einen Wert des Typs `Stream` zurück und ist ein Beispiel für einen Vorgang, dessen Eingabe- und Ausgabenachrichten per Streaming übertragen werden. `GetReversedStream` akzeptiert keine Eingaben und gibt einen `Stream`-Wert (im Streamingmodus) zurück.  
  
2. Der Streamingmodus muss für die Bindung aktiviert werden. Sie legen eine `TransferMode`-Eigenschaft fest, für die die folgenden Werte zulässig sind:  
  
    1. `Buffered`,  
  
    2. `Streamed`, womit ein Kommunikationsstream in beide Richtungen ermöglicht wird.  
  
    3. `StreamedRequest`, womit der Streamingmodus lediglich für die Übertragung der Anforderung aktiviert wird.  
  
    4. `StreamedResponse`, womit der Streamingmodus lediglich für die Übertragung der Antwort aktiviert wird.  
  
     Die `BasicHttpBinding`-Bindung macht die `TransferMode`-Eigenschaft für die Bindung verfügbar. Dies gilt ebenso für `NetTcpBinding` und `NetNamedPipeBinding`. Die `TransferMode`-Eigenschaft kann auch für das Transportbindungselement festgelegt und in einer benutzerdefinierten Bindung verwendet werden.  
  
     In den folgenden Beispielen wird gezeigt, wie `TransferMode` im Code und durch Ändern der Konfigurationsdatei festgelegt wird. In beiden Beispielen wird zudem die `maxReceivedMessageSize`-Eigenschaft auf 64&#160;MB festgelegt und damit die maximal zulässige Größe für den Empfang von Nachrichten beschränkt. Die Standardeinstellung von `maxReceivedMessageSize` ist 64&#160;KB, was normalerweise zu niedrig für die Verwendung des Streamingmodus ist. Legen Sie diese Größeneinstellung, abhängig von der maximalen Größe der Nachrichten, die von der Anwendung empfangen werden sollen, auf einen geeigneten Wert fest. Beachten Sie außerdem, dass die `maxBufferSize`-Einstellung die maximale Puffergröße angibt, und legen Sie diese Eigenschaft auf einen angemessenen Wert fest.  
  
    1. Der folgende Ausschnitt aus der Konfiguration des Beispiel zeigt, wie die `TransferMode`-Eigenschaft für `basicHttpBinding` und eine benutzerdefinierte HTTP-Bindung auf den Streamingmodus festgelegt wird.  
  
         [!code-xml[c_HowTo_EnableStreaming#103](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/common/app.config#103)]
  
    2. Der folgende Codeausschnitt zeigt, wie die `TransferMode`-Eigenschaft für `basicHttpBinding` und eine benutzerdefinierte HTTP-Bindung auf den Streamingmodus festgelegt wird.  
  
         [!code-csharp[c_HowTo_EnableStreaming_code#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming_code/cs/c_howto_enablestreaming_code.cs#2)]
         [!code-vb[c_HowTo_EnableStreaming_code#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming_code/vb/c_howto_enablestreaming_code.vb#2)]  
  
    3. Der folgende Codeausschnitt zeigt, wie die `TransferMode`-Eigenschaft für eine benutzerdefinierte TCP-Bindung auf den Streamingmodus festgelegt wird.  
  
         [!code-csharp[c_HowTo_EnableStreaming_code#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming_code/cs/c_howto_enablestreaming_code.cs#3)]
         [!code-vb[c_HowTo_EnableStreaming_code#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming_code/vb/c_howto_enablestreaming_code.vb#3)]  
  
3. Die Vorgänge `GetStream`, `UploadStream` und `EchoStream` sind damit befasst, Daten direkt aus einer Datei zu senden oder empfangene Daten direkt in eine Datei auszugeben. Der folgende Code ist für `GetStream` vorgesehen  
  
     [!code-csharp[c_HowTo_EnableStreaming#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#4)]
     [!code-vb[c_HowTo_EnableStreaming#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#4)]  
  
### <a name="writing-a-custom-stream"></a>Schreiben einer benutzerdefinierten Streamklasse  
  
1. Wenn jedes Element eines Datenstreams beim Senden oder Empfangen auf eine besondere Weise verarbeitet werden soll, müssen Sie eine benutzerdefinierte Streamklasse von der <xref:System.IO.Stream>-Klasse ableiten Der folgende Code enthält als Beispiel für einen benutzerdefinierten Stream die `GetReversedStream`-Methode und die `ReverseStream`-Klasse.  
  
     `GetReversedStream` erstellt eine neue Instanz der `ReverseStream`-Klasse und gibt eine Instanz dieser Klasse zurück. Die tatsächliche Verarbeitung erfolgt, wenn das System Daten aus dem `ReverseStream`-Objekt liest. Die `ReverseStream.Read`-Methode liest eine Gruppe von Bytes aus der zugrunde liegenden Datei, invertiert die Reihenfolge der Bytes und gibt die invertierten Bytes zurück. Diese Methode invertiert nicht den gesamten Dateiinhalt, sondern jeweils nur eine Gruppe von Bytes. Dieses Beispiel zeigt, wie Daten im Streamingmodus verarbeitet werden, wenn Daten aus dem Stream gelesen oder in den Stream geschrieben werden.  
  
     [!code-csharp[c_HowTo_EnableStreaming#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#2)]
     [!code-vb[c_HowTo_EnableStreaming#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Umfangreiche Daten und Streaming](large-data-and-streaming.md)
- [STREAM](../samples/stream.md)
