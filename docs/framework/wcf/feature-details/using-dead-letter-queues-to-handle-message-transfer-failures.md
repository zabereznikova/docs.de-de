---
title: "Verwenden von Warteschlangen f&#252;r unzustellbare Nachrichten zur Handhabung von Nachrichten&#252;bertragungsfehlern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9e891c6a-d960-45ea-904f-1a00e202d61a
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Verwenden von Warteschlangen f&#252;r unzustellbare Nachrichten zur Handhabung von Nachrichten&#252;bertragungsfehlern
Die Zustellung von in der Warteschlange stehenden Nachrichten kann fehlschlagen. Diese fehlgeschlagenen Nachrichten werden in einer Warteschlange für unzustellbare Nachrichten aufgezeichnet. Das Fehlschlagen der Zustellung kann beispielsweise durch Netzwerkfehler, eine gelöschte Warteschlange, eine volle Warteschlange, einen Authentifizierungsfehler oder eine zu späte Zustellung verursacht werden.  
  
 In der Warteschlange stehende Nachrichten können über lange Zeit hinweg in der Warteschlange verbleiben, wenn die empfangende Anwendung sie nicht umgehend aus der Warteschlange liest. Dieses Verhalten ist möglicherweise nicht für zeitempfindliche Nachrichten geeignet. Zeitempfindliche Nachrichten verfügen über eine Eigenschaft für die Gültigkeitsdauer (Time to Live, TTL), die in der Bindung der Warteschlange festgelegt ist und angibt, wie lange die Nachrichten in der Warteschlange verbleiben können, bevor sie ablaufen. Abgelaufene Nachrichten werden an eine spezielle Warteschlange gesendet und zwar an die Warteschlange für unzustellbare Nachrichten. Nachrichten können auch aus anderen Gründen in einer Warteschlange für unzustellbare Nachrichten platziert werden, z. B. aufgrund des Überschreitens eines Warteschlangenkontingents oder aufgrund eines Authentifizierungsfehlers.  
  
 Im Allgemeinen schreiben Anwendungen Entschädigungslogik, um Nachrichten aus der Warteschlange für unzustellbare Nachrichten sowie Fehlerursachen zu lesen. Die Entschädigungslogik hängt von der Ursache des Fehlers ab. Im Falle eines Authentifizierungsfehlers können Sie beispielsweise das an die Nachricht angehängte Zertifikat korrigieren und die Nachricht anschließend erneut senden. Wenn eine Zustellung fehlgeschlagen ist, weil das Zielwarteschlangenkontingent nicht erreicht wurde, können Sie erneut einen Zustellungsversuch vornehmen, in der Hoffnung, dass das Kontingentproblem behoben wurde.  
  
 Die meisten Warteschlangensysteme haben eine systemweite Warteschlange für unzustellbare Nachrichten, in der alle fehlgeschlagenen Nachrichten dieses Systems gespeichert werden. Message Queuing (MSMQ) bietet zwei systemweite Warteschlangen für unzustellbare Nachrichten: eine transaktionale systemweite Warteschlange für unzustellbare Nachrichten, die Nachrichten speichert, die nicht an die transaktionale Warteschlange gesendet werden konnten, und eine nicht transaktionale Warteschlange für unzustellbare Nachrichten, die Nachrichten speichert, die nicht an die nicht transaktionale Warteschlange gesendet werden konnten. Wenn zwei Clients Nachrichten an verschiedene Dienste senden und deshalb verschiedene Warteschlangen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] denselben MSMQ-Dienst zum Senden verwenden, können möglicherweise verschiedene Nachrichten in der Systemwarteschlange für unzustellbare Nachrichten enthalten sein. Dies ist nicht immer optimal. In vielen Fällen (z. B. im Hinblick auf die Sicherheit) ist es nicht ratsam, dass ein Client die Nachrichten eines anderen Clients aus der Warteschlange für unzustellbare Nachrichten liest. Bei einer gemeinsam genutzten Warteschlange für unzustellbare Nachrichten müssen die Clients darüber hinaus die Warteschlange nach von ihnen gesendeten Nachrichten durchsuchen, was je nach Anzahl der Nachrichten in der Warteschlange für unzustellbare Nachrichten viel zu aufwendig sein kann. Daher müssen Sie in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `NetMsmqBinding`, `MsmqIntegrationBinding,` und MSMQ auf [!INCLUDE[wv](../../../../includes/wv-md.md)] eine benutzerdefinierte Warteschlange für unzustellbare (auch als anwendungsspezifische Warteschlange für unzustellbare Nachrichten bezeichnet) bereit.  
  
 Die benutzerdefinierte Warteschlange für unzustellbare Nachrichten ermöglicht eine Isolation zwischen Clients, die den gleichen MSMQ-Dienst verwenden, um Nachrichten zu senden.  
  
 Auf [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] stellt [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] eine systemweite Warteschlange für unzustellbare Nachrichten für alle in der Warteschlange stehenden Clientanwendungen bereit. Auf [!INCLUDE[wv](../../../../includes/wv-md.md)] stellt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] eine Warteschlange für unzustellbare Nachrichten für jede in der Warteschlange stehende Clientanwendung bereit.  
  
## <a name="specifying-use-of-the-dead-letter-queue"></a>Angeben der Verwendung der Warteschlange für unzustellbare Nachrichten  
 Eine Warteschlange für unzustellbare Nachrichten befindet sich im Warteschlangen-Manager der sendenden Anwendung. Sie speichert Nachrichten, die abgelaufen sind oder nicht zugestellt werden konnten.  
  
 Die Bindung weist die folgenden Eigenschaften für eine Warteschlange für unzustellbare Nachrichten auf:  
  
-   <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A>  
  
-   <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>  
  
