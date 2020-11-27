---
title: Verwenden von Sitzungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sessions [WCF]
ms.assetid: 864ba12f-3331-4359-a359-6d6d387f1035
ms.openlocfilehash: 42159b3871d974e53751468b422cbe9f72b6f908
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273684"
---
# <a name="using-sessions"></a>Verwenden von Sitzungen

In Windows Communication Foundation (WCF)-Anwendungen korreliert eine *Sitzung* eine Gruppe von Nachrichten in eine Konversation. WCF-Sitzungen unterscheiden sich von dem in ASP.NET-Anwendungen verfügbaren Sitzungs Objekt, unterstützen unterschiedliche Verhaltensweisen und werden auf unterschiedliche Weise gesteuert. In diesem Thema werden die Funktionen beschrieben, die Sitzungen in WCF-Anwendungen aktivieren und wie Sie verwendet werden.  
  
## <a name="sessions-in-windows-communication-foundation-applications"></a>Sitzungen in Windows Communication Foundation-Anwendungen  

 Wenn ein Dienstvertrag angibt, dass er eine Sitzung benötigt, bedeutet dies, dass alle Aufrufe (das heißt der zugrunde liegende Nachrichtenaustausch, durch den die Aufrufe unterstützt werden) Teil derselben Konversation sein müssen. Falls in einem Vertrag angegeben wird, dass Sitzungen zwar erlaubt, aber nicht erforderlich sind, können Clients eine Verbindung herstellen und eine Sitzung aufbauen oder auch nicht. Wird eine Sitzung beendet und eine Nachricht über denselben Kanal gesendet, wird eine Ausnahme ausgelöst.  
  
 WCF-Sitzungen verfügen über die folgenden Hauptfunktionen:  
  
- Sie werden explizit von der aufrufenden Anwendung (dem WCF-Client) initiiert und beendet.  
  
- Die während einer Sitzung gesendeten Nachrichten werden in der Reihenfolge verarbeitet, in der sie empfangen wurden.  
  
- Durch Sitzungen wird eine Gruppe von Nachrichten zu einer Konversation zusammengefasst. Es sind verschiedene Korrelationstypen möglich. So werden zum Beispiel bei einem sitzungsbasierten Kanal Nachrichten auf Grundlage einer gemeinsamen Netzwerkverbindung zueinander in Beziehung gesetzt, bei einem anderen Kanal geschieht dies wiederum auf Grundlage eines gemeinsamen Tags im Nachrichtentext. Die Funktionen, die von der Sitzung abgeleitet werden können, sind abhängig von der Art der Korrelation.  
  
- Einer WCF-Sitzung ist kein allgemeiner Datenspeicher zugeordnet.  
  
 Wenn Sie mit der <xref:System.Web.SessionState.HttpSessionState?displayProperty=nameWithType> -Klasse in ASP.NET-Anwendungen und der von ihr bereitgestellten Funktionalität vertraut sind, werden Sie möglicherweise die folgenden Unterschiede zwischen dieser Art von Sitzung und WCF-Sitzungen bemerken:  
  
- ASP.NET-Sitzungen werden immer vom Server initiiert.  
  
- ASP.NET-Sitzungen sind implizit Unsortiert.  
  
- ASP.NET-Sitzungen stellen einen allgemeinen Datenspeichermechanismus für Anforderungen bereit.  
  
 In diesem Thema wird Folgendes beschrieben:  
  
- Das Standardausführungsverhalten bei Verwendung sitzungsbasierter Bindungen auf Dienstmodellebene  
  
- Die Typen von Features, die von den auf der WCF-Sitzung basierenden, vom System bereitgestellten Bindungen bereitgestellt werden.  
  
- Erstellen eines Vertrags, der eine Sitzungsanforderung deklariert  
  
- Verstehen und Steuern der Erstellung und Beendigung einer Sitzung sowie der Beziehung zwischen der Sitzung und der Dienstinstanz  
  
