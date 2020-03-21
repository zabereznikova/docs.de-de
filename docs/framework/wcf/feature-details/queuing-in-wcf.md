---
title: Warteschlangen in WCF
ms.date: 03/30/2017
ms.assetid: e98d76ba-1acf-42cd-b137-0f8214661112
ms.openlocfilehash: e6608a3d556b546660be904eb8c853243e833d2e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184563"
---
# <a name="queuing-in-wcf"></a>Warteschlangen in WCF
In diesem Abschnitt wird beschrieben, wie die Kommunikation in der Warteschlange in Windows Communication Foundation (WCF) verwendet wird.  
  
## <a name="queues-as-a-wcf-transport-binding"></a>Warteschlangen als WCF-Transportbindung  
 In WCF legen die Verträge fest, was ausgetauscht wird. Verträge sind geschäftsabhängige oder anwendungsspezifische Nachrichtenaustausche. Der Mechanismus (oder die „Art und Weise“) zum Austausch von Nachrichten wird in den Bindungen angegeben. Bindungen in WCF kapseln Details des Nachrichtenaustauschs. Die Bindungen stellen dem Benutzer Konfigurationssteuerelemente zur Verfügung, mit denen verschiedene Aspekte des Transports oder des Protokolls gesteuert werden, der bzw. das von den Bindungen dargestellt wird. Queuing in WCF wird wie jede andere Transportbindung behandelt, was für viele Warteschlangenanwendungen ein großer Vorteil ist. Heute werden zahlreiche Warteschlangenanwendungen anders geschrieben als andere verteilte RPC (Remote Procedure Call)-Anwendungen, wodurch die Verfolgung und Verwaltung erschwert wird. Mit WCF ist der Stil des Schreibens einer verteilten Anwendung ähnlich, wodurch es einfacher zu verfolgen und zu warten ist. Durch separates Trennen des Austauschmechanismus von der Geschäftslogik wird zudem die Konfiguration des Transports oder das Vornehmen von Änderungen erleichtert, ohne dass der anwendungsspezifische Code davon betroffen ist. Die folgende Abbildung zeigt die Struktur eines WCF-Diensts und eines Clients mit MSMQ als Transport.  
  
 ![In die Warteschlange gestelltes Anwendungsdiagramm](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "Verteilte Warteschlangen (Abbildung)")  
  
 Aus der vorherigen Abbildung geht hervor, dass mit dem Client und dem Dienst nur die Anwendungssemantik definiert werden muss, d.&#160;h. der Vertrag und die Implementierung. Eine der Warteschlange hinzugefügte Bindung wird vom Dienst mit den bevorzugten Einstellungen konfiguriert. Der Client verwendet das [ServiceModel Metadata Utility Tool (Svcutil.exe),](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) um einen WCF-Client für den Dienst zu generieren und eine Konfigurationsdatei zu generieren, die die Bindungen beschreibt, die zum Senden von Nachrichten an den Dienst verwendet werden sollen. Um eine Nachricht in der Warteschlange zu senden, instanziiert der Client einen WCF-Client und ruft einen Vorgang darauf auf. Daraufhin wird die Nachricht an die Übertragungswarteschlange gesendet und an die Zielwarteschlange übertragen. Alle Komplexitäten der in der Warteschlange enthaltenen Kommunikation werden der Anwendung, die Nachrichten sendet und empfängt, nicht angezeigt.  
  
 Zu den Einschränkungen bezüglich der Bindung in der Warteschlange in WCF gehören:  
  
- Alle Dienstvorgänge müssen unwegsam sein, da die standardmäßige Bindung in der Warteschlange in WCF die Duplexkommunikation mithilfe von Warteschlangen nicht unterstützt. Ein zweiwegs-Kommunikationsbeispiel ([Zwei-Wege-Kommunikation](../../../../docs/framework/wcf/samples/two-way-communication.md)) veranschaulicht, wie zwei einseitige Verträge verwendet werden, um Duplexkommunikation mithilfe von Warteschlangen zu implementieren.  
  
