---
title: Warteschlangen in WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e98d76ba-1acf-42cd-b137-0f8214661112
caps.latest.revision: "21"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 64a66b1ce04f6c644eef266fee1c89366f1fb707
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="queuing-in-wcf"></a>Warteschlangen in WCF
In diesem Abschnitt wird beschrieben, wie der Warteschlange hinzugefügte Kommunikation in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet wird.  
  
## <a name="queues-as-a-wcf-transport-binding"></a>Warteschlangen als WCF-Transportbindung  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] geben die Verträge an, welche Objekte ausgetauscht werden. Verträge sind geschäftsabhängige oder anwendungsspezifische Nachrichtenaustausche. Der Mechanismus (oder die "Art und Weise") zum Austausch von Nachrichten wird in den Bindungen angegeben. Bindungen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kapseln Details des Nachrichtenaustauschs. Die Bindungen stellen dem Benutzer Konfigurationssteuerelemente zur Verfügung, mit denen verschiedene Aspekte des Transports oder des Protokolls gesteuert werden, der bzw. das von den Bindungen dargestellt wird. Warteschlangen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] werden wie jede andere Transportbindung behandelt, was ein großer Vorteil für zahlreiche Warteschlangenanwendungen ist. Heute werden zahlreiche Warteschlangenanwendungen anders geschrieben als andere verteilte RPC (Remote Procedure Call)-Anwendungen, wodurch die Verfolgung und Verwaltung erschwert wird. Mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] wird ein sehr ähnlicher Stil für das Schreiben einer verteilten Anwendung verwendet, wodurch die Verfolgung und Verwaltung erleichtert wird. Durch separates Trennen des Austauschmechanismus von der Geschäftslogik wird zudem die Konfiguration des Transports oder das Vornehmen von Änderungen erleichtert, ohne dass der anwendungsspezifische Code davon betroffen ist. Die folgende Abbildung zeigt die Struktur eines WCF-Diensts und eines Clients mit MSMQ als Transport.  
  
 ![In der Warteschlange Anwendungsdiagramm](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "Distributed-Warteschlange-Abbildung")  
  
 Aus der vorherigen Abbildung geht hervor, dass mit dem Client und dem Dienst nur die Anwendungssemantik definiert werden muss, d.&#160;h. der Vertrag und die Implementierung. Eine der Warteschlange hinzugefügte Bindung wird vom Dienst mit den bevorzugten Einstellungen konfiguriert. Der Client verwendet die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Generieren einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client an den Dienst und eine Konfigurationsdatei zu generieren, die die Bindungen verwendet, die zum Senden von Nachrichten an den Dienst beschreibt. Zum Senden einer in der Warteschlange enthaltenen Nachricht wird vom Client ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client instanziiert und ein Vorgang darauf ausgelöst. Daraufhin wird die Nachricht an die Übertragungswarteschlange gesendet und an die Zielwarteschlange übertragen. Alle Komplexitäten der in der Warteschlange enthaltenen Kommunikation werden der Anwendung, die Nachrichten sendet und empfängt, nicht angezeigt.  
  
 Beachten Sie folgende Warnhinweise zu der Warteschlange hinzugefügten Bindungen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   Alle Dienstvorgänge müssen unidirektional sein, da von der standardmäßigen in der Warteschlange enthaltenen Bindung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] keine Duplexkommunikation mithilfe von Warteschlangen unterstützt wird. Ein Beispiel für die bidirektionale Kommunikation ([bidirektionaler Kommunikation](../../../../docs/framework/wcf/samples/two-way-communication.md)) zeigt, wie zwei unidirektionale Verträgen Duplexkommunikation mithilfe von Warteschlangen zu implementieren.  
  
-   Soll ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client mithilfe von Metadaten generiert werden, ist für den Austausch ein zusätzlicher HTTP-Endpunkt im Dienst erforderlich, damit durch eine direkte Abfrage der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client generiert wird und Bindungsinformationen zur ordnungsgemäßen Konfiguration der in der Warteschlange enthaltenen Kommunikation abgerufen werden.  
  
-   Auf Basis der der Warteschlange hinzugefügten Bindung ist eine zusätzliche Konfiguration außerhalb von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erforderlich. Beispielsweise erfordert die mit <xref:System.ServiceModel.NetMsmqBinding> zur Verfügung gestellte [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Klasse die Konfiguration der Bindungen sowie eine Mindestkonfiguration von Message Queuing (MSMQ).  
  
 In den folgenden Abschnitten werden die bestimmten in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] enthaltenen und der Warteschlange hinzugefügten Bindungen beschrieben, die auf MSMQ basieren.  
  
### <a name="msmq"></a>MSMQ  
 Für den der Warteschlange hinzugefügten Transport in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] wird MSMQ für die der Warteschlange hinzugefügten Kommunikation verwendet.  
  
 MSMQ steht als optionale Windows-Komponente zur Verfügung und wird als NT-Dienst ausgeführt. MSMQ erfasst Nachrichten, die in einer Übertragungswarteschlange übertragen und an eine Zielwarteschlange gesendet werden. Die MSMQ-Warteschlangen-Manager implementieren ein zuverlässiges Nachrichtenübertragungsprotokoll, damit Nachrichten bei der Übertragung nicht verloren gehen. Das Protokoll kann entweder systemeigen oder SOAP-basiert sein, zum Beispiel das SOAP Reliable Message Protocol (SRMP).  
  
 In MSMQ können Warteschlangen transaktional oder nicht transaktional sein. Eine transaktionale Warteschlange ermöglicht das Erfassen und Zustellen von Nachrichten in einer Transaktion und das anschließende dauerhafte Speichern in der Warteschlange. An eine transaktionale Warteschlange gesendete Nachrichten werden genau einmal entsprechend ihrer Reihenfolge übertragen. Mit einer nicht transaktionalen Warteschlange können sowohl flüchtige als auch permanente Nachrichten gesendet werden. An nicht transaktionale Warteschlange gesendete Nachrichten werden nicht zuverlässig übertragen, sodass manche Nachrichten verloren gehen können.  
  
 MSMQ-Warteschlangen können auch mit einer Windows-Identität, die im Active Directory-Verzeichnisdienst registriert wird, gesichert werden. Bei der Installation von MSMQ kann die Active Directory-Integration installiert werden. Der Computer muss in diesem Fall Teil eines Windows-Domänennetzwerks sein.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]MSMQ, finden Sie unter [Installieren von Message Queuing (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md).  
  
### <a name="netmsmqbinding"></a>NetMsmqBinding  
 Die [ \<NetMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md) wird von die Bindung [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] werden für zwei [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Endpunkte für die Kommunikation über MSMQ. Die Bindung macht deshalb MSMQ-spezifische Eigenschaften verfügbar. Allerdings sind nicht alle MSMQ-Features und -Eigenschaften in `NetMsmqBinding` verfügbar. Die kompakte `NetMsmqBinding` verfügt über ein optimales Spektrum an Features, die für die meisten Kunden ausreichend sind.  
  
 `NetMsmqBinding` beschreibt die grundlegenden Warteschlangenkonzepte, die bisher in Form von Bindungseigenschaften erörtert wurden. Mit diesen Eigenschaften wird wiederum MSMQ mitgeteilt, wie Nachrichten übertragen und zugestellt werden sollen. Eine Erläuterung der Eigenschaftenkategorien befindet sich in den folgenden Abschnitten. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] den grundlegenden Themen mit einer genaueren Beschreibung bestimmter Eigenschaften.  
  
#### <a name="exactlyonce-and-durable-properties"></a>ExactlyOnce-Eigenschaft und Durable-Eigenschaft  
 Die `ExactlyOnce`-Eigenschaft und die `Durable`-Eigenschaft beeinflussen die Übertragung von Nachrichten zwischen Warteschlangen:  
  
-   `ExactlyOnce`: Bei einer Festlegung auf `true` (Standard) wird durch den in der Warteschlange stehenden Kanal sichergestellt, dass die Nachricht im Falle der Zustellung nicht dupliziert wird. Dabei wird auch gewährleistet, dass die Nachricht nicht verloren geht. Falls eine Zustellung der Nachricht nicht möglich ist oder die Gültigkeitsdauer der Nachricht abläuft, bevor die Nachricht zugestellt werden kann, wird die nicht zugestellte Nachricht mit der Ursache für den Zustellungsfehler in einer Warteschlange für unzustellbare Nachrichten aufgezeichnet. Wenn der der Warteschlange hinzugefügte Kanal auf `false` festgelegt ist, wird versucht, die Nachricht zu übertragen. In diesem Fall können Sie optional eine Warteschlange für unzustellbare Nachrichten auswählen.  
  
-   `Durable:` Bei einer Festlegung auf `true` (Standard) wird durch den der Warteschlange hinzugefügten Kanal sichergestellt, dass MSMQ die Nachricht permanent auf einem Datenträger speichert. Wird der MSMQ-Dienst beendet und neu gestartet, werden die Nachrichten auf dem Datenträger somit an die Zielwarteschlange übertragen oder an den Dienst gesendet. Bei einer Festlegung auf `false` werden die Nachrichten in einem flüchtigen Speicher gespeichert und gehen beim Beenden und Neustarten des MSMQ-Diensts verloren.  
  
 Für eine zuverlässige Übertragung von `ExactlyOnce` wird von MSMQ eine transaktionale Warteschlange gefordert. Zudem wird von MSMQ gefordert, dass eine Transaktion von einer Transaktionswarteschlange gelesen wird. Bei Verwendung von `NetMsmqBinding` muss eine Transaktion daher Nachrichten senden oder empfangen, wenn `ExactlyOnce` auf `true` festgelegt ist. Vergleichbar damit ist, dass MSMQ eine nicht transaktionale Warteschlange für Zusicherungen nach dem Best-Effort-Prinzip (beispielsweise wenn `ExactlyOnce` auf `false` festgelegt ist) sowie für flüchtiges Messaging benötigt. Wird `ExactlyOnce` auf `false` oder durable auf `false` festgelegt, ist Senden oder Empfangen mithilfe einer Transaktion nicht möglich.  
  
> [!NOTE]
>  Stellen Sie sicher, dass die richtige Warteschlange (transaktional oder nicht transaktional) auf Grundlage der Einstellungen in den Bindungen erstellt wird. Wenn für `ExactlyOnce` der Wert `true` gilt, verwenden Sie eine Transaktionswarteschlange und andernfalls eine nicht transaktionale Warteschlange.  
  
#### <a name="dead-letter-queue-properties"></a>Eigenschaften der Warteschlange für unzustellbare Nachrichten  
 Die Warteschlange für unzustellbare Nachrichten wird verwendet, um unzustellbare Nachrichten zu speichern. Der Benutzer kann kompensierende Logik schreiben, die Nachrichten aus der Warteschlange für unzustellbare Nachrichten liest.  
  
 Viele Warteschlangensysteme verfügen über eine systemweite Warteschlange für unzustellbare Nachrichten. MSMQ verfügt über eine systemweite Warteschlange für unzustellbare nicht transaktionale Nachrichten. Diese Warteschlange wird für Nachrichten verwendet, deren Zustellung an nicht transaktionale Warteschlangen nicht möglich ist. Darüber hinaus besitzt MSMQ eine systemweite transaktionale Warteschlange für unzustellbare Nachrichten, die für Nachrichten verwendet wird, die nicht an Transaktionswarteschlange gesendet werden können.  
  
 Wird der MSMQ-Dienst von mehreren Clients, die Nachrichten an verschiedene Zielwarteschlangen senden, gemeinsam verwendet, werden alle von den Clients gesendeten Nachrichten in dieselbe Warteschlange für unzustellbare Nachrichten verschoben. Dies ist nicht immer empfehlenswert. Zum Zweck einer besseren Isolierung verfügen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und MSMQ in [!INCLUDE[wv](../../../../includes/wv-md.md)] über eine benutzerdefinierte Warteschlange für unzustellbare Nachrichten (oder eine anwendungsspezifische Warteschlange für unzustellbare Nachrichten), die der Benutzer zum Speichern der unzustellbaren Nachrichten angeben kann. Daher verwenden unterschiedliche Clients nicht gemeinsam dieselbe Warteschlange für unzustellbare Nachrichten.  
  
 Die Bindung verfügt über zwei wichtige Eigenschaften:  
  
-   `DeadLetterQueue`: Diese Eigenschaft ist eine Enumeration, die angibt, ob eine Warteschlange für unzustellbare Nachrichten angefordert wird. Die Enumeration enthält auch die Art der Warteschlange für unzustellbare Nachrichten, sofern eine Warteschlange angefordert wird. Die Werte sind `None`, `System` und `Custom`. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]die Interpretation dieser Eigenschaften finden Sie unter [behandeln übertragen Nachrichtenfehlern unzustellbare Warteschlangen verwenden](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
  
-   `CustomDeadLetterQueue`: Diese Eigenschaft ist die Uniform Resource Identifier (URI)-Adresse der anwendungsspezifischen Warteschlange für unzustellbare Nachrichten. Dies ist erforderlich, wenn `DeadLetterQueue`.`Custom` wird ausgewählt.  
  
#### <a name="poison-message-handling-properties"></a>Eigenschaften der Behandlung nicht verarbeitbarer Nachrichten  
 Liest der Dienst im Rahmen einer Transaktion Nachrichten aus der Zielwarteschlange, kann die Nachricht vom Dienst aus verschiedenen Gründen möglicherweise nicht verarbeitet werden. Die Nachricht wird anschließend zum erneuten Lesen in die Warteschlange zurückgestellt. Zur Verarbeitung von Nachrichten, die mehrmals nicht zugestellt werden konnten, kann in der Bindung ein Satz Eigenschaften zur Behandlung nicht verarbeitbarer Nachrichten konfiguriert werden. Es gibt vier Eigenschaften: `ReceiveRetryCount`, `MaxRetryCycles`, `RetryCycleDelay` und `ReceiveErrorHandling`. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Diese Eigenschaften finden Sie unter [Behandlung nicht verarbeitbarer Nachrichten](../../../../docs/framework/wcf/feature-details/poison-message-handling.md).  
  
#### <a name="security-properties"></a>Sicherheitseigenschaften  
 MSMQ verfügt über ein eigenes Sicherheitsmodell, zu dem beispielsweise Zugriffssteuerungslisten in einer Warteschlange oder das Senden von authentifizierten Nachrichten gehören. `NetMsmqBinding` macht diese Sicherheitseigenschaften als Teil der Transportsicherheitseinstellungen verfügbar. Die Bindung für Transportsicherheit besitzt zwei Eigenschaften: `MsmqAuthenticationMode` und `MsmqProtectionLevel`. Einstellungen in diesen Eigenschaften sind von der Konfiguration von MSMQ abhängig. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Sichern von Nachrichten mit Transportsicherheit](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md).  
  
 Zusätzlich zur Transportsicherheit kann die eigentliche SOAP-Nachricht mit Nachrichtensicherheit gesichert werden. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Sichern von Nachrichten unter Verwendung der Nachrichtensicherheit](../../../../docs/framework/wcf/feature-details/securing-messages-using-message-security.md).  
  
 `MsmqTransportSecurity` macht ebenfalls zwei Eigenschaften verfügbar, `MsmqEncryptionAlgorithm` und `MsmqHashAlgorithm`. Dabei handelt es sich um Enumerationen verschiedener Algorithmen, die bei Übertragungen zwischen Warteschlangen für die Verschlüsselung von Nachrichten und das Hashing der Signaturen gewählt werden können.  
  
#### <a name="other-properties"></a>Andere Eigenschaften  
 Neben den zuvor genannten Eigenschaften stehen in der Bindung auch andere MSMQ-spezifische Eigenschaften zur Verfügung:  
  
-   `UseSourceJournal`: Eine Eigenschaft, mit der angegeben wird, dass die Führung von Quelljournalen aktiviert ist. Die Führung von Quelljournalen ist ein MSMQ-Feature zum Erfassen von Nachrichten, die erfolgreich von der Übertragungswarteschlange übertragen wurden.  
  
-   `UseMsmqTracing`: Eine Eigenschaft, mit der angegeben wird, dass die MSMQ-Ablaufverfolgung aktiviert ist. Die MSMQ-Ablaufverfolgung sendet Berichtsnachrichten an eine Berichtwarteschlange, wenn eine Nachricht einen Computer, der als Host für einen MSMQ-Warteschlangen-Manager fungiert, verlässt oder bei diesem eingeht.  
  
-   `QueueTransferProtocol`: Eine Enumeration des Protokolls, das für Nachrichtenübertragungen zwischen Warteschlangen verwendet wird. MSMQ implementiert ein systemeigenes Protokoll für Übertragungen zwischen Warteschlangen und ein SOAP-basiertes Protokoll mit der Bezeichnung SOAP Reliable Messaging Protocol (SRMP). SRMP wird bei Verwendung von HTTP-Transport für Übertragungen zwischen Warteschlangen verwendet. Sicheres SRMP wird bei Verwendung von HTTPS für Übertragungen zwischen Warteschlangen verwendet.  
  
