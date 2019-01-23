---
title: Zuverlässige Dienste
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], reliable messaging
- Windows Communication Foundation [WCF], reliable messaging
- WCF [WCF], reliable sessions
- Windows Communication Foundation [WCF], reliable sessions
- service contracts [WCF], reliable services
ms.assetid: 07814ed0-0775-47f2-987b-d8134fdd5099
ms.openlocfilehash: a3a53cb26ffb0e5934982c1c9f367115177b9b59
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559397"
---
# <a name="reliable-services"></a>Zuverlässige Dienste
Warteschlangen und zuverlässige Sitzungen sind die Windows Communication Foundation (WCF)-Funktionen, die zuverlässiges messaging implementieren. In diesem Thema wird erläutert, die zuverlässigen Messagingfunktionen von WCF.  
  
 *Zuverlässiges messaging* wird gezeigt, wie einer zuverlässigen messagingquelle (bezeichnet die *Quelle*) überträgt die Nachrichten zuverlässig an ein zuverlässiges messagingziel (wird aufgerufen, die *Ziel*).  
  
 Zuverlässiges Messaging führt die folgenden Funktionen aus:  
  
-   Überträgt Zusicherungen für Nachrichten, die unabhängig von der Nachrichtenübertragung oder den Transportfehlern von einer Quelle an ein Ziel gesendet werden.  
  
-   Trennt die Quelle und das Ziel voneinander. So ist eine unabhängige Wiederherstellung nach einem Fehler von Quelle und Ziel sowie eine zuverlässige Übertragung und Zustellung von Nachrichten möglich, auch wenn die Quelle oder das Ziel nicht verfügbar ist.  
  
 Der Preis eines zuverlässigen Messagings besteht häufig in einer hohen Latenz. *Latenz* ist die Zeit, die es, für die Nachricht dauert an das Ziel aus der Quelle zu erreichen. WCF bietet daher die folgenden Typen von zuverlässigem messaging:  
  
-   [Zuverlässige Sitzungen](../../../docs/framework/wcf/feature-details/reliable-sessions.md), zuverlässigen Übertragung ohne hohe Latenz.  
  
-   [Warteschlangen in WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md), welcher bietet zuverlässigen Übertragung und einer Trennung zwischen Quelle und Ziel.  
  
## <a name="reliable-sessions"></a>Zuverlässige Sitzungen  
 Zuverlässige Sitzungen bieten eine zuverlässige End-to-End-Übertragung von Nachrichten zwischen einer Quelle und einem Ziel. Dazu wird das zuverlässige WS-Messaging-Protokoll unabhängig von der Anzahl oder dem Typ der Vermittler verwendet, durch die die Messagingendpunkte (Quelle und Ziel) getrennt werden. Dies umfasst alle Transportvermittler, die kein SOAP (z.&#160;B. HTTP-Proxys) verwenden, oder Vermittler, die SOAP (z.&#160;B. SOAP-basierte Router oder Brücken) verwenden, und die für die Übertragung von Nachrichten zwischen den Endpunkten erforderlich sind. Zuverlässige Sitzungen verwenden ein Übertragungsfenster im Arbeitsspeicher, um SOAP-Fehler auf Nachrichtenebene zu maskieren und Verbindungen im Falle von Transportfehlern neu herzustellen.  
  
 Zuverlässige Sitzungen bieten zuverlässige Nachrichtenübertragungen mit niedriger Latenz. Sie stellen SOAP-Nachrichten über Proxys oder Vermittler bereit, vergleichbar mit der TCP-Bereitstellung für Pakete über IP-Brücken. Weitere Informationen zu zuverlässigen Sitzungen finden Sie unter [zuverlässige Sitzungen](../../../docs/framework/wcf/feature-details/reliable-sessions.md).  
  
### <a name="queues"></a>Warteschlangen  
 Warteschlangen in WCF bieten zuverlässigen Übertragungen von Nachrichten und eine Trennung zwischen Quellen und Zielen Nachteil hoher Latenz. WCF in der Warteschlange Kommunikation basiert auf Message Queuing (MSMQ).  
  
 MSMQ steht als optionale Windows-Komponente zur Verfügung. Der MSMQ-Dienst wird als Windows-Dienst ausgeführt. Er erfasst Nachrichten, die in einer Übertragungswarteschlange der Quelle übertragen und einer Zielwarteschlange zugestellt werden. Die Zielwarteschlange akzeptiert Nachrichten im Auftrag des Ziels für eine spätere Zustellung, wenn das Ziel Nachrichten anfordert. Die MSMQ-Manager implementieren ein zuverlässiges Nachrichtenübertragungsprotokoll, damit Nachrichten bei der Übertragung nicht verloren gehen. Das Protokoll kann entweder systemeigen oder SOAP-basiert sein, zum Beispiel das SOAP Reliable Messaging Protocol (SRMP).  
  
 Die Trennung, gekoppelt mit zuverlässigen Nachrichtenübertragungen zwischen Warteschlangen, ermöglicht Anwendungen, die lose miteinander verbunden sind, eine zuverlässige Kommunikation. Im Gegensatz zu zuverlässigen Sitzungen müssen die Quelle und das Ziel nicht zum gleichen Zeitpunkt ausgeführt werden. So werden implizit Szenarien möglich, bei denen Warteschlangen als Lastausgleichsmechanismus verwendet werden, wenn die Geschwindigkeit der Nachrichtenerzeugung und die Geschwindigkeit des Nachrichtenkonsums nicht übereinstimmen. Weitere Informationen zu Warteschlangen finden Sie unter [Warteschlangen in WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md).  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über zuverlässige Sitzungen](../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)
- [Queuing in WCF](../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
