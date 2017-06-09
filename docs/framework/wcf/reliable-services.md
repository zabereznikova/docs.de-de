---
title: "Zuverl&#228;ssige Dienste | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Dienstverträge [WCF], Zuverlässige Dienste"
  - "WCF [WCF], Zuverlässiges Messaging"
  - "WCF [WCF], Zuverlässige Sitzungen"
  - "Windows Communication Foundation [WCF], Zuverlässiges Messaging."
  - "Windows Communication Foundation [WCF], Zuverlässige Sitzungen"
ms.assetid: 07814ed0-0775-47f2-987b-d8134fdd5099
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Zuverl&#228;ssige Dienste
Warteschlangen und zuverlässige Sitzungen sind die [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Funktionen, die zuverlässiges Messaging implementieren.In diesem Thema werden die zuverlässigen Messagingfunktionen von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] erläutert.  
  
 *Zuverlässiges Messaging* ist die Übertragung von einer zuverlässigen Messagingquelle \(bezeichnet als *Quelle*\) an ein zuverlässiges Messagingziel \(bezeichnet als *Ziel*\).  
  
 Zuverlässiges Messaging führt die folgenden Funktionen aus:  
  
-   Überträgt Zusicherungen für Nachrichten, die unabhängig von der Nachrichtenübertragung oder den Transportfehlern von einer Quelle an ein Ziel gesendet werden.  
  
-   Trennt die Quelle und das Ziel voneinander.So ist eine unabhängige Wiederherstellung nach einem Fehler von Quelle und Ziel sowie eine zuverlässige Übertragung und Zustellung von Nachrichten möglich, auch wenn die Quelle oder das Ziel nicht verfügbar ist.  
  
 Der Preis eines zuverlässigen Messagings besteht häufig in einer hohen Latenz.*Latenz* ist die Zeit, die eine Nachricht von der Quelle bis zum Ziel benötigt.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] stellt deshalb die folgenden zuverlässigen Messagingarten bereit:  
  
-   [Zuverlässige Sitzungen](../../../docs/framework/wcf/feature-details/reliable-sessions.md) mit einer zuverlässigen Übertragung ohne hohe Latenz.  
  
-   [Warteschlangen in WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md) mit einer zuverlässigen Übertragung und einer Trennung zwischen Quelle und Ziel.  
  
## Zuverlässige Sitzungen  
 Zuverlässige Sitzungen bieten eine zuverlässige End\-to\-End\-Übertragung von Nachrichten zwischen einer Quelle und einem Ziel. Dazu wird das zuverlässige WS\-Messaging\-Protokoll unabhängig von der Anzahl oder dem Typ der Vermittler verwendet, durch die die Messagingendpunkte \(Quelle und Ziel\) getrennt werden.Dies umfasst alle Transportvermittler, die kein SOAP \(z. B. HTTP\-Proxys\) verwenden, oder Vermittler, die SOAP \(z. B. SOAP\-basierte Router oder Brücken\) verwenden, die für die Übertragung von Nachrichten zwischen den Endpunkten erforderlich sind.Zuverlässige Sitzungen verwenden ein Übertragungsfenster im Arbeitsspeicher, um SOAP\-Fehler auf Nachrichtenebene zu maskieren und Verbindungen im Falle von Transportfehlern neu herzustellen.  
  
 Zuverlässige Sitzungen bieten zuverlässige Nachrichtenübertragungen mit niedriger Latenz.Sie stellen SOAP\-Nachrichten über Proxys oder Vermittler bereit, vergleichbar mit der TCP\-Bereitstellung für Pakete über IP\-Brücken.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zu zuverlässigen Sitzungen finden Sie unter [Zuverlässige Sitzungen](../../../docs/framework/wcf/feature-details/reliable-sessions.md).  
  
### Warteschlangen  
 Warteschlangen in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bieten zuverlässige Übertragungen von Nachrichten und eine Trennung zwischen Quelle und Ziel mit dem Nachteil hoher Latenz.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bietet Kommunikation in der Warteschlange zusätzlich zu Message Queuing \(MSMQ\).  
  
 MSMQ steht als optionale Windows\-Komponente zur Verfügung.Der MSMQ\-Dienst wird als Windows\-Dienst ausgeführt.Er erfasst Nachrichten, die in einer Übertragungswarteschlange der Quelle übertragen und einer Zielwarteschlange zugestellt werden.Die Zielwarteschlange akzeptiert Nachrichten im Auftrag des Ziels für eine spätere Zustellung, wenn das Ziel Nachrichten anfordert.Die MSMQ\-Manager implementieren ein zuverlässiges Nachrichtenübertragungsprotokoll, damit Nachrichten bei der Übertragung nicht verloren gehen.Das Protokoll kann entweder systemeigen oder SOAP\-basiert sein, zum Beispiel das SOAP Reliable Messaging Protocol \(SRMP\).  
  
 Die Trennung, gekoppelt mit zuverlässigen Nachrichtenübertragungen zwischen Warteschlangen, ermöglicht Anwendungen, die lose miteinander verbunden sind, eine zuverlässige Kommunikation.Im Gegensatz zu zuverlässigen Sitzungen müssen die Quelle und das Ziel nicht zum gleichen Zeitpunkt ausgeführt werden.So werden implizit Szenarien möglich, bei denen Warteschlangen als Lastausgleichsmechanismus verwendet werden, wenn die Geschwindigkeit der Nachrichtenerzeugung und die Geschwindigkeit des Nachrichtenkonsums nicht übereinstimmen.[!INCLUDE[crabout](../../../includes/crabout-md.md)] über Warteschlangen finden Sie unter [Warteschlangen in WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md).  
  
## Siehe auch  
 [Übersicht über zuverlässige Sitzungen](../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)   
 [Warteschlangen in WCF](../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)