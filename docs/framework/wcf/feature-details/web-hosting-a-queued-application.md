---
title: Webhosting einer Anwendung mit Queuing
ms.date: 03/30/2017
ms.assetid: c7a539fa-e442-4c08-a7f1-17b7f5a03e88
ms.openlocfilehash: 17c3d2167d3f98017c5f366ab0d700d9fb889f82
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600139"
---
# <a name="web-hosting-a-queued-application"></a>Webhosting einer Anwendung mit Queuing
Der Windows-Prozessaktivierungsdienst (Windows Process Activation Service, WAS) verwaltet die Aktivierung und Lebensdauer der Workerprozesse, die Anwendungen enthalten, die WCF-Dienste (Windows Communication Foundation) hosten. Das WAS-Prozessmodell generalisiert das IIS 6.0-Prozessmodell für den HTTP-Server, indem die Abhängigkeit von HTTP entfernt wird. Dadurch können WCF-Dienste sowohl HTTP-als auch nicht-HTTP-Protokolle, wie z. b. net. MSMQ und MSMQ. FormatName, in einer Host Umgebung verwenden, die Nachrichten basierte Aktivierung unterstützt und die Möglichkeit bietet, eine große Anzahl von Anwendungen auf einem bestimmten Computer zu hosten.  
  
 WAS enthält einen Message Queuing (MSMQ)-Aktivierungsdienst, der eine Anwendung mit Queuing aktiviert, wenn mindestens eine Nachricht in einer der von der Anwendung verwendeten Warteschlangen platziert wird. Der MSMQ-Aktivierungsdienst ist ein NT-Dienst, der standardmäßig automatisch gestartet wird.  
  
 Weitere Informationen zu was und den dazugehörigen Vorteilen finden Sie unter [Hosting in Windows Process Activation Service](hosting-in-windows-process-activation-service.md). Weitere Informationen zu MSMQ finden Sie unter [Übersicht über Warteschlangen](queues-overview.md).
  
## <a name="queue-addressing-in-was"></a>Adressieren von Warteschlangen in WAS  
 WAS-Anwendungen weisen Uniform Resource Identifier (URI)-Adressen auf. Anwendungsadressen haben zwei Teile: einen Basis-URI-Präfix und eine anwendungsspezifische, relative Adresse (Pfad). Diese beiden Teile stellen beim Zusammenfügen die externe Adresse für eine Anwendung bereit. Das Basis-URI-Präfix wird aus der Site Bindung erstellt und für alle Anwendungen unter der Site verwendet, z. b. "net. MSMQ://localhost", "MSMQ. FormatName://localhost" oder "net. TCP://localhost". Anwendungs Adressen werden dann durch die Verwendung von anwendungsspezifischen Pfad Fragmenten (z. b. "/applicationOne") erstellt und an das Basis-URI-Präfix angehängt, um den vollständigen Anwendungs-URI zu erhalten, z. b. "net. MSMQ://localhost/applicationOne".  
  
 Der MSMQ-Aktivierungsdienst verwendet den Anwendungs-URI zum Abgleichen der Warteschlange, die der MSMQ-Aktivierungsdienst auf Nachrichten überwachen muss. Wenn der MSMQ-Aktivierungsdienst startet, listet er alle öffentlichen und privaten Warteschlangen auf dem Computer auf, für deren Empfang er konfiguriert ist, und überwacht ihn auf Nachrichten. Alle 10 Minuten aktualisiert der MSMQ-Aktivierungsdienst die Liste der zu überwachenden Warteschlangen. Wenn in einer Warteschlange eine Nachricht gefunden wird, gleicht der Aktivierungsdienst den Warteschlangennamen entsprechend dem längsten übereinstimmenden Anwendungs-URI für die Bindung „net.msmq“ ab und aktiviert die Anwendung.  
  
