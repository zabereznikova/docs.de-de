---
title: Zugreifen auf Dienste mithilfe eines Clients
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c8329832-bf66-4064-9034-bf39f153fc2d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 180367920eb6f900fbb6b234b94f3b3a2c7fe52f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="accessing-services-using-a-client"></a>Zugreifen auf Dienste mithilfe eines Clients
Clientanwendungen müssen für die Kommunikation mit Diensten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client- oder Kanalobjekte erstellen, konfigurieren und verwenden. Die [Überblick über WCF-Client](../../../../docs/framework/wcf/wcf-client-overview.md) Thema bietet einen Überblick über die Objekte und die Schritte zum Erstellen von Objekten für grundlegende Client- und kanalobjekten und deren Verwendung.  
  
 Dieses Thema bietet ausführlichere Informationen zu Problemen mit Clientanwendungen sowie Client- und Kanalobjekten, die abhängig von Ihrem Szenario hilfreich sein können.  
  
## <a name="overview"></a>Übersicht  
 In diesem Thema werden das Verhalten und die Probleme zu Folgendem beschrieben:  
  
-   Kanal- und Sitzungslebensdauer.  
  
-   Behandeln von Ausnahmen.  
  
-   Grundlagen von Blockierungsproblemen.  
  
-   Interaktives Initialisieren von Kanälen.  
  
### <a name="channel-and-session-lifetimes"></a>Kanal- und Sitzungslebensdauer  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Anwendungen umfassen zwei Kategorien von Kanälen, Datagramm und sitzungsbasiert.  
  
 Ein *Datagramm* ist ein Kanal, in dem alle Nachrichten nicht korreliert sind. Auf einem Datagrammkanal ist normalerweise beim Fehlschlagen eines Eingabe- oder Ausgabevorgangs der nächste Vorgang nicht betroffen, und der gleiche Kanal kann wiederverwendet werden. Daher schlagen Datagrammkanäle in der Regel nicht fehl.  
  
 *Sitzungsbasierte* Kanäle sind hingegen Kanäle mit einer Verbindung mit den anderen Endpunkt. Nachrichten in einer Sitzung auf einer Seite korrelieren immer mit der gleichen Sitzung auf der anderen Seite. Außerdem müssen sich beide Teilnehmer einer Sitzung einigen, dass die Anforderungen ihrer Konversation erfüllt wurden, damit diese Sitzung als erfolgreich gilt. Wenn sie sich nicht einigen können, kann der sitzungsbasierte Kanal fehlschlagen.  
  
 Öffnen Sie Clients explizit oder implizit, indem Sie den ersten Vorgang aufrufen.  
  
> [!NOTE]
>  Der Versuch, fehlgeschlagene sitzungsbasierte Kanäle explizit zu erkennen, ist normalerweise nicht sinnvoll, da der Zeitpunkt der Benachrichtigung von der Sitzungsimplementierung abhängt. Da beispielsweise die <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType> (bei deaktivierter zuverlässiger Sitzung) die Sitzung der TCP-Verbindung anzeigt, wenn Sie das <xref:System.ServiceModel.ICommunicationObject.Faulted?displayProperty=nameWithType>-Ereignis auf dem Dienst oder dem Client abhören, werden Sie wahrscheinlich bei einem Netzwerkfehler schnell benachrichtigt. Zuverlässige Sitzungen (festgelegt durch Bindungen, in denen <xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=nameWithType> aktiviert ist) sind jedoch so konzipiert, dass sie Dienste von kleineren Netzwerkfehlern isolieren. Wenn die Sitzung innerhalb eines angemessenen Zeitraums wieder eingerichtet werden kann, schlägt die gleiche, für zuverlässige Sitzungen konfigurierte Bindung unter Umständen nicht fehl, bis die Unterbrechung einen längeren Zeitraum andauert.  
  
 Die meisten der vom System bereitgestellten Bindungen (die Kanäle für die Anwendungsebene verfügbar machen) verwenden standardmäßig Sitzungen, <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> jedoch nicht. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Mithilfe von Sitzungen](../../../../docs/framework/wcf/using-sessions.md).  
  
