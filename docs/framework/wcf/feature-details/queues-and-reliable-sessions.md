---
title: Warteschlangen und zuverlässige Sitzungen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e794d03-141c-45ed-b6b1-6c0e104c1464
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dbbaa432f7f1e137fc6cbd47ecd8e24d9eab97c3
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="queues-and-reliable-sessions"></a>Warteschlangen und zuverlässige Sitzungen
Warteschlangen und zuverlässige Sitzungen sind die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Funktionen, die zuverlässiges Messaging implementieren. In den Themen dieses Abschnitts werden die Funktionen für zuverlässiges Messaging von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erläutert.  
  
 Zuverlässiges Messaging ist die Übertragung von einer zuverlässigen Messagingquelle (bezeichnet als Quelle) an ein zuverlässiges Messagingziel (bezeichnet als Ziel).  
  
 Die wichtigsten Aspekte für zuverlässiges Messaging sind:  
  
-   Übertragen von Zusicherungen für Nachrichten, die unabhängig von einem Fehler bei der Nachrichtenübertragung oder den Transportfehlern von einer Quelle an ein Ziel gesendet werden.  
  
-   Trennen von Quelle und Ziel, was eine unabhängige Wiederherstellung nach einem Fehler von Quelle und Ziel sowie eine zuverlässige Übertragung und Zustellung von Nachrichten ermöglicht, auch wenn die Quelle oder das Ziel nicht verfügbar ist.  
  
 Der Preis eines zuverlässigen Messagings besteht häufig in einer hohen Latenz. Latenz ist die Zeit, die eine Nachricht von der Quelle bis zum Ziel benötigt. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt deshalb die folgenden zuverlässigen Messagingarten bereit:  
  
-   [Zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions.md), welches Angebot zuverlässige Übertragung ohne die Kosten einer hohen Latenz  
  
-   [Warteschlangen in WCF](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md), dem bieten zuverlässige Übertragungen und Trennung zwischen der Quelle und Ziel.  
  
## <a name="reliable-sessions"></a>Zuverlässige Sitzungen  
 Zuverlässige Sitzungen bieten eine zuverlässige End-to-End-Übertragung von Nachrichten zwischen einer Quelle und einem Ziel. Dazu wird das WS-ReliableMessaging-Protokoll unabhängig von der Anzahl oder dem Typ der Vermittler verwendet, durch die die Messagingendpunkte (Quelle und Ziel) getrennt werden. Dies umfasst alle Transportvermittler, die kein SOAP (z.&#160;B. HTTP-Proxys) verwenden, oder Vermittler, die SOAP (z.&#160;B. SOAP-basierte Router oder Brücken) verwenden, und die für die Übertragung von Nachrichten zwischen den Endpunkten erforderlich sind. Zuverlässige Sitzungen verwenden ein Übertragungsfenster im Arbeitsspeicher, um SOAP-Fehler auf Nachrichtenebene zu maskieren und Verbindungen im Falle von Transportfehlern neu herzustellen.  
  
 Zuverlässige Sitzungen bieten zuverlässige Nachrichtenübertragungen mit niedriger Latenz. Sie stellen SOAP-Nachrichten über Proxys oder Vermittler bereit, vergleichbar mit der TCP-Bereitstellung für Pakete über IP-Brücken. Weitere Informationen über zuverlässige Sitzungen finden Sie unter [zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions.md).  
  
### <a name="queues"></a>Warteschlangen  
 Warteschlangen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bieten zuverlässige Übertragungen von Nachrichten und eine Trennung zwischen Quellen und Zielen mit dem Nachteil hoher Latenz. Kommunikation in der Warteschlange in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] beruht auf Message Queuing (auch als MSMQ bekannt).  
  
 MSMQ wird als Option mit Windows zur Verfügung gestellt und wird als NT-Dienst ausgeführt. Er erfasst Nachrichten, die in einer Übertragungswarteschlange der Quelle übertragen und einer Zielwarteschlange zugestellt werden. Die Zielwarteschlange akzeptiert Nachrichten im Auftrag des Ziels für eine spätere Zustellung, wenn das Ziel Nachrichten anfordert. Die MSMQ-Warteschlangen-Manager implementieren ein zuverlässiges Nachrichtenübertragungsprotokoll, damit Nachrichten bei der Übertragung nicht verloren gehen. Das Protokoll kann entweder systemeigen oder SOAP-basiert sein, zum Beispiel das SOAP Reliable Messaging Protocol (SRMP).  
  
 Die Trennung, gekoppelt mit zuverlässigen Nachrichtenübertragungen zwischen Warteschlangen, ermöglicht Anwendungen, die lose miteinander verbunden sind, eine zuverlässige Kommunikation. Im Gegensatz zu zuverlässigen Sitzungen müssen die Quelle und das Ziel nicht zum gleichen Zeitpunkt ausgeführt werden. So werden implizit Szenarien möglich, bei denen Warteschlangen als Lastausgleichsmechanismus verwendet werden, wenn die Geschwindigkeit der Nachrichtenerzeugung und die Geschwindigkeit des Nachrichtenkonsums nicht übereinstimmen. Weitere Informationen zu Warteschlangen finden Sie unter [Warteschlangen in WCF](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Warteschlangen in WCF](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [Queuing in WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [Zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)  
 [Übersicht über zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)
