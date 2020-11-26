---
title: Warteschlangen und zuverlässige Sitzungen
ms.date: 03/30/2017
ms.assetid: 7e794d03-141c-45ed-b6b1-6c0e104c1464
ms.openlocfilehash: db47838db1608dac4e0fe22252795b6dd33a0b6e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244690"
---
# <a name="queues-and-reliable-sessions"></a>Warteschlangen und zuverlässige Sitzungen

Warteschlangen und zuverlässige Sitzungen sind die Windows Communication Foundation (WCF)-Features, die zuverlässiges Messaging implementieren. In den Themen in diesem Abschnitt werden die Features für zuverlässiges WCF-Messaging erläutert.  
  
 Zuverlässiges Messaging ist die Übertragung von einer zuverlässigen Messagingquelle (bezeichnet als Quelle) an ein zuverlässiges Messagingziel (bezeichnet als Ziel).  
  
 Die wichtigsten Aspekte für zuverlässiges Messaging sind:  
  
- Übertragen von Zusicherungen für Nachrichten, die unabhängig von einem Fehler bei der Nachrichtenübertragung oder den Transportfehlern von einer Quelle an ein Ziel gesendet werden.  
  
- Trennen von Quelle und Ziel, was eine unabhängige Wiederherstellung nach einem Fehler von Quelle und Ziel sowie eine zuverlässige Übertragung und Zustellung von Nachrichten ermöglicht, auch wenn die Quelle oder das Ziel nicht verfügbar ist.  
  
 Der Preis eines zuverlässigen Messagings besteht häufig in einer hohen Latenz. Latenz ist die Zeit, die eine Nachricht von der Quelle bis zum Ziel benötigt. WCF stellt daher die folgenden Typen von zuverlässigem Messaging bereit:  
  
- [Zuverlässige Sitzungen](reliable-sessions.md), die eine zuverlässige Übertragung ohne hohe Latenz Kosten bieten  
  
- [Warteschlangen in WCF](queues-in-wcf.md), die sowohl zuverlässige Übertragungen als auch eine Trennung zwischen der Quelle und dem Ziel bieten.  
  
## <a name="reliable-sessions"></a>Zuverlässige Sitzungen  

 Zuverlässige Sitzungen bieten eine zuverlässige End-to-End-Übertragung von Nachrichten zwischen einer Quelle und einem Ziel. Dazu wird das WS-ReliableMessaging-Protokoll unabhängig von der Anzahl oder dem Typ der Vermittler verwendet, durch die die Messagingendpunkte (Quelle und Ziel) getrennt werden. Dies umfasst alle Transportvermittler, die kein SOAP (z.&#160;B. HTTP-Proxys) verwenden, oder Vermittler, die SOAP (z.&#160;B. SOAP-basierte Router oder Brücken) verwenden, und die für die Übertragung von Nachrichten zwischen den Endpunkten erforderlich sind. Zuverlässige Sitzungen verwenden ein Übertragungsfenster im Arbeitsspeicher, um SOAP-Fehler auf Nachrichtenebene zu maskieren und Verbindungen im Falle von Transportfehlern neu herzustellen.  
  
 Zuverlässige Sitzungen bieten zuverlässige Nachrichtenübertragungen mit niedriger Latenz. Sie stellen SOAP-Nachrichten über Proxys oder Vermittler bereit, vergleichbar mit der TCP-Bereitstellung für Pakete über IP-Brücken. Weitere Informationen zu zuverlässigen Sitzungen finden Sie unter [zuverlässige Sitzungen](reliable-sessions.md).  
  
## <a name="queues"></a>Warteschlangen  

 Warteschlangen in WCF bieten zuverlässige Übertragungen von Nachrichten und eine Trennung zwischen Quellen und Zielen, um hohe Latenzzeiten zu verursachen. Die WCF-Warteschlangen Kommunikation baut auf Message Queuing (auch bekannt als MSMQ) auf.  
  
 MSMQ wird als Option mit Windows zur Verfügung gestellt und wird als NT-Dienst ausgeführt. Er erfasst Nachrichten, die in einer Übertragungswarteschlange der Quelle übertragen und einer Zielwarteschlange zugestellt werden. Die Zielwarteschlange akzeptiert Nachrichten im Auftrag des Ziels für eine spätere Zustellung, wenn das Ziel Nachrichten anfordert. Die MSMQ-Warteschlangen-Manager implementieren ein zuverlässiges Nachrichtenübertragungsprotokoll, damit Nachrichten bei der Übertragung nicht verloren gehen. Das Protokoll kann entweder systemeigen oder SOAP-basiert sein, zum Beispiel das SOAP Reliable Messaging Protocol (SRMP).  
  
 Die Trennung, gekoppelt mit zuverlässigen Nachrichtenübertragungen zwischen Warteschlangen, ermöglicht Anwendungen, die lose miteinander verbunden sind, eine zuverlässige Kommunikation. Im Gegensatz zu zuverlässigen Sitzungen müssen die Quelle und das Ziel nicht zum gleichen Zeitpunkt ausgeführt werden. So werden implizit Szenarien möglich, bei denen Warteschlangen als Lastausgleichsmechanismus verwendet werden, wenn die Geschwindigkeit der Nachrichtenerzeugung und die Geschwindigkeit des Nachrichtenkonsums nicht übereinstimmen. Weitere Informationen zu Warteschlangen finden Sie unter [Warteschlangen in WCF](queues-in-wcf.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Warteschlangen in WCF](queues-in-wcf.md)
- [Warteschlangen in WCF](queuing-in-wcf.md)
- [Zuverlässige Sitzungen](reliable-sessions.md)
- [Übersicht über zuverlässige Sitzungen](reliable-sessions-overview.md)