### <a name="the-proper-use-of-sessions"></a>Richtige Verwendung von Sitzungen  
 Sitzungen bieten die Möglichkeit festzustellen, ob der gesamte Nachrichtenaustausch vollständig ist und von beiden Seiten als erfolgreich betrachtet wurde. Es wird empfohlen, dass eine aufrufende Anwendung den Kanal innerhalb eines Try-Blocks öffnet, verwendet und schließt. Wenn ein Sitzungskanal geöffnet ist, die <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType>-Methode einmal aufgerufen wird und dieser Aufruf erfolgreich beendet wurde, war die Sitzung erfolgreich. Erfolgreich bedeutet in diesem Fall, dass alle von der Bindung angegebenen Zustellungsgarantien d erfüllt wurden und die andere Seite auf dem Kanal nicht <xref:System.ServiceModel.ICommunicationObject.Abort%2A?displayProperty=nameWithType> vor dem Aufrufen von <xref:System.ServiceModel.ICommunicationObject.Close%2A> aufgerufen hat.  
  
 Der folgende Abschnitt enthält ein Beispiel für diesen Clientansatz.  
  
### <a name="handling-exceptions"></a>Behandeln von Ausnahmen  
 Das Behandeln von Ausnahmen in Clientanwendungen ist einfach. Wird ein Kanal innerhalb eines Try-Blocks geöffnet, verwendet und geschlossen, war die Konversation erfolgreich, wenn keine Ausnahme ausgelöst wird. In der Regel wird die Konversation abgebrochen, wenn eine Ausnahme ausgelöst wird.  
  