-   `UseActiveDirectory`: Ein boolescher Wert, mit dem angegeben wird, ob Active Directory für die Auflösung von Warteschlangenadressen verwendet werden muss. Standardmäßig ist dieser Wert deaktiviert. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][-Endpunkte und die Adressierung von Warteschlangen](../../../../docs/framework/wcf/feature-details/service-endpoints-and-queue-addressing.md).  
  
### <a name="msmqintegrationbinding"></a>MsmqIntegrationBinding  
 `MsmqIntegrationBinding` wird verwendet, wenn ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkt mit einer vorhandenen MSMQ-Anwendung kommunizieren soll, die mit C, C++, COM oder System.Messaging-APIs geschrieben wurde.  
  
 Die Bindungseigenschaften sind für `NetMsmqBinding` identisch. Folgende Unterschiede sind jedoch zu berücksichtigen:  
  
-   Der Vorgangsvertrag für `MsmqIntegrationBinding` ist auf das Verwenden eines Einzelparameters vom Typ <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601> beschränkt, in dem der Typparameter der Texttyp ist.  
  
-   Ein Großteil der Eigenschaften der systemeigenen MSMQ-Nachrichten steht in <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601> zur Verfügung.  
  
-   Die Serialisierung und Deserialisierung des Nachrichtentexts wird durch verfügbare Serialisierungsprogramme wie XML und ActiveX unterstützt.  
  
