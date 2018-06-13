---
title: Empfohlene Vorgehensweisen für zuverlässige Sitzungen
ms.date: 03/30/2017
ms.assetid: b94f6e01-8070-40b6-aac7-a2cb7b4cb4f2
ms.openlocfilehash: 1d9671e7e3124d535b66de8cd8468f76dcb32b10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491624"
---
# <a name="best-practices-for-reliable-sessions"></a>Empfohlene Vorgehensweisen für zuverlässige Sitzungen

In diesem Thema werden bewährte Vorgehensweisen für zuverlässige Sitzungen.

## <a name="setting-maxtransferwindowsize"></a>Festlegen von MaxTransferWindowSize

Zuverlässige Sitzungen in Windows Communication Foundation (WCF) verwenden ein Übertragungsfenster, um Nachrichten auf dem Client und Dienst aufzunehmen. Der konfigurierbare Eigenschaft <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> gibt an, wie viele Nachrichten das Übertragungsfenster speichern kann.

Auf den Absender gibt dies an, wie viele Nachrichten das Übertragungsfenster während des Wartens auf Bestätigungen speichern kann; beim Empfänger gibt an, wie viele Nachrichten für den Dienst gepuffert werden sollen.

Auswahl der richtigen Größe wirkt sich auf die Effizienz des Netzwerks und die optimalen Kapazität des Diensts. In den folgenden Abschnitten ausführlich beschrieben was zu berücksichtigen, wenn Sie einen Wert für diese Eigenschaft und die Auswirkungen des Werts auswählen.

Die Standardgröße des übertragungsfensters fasst ist acht Nachrichten.

### <a name="efficient-use-of-the-network"></a>Effiziente Verwendung des Netzwerks

In diesem Kontext ist der Begriff *Netzwerk* alles verwendet als Grundlage für die Kommunikation zwischen einem Client (Absender) und einem Dienst (Empfänger) entspricht. Dies schließt die transportverbindungen und alle Vermittler oder Brücken dazwischen, einschließlich SOAP-Routern oder HTTP-Proxys und-Firewalls.

Die effiziente Verwendung des Netzwerks stellt sicher, dass die Netzwerkkapazität vollständig ausgeschöpft wird. Sowohl die Menge der Daten, die pro Sekunde über das Netzwerk übertragen werden können (*Datenrate*) und die Zeit, die zum Übertragen von Daten vom Absender zum Empfänger (*Latenz*) auswirken, wie effizient das Netzwerk wird verwendet.

Für die sendende Seite gibt die Eigenschaft <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> an, wie viele Nachrichten das Übertragungsfenster während des Wartens auf Bestätigungen speichern kann. Wenn die Netzwerklatenz hoch ist, und um reaktionsschnelles senden und effiziente Verwendung das Netzwerks sicherzustellen, sollten Sie Größe des übertragungsfensters erhöhen.

Z. B. konnte auch, wenn der Absender mit Datenrate Schritt hält, einrichten, Latenz hoch sein, wenn zahlreiche Vermittler zwischen Sender und Empfänger vorhanden sind oder die Daten über eine verlustbehaftete Durchgangs- oder Netzwerk weitergeleitet. Daher muss der Sender auf Bestätigungen für die Nachrichten in seinem Übertragungsfenster warten, bevor Sie akzeptiert neue Nachrichten zu senden. Je kleiner der Puffer mit häufiger Latenz, desto weniger effektiv die Netzwerkverwendung. Andererseits, möglicherweise zu hoch Übertragungsfenster des Diensts auswirken, da der Dienst möglicherweise Stand bei der hohen Senderate des vom Client gesendeten Daten.

### <a name="running-the-service-to-capacity"></a>Der Dienst ausgeführt wird, um Kapazität

Wie das Netzwerk effizient genutzt wird, sollten Sie idealerweise auch optimalen Kapazität Ausführung des Dienstes. Die Eigenschaft für die Größe des Übertragungsfensters beim Empfänger gibt an, wie viele Nachrichten der Empfänger puffern kann. Diese Nachrichtenpufferung hilft nicht nur der Flusssteuerung im Netzwerk, sondern erlaubt dem Client auch, mit voller Kapazität zu laufen. Z. B., wenn der Puffer ist eine Nachricht und die Nachrichten treffen schneller als der Dienst verarbeitet werden kann Klicken Sie dann das Netzwerk möglicherweise Nachrichten ablegen und Kapazität verschwendet oder unzureichend ausgenutzt werden könnte.

Unter Verwendung eines Puffers erhöht die Verfügbarkeit des Diensts, während es gleichzeitig empfangen und Puffern kann eine Nachricht beim Verarbeiten der zuvor empfangenen Nachrichten.

