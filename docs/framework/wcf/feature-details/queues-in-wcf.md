---
title: Warteschlangen in Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: queues [WCF]
ms.assetid: 43008409-1bb4-4bd4-85d7-862c8f10ae20
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d00f8847e64e30b42490f319ea3e1df5e5a1850d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="queues-in-windows-communication-foundation"></a>Warteschlangen in Windows Communication Foundation
Die Themen in diesem Abschnitt erläutern die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Unterstützung für Warteschlangen. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt Warteschlangen, indem Microsoft Message Queuing (vormals MSMQ) als Transport herangezogen wird. Hierdurch werden die folgenden Szenarien möglich:  
  
-   Lose verbundene Anwendungen: Die sendenden Anwendungen können Nachrichten an Warteschlangen senden, unabhängig davon, ob die empfangende Anwendung für die Verarbeitung der Nachricht zur Verfügung steht. Die Warteschlange macht die Verarbeitung unabhängig. So kann die sendende Anwendung Nachrichten mit einer Frequenz an die Warteschlange senden, die unabhängig davon ist, wie schnell die empfangenden Anwendungen die Nachrichten verarbeiten können. Die Gesamtverfügbarkeit des Systems verbessert sich, wenn das Senden von Nachrichten an eine Warteschlange und die Nachrichtenverarbeitung nur lose miteinander verbunden sind.  
  
-   Fehlerisolierung: Anwendungen, die Nachrichten an eine Warteschlange senden oder Nachrichten empfangen, können fehlschlagen, ohne dass dies Auswirkungen auf die anderen Anwendungen hat. Wenn beispielsweise in der empfangenden Anwendung ein Fehler auftritt, kann die sendende Anwendung trotzdem weiterhin Nachrichten an die Warteschlange senden. Sobald der Empfänger wieder einsatzbereit ist, können die Nachrichten in der Warteschlange verarbeitet werden. Durch die Fehlerisolierung werden Zuverlässigkeit und Verfügbarkeit des Systems insgesamt verbessert.  
  
-   Lastenausgleich: Sendende Anwendungen können empfangende Anwendungen mit Nachrichten überlasten. Durch Warteschlangen kann ein Ungleichgewicht an gesendeten und verarbeiteten Nachrichten ausgeglichen werden, sodass der Empfänger nicht mit Nachrichten überschwemmt wird.  
  
-   Getrennte Vorgänge: Die Vorgänge des Sendens, Empfangens und Verarbeitens können bei der Kommunikation über Netzwerke mit hoher Latenz oder eingeschränkter Verfügbarkeit, wie dies zum Beispiel bei mobilen Geräten der Fall ist, voneinander getrennt werden. Warteschlangen ermöglichen die Fortsetzung dieser Vorgänge, selbst wenn die Endpunkte nicht erreichbar sind. Sobald die Verbindung wiederhergestellt ist, leitet die Warteschlange die Nachrichten an die empfangende Anwendung weiter.  
  
 Wenn Sie die Warteschlangenfunktion in einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendung einsetzen möchten, können Sie eine Standardbindung verwenden oder Ihre eigene Bindung erstellen, falls die Standardbindungen Ihre Anforderungen nicht erfüllen. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]relevante standardbindungen und auswählen, finden Sie in [Vorgehensweise: Exchange-Nachrichten mit WCF-Endpunkten und Message Queuing-Anwendungen](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Erstellung benutzerdefinierter Bindungen finden Sie unter [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Nachrichtenwarteschlangen (Übersicht)](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 Eine Übersicht über die Konzepte des Message Queuings (Nachrichtenwarteschlangen).  
  
 [Warteschlangen in WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 Eine Übersicht über die Warteschlangenunterstützung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Vorgehensweise: Exchange in der Warteschlange Nachrichten mit WCF-Endpunkten](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 Erläutert die Verwendung der <xref:System.ServiceModel.NetMsmqBinding>-Klasse für die Kommunikation zwischen einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client und einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst.  
  
 [Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 Erläutert die Verwendung von <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> für die Kommunikation zwischen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und Message Queuing-Anwendungen.  
  
 [Gruppierung in der Warteschlange Nachrichten in einer Sitzung](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md)  
 Erläutert, wie Nachrichten in einer Warteschlange gruppiert werden können, um die Verarbeitung zusammengehöriger Nachrichten durch eine einzelne Empfängeranwendung zu erleichtern.  
  
 [Batchverarbeitung von Nachrichten in einer Transaktion](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md)  
 Erläutert die Batchverarbeitung von Nachrichten in einer Transaktion.  
  
 [Behandeln von Nachrichtenübertragungsfehlern mithilfe von unzustellbare Warteschlangen](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
 Erläutert die Handhabung von Nachrichtenübertragungen und Sendefehlern mithilfe von Warteschlangen für unzustellbare Nachrichten und beschreibt, wie Nachrichten in der Warteschlange für unzustellbare Nachrichten verarbeitet werden.  
  
 [Die Handhabung beschädigter Nachrichten](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)  
 Erläutert den Umgang mit beschädigten (nicht verarbeitbaren) Nachrichten, das heißt Nachrichten, die auch nach der maximalen Anzahl von Versuchen nicht an die Empfängeranwendung gesendet werden konnten.  
  
 [Unterschiede bei den Warteschlangenfunktionen in Windows Vista, WindowsServer 2003 und Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)  
 Bietet eine Übersicht über die Unterschiede bei den Warteschlangenfunktionen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zwischen [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
 [Sichern von Nachrichten mit Transportsicherheit](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)  
 Beschreibt, wie Nachrichten in Warteschlangen mithilfe der Transportsicherheit geschützt werden können.  
  
 [Sichern von Nachrichten unter Verwendung der Nachrichtensicherheit](../../../../docs/framework/wcf/feature-details/securing-messages-using-message-security.md)  
 Beschreibt, wie Nachrichten in Warteschlangen mithilfe der Nachrichtensicherheit geschützt werden können.  
  
 [Problembehandlung bei Nachrichtenwarteschlangen](../../../../docs/framework/wcf/feature-details/troubleshooting-queued-messaging.md)  
 Beschreibt, wie allgemeine Warteschlangenprobleme behoben werden können.  
  
 [Bewährte Methoden für die Warteschlangenkommunikation](../../../../docs/framework/wcf/feature-details/best-practices-for-queued-communication.md)  
 Stellt bewährte Methoden für die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Kommunikation unter Verwendung von Warteschlangen vor.  
  
## <a name="see-also"></a>Siehe auch  
 [Message Queuing](http://msdn.microsoft.com/en-us/ff917e87-05d5-478f-9430-0f560675ece1)