## <a name="default-execution-behavior-using-sessions"></a>Standardausführungsverhalten mit Sitzungen  

 Eine Bindung, die eine Sitzung zu initiieren versucht, wird als *sitzungsbasierte* Bindung bezeichnet. Dienstverträge geben an, dass sie sitzungsbasierte Bindungen erfordern, zulassen oder verweigern, indem sie die <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> -Eigenschaft in der Dienstvertragschnittstelle (oder -klasse) auf einen der <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType> -Enumerationswerte festlegen. Standardmäßig ist der Wert dieser Eigenschaft. dies <xref:System.ServiceModel.SessionMode.Allowed> bedeutet, dass der Dienst die bereitgestellte Sitzung aufbaut und verwendet, wenn ein Client eine Sitzungs basierte Bindung mit einer WCF-Dienst Implementierung verwendet.  
  
 Wenn ein WCF-Dienst eine Client Sitzung akzeptiert, sind die folgenden Funktionen standardmäßig aktiviert:  
  
1. Alle Aufrufe zwischen einem WCF-Client Objekt werden von der gleichen Dienst Instanz behandelt.  
  
2. Andere sitzungsbasierte Bindungen stellen zusätzliche Funktionen bereit.  
  
## <a name="system-provided-session-types"></a>Vom System bereitgestellte Sitzungstypen  

 Eine sitzungsbasierte Bindung unterstützt die Standardzuordnung einer Dienstinstanz zu einer bestimmten Sitzung. Andere sitzungsbasierte Bindungen ermöglichen nicht nur die zuvor beschriebene sitzungsbasierte Instanziierungssteuerung, sondern unterstützen darüber hinaus andere Funktionen.  
  
 WCF bietet die folgenden Typen von Sitzungs basiertem Anwendungsverhalten:  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType> unterstützt sicherheitsbasierte Sitzungen, bei denen sich beide Kommunikationspartner auf eine bestimmte sichere Konversation verständigen. Weitere Informationen finden Sie unter [Sichern von Diensten](securing-services.md). Die <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType> -Bindung, bei der sowohl Sicherheitssitzungen als auch zuverlässige Sitzungen unterstützt werden, verwendet z.&#160;B. standardmäßig nur eine sichere Sitzung, die Nachrichten digital verschlüsselt und signiert.  
  
- Die <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType> -Bindung unterstützt TCP/IP-basierte Sitzungen, um sicherzustellen, dass alle Nachrichten von der Verbindung auf Socketebene miteinander in Beziehung gesetzt werden.  
  
- Das <xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=nameWithType> -Element, das die WS-ReliableMessaging-Spezifikation implementiert, bietet Unterstützung für zuverlässige Sitzungen, in denen Nachrichten so konfiguriert werden können, dass sie der Reihenfolge nach und genau einmal zugestellt werden, sodass der Empfang von Nachrichten sichergestellt wird, auch wenn sich diese während der Konversation durch mehrere Knoten bewegen. Weitere Informationen finden Sie unter [zuverlässige Sitzungen](./feature-details/reliable-sessions.md).  
  
- Die <xref:System.ServiceModel.NetMsmqBinding?displayProperty=nameWithType> -Bindung stellt MSMQ-Datagrammsitzungen bereit. Weitere Informationen finden Sie unter [Warteschlangen in WCF](./feature-details/queues-in-wcf.md).  
  
 Durch Festlegen der <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> -Eigenschaft wird nicht der vom Vertrag angeforderte Typ der Sitzung angegeben, sondern nur, dass eine Sitzung erforderlich ist.  
  
## <a name="creating-a-contract-that-requires-a-session"></a>Erstellen eines Vertrags, der eine Sitzung erfordert  

 Beim Erstellen eines Vertrags, der eine Sitzung erfordert, wird angegeben, dass die gesamte Gruppe von Vorgängen, die der Dienstvertrag deklariert, innerhalb derselben Sitzung ausgeführt werden muss und dass Nachrichten der Reihenfolge nach zugestellt werden müssen. Zum Bestätigen der Ebene der Sitzungsunterstützung, die ein Dienstvertrag erfordert, legen Sie die <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> -Eigenschaft der Dienstvertragschnittstelle oder -klasse auf den Wert der <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType> -Enumeration fest. Damit geben Sie an, ob der Vertrag:  
  