Es wird empfohlen, Sie die gleiche verwenden `MaxTransferWindowSize` auf dem Absender und Empfänger.

### <a name="enabling-flow-control"></a>Aktivieren der flusssteuerung

*Flusssteuerung* ist ein Mechanismus, der sicherstellt, dass Sender und Empfänger Schritt halten, miteinander, d. h. der Nachrichten genutzt werden und Reaktionen bewirkten so schnell, wie sie erstellt haben. Eine vernünftige Größe des Übertragungsfensters von Client und Dienst stellt sicher, dass Sender und Empfänger ausreichend synchron arbeiten.

Es wird dringend empfohlen, dass Sie die Eigenschaft festlegen <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A> auf `true` bei Verwendung eine zuverlässige Sitzung zwischen einem WCF-Client und einem WCF-Dienst.

## <a name="setting-maxpendingchannels"></a>Festlegen von MaxPendingChannels

Wenn Sie einen Dienst schreiben, der zuverlässige Sitzungskommunikation mit anderen Clients ermöglicht, ist es möglich, dass viele Clients, die eine zuverlässige Sitzung mit dem Dienst gleichzeitig herzustellen. Die Antwort des Diensts hängt in diesen Fällen von der `MaxPendingChannels`-Eigenschaft ab.

Wenn der Sender einen zuverlässige Sitzungskanal zum Empfänger erstellt, dann begründet ein Handshake zwischen ihnen eine zuverlässige Sitzung. Ist die zuverlässige Sitzung eingerichtet, wird der Kanal für seine Annahme durch den Dienst in eine Warteschlange ausstehender Kanäle eingereiht. Die `MaxPendingChannels`-Eigenschaft gibt an, wie viele Kanäle in diesem Zustand sein können.

Es ist möglich, dass der Dienst in einem Zustand, in dem sie weitere Kanäle akzeptieren kann. Wenn die Warteschlange voll ist, beim Versuch, eine zuverlässige Sitzung herzustellen wird abgelehnt, und der Client muss wiederholen.

Es ist auch möglich, dass die in der Warteschlange befindenden Kanäle für eine längere Zeit in der Warteschlange bleiben. In der Zwischenzeit kann in der zuverlässigen Sitzung ein Inaktivitätstimeout auftreten, wodurch der Kanal in einem fehlerhaften Zustand übergeht.

Wenn Sie einen Dienst schreiben, der mehrere Clients gleichzeitig bedient, sollten Sie einen Wert festlegen, der für Ihre Bedürfnisse geeignet ist. Festlegen der zu hohen Wert für die `MaxPendingChannels` Eigenschaft wirkt sich auf Ihr Workingset.

Der Standardwert für <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A> vier Kanäle ist.

## <a name="reliable-sessions-and-hosting"></a>Zuverlässige Sitzungen und hosting

Beim Hosten eines Diensts, das zuverlässige Sitzungen verwendet wird, sollten Sie die folgenden wichtigen Überlegungen halten, beachten Sie:

- Zuverlässige Sitzungen sind zustandsbehaftet, und der Zustand wird in der AppDomain beibehalten. Dies bedeutet, dass alle Nachrichten, die Teil einer zuverlässigen Sitzung sind, in der gleichen AppDomain verarbeitet werden müssen. Diese Einschränkung können nicht garantieren, Webfarmen und Webgärten, in denen die Größe der Farm oder des Gartens größer als ein Knoten ist.

- Zuverlässige Sitzungen, die duale HTTP-Kanäle (z. B. `WsDualHttpBinding`) können mehr als die Standardgröße von zwei HTTP-Verbindungen pro Client erforderlich ist. Dies bedeutet, dass eine zuverlässige duplexsitzung bis zu zwei Verbindungen in jede Richtung erfordern kann, da gleichzeitige Anwendungen und Protokollnachrichten jeden Weg und zu einem beliebigen Zeitpunkt übertragen werden können. Unter bestimmten Umständen das Nachrichtenaustauschmuster des Diensts abhängen bedeutet dies, dass es möglich ist, einen im Web gehosteten Dienst duale HTTP-Verbindungen und zuverlässige Sitzungen ein Deadlock auftreten. Fügen Sie zum Erhöhen der Anzahl der zulässigen HTTP-Verbindungen pro Client Folgendes in die entsprechende Konfigurationsdatei (z. B. *"Web.config"* des betreffenden Diensts):

  ```xml
  <configuration>
    <system.net>
      <connectionManagement>
        <add name="*" maxconnection="4" />
      </connectionManagement>
    </system.net>
  </configuration>
  ```

  Der Wert, der die `maxconnection` Attribut gibt die Anzahl der benötigten Verbindungen. Das Minimum darf in diesem Fall geben vier Verbindungen.