## <a name="reading-messages-from-the-dead-letter-queue"></a>Lesen von Nachrichten aus der Warteschlange für unzustellbare Nachrichten  
 Eine Anwendung, die Nachrichten aus einer Warteschlange für unzustellbare Nachrichten liest, ähnelt einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst, der aus einer Anwendungswarteschlange liest, wobei folgende geringfügige Unterschiede zu beachten sind:  
  
-   Zum Lesen von Nachrichten aus einer transaktionalen Systemwarteschlange für unzustellbare Nachrichten muss der URI (Uniform Resource Identifier) folgendes Format aufweisen: net.msmq://localhost/system$;DeadXact.  
  
-   Zum Lesen von Nachrichten aus einer nicht transaktionalen Systemwarteschlange für unzustellbare Nachrichten muss der URI folgendes Format aufweisen: net.msmq://localhost/system$;DeadLetter.  
  
-   Um eine benutzerdefinierte Warteschlange für unzustellbare Nachrichten gelesen werden, muss der URI von der Form: Net.msmq://localhost/private/*Custom-Dlq-Name*>, *Custom-Dlq-Name* ist der Name der benutzerdefinierten Warteschlange für unzustellbare Nachrichten.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]zur Adressierung von Warteschlangen finden Sie unter [Dienstendpunkte und Adressieren von Warteschlangen](../../../../docs/framework/wcf/feature-details/service-endpoints-and-queue-addressing.md).  
  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Stapel des Empfängers gleicht Adressen, die der Dienst überwacht, mit der Adresse auf der Nachricht ab. Wenn die Adressen übereinstimmen, wird die Nachricht weitergeleitet; stimmen sie nicht überein, wird die Nachricht nicht weitergeleitet. Dies kann Probleme beim Lesen aus der Warteschlange für unzustellbare Nachrichten verursachen, da die Nachrichten in der Warteschlange in der Regel an den Dienst und nicht an den Dienst der Warteschlange für unzustellbare Nachrichten adressiert sind. Daher muss der Dienst, der aus der Warteschlange für unzustellbare Nachrichten liest, einen Adressfilter `ServiceBehavior` installieren, der den Stapel auffordert, alle Nachrichten in der Warteschlange unabhängig vom Adressaten abzugleichen. Sie müssen insbesondere hinzufügen ein `ServiceBehavior` mit der <xref:System.ServiceModel.AddressFilterMode> Parameter an den Dienst aus der Warteschlange für unzustellbare Nachrichten liest.  
  
## <a name="poison-message-handling-from-the-dead-letter-queue"></a>Die Handhabung von beschädigten Nachrichten aus der Warteschlange für unzustellbare Nachrichten  
 Die Handhabung beschädigter Nachrichten ist für Warteschlangen für unzustellbare Nachrichten verfügbar. Dabei gelten bestimmte Voraussetzungen. Da beim Lesen aus der Systemwarteschlange für unzustellbare Nachrichten keine untergeordneten Warteschlangen erstellt werden können, kann `ReceiveErrorHandling` nicht auf `Move` festgelegt werden. Beachten Sie, dass Sie beim Lesen aus einer benutzerdefinierten Warteschlange für unzustellbare Nachrichten untergeordnete Warteschlangen nutzen können und dass `Move` daher eine gültige Disposition für die beschädigte Nachricht ist.  
  
 Wenn `ReceiveErrorHandling` beim Lesen aus der benutzerdefinierten Warteschlange für unzustellbare Nachrichten auf `Reject` eingestellt ist, wird die beschädigte Nachricht in der Systemwarteschlange für unzustellbare Nachrichten platziert. Beim Lesen aus der Systemwarteschlange für unzustellbare Nachrichten wird die Nachricht abgelegt (gelöscht). Ein Ausschluss aus einer Systemwarteschlange für unzustellbare Nachrichten in MSMQ legt die Nachricht ab (löscht sie).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie eine Warteschlange für unzustellbare Nachrichten erstellt und für die Verarbeitung abgelaufener Nachrichten verwendet wird. Das Beispiel basiert auf dem Beispiel in [wie: Exchange in der Warteschlange Nachrichten mit WCF-Endpunkten](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md). Im folgenden Beispiel wird dargestellt, wie der Clientcode auf den Dienst für die Auftragsverarbeitung geschrieben wird, der für jede Anwendung eine Warteschlange für unzustellbare Nachrichten verwendet. Im Beispiel wird auch gezeigt, wie Nachrichten aus der Warteschlange für unzustellbare Nachrichten verarbeitet werden.  
  
 Der folgende Code ist für einen Client, der eine Warteschlange für unzustellbare Nachrichten für jede Anwendung angibt.  
  
 [!code-csharp[S_DeadLetter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_deadletter/cs/client.cs#1)]
 [!code-vb[S_DeadLetter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_deadletter/vb/client.vb#1)]  
  
 Der folgende Code ist für die Clientkonfigurationsdatei.  
  
  
  
 Der folgende Code ist für einen Dienst, der Nachrichten aus einer Warteschlange für unzustellbare Nachrichten verarbeitet.  
  
 [!code-csharp[S_DeadLetter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_deadletter/cs/dlservice.cs#3)]
 [!code-vb[S_DeadLetter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_deadletter/vb/dlservice.vb#3)]  
  
 Der folgende Code ist für die Dienstkonfigurationsdatei für die Warteschlange für unzustellbare Nachrichten.  
  
  
  
## <a name="see-also"></a>Siehe auch  
 [Nachrichtenwarteschlangen (Übersicht)](../../../../docs/framework/wcf/feature-details/queues-overview.md)   
 [Gewusst wie: Austauschen in einer Warteschlange Nachrichten mit WCF-Endpunkten](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)   
 [Nicht verarbeitbare Nachrichten](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)