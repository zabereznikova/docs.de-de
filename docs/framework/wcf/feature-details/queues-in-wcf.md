---
title: Warteschlangen in Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- queues [WCF]
ms.assetid: 43008409-1bb4-4bd4-85d7-862c8f10ae20
ms.openlocfilehash: d63b03e519484ad6ec90b4267a49b77738593e45
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244651"
---
# <a name="queues-in-windows-communication-foundation"></a>Warteschlangen in Windows Communication Foundation

In den Themen in diesem Abschnitt wird Windows Communication Foundation (WCF)-Unterstützung für Warteschlangen beschrieben. WCF bietet Unterstützung für Warteschlangen, indem Microsoft Message Queuing (früher als MSMQ bezeichnet) als Transport genutzt wird, und ermöglicht die folgenden Szenarien:  
  
- Lose verbundene Anwendungen: Die sendenden Anwendungen können Nachrichten an Warteschlangen senden, unabhängig davon, ob die empfangende Anwendung für die Verarbeitung der Nachricht zur Verfügung steht. Die Warteschlange macht die Verarbeitung unabhängig. So kann die sendende Anwendung Nachrichten mit einer Frequenz an die Warteschlange senden, die unabhängig davon ist, wie schnell die empfangenden Anwendungen die Nachrichten verarbeiten können. Die Gesamtverfügbarkeit des Systems verbessert sich, wenn das Senden von Nachrichten an eine Warteschlange und die Nachrichtenverarbeitung nur lose miteinander verbunden sind.  
  
- Fehlerisolierung: Anwendungen, die Nachrichten an eine Warteschlange senden oder Nachrichten empfangen, können fehlschlagen, ohne dass dies Auswirkungen auf die anderen Anwendungen hat. Wenn beispielsweise in der empfangenden Anwendung ein Fehler auftritt, kann die sendende Anwendung trotzdem weiterhin Nachrichten an die Warteschlange senden. Sobald der Empfänger wieder einsatzbereit ist, können die Nachrichten in der Warteschlange verarbeitet werden. Durch die Fehlerisolierung werden Zuverlässigkeit und Verfügbarkeit des Systems insgesamt verbessert.  
  
- Lastenausgleich: Sendende Anwendungen können empfangende Anwendungen mit Nachrichten überlasten. Durch Warteschlangen kann ein Ungleichgewicht an gesendeten und verarbeiteten Nachrichten ausgeglichen werden, sodass der Empfänger nicht mit Nachrichten überschwemmt wird.  
  
- Getrennte Vorgänge: Die Vorgänge des Sendens, Empfangens und Verarbeitens können bei der Kommunikation über Netzwerke mit hoher Latenz oder eingeschränkter Verfügbarkeit, wie dies zum Beispiel bei mobilen Geräten der Fall ist, voneinander getrennt werden. Warteschlangen ermöglichen die Fortsetzung dieser Vorgänge, selbst wenn die Endpunkte nicht erreichbar sind. Sobald die Verbindung wiederhergestellt ist, leitet die Warteschlange die Nachrichten an die empfangende Anwendung weiter.  
  
 Wenn Sie die Warteschlangen Funktion in einer WCF-Anwendung verwenden möchten, können Sie eine der Standard Bindungen verwenden, oder Sie können eine benutzerdefinierte Bindung erstellen, wenn eine der Standard Bindungen Ihre Anforderungen nicht erfüllt. Weitere Informationen über relevante Standard Bindungen und deren Auswahl finden Sie unter Vorgehens [Weise: Austauschen von Nachrichten mit WCF-Endpunkten und Message Queuing Anwendungen](how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md). Weitere Informationen zum Erstellen benutzerdefinierter Bindungen finden Sie unter [Benutzerdefinierte Bindungen](../extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Warteschlangenübersicht](queues-overview.md)  
 Eine Übersicht über die Konzepte des Message Queuings (Nachrichtenwarteschlangen).  
  
 [Warteschlangen in WCF](queuing-in-wcf.md)  
 Eine Übersicht über die Unterstützung von WCF-Warteschlangen.  
  
 [Vorgehensweise: Austauschen von Nachrichten in einer Warteschlange mit WCF-Endpunkten](how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 Erläutert, wie die- <xref:System.ServiceModel.NetMsmqBinding> Klasse für die Kommunikation zwischen einem WCF-Client und einem WCF-Dienst verwendet wird.  
  
 [Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen](how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 Erläutert die Verwendung <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> von für die Kommunikation zwischen WCF-und Message Queuing-Anwendungen.  
  
 [Gruppieren von Nachrichten in der Warteschlange einer Sitzung](grouping-queued-messages-in-a-session.md)  
 Erläutert, wie Nachrichten in einer Warteschlange gruppiert werden können, um die Verarbeitung zusammengehöriger Nachrichten durch eine einzelne Empfängeranwendung zu erleichtern.  
  
 [Batchverarbeitung von Nachrichten in einer Transaktion](batching-messages-in-a-transaction.md)  
 Erläutert die Batchverarbeitung von Nachrichten in einer Transaktion.  
  
 [Verwenden von Warteschlangen für unzustellbare Nachrichten zur Handhabung von Nachrichtenübertragungsfehlern](using-dead-letter-queues-to-handle-message-transfer-failures.md)  
 Erläutert die Handhabung von Nachrichtenübertragungen und Sendefehlern mithilfe von Warteschlangen für unzustellbare Nachrichten und beschreibt, wie Nachrichten in der Warteschlange für unzustellbare Nachrichten verarbeitet werden.  
  
 [Behandlung nicht verarbeitbarer Nachrichten](poison-message-handling.md)  
 Erläutert den Umgang mit beschädigten (nicht verarbeitbaren) Nachrichten, das heißt Nachrichten, die auch nach der maximalen Anzahl von Versuchen nicht an die Empfängeranwendung gesendet werden konnten.  
  
 [Unterschiede zwischen den Warteschlangenfunktionen in Windows Vista, Windows Server 2003 und Windows XP](diff-in-queue-in-vista-server-2003-windows-xp.md)  
 Fasst die Unterschiede in der WCF-Warteschlangen Funktion zwischen Windows Vista, Windows Server 2003 und Windows XP zusammen.  
  
 [Sichern von Nachrichten mit Transportsicherheit](securing-messages-using-transport-security.md)  
 Beschreibt, wie Nachrichten in Warteschlangen mithilfe der Transportsicherheit geschützt werden können.  
  
 [Sichern von Nachrichten mithilfe der Nachrichtensicherheit](securing-messages-using-message-security.md)  
 Beschreibt, wie Nachrichten in Warteschlangen mithilfe der Nachrichtensicherheit geschützt werden können.  
  
 [Problembehandlung bei Nachrichtenwarteschlangen](troubleshooting-queued-messaging.md)  
 Beschreibt, wie allgemeine Warteschlangenprobleme behoben werden können.  
  
 [Bewährte Methoden für die Kommunikation unter Verwendung von Warteschlangen](best-practices-for-queued-communication.md)  
 Erläutert bewährte Methoden für die Verwendung der WCF-Warteschlangen Kommunikation.  