### <a name="sample-code"></a>Beispielcode  
 Schritt-für-Schritt-Anweisungen zum Schreiben von WCF-Diensten, die MSMQ verwenden, finden Sie in den folgenden Themen:  
  
-   [Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
  
-   [Vorgehensweise: Exchange in der Warteschlange Nachrichten mit WCF-Endpunkten](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
  
 Ein vollständiges Codebeispiel, das die Verwendung von MSMQ in WCF veranschaulicht, finden Sie in den folgenden Themen:  
  
-   [Abgewickelte MSMQ-Bindung](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
  
-   [Volatile-Warteschlangenkommunikation](../../../../docs/framework/wcf/samples/volatile-queued-communication.md)  
  
-   [Warteschlangen für unzustellbare](../../../../docs/framework/wcf/samples/dead-letter-queues.md)  
  
-   [Sitzungen und Warteschlangen](../../../../docs/framework/wcf/samples/sessions-and-queues.md)  
  
-   [Bidirektionale Kommunikation](../../../../docs/framework/wcf/samples/two-way-communication.md)  
  
-   [Transaktive Batchverarbeitung:](../../../../docs/framework/wcf/samples/transacted-batching.md)  
  
-   [SRMP](../../../../docs/framework/wcf/samples/srmp.md)  
  
-   [Nachrichtensicherheit über Message Queuing](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Dienstendpunkte und Adressieren von Warteschlangen](../../../../docs/framework/wcf/feature-details/service-endpoints-and-queue-addressing.md)  
 [Webhosting einer Anwendung mit Queuing](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md)
