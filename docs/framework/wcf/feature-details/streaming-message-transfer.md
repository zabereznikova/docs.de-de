---
title: Nachrichtenübertragung per Stream
ms.date: 03/30/2017
ms.assetid: 72a47a51-e5e7-4b76-b24a-299d51e0ae5a
ms.openlocfilehash: 462144856750a1b8726b574fdc82746da2d72ff7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594789"
---
# <a name="streaming-message-transfer"></a>Nachrichtenübertragung per Stream
Windows Communication Foundation (WCF)-Transporte unterstützen zwei Modi zum Übertragen von Nachrichten:  
  
- Bei gepufferten Übertragungen wird die gesamte Nachricht in einem Puffer zwischengespeichert, bis die Übertragung abgeschlossen ist. Gepufferte Nachrichten müssen vollständig übertragen worden sein, bevor sie vom Empfänger gelesen werden können.  
  
- Bei Streamingübertragungen wird die Nachricht als Stream verfügbar gemacht. Die Nachricht kann vom Empfänger verarbeitet werden, bevor sie vollständig empfangen wurde.  
  
- Streamübertragungen können die Skalierbarkeit eines Diensts verbessern, indem sie große Speicherpuffer überflüssig machen. Der Einfluss einer Änderung des Übertragungsmodus auf die Skalierbarkeit ist abhängig von der Größe der übertragenen Nachricht. Je größer eine Nachricht ist, desto eher ist eine Streamübertragung zu bevorzugen.  
  
 HTTP, TCP/IP sowie Named Pipe-Transporte verwenden gepufferte Übertragungen. In diesem Dokument wird beschrieben, wie Streamingübertragungen anstelle von gepufferten Übertragungen für diese Transporte verwendet werden, und welche Konsequenzen sich daraus ergeben.  
  
## <a name="enabling-streamed-transfers"></a>Aktivieren von Streamübertragungen  
 Die Auswahl zwischen der gepufferten Übertragung und der Streamingübertragung erfolgt mithilfe des Transportbindungselements. Das Bindungselement weist eine <xref:System.ServiceModel.TransferMode>-Eigenschaft auf, die auf `Buffered`, `Streamed`, `StreamedRequest` oder `StreamedResponse` festgelegt werden kann. Wenn Sie den Übertragungsmodus auf `Streamed` festlegen, wird ein Kommunikationsstream in beide Richtungen ermöglicht. Wenn Sie den Übertragungsmodus auf `StreamedRequest` oder `StreamedResponse` festlegen, wird ein Kommunikationsstream nur in der angegebenen Richtung ermöglicht.  
  
 Mit den Bindungen <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.NetTcpBinding> und <xref:System.ServiceModel.NetNamedPipeBinding> wird die <xref:System.ServiceModel.TransferMode>-Eigenschaft verfügbar gemacht. Für andere Transporte müssen Sie eine benutzerdefinierte Bindung erstellen, um den Übertragungsmodus festzulegen.  
  
 Die Entscheidung über die Verwendung der gepufferten oder der Streamingübertragung wird lokal am Endpunkt getroffen. Bei HTTP-Übertragungen wird der Übertragungsmodus nicht über Verbindungen oder an Server oder andere Vermittler weitergegeben. Das Festlegen des Übertragungsmodus spiegelt sich nicht in der Beschreibung der Dienstschnittstelle wider. Nachdem Sie eine Clientklasse für einen Dienst erstellt haben, müssen Sie die Konfigurationsdatei für Dienste bearbeiten, die mit Streamingübertragungen verwendet werden sollen, um den Modus festzulegen. Bei TCP und Named Pipe-Transporten wird der Übertragungsmodus als Richtlinienassertion weitergegeben.  
  
 Codebeispiele finden Sie unter Gewusst [wie: Aktivieren des Streamings](how-to-enable-streaming.md).  
  
## <a name="enabling-asynchronous-streaming"></a>Aktivieren von asynchronem Streaming  
 Um das asynchrone Streaming zu aktivieren, fügen Sie dem Diensthost das <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>-Endpunktverhalten hinzu und legen dessen <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.AsynchronousSendEnabled%2A>-Eigenschaft auf `true` fest.  
  
 Mit dieser WCF-Version wird die Fähigkeit zum echten asynchronen Streaming auf der Senderseite hinzugefügt. Dies verbessert die Skalierbarkeit des Diensts in Szenarien, in denen Nachrichten an mehrere Clients gestreamt werden, von denen einige eine langsame Lesegeschwindigkeit haben, möglicherweise aufgrund von Netzwerküberlastung, oder überhaupt nicht lesen. In diesen Szenarien werden einzelne Threads für den Dienst pro Client nicht blockiert. Dadurch wird sichergestellt, dass der Dienst in der Lage ist, viel mehr Clients zu verarbeiten und somit die Skalierbarkeit des Diensts zu verbessern.  
  
## <a name="restrictions-on-streamed-transfers"></a>Einschränkungen für Streamübertragungen  
 Wenn Sie den Streamübertragungsmodus verwenden, werden zusätzliche Einschränkungen von der Laufzeit implementiert.  
  
 Vorgänge, die unter Verwendung einer Streamübertragung ausgeführt werden, können einen Vertrag mit maximal einem Eingabe- oder Ausgabeparameter aufweisen. Der Parameter entspricht dem gesamten Nachrichtentext, und es muss sich um <xref:System.ServiceModel.Channels.Message>, um einen abgeleiteten Typ von <xref:System.IO.Stream> oder um eine <xref:System.Xml.Serialization.IXmlSerializable>-Implementierung handeln. Ein Rückgabewert für einen Vorgang entspricht einem Ausgabeparameter.  
  
 Einige WCF-Features, z. b. zuverlässiges Messaging, Transaktionen und SOAP-Sicherheit auf Nachrichten Ebene, basieren auf der Pufferung von Nachrichten für Übertragungen. Dadurch können mögliche Leistungsvorteile durch das Streaming reduziert oder zunichte gemacht werden. Mit der Sicherheit auf Transportebene oder mit der Sicherheit auf Transportebene sowie dem Authentifizierungsmodus für die Nachrichtensicherheit können Sie eine Streamübertragung absichern.  
  
 SOAP-Header werden immer gepuffert, auch wenn eine Streamübertragung verwendet wird. Die Nachrichtenheader dürfen nicht größer sein als das `MaxBufferSize`-Transportkontingent. Weitere Informationen zu dieser Einstellung finden Sie unter [Transport Kontingente](transport-quotas.md).  
  
## <a name="differences-between-buffered-and-streamed-transfers"></a>Unterschiede zwischen gepufferten und Streamingübertragungen  
 Durch das Ändern des Übertragungsmodus von gepuffert in gestreamt wird auch die systemeigene Kanalform von TCP- und Named Pipe-Transporten geändert. Die systemeigene Kanalform für gepufferte Übertragungen ist <xref:System.ServiceModel.Channels.IDuplexSessionChannel>. Die systemeigenen Kanäle für Streamingübertragungen sind <xref:System.ServiceModel.Channels.IRequestChannel> und <xref:System.ServiceModel.Channels.IReplyChannel>. Wenn Sie den Übertragungsmodus in einer bestehenden Anwendung ändern möchten, die diese Transporte unmittelbar (d. h. nicht über einen Dienstvertrag) verwendet, müssen Sie die erwartete Kanalform für Kanalfactorys und -listener ändern.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Aktivieren des Streamingmodus](how-to-enable-streaming.md)