- Um einen WCF-Client mithilfe des Metadatenaustauschs zu generieren, ist ein zusätzlicher HTTP-Endpunkt für den Dienst erforderlich, damit er direkt abgefragt werden kann, um den WCF-Client zu generieren und Bindungsinformationen zu erhalten, um die Kommunikation in der Warteschlange entsprechend zu konfigurieren.  
  
- Basierend auf der Warteschlangenbindung ist eine zusätzliche Konfiguration außerhalb von WCF erforderlich. Beispielsweise erfordert <xref:System.ServiceModel.NetMsmqBinding> die Klasse, die mit WCF ausgeliefert wird, dass Sie die Bindungen konfigurieren und Message Queuing (MSMQ) minimal konfigurieren.  
  
 In den folgenden Abschnitten werden die spezifischen Bindungen in der Warteschlange beschrieben, die mit WCF ausgeliefert werden und auf MSMQ basieren.  
  
### <a name="msmq"></a>MSMQ  
 Der Warteschlangentransport in WCF verwendet MSMQ für seine Warteschlangenkommunikation.  
  
 MSMQ steht als optionale Windows-Komponente zur Verfügung und wird als NT-Dienst ausgeführt. MSMQ erfasst Nachrichten, die in einer Übertragungswarteschlange übertragen und an eine Zielwarteschlange gesendet werden. Die MSMQ-Warteschlangen-Manager implementieren ein zuverlässiges Nachrichtenübertragungsprotokoll, damit Nachrichten bei der Übertragung nicht verloren gehen. Das Protokoll kann entweder systemeigen oder SOAP-basiert sein, zum Beispiel das SOAP Reliable Message Protocol (SRMP).  
  
 In MSMQ können Warteschlangen transaktional oder nicht transaktional sein. Eine transaktionale Warteschlange ermöglicht das Erfassen und Zustellen von Nachrichten in einer Transaktion und das anschließende dauerhafte Speichern in der Warteschlange. An eine transaktionale Warteschlange gesendete Nachrichten werden genau einmal entsprechend ihrer Reihenfolge übertragen. Mit einer nicht transaktionalen Warteschlange können sowohl flüchtige als auch permanente Nachrichten gesendet werden. An nicht transaktionale Warteschlange gesendete Nachrichten werden nicht zuverlässig übertragen, sodass manche Nachrichten verloren gehen können.  
  
 MSMQ-Warteschlangen können auch mit einer Windows-Identität, die im Active Directory-Verzeichnisdienst registriert wird, gesichert werden. Bei der Installation von MSMQ kann die Active Directory-Integration installiert werden. Der Computer muss in diesem Fall Teil eines Windows-Domänennetzwerks sein.  
  
 Weitere Informationen zu MSMQ finden Sie unter [Installieren von Message Queuing (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md).  
  
### <a name="netmsmqbinding"></a>NetMsmqBinding  
 Die [ \<netMsmqBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md) ist die Bindung, die WCF in der Warteschlange für die Kommunikation von zwei WCF-Endpunkten mit MSMQ bereitstellt. Die Bindung macht deshalb MSMQ-spezifische Eigenschaften verfügbar. Allerdings sind nicht alle MSMQ-Features und -Eigenschaften in `NetMsmqBinding` verfügbar. Die kompakte `NetMsmqBinding` verfügt über ein optimales Spektrum an Funktionen, die für die meisten Kunden ausreichend sind.  
  
 `NetMsmqBinding` beschreibt die grundlegenden Warteschlangenkonzepte, die bisher in Form von Bindungseigenschaften erörtert wurden. Mit diesen Eigenschaften wird wiederum MSMQ mitgeteilt, wie Nachrichten übertragen und zugestellt werden sollen. Eine Erläuterung der Eigenschaftenkategorien befindet sich in den folgenden Abschnitten. Weitere Informationen finden Sie in den konzeptionellen Themen, in denen bestimmte Eigenschaften ausführlicher beschrieben werden.  
  
#### <a name="exactlyonce-and-durable-properties"></a>ExactlyOnce-Eigenschaft und Durable-Eigenschaft  
 Die `ExactlyOnce`-Eigenschaft und die `Durable`-Eigenschaft beeinflussen die Übertragung von Nachrichten zwischen Warteschlangen:  
  
- `ExactlyOnce`: Bei einer Festlegung auf `true` (Standard) wird durch den in der Warteschlange stehenden Kanal sichergestellt, dass die Nachricht im Falle der Zustellung nicht dupliziert wird. Dabei wird auch gewährleistet, dass die Nachricht nicht verloren geht. Falls eine Zustellung der Nachricht nicht möglich ist oder die Gültigkeitsdauer der Nachricht abläuft, bevor die Nachricht zugestellt werden kann, wird die nicht zugestellte Nachricht mit der Ursache für den Zustellungsfehler in einer Warteschlange für unzustellbare Nachrichten aufgezeichnet. Wenn der der Warteschlange hinzugefügte Kanal auf `false` festgelegt ist, wird versucht, die Nachricht zu übertragen. In diesem Fall können Sie optional eine Warteschlange für unzustellbare Nachrichten auswählen.  
  
- `Durable:` Bei einer Festlegung auf `true` (Standard) wird durch den der Warteschlange hinzugefügten Kanal sichergestellt, dass MSMQ die Nachricht permanent auf einem Datenträger speichert. Wird der MSMQ-Dienst beendet und neu gestartet, werden die Nachrichten auf dem Datenträger somit an die Zielwarteschlange übertragen oder an den Dienst gesendet. Bei einer Festlegung auf `false` werden die Nachrichten in einem flüchtigen Speicher gespeichert und gehen beim Beenden und Neustarten des MSMQ-Diensts verloren.  
  
 Für eine zuverlässige Übertragung von `ExactlyOnce` wird von MSMQ eine transaktionale Warteschlange gefordert. Zudem wird von MSMQ gefordert, dass eine Transaktion von einer Transaktionswarteschlange gelesen wird. Bei Verwendung von `NetMsmqBinding` muss eine Transaktion daher Nachrichten senden oder empfangen, wenn `ExactlyOnce` auf `true` festgelegt ist. Vergleichbar damit ist, dass MSMQ eine nicht transaktionale Warteschlange für Zusicherungen nach dem Best-Effort-Prinzip (beispielsweise wenn `ExactlyOnce` auf `false` festgelegt ist) sowie für flüchtiges Messaging benötigt. Wird `ExactlyOnce` auf `false` oder durable auf `false` festgelegt, ist Senden oder Empfangen mithilfe einer Transaktion nicht möglich.  
  
> [!NOTE]
> Stellen Sie sicher, dass die richtige Warteschlange (transaktional oder nicht transaktional) auf Grundlage der Einstellungen in den Bindungen erstellt wird. Wenn für `ExactlyOnce` der Wert `true` gilt, verwenden Sie eine Transaktionswarteschlange und andernfalls eine nicht transaktionale Warteschlange.  
  
#### <a name="dead-letter-queue-properties"></a>Eigenschaften der Warteschlange für unzustellbare Nachrichten  
 Die Warteschlange für unzustellbare Nachrichten wird verwendet, um unzustellbare Nachrichten zu speichern. Der Benutzer kann kompensierende Logik schreiben, die Nachrichten aus der Warteschlange für unzustellbare Nachrichten liest.  
  
 Viele Warteschlangensysteme verfügen über eine systemweite Warteschlange für unzustellbare Nachrichten. MSMQ verfügt über eine systemweite Warteschlange für unzustellbare nicht transaktionale Nachrichten. Diese Warteschlange wird für Nachrichten verwendet, deren Zustellung an nicht transaktionale Warteschlangen nicht möglich ist. Darüber hinaus besitzt MSMQ eine systemweite transaktionale Warteschlange für unzustellbare Nachrichten, die für Nachrichten verwendet wird, die nicht an Transaktionswarteschlange gesendet werden können.  
  
 Wird der MSMQ-Dienst von mehreren Clients, die Nachrichten an verschiedene Zielwarteschlangen senden, gemeinsam verwendet, werden alle von den Clients gesendeten Nachrichten in dieselbe Warteschlange für unzustellbare Nachrichten verschoben. Dies ist nicht immer empfehlenswert. Für eine bessere Isolierung stellen WCF und MSMQ in Windows Vista eine benutzerdefinierte Warteschlange für unzustellbare Nachrichten (oder anwendungsspezifische Warteschlange für unzustellbare Nachrichten) bereit, die der Benutzer angeben kann, um Nachrichten zu speichern, die die Zustellung fehlschlagen. Daher verwenden unterschiedliche Clients nicht gemeinsam dieselbe Warteschlange für unzustellbare Nachrichten.  
  
 Die Bindung verfügt über zwei wichtige Eigenschaften:  
  
- `DeadLetterQueue`: Diese Eigenschaft ist eine Enumeration, die angibt, ob eine Warteschlange für unzustellbare Nachrichten angefordert wird. Die Enumeration enthält auch die Art der Warteschlange für unzustellbare Nachrichten, sofern eine Warteschlange angefordert wird. Mögliche Werte sind `None`, `System` und `Custom`. Weitere Informationen zur Interpretation dieser Eigenschaften finden Sie unter Verwenden von Warteschlangen für tote Buchstaben zum Behandeln von [Nachrichtenübertragungsfehlern](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
  
- `CustomDeadLetterQueue`: Diese Eigenschaft ist die Uniform Resource Identifier (URI)-Adresse der anwendungsspezifischen Warteschlange für unzustellbare Nachrichten. Dies ist `DeadLetterQueue`erforderlich, wenn .`Custom` gewählt wird.  
  
#### <a name="poison-message-handling-properties"></a>Eigenschaften der Behandlung nicht verarbeitbarer Nachrichten  
 Liest der Dienst im Rahmen einer Transaktion Nachrichten aus der Zielwarteschlange, kann die Nachricht vom Dienst aus verschiedenen Gründen möglicherweise nicht verarbeitet werden. Die Nachricht wird anschließend zum erneuten Lesen in die Warteschlange zurückgestellt. Zur Verarbeitung von Nachrichten, die mehrmals nicht zugestellt werden konnten, kann in der Bindung ein Satz Eigenschaften zur Behandlung nicht verarbeitbarer Nachrichten konfiguriert werden. Es gibt vier Eigenschaften: `ReceiveRetryCount`, `MaxRetryCycles`, `RetryCycleDelay` und `ReceiveErrorHandling`. Weitere Informationen zu diesen Eigenschaften finden Sie unter [Giftnachrichtenbehandlung](../../../../docs/framework/wcf/feature-details/poison-message-handling.md).  
  
#### <a name="security-properties"></a>Sicherheitseigenschaften  
 MSMQ verfügt über ein eigenes Sicherheitsmodell, zu dem beispielsweise Zugriffssteuerungslisten in einer Warteschlange oder das Senden von authentifizierten Nachrichten gehören. `NetMsmqBinding` macht diese Sicherheitseigenschaften als Teil der Transportsicherheitseinstellungen verfügbar. Die Bindung für Transportsicherheit besitzt zwei Eigenschaften: `MsmqAuthenticationMode` und `MsmqProtectionLevel`. Einstellungen in diesen Eigenschaften sind von der Konfiguration von MSMQ abhängig. Weitere Informationen finden Sie unter [Sichern von Nachrichten mithilfe der Transportsicherheit](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md).  
  
 Zusätzlich zur Transportsicherheit kann die eigentliche SOAP-Nachricht mit Nachrichtensicherheit gesichert werden. Weitere Informationen finden Sie unter Sichern von Nachrichten mithilfe der [Nachrichtensicherheit](../../../../docs/framework/wcf/feature-details/securing-messages-using-message-security.md).  
  
 `MsmqTransportSecurity` macht ebenfalls zwei Eigenschaften verfügbar, `MsmqEncryptionAlgorithm` und `MsmqHashAlgorithm`. Dabei handelt es sich um Enumerationen verschiedener Algorithmen, die bei Übertragungen zwischen Warteschlangen für die Verschlüsselung von Nachrichten und das Hashing der Signaturen gewählt werden können.  
  
#### <a name="other-properties"></a>Andere Eigenschaften  
 Neben den zuvor genannten Eigenschaften stehen in der Bindung auch andere MSMQ-spezifische Eigenschaften zur Verfügung:  
  
- `UseSourceJournal`: Eine Eigenschaft, mit der angegeben wird, dass die Führung von Quelljournalen aktiviert ist. Die Führung von Quelljournalen ist eine MSMQ-Funktion zum Erfassen von Nachrichten, die erfolgreich von der Übertragungswarteschlange übertragen wurden.  
  
- `UseMsmqTracing`: Eine Eigenschaft, mit der angegeben wird, dass die MSMQ-Ablaufverfolgung aktiviert ist. Die MSMQ-Ablaufverfolgung sendet Berichtsnachrichten an eine Berichtwarteschlange, wenn eine Nachricht einen Computer, der als Host für einen MSMQ-Warteschlangen-Manager fungiert, verlässt oder bei diesem eingeht.  
  
- `QueueTransferProtocol`: Eine Enumeration des Protokolls, das für Nachrichtenübertragungen zwischen Warteschlangen verwendet wird. MSMQ implementiert ein systemeigenes Protokoll für Übertragungen zwischen Warteschlangen und ein SOAP-basiertes Protokoll mit der Bezeichnung SOAP Reliable Messaging Protocol (SRMP). SRMP wird bei Verwendung von HTTP-Transport für Übertragungen zwischen Warteschlangen verwendet. Sicheres SRMP wird bei Verwendung von HTTPS für Übertragungen zwischen Warteschlangen verwendet.  
  
- `UseActiveDirectory`: Ein boolescher Wert, mit dem angegeben wird, ob Active Directory für die Auflösung von Warteschlangenadressen verwendet werden muss. Standardmäßig ist dieser Wert deaktiviert. Weitere Informationen finden Sie unter [Serviceendpoints und Queue Addressing](../../../../docs/framework/wcf/feature-details/service-endpoints-and-queue-addressing.md).  
  
### <a name="msmqintegrationbinding"></a>MsmqIntegrationBinding  
 Der `MsmqIntegrationBinding` wird verwendet, wenn ein WCF-Endpunkt mit einer vorhandenen MSMQ-Anwendung kommunizieren soll, die in C-, C++-, COM- oder System.Messaging-APIs geschrieben ist.  
  
 Die Bindungseigenschaften sind für `NetMsmqBinding` identisch. Folgende Unterschiede sind jedoch zu berücksichtigen:  
  
- Der Vorgangsvertrag für `MsmqIntegrationBinding` ist auf das Verwenden eines Einzelparameters vom Typ <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601> beschränkt, in dem der Typparameter der Texttyp ist.  
  
- Ein Großteil der Eigenschaften der systemeigenen MSMQ-Nachrichten steht in <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601> zur Verfügung.  
  
- Die Serialisierung und Deserialisierung des Nachrichtentexts wird durch verfügbare Serialisierungsprogramme wie XML und ActiveX unterstützt.  
  
### <a name="sample-code"></a>Beispielcode  
 Schritt-für-Schritt-Anweisungen zum Schreiben von WCF-Diensten, die MSMQ verwenden, finden Sie in den folgenden Themen:  
  
- [Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
  
- [Gewusst wie: Austauschen von Nachrichten in einer Warteschlange mit WCD-Endpunkten](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
  
 Ein vollständiges Codebeispiel, das die Verwendung von MSMQ in WCF veranschaulicht, finden Sie in den folgenden Themen:  
  
- [Abgewickelte MSMQ-Bindung](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
  
- [Flüchtige Kommunikation unter Verwendung von Warteschlangen](../../../../docs/framework/wcf/samples/volatile-queued-communication.md)  
  
- [Warteschlangen für unzustellbare Meldungen](../../../../docs/framework/wcf/samples/dead-letter-queues.md)  
  
- [Sitzungen und Warteschlangen](../../../../docs/framework/wcf/samples/sessions-and-queues.md)  
  
- [Bidirektionale Kommunikation](../../../../docs/framework/wcf/samples/two-way-communication.md)
  
- [SRMP](../../../../docs/framework/wcf/samples/srmp.md)  
  
- [Nachrichtensicherheit über Message Queuing](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Dienstendpunkte und Adressieren von Warteschlangen](../../../../docs/framework/wcf/feature-details/service-endpoints-and-queue-addressing.md)
- [Webhosting einer Anwendung mit Queuing](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md)