> [!NOTE]
> Die aktivierte Anwendung muss mit dem Präfix des Warteschlangennamens übereinstimmen (längstmögliche Übereinstimmung).  
  
 Ein Warteschlangenname lautet beispielsweise msmqWebHost/orderProcessing/service.svc. Wenn Anwendung 1 über ein virtuelles Verzeichnis /msmqWebHost/orderProcessing mit service.svc darunter verfügt und Anwendung 2 über ein virtuelles Verzeichnis /msmqWebHost mit orderProcessing.svc darunter verfügt, wird Anwendung 1 aktiviert. Wenn Anwendung 1 gelöscht wird, wird Anwendung 2 aktiviert.  
  
> [!NOTE]
> Beim Erstellen einer Warteschlange aktivieren gesendete Nachrichten eine Anwendung erst dann, wenn der MSMQ-Aktivierungsdienst die Warteschlangenliste aktiviert; dies geschieht maximal 10 Minuten nach dem Erstellen der Warteschlange. Beim Neustart des Aktivierungsdienstes wird auch die Warteschlangenliste aktualisiert.  
  
### <a name="the-effect-of-private-and-public-queues-on-addressing"></a>Die Auswirkung privater und öffentlicher Warteschlangen auf die Adressierung  
 Der MSMQ-Aktivierungsdienst unterscheidet nicht zwischen privater und öffentlicher Warteschlangenüberwachung. Öffentliche und private Warteschlangen sollten nicht den gleichen Namen haben. Anderenfalls wird eine im Internet gehostete Anwendung möglicherweise beim Lesen aus einer der beiden Warteschlangen aktiviert.  
  
### <a name="queue-configuration-for-activation"></a>Warteschlangenkonfiguration zur Aktivierung  
 Der MSMQ-Aktivierungsdienst wird als NETZWERKDIENST ausgeführt. Dieser Dienst überwacht Warteschlangen zum Aktivieren von Anwendungen. Zum Aktivieren von Anwendungen aus der Warteschlange muss die Warteschlange NETZWERKDIENST-Zugriff bieten, um Nachrichten in der Zugriffssteuerungsliste einzusehen.  
  
### <a name="poison-messaging"></a>Nicht verarbeitbare Nachrichten  
 Die Verarbeitung von nicht verarbeitbaren Nachrichten in WCF wird vom Kanal behandelt, der nicht nur erkennt, dass eine Nachricht vergiftet ist, sondern eine Disposition basierend auf der Benutzerkonfiguration auswählt. Als Ergebnis gibt es eine einzelne Nachricht in der Warteschlange. Die im Internet gehostete Anwendung bricht mehrmals hintereinander ab, und die Nachricht wird in eine Wiederholungswarteschlange verschoben. Zu einem von der Zeitverzögerung zwischen den Wiederholungszyklen festgelegten Zeitpunkt wird die Nachricht aus der Wiederholungswarteschlange für einen erneuten Versuch in die Hauptwarteschlange verschoben. Dazu muss jedoch der in der Warteschlange stehende Kanal aktiv sein. Wenn die Anwendung vom WAS wiederverwendet wird, verbleibt die Nachricht in der Wiederholungswarteschlange, bis eine weitere Nachricht zum Aktivieren der Anwendung mit Queuing in der Hauptwarteschlange eingeht. In diesem Fall kann das Problem behoben werden, indem die Nachricht manuell aus der Wiederholungswarteschlange zurück in die Hauptwarteschlange verschoben wird, um die Anwendung erneut zu aktivieren.  
  
### <a name="subqueue-and-system-queue-caveat"></a>Einschränkung für Unterwarteschlangen und Systemwarteschlangen  
 Eine in WAS gehostete Anwendungen kann in einer Systemwarteschlange wie der systemweiten Warteschlange für unzustellbare Nachrichten oder in Unterwarteschlangen wie der Unterwarteschlange für potenziell schädliche Nachrichten nicht basierend auf Nachrichten aktiviert werden. Dies ist eine Einschränkung für diese Produktversion.  
  
## <a name="see-also"></a>Weitere Informationen

- [Behandlung nicht verarbeitbarer Nachrichten](poison-message-handling.md)
- [Dienstendpunkte und Adressieren von Warteschlangen](service-endpoints-and-queue-addressing.md)
