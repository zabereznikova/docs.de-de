---
title: Unterschiede zwischen den Warteschlangenfunktionen in Windows Vista, Windows Server 2003 und Windows XP
ms.date: 03/30/2017
helpviewer_keywords:
- queues [WCF], differences in operating systems
ms.assetid: aa809d93-d0a3-4ae6-a726-d015cca37c04
ms.openlocfilehash: 694d7af8e6e869a7a21a3414be6c69cf9f5e7c8f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626996"
---
# <a name="differences-in-queuing-features-in-windows-vista-windows-server-2003-and-windows-xp"></a>Unterschiede zwischen den Warteschlangenfunktionen in Windows Vista, Windows Server 2003 und Windows XP
In diesem Thema werden die Unterschiede in der Windows Communication Foundation (WCF)-Warteschlangenfunktion zwischen zusammengefasst [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], und [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
## <a name="application-specific-dead-letter-queue"></a>Anwendungsspezifische Warteschlange für unzustellbare Nachrichten  
 In der Warteschlange stehende Nachrichten können eine unbegrenzte Zeit hinweg in der Warteschlange verbleiben, wenn die empfangende Anwendung sie nicht umgehend aus der Warteschlange liest. Dieses Verhalten ist bei zeitempfindlichen Nachrichten möglicherweise nicht empfehlenswert. Für zeitempfindliche Nachrichten ist in der Bindung, die sich in der Warteschlange befindet, eine `TimeToLive`-Eigenschaft festgelegt. Diese Eigenschaft gibt an, wie lang die Nachrichten in der Warteschlange sein können, bevor sie ablaufen. Abgelaufene Nachrichten werden an eine spezielle Warteschlange gesendet und zwar an die Warteschlange für unzustellbare Nachrichten. Nachrichten können auch aus anderen Gründen in eine Warteschlange für unzustellbare Meldungen verschoben werden, z.&amp;#160;B. aufgrund des Überschreitens eines Warteschlangenkontingents oder wegen eines Authentifizierungsfehlers.  
  
 In der Regel gibt es eine systemweite Warteschlange für nicht zustellbare Nachrichten für alle Anwendungen, die denselben Warteschlangen-Manager verwenden. Eine Warteschlange für nicht zustellbare Nachrichten für jede einzelne Anwendung ermöglicht eine bessere Isolation zwischen den Anwendungen, die mit Warteschlangen arbeiten und denselben Warteschlangen-Manager verwenden. Dabei können für die Anwendungen eigene, anwendungsspezifische Warteschlangen für nicht zustellbare Nachrichten angegeben werden. Eine Anwendung, die eine Warteschlange für unzustellbare Nachrichten gemeinsam mit anderen Anwendungen nutzt, muss die Wartschlangen nach den Nachrichten durchsuchen, die für sie bestimmt sind. Bei einer anwendungsspezifischen Warteschlange für unzustellbare Nachrichten ist sichergestellt, dass alle Nachrichten in der Warteschlange diese Anwendung betreffen.  
  
 [!INCLUDE[wv](../../../../includes/wv-md.md)] unterstützt anwendungsspezifische Warteschlangen für unzustellbare Nachrichten. Anwendungsspezifische Warteschlangen für unzustellbare Nachrichten sind in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] nicht verfügbar. Anwendungen müssen hier die systemweite Warteschlange für unzustellbare Nachrichten verwenden.  
  
## <a name="poison-message-handling"></a>Behandlung nicht verarbeitbarer Nachrichten  
 Eine nicht verarbeitbare Nachricht ist eine Nachricht, die auch nach der maximalen Anzahl von Zustellversuchen nicht an die empfangende Anwendung übermittelt werden konnte. Diese Situation kann auftreten, wenn eine Anwendung, die Nachrichten aus einer Transaktionswarteschlange liest, die Nachricht aufgrund von Fehlern nicht sofort verarbeiten kann. Wenn die Anwendung die Transaktion abbricht, in der die in der Warteschlange stehende Nachricht empfangen wurde, wird die Nachricht an die Warteschlange zurückgegeben. Die Anwendung versucht dann, die Nachricht in einer neuen Transaktion abzurufen. Wenn das Problem, das den Fehler verursacht, nicht korrigiert wird, kann die empfangende Anwendung in einer Schleife hängen bleiben, in der sie dieselbe Nachricht immer wieder empfängt und abbricht, bis die maximale Anzahl der Zustellungsversuche überschritten wird, und so entsteht eine nicht verarbeitbare Nachricht.  
  
 Die folgenden Hauptunterschiede zwischen dem Message Queuing (MSMQ) in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] sind für die Behandlung nicht verarbeitbarer Nachrichten relevant:  
  
- MSMQ unter [!INCLUDE[wv](../../../../includes/wv-md.md)] unterstützt untergeordnete Warteschlangen, während [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] keine untergeordneten Warteschlangen unterstützen. Untergeordnete Warteschlangen werden zur Behandlung nicht verarbeitbarer Nachrichten verwendet. Die Wiederholungswarteschlangen und die Warteschlange für potenziell schädliche Nachrichten sind untergeordnete Warteschlangen der Anwendungswarteschlange, die basierend auf den Einstellungen für die Behandlung nicht verarbeitbarer Nachrichten erstellt wird. Die Eigenschaft `MaxRetryCycles` bestimmt, wie viele untergeordnete Wiederholungwarteschlangen erstellt werden sollen. Deshalb werden bei der Ausführung unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] die `MaxRetryCycles` ignoriert, und `ReceiveErrorHandling.Move` wird nicht zugelassen.  
  
- MSMQ in [!INCLUDE[wv](../../../../includes/wv-md.md)] unterstützt die negative Bestätigung, [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] hingegen nicht. Eine negative Bestätigung vom empfangenden Warteschlangen-Manager bewirkt, dass der sendende Warteschlangen-Manager die abgelehnte Nachricht in die Warteschlange für unzustellbare Nachrichten einstellt. Damit ist `ReceiveErrorHandling.Reject` in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] nicht zulässig.  
  
- MSMQ in [!INCLUDE[wv](../../../../includes/wv-md.md)] unterstützt eine Nachrichteneigenschaft, die zählt, wie oft die Nachrichtenzustellung versucht wird. Diese Abbruchanzahleigenschaft ist in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] nicht verfügbar. WCF verwaltet die abbruchanzahl im Arbeitsspeicher, sodass es möglich, dass diese Eigenschaft nicht auf einen genauen Wert enthalten kann, wenn dieselbe Nachricht von mehr als ein WCF-Dienst in einer Webfarm gelesen wird.  
  
## <a name="remote-transactional-read"></a>Remote durchgeführte Lesevorgänge  
 MSMQ in [!INCLUDE[wv](../../../../includes/wv-md.md)] unterstützt remote durchgeführte Lesevorgänge. Dabei kann eine Anwendung, die aus einer Warteschlange liest, auf einem anderen Computer ausgeführt werden als dem Computer, auf dem die Warteschlange gehostet wird. Dies ermöglicht, dass eine Dienstefarm aus einer zentralen Warteschlange lesen kann, was den Gesamtdurchsatz im System erhöht. Darüber hinaus wird sichergestellt, dass im Fall eines Fehlers während des Lesens oder Verarbeitens einer Nachricht ein Rollback der Transaktion erfolgt und die Nachricht zur späteren Verarbeitung in der Warteschlange verbleibt.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Warteschlangen für unzustellbare Nachrichten zur Handhabung von Nachrichtenübertragungsfehlern](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)
- [Behandlung nicht verarbeitbarer Nachrichten](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)