- Eine Sitzung erfordert.  
  
- Es einem Client ermöglicht, eine Sitzung aufzubauen.  
  
- Eine Sitzung verhindert.  
  
 Durch Festlegen der <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> -Eigenschaft wird allerdings nicht der vom Vertrag angeforderte Typ des sitzungsbasierten Verhaltens angegeben. Er weist WCF an, zur Laufzeit zu bestätigen, dass die konfigurierte Bindung (die den Kommunikationskanal erstellt) für den Dienst nicht funktioniert, keine Sitzung erstellt oder eine Sitzung einrichten kann, wenn ein Dienst implementiert wird. Die Bindung kann diese Anforderung wiederum mit einem beliebigen, von ihr gewählten Typ eines sitzungsbasierten Verhaltens erfüllen – Sicherheit, Transport, Zuverlässigkeit oder eine Kombination daraus. Das genaue Verhalten hängt vom ausgewählten <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType> -Wert ab. Wenn die konfigurierte Bindung des Diensts nicht dem Wert von <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A>entspricht, wird eine Ausnahme ausgelöst. Bindungen und die von ihnen erstellten Kanäle, die Sitzungen unterstützen, werden als sitzungsbasiert bezeichnet.  
  
 Der folgende Dienstvertrag gibt an, dass alle Vorgänge in `ICalculatorSession` innerhalb einer Sitzung ausgetauscht werden müssen. Mit Ausnahme der `Equals` -Methode gibt keiner der Vorgänge einen Wert an den Aufrufer zurück. Die `Equals` -Methode verwendet jedoch keine Parameter und kann daher nur einen Wert ungleich 0 (null) innerhalb der Sitzung zurückgeben, in der Daten bereits an die anderen Vorgänge übergeben wurden. Dieser Vertrag erfordert, dass eine Sitzung ordnungsgemäß funktioniert. Ist keine Sitzung einem bestimmten Client zugeordnet, kann die Dienstinstanz nicht ermitteln, welche Daten dieser Client bereits gesendet hat.  
  
 [!code-csharp[S_Service_Session#1](../../../samples/snippets/csharp/VS_Snippets_CFX/s_service_session/cs/service.cs#1)]
 [!code-vb[S_Service_Session#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_service_session/vb/service.vb#1)]  
  
 Wenn ein Dienst eine Sitzung zulässt, wird die Sitzung aufgebaut und verwendet, wenn der Client eine Sitzung initiiert, andernfalls wird keine Sitzung aufgebaut.  
  
## <a name="sessions-and-service-instances"></a>Sitzungen und Dienstinstanzen  

 Wenn Sie das standardmäßige Instanziierungsverhalten in WCF verwenden, werden alle Aufrufe zwischen einem WCF-Client Objekt von der gleichen Dienst Instanz verarbeitet. Daher können Sie sich eine Sitzung auf Anwendungsebene so vorstellen, dass sie ein Anwendungsverhalten ermöglicht, das dem lokalen Aufrufverhalten ähnlich ist. Wenn Sie zum Beispiel ein lokales Objekt erstellen:  
  
- Wird ein Konstruktor aufgerufen.  
  
- Alle nachfolgenden Aufrufe an den WCF-Client Objekt Verweis werden von der gleichen Objektinstanz verarbeitet.  
  
- Wird ein Destruktor aufgerufen, wenn der Objektverweis gelöscht wird.  
  
 Sitzungen ermöglichen ein ähnliches Verhalten zwischen Clients und Diensten, solange das Standardverhalten der Dienstinstanz verwendet wird. Wenn ein Dienstvertrag Sitzungen erfordert oder unterstützt, kann mindestens ein Vorgang durch Festlegen der <xref:System.ServiceModel.OperationContractAttribute.IsInitiating%2A> -Eigenschaft und der <xref:System.ServiceModel.OperationContractAttribute.IsTerminating%2A> -Eigenschaft zum Initiieren oder Beenden einer Sitzung angegeben werden.  
  
 *Initiierungsvorgänge* sind Vorgänge, die als erster Vorgang einer neuen Sitzung aufgerufen werden müssen. Nicht-Initiierungsvorgänge können nur aufgerufen werden, nachdem mindestens ein Initiierungsvorgang aufgerufen wurde. Sie können folglich eine Art Sitzungskonstruktor für den Dienst erstellen, indem Sie Initiierungsvorgänge deklarieren, die dazu gedacht sind, Eingaben von Clients anzunehmen, die sich für den Anfang der Dienstinstanz eignen. (Der Zustand ist jedoch der Sitzung zugeordnet, nicht dem Dienstobjekt.)  
  
 *Beendigungsvorgänge* sind dagegen Vorgänge, die als letzte Nachricht in einer vorhandenen Sitzung aufgerufen werden müssen. Im Standardfall verwendet WCF das Dienstobjekt und seinen Kontext wieder, nachdem die Sitzung, der der Dienst zugeordnet war, geschlossen wurde. Sie können folglich eine Art Destruktor erstellen, indem Sie Beendigungsvorgänge deklarieren, die zum Ausführen einer Funktion gedacht sind, die sich für das Ende der Dienstinstanz eignet.  
  
> [!NOTE]
> Das Standardverhalten ist lokalen Konstruktoren und Destruktoren ähnlich, aber eben nur ähnlich. Jeder WCF-Dienst Vorgang kann ein Initiierungs-oder Beendigungs Vorgang oder beides gleichzeitig sein. Außerdem können Initiierungsvorgänge im Standardfall beliebig oft in einer beliebigen Reihenfolge aufgerufen werden, nachdem der erste Vorgang aufgerufen wurde. Es werden keine zusätzlichen Sitzungen erstellt, sobald die Sitzung aufgebaut und einer Instanz zugeordnet wurde, es sei denn, Sie steuern die Lebensdauer der Dienstinstanz explizit (durch Bearbeiten des <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> -Objekts). Der Zustand wird schließlich der Sitzung zugeordnet, nicht dem Dienstobjekt.  
  
 Der `ICalculatorSession` im vorhergehenden Beispiel verwendete Vertrag erfordert beispielsweise, dass das WCF-Client Objekt zuerst den `Clear` Vorgang vor allen anderen Vorgängen aufruft und dass die Sitzung mit diesem WCF-Client Objekt beendet werden soll, wenn der Vorgang aufgerufen wird `Equals` . Das folgende Codebeispiel zeigt einen Vertrag, der diese Anforderungen erzwingt. `Clear` muss zuerst aufgerufen werden, um eine Sitzung zu initiieren. Diese Sitzung endet, wenn `Equals` aufgerufen wird.  
  
 [!code-csharp[SCA.IsInitiatingIsTerminating#1](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.isinitiatingisterminating/cs/service.cs#1)]
 [!code-vb[SCA.IsInitiatingIsTerminating#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.isinitiatingisterminating/vb/service.vb#1)]  
  
 Dienste starten keine Sitzungen mit Clients. In WCF-Client Anwendungen besteht eine direkte Beziehung zwischen der Lebensdauer des Sitzungs basierten Kanals und der Lebensdauer der Sitzung. Aus diesem Grund erstellen Clients neue Sitzungen, indem sie neue sitzungsbasierte Kanäle erstellen, und beenden bestehende Sitzungen, indem sie sitzungsbasierte Kanäle ordnungsgemäß schließen. Ein Client startet eine Sitzung mit einem Dienstendpunkt, indem er einen der folgenden Vorgänge aufruft:  
  
- <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> auf dem Kanal, das durch einen Aufruf an <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>zurückgegeben wurde.  
  
- <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> auf dem WCF-Client Objekt, das vom [Service Model Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)generiert wurde.  
  
- Ein initiierender Vorgang für beide Typen von WCF-Client Objekten (Standardmäßig werden alle Vorgänge initiiert). Wenn der erste Vorgang aufgerufen wird, öffnet das WCF-Client Objekt den Kanal automatisch und initiiert eine Sitzung.  
  
 Ein Client beendet eine Sitzung in der Regel mit einem Dienstendpunkt, indem er einen der folgenden Vorgänge aufruft:  
  
- <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType> auf dem Kanal, das durch einen Aufruf an <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>zurückgegeben wurde.  
  
- <xref:System.ServiceModel.ClientBase%601.Close%2A?displayProperty=nameWithType> auf dem von Svcutil.exe generierten WCF-Client Objekt.  
  
- Ein Beendender Vorgang für beide Typen von WCF-Client Objekten (Standardmäßig werden keine Vorgänge beendet; der Vertrag muss explizit einen Beendigungs Vorgang angeben). Wenn der erste Vorgang aufgerufen wird, öffnet das WCF-Client Objekt den Kanal automatisch und initiiert eine Sitzung.  
  
 Beispiele finden Sie unter [How to: Create a Service That Requires Sessions](./feature-details/how-to-create-a-service-that-requires-sessions.md) sowie unter [Default Service Behavior](./samples/default-service-behavior.md) und [Instancing](./samples/instancing.md) .  
  
 Weitere Informationen zu Clients und Sitzungen finden Sie unter [zugreifen auf Dienste mithilfe eines WCF-Clients](./feature-details/accessing-services-using-a-client.md).  
  
## <a name="sessions-interact-with-instancecontext-settings"></a>Interaktion von Sitzungen und InstanceContext-Einstellungen  

 Zwischen der <xref:System.ServiceModel.SessionMode> -Enumeration in einem Vertrag und der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> -Eigenschaft gibt es eine Interaktion, durch die die Zuordnung zwischen Kanälen und bestimmten Dienstobjekten gesteuert wird. Weitere Informationen finden Sie unter [Sitzungen, Instanziierung und](./feature-details/sessions-instancing-and-concurrency.md)Parallelität.  
  
### <a name="sharing-instancecontext-objects"></a>Freigeben von InstanceContext-Objekten  

 Sie können auch steuern, welcher sitzungsbasierte Kanal oder Aufruf welchem <xref:System.ServiceModel.InstanceContext> -Objekt zugeordnet wird, indem Sie diese Zuordnung selbst vornehmen.
  
## <a name="sessions-and-streaming"></a>Sitzungen und Streaming  

 Wenn Sie über eine große Datenmenge verfügen, ist der Streamingübertragungsmodus in WCF eine mögliche Alternative zum Standardverhalten, bei dem Nachrichten im Arbeitsspeicher vollständig gepuffert und verarbeitet werden. Möglicherweise tritt beim Streaming von Aufrufen mit einer sitzungsbasierten Bindung ein unerwartetes Verhalten auf. Alle Streamingaufrufe erfolgen über einen einzigen Kanal (den Datagrammkanal), der keine Sitzungen unterstützt, selbst wenn die verwendete Bindung für die Verwendung von Sitzungen konfiguriert ist. Wenn mehrere Clients über eine sitzungsbasierte Bindung Streamingaufrufe an das gleiche Dienstobjekt senden und der Parallelitätsmodus des Dienstobjekts auf "single" und sein Instanzkontextmodus auf `PerSession`festgelegt ist, müssen alle Aufrufe den Datagrammkanal passieren, sodass immer nur jeweils ein Aufruf verarbeitet wird. Für mindestens einen Client kann ein Timeout auftreten. Sie können dieses Problem umgehen, indem Sie entweder das Dienst Objekt auf oder die Parallelität auf "Multiple" festlegen `InstanceContextMode` `PerCall` .  
  
> [!NOTE]
> MaxConcurrentSessions hat in diesem Fall keine Auswirkungen, da nur eine Sitzung verfügbar ist.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.OperationContractAttribute.IsInitiating%2A>
- <xref:System.ServiceModel.OperationContractAttribute.IsTerminating%2A>