> [!NOTE]
>  Die Verwendung der `using`-Anweisung (`Using` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]) wird nicht empfohlen. Das liegt daran, dass das Ende der `using`-Anweisung möglicherweise Ausnahmen verursacht, die andere Ausnahmen maskieren können, von denen Sie wissen sollten. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vermeiden von Problemen mit der Using-Anweisung](../../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
 Im folgenden Codebeispiel verwendet das empfohlene Clientmuster einen Try/Catch-Block und nicht die `using`-Anweisung.  
  
 [!code-csharp[FaultContractAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/client.cs#3)]
 [!code-vb[FaultContractAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/client.vb#3)]  
  
> [!NOTE]
>  Das Überprüfen des Werts der <xref:System.ServiceModel.ICommunicationObject.State%2A?displayProperty=nameWithType>-Eigenschaft ist eine Racebedingung und wird beim Feststellen, ob ein Kanal wiederverwendet oder geschlossen werden soll, nicht empfohlen.  
  
 Datagrammkanäle schlagen nie fehl, auch wenn beim Schließen Ausnahmen auftreten. Außerdem lösen Nichtduplex-Clients, bei denen keine Authentifizierung über eine sichere Konversation möglich ist, in der Regel eine <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType> aus. Wenn jedoch für den Duplexclient, der eine sichere Konversation verwendet, keine Authentifizierung möglich ist, erhält der Client stattdessen eine <xref:System.TimeoutException?displayProperty=nameWithType>.  
  
 Weitere Informationen zum Arbeiten mit Fehlerinformationen auf Anwendungsebene, finden Sie unter [angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md). [Erwartete Ausnahmen](../../../../docs/framework/wcf/samples/expected-exceptions.md) erwartete Ausnahmen beschreibt und zeigt, wie sie behandelt. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]zum Behandeln von Fehlern beim Entwickeln von Kanälen finden Sie unter [Behandlung von Ausnahmen und Fehlern](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).  
  
### <a name="client-blocking-and-performance"></a>Clientblockierung und Leistung  
 Wenn eine Anwendung synchron einen Anforderungs-/Antwortvorgang aufruft, wird der Client blockiert, bis ein Rückgabewert empfangen oder eine Ausnahme (wie <xref:System.TimeoutException?displayProperty=nameWithType>) ausgelöst wird. Dieses Verhalten ähnelt lokalem Verhalten. Ruft eine Anwendung synchron einen Vorgang auf einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientobjekt oder -kanal auf, wird der Client erst dann zurückgegeben, wenn die Kanalebene die Daten an das Netzwerk schreiben kann oder bis eine Ausnahme ausgelöst wird. Und während das unidirektionale Nachrichtenaustauschmuster (angegeben durch die Markierung eines Vorgangs, wobei <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> auf `true` festgelegt ist) die Reaktionsgeschwindigkeit einiger Clients verbessern kann, können unidirektionale Vorgänge abhängig von der Bindung und den bisher gesendeten Nachrichten auch blockiert werden. Bei unidirektionalen Vorgängen geht es nur um den Nachrichtenaustausch. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Unidirektionale Dienste](../../../../docs/framework/wcf/feature-details/one-way-services.md).  
  
 Große Datensegmente können die Clientverarbeitung verlangsamen, egal, welches Nachrichtenaustauschmuster verwendet wird. Um zu verstehen, wie diese Probleme behandelt, finden Sie unter [umfangreiche Daten und Streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).  
  
 Wenn die Anwendung beim Abschluss eines Vorgangs mehr arbeiten muss, sollten Sie ein asynchrones Methodenpaar an der Dienstvertragschnittstelle erstellen, das der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client implementiert. Die einfachste Möglichkeit hierzu ist die Verwendung der `/async` wechseln Sie auf die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Ein Beispiel finden Sie unter [Vorgehensweise: Aufrufen Service Vorgänge asynchron](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Clientleistung zu erhöhen, finden Sie unter [Clientanwendungen mittlerer Ebene](../../../../docs/framework/wcf/feature-details/middle-tier-client-applications.md).  
  
### <a name="enabling-the-user-to-select-credentials-dynamically"></a>Dynamisches Auswählen von Anmeldeinformationen durch den Benutzer  
 Über die <xref:System.ServiceModel.Dispatcher.IInteractiveChannelInitializer>-Schnittstelle können Anwendungen eine Benutzeroberfläche anzeigen, auf der der Benutzer Anmeldeinformationen zum Erstellen eines Kanals auswählen kann, bevor die Timeout-Zeitgeber starten.  
  
 Es gibt zwei Methoden, wie Anwendungsentwickler ein eingefügtes <xref:System.ServiceModel.Dispatcher.IInteractiveChannelInitializer> nutzen können. Die Clientanwendung kann entweder Aufrufen <xref:System.ServiceModel.ClientBase%601.DisplayInitializationUI%2A?displayProperty=nameWithType> oder <xref:System.ServiceModel.IClientChannel.DisplayInitializationUI%2A?displayProperty=nameWithType> (oder eine asynchrone Version) vor dem Öffnen des Kanals (die *explizite* Ansatz) oder den ersten Vorgang aufrufen (die *implizite*Ansatz).  
  
 Bei Verwendung des impliziten Ansatzes muss die Anwendung den ersten Vorgang für eine <xref:System.ServiceModel.ClientBase%601>-Erweiterung oder eine <xref:System.ServiceModel.IClientChannel>-Erweiterung aufrufen. Wenn ein anderes Element als der erste Vorgang aufgerufen wird, wird eine Ausnahme ausgelöst.  
  
 Bei Verwendung des expliziten Ansatzes müssen durch die Anwendung die folgenden Schritte in dieser Reihenfolge ausgeführt werden:  
  
1.  Rufen Sie <xref:System.ServiceModel.ClientBase%601.DisplayInitializationUI%2A?displayProperty=nameWithType> oder <xref:System.ServiceModel.IClientChannel.DisplayInitializationUI%2A?displayProperty=nameWithType> (oder eine asynchrone Version) auf.  
  
2.  Wenn die Initialisierer zurückgegeben wurden, rufen Sie entweder die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode für das <xref:System.ServiceModel.IClientChannel>-Objekt oder für das <xref:System.ServiceModel.IClientChannel>-Objekt auf, das durch die <xref:System.ServiceModel.ClientBase%601.InnerChannel%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wird.  
  
3.  Aufrufen von Vorgängen.  
  
 Es wird empfohlen, dass Anwendungen mit Produktionsqualität den Prozess der Benutzeroberfläche mithilfe des expliziten Ansatzes steuern.  
  
 Anwendungen, die den impliziten Ansatz verwenden, rufen die Initialisierer der Benutzeroberfläche auf, aber wenn der Benutzer nicht innerhalb des Sendetimeouts der Bindung antwortet, wird bei Zurückgeben der Benutzeroberfläche eine Ausnahme ausgelöst.  
  
## <a name="see-also"></a>Siehe auch  
 [Duplexdienste](../../../../docs/framework/wcf/feature-details/duplex-services.md)  
 [Vorgehensweise: Zugreifen auf Dienste mit unidirektionalen und Anforderung-Antwort-Verträgen](../../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)  
 [Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [Vorgehensweise: Zugriff auf einen WSE 3.0 Service](../../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)  
 [Vorgehensweise: Verwenden der ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)  
 [Vorgehensweise: Aufrufen von Dienstvorgängen](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)  
 [Clientanwendungen mittlerer Ebene](../../../../docs/framework/wcf/feature-details/middle-tier-client-applications.md)
