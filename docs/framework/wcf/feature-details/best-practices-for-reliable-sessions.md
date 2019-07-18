---
title: Empfohlene Vorgehensweisen für zuverlässige Sitzungen
ms.date: 03/30/2017
ms.assetid: b94f6e01-8070-40b6-aac7-a2cb7b4cb4f2
ms.openlocfilehash: 1d9671e7e3124d535b66de8cd8468f76dcb32b10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857986"
---
# <a name="best-practices-for-reliable-sessions"></a>Empfohlene Vorgehensweisen für zuverlässige Sitzungen

In diesem Thema werden bewährte Vorgehensweisen für zuverlässige Sitzungen.

## <a name="setting-maxtransferwindowsize"></a>Festlegen von MaxTransferWindowSize

Zuverlässige Sitzungen in Windows Communication Foundation (WCF) verwenden ein Übertragungsfenster, um Nachrichten auf dem Client und Dienst zu speichern. Der konfigurierbare Eigenschaft <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> gibt an, wie viele Nachrichten das Übertragungsfenster speichern kann.

Für die sendende gibt dies an, wie viele Nachrichten das Übertragungsfenster während des Wartens auf Bestätigungen speichern kann; beim Empfänger gibt es an, wie viele Nachrichten für den Dienst gepuffert werden sollen.

Auswahl der richtigen Größe wirkt sich auf die Effizienz des Netzwerks und der optimalen Kapazität des Diensts. In den folgenden Abschnitten ausführlich beschrieben was beim Auswählen der eines Wert für diese Eigenschaft und die Auswirkungen des Werts zu berücksichtigen.

Die Standardfenstergröße für die Übertragung ist acht Nachrichten.

### <a name="efficient-use-of-the-network"></a>Effiziente Verwendung des Netzwerks

In diesem Kontext ist der Begriff *Netzwerk* Zusammenhang alles, was als Grundlage für die Kommunikation zwischen einem Client (Absender) und einem Dienst (Empfänger) verwendet. Dies schließt die transportverbindungen und alle Vermittler oder Brücken zwischen, einschließlich SOAP-Routern oder HTTP-Proxys/Firewalls.

Die effiziente Verwendung des Netzwerks stellt sicher, dass die Netzwerkkapazität vollständig ausgeschöpft wird. Sowohl die Menge der Daten, die pro Sekunde über das Netzwerk übertragen werden können (*Datenrate*) und die Zeit, die zum Übertragen von Daten vom Absender zum Empfänger (*Latenz*) auswirken, wie effizient das Netzwerk wird verwendet.

Für die sendende Seite gibt die Eigenschaft <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> an, wie viele Nachrichten das Übertragungsfenster während des Wartens auf Bestätigungen speichern kann. Wenn die Netzwerklatenz hoch ist, und um reaktionsschnelles senden und effiziente Verwendung das Netzwerks sicherzustellen, sollten Sie die Größe des übertragungsfensters erhöhen.

Z. B. konnte auch, wenn der Absender mit der Datenrate Schritt hält, Latenz hoch sein, wenn zahlreiche Vermittler zwischen Sender und Empfänger vorhanden, oder die Daten müssen über ein verlustreiches Vermittler oder das Netzwerk übergeben. Daher muss der Sender auf Bestätigungen für die Nachrichten in seinem Übertragungsfenster warten, bevor er weitere Nachrichten senden. Je kleiner der Puffer mit hoher Latenz, desto weniger effektiv die Netzwerkauslastung. Auf der anderen Seite kann hoch Übertragungsfenster des Diensts beeinträchtigen, da der Dienst möglicherweise benötigt, dessen Stand bei der hohen Senderate des vom Client gesendeten Daten zu.

### <a name="running-the-service-to-capacity"></a>Der Dienst ausgeführt wird, um die Kapazität

Wie das Netzwerk effizient genutzt wird, im Idealfall möchten Sie auch über den Dienst mit optimaler Kapazität ausgeführt. Die Eigenschaft für die Größe des Übertragungsfensters beim Empfänger gibt an, wie viele Nachrichten der Empfänger puffern kann. Diese Nachrichtenpufferung hilft nicht nur der Flusssteuerung im Netzwerk, sondern erlaubt dem Client auch, mit voller Kapazität zu laufen. Beispielsweise wenn der Puffer ist eine Nachricht und die Nachrichten treffen schneller als der Dienst verarbeitet werden kann Klicken Sie dann das Netzwerk möglicherweise Nachrichten verwerfen und Kapazität verschwendet oder unzureichend ausgenutzt werden kann.

Verwendung eines Puffers erhöht die Verfügbarkeit des Diensts, während es gleichzeitig empfangen und Puffern kann eine Nachricht beim Verarbeiten der zuvor empfangenen Nachrichten.

Es wird empfohlen, Sie die gleiche verwenden `MaxTransferWindowSize` auf dem Absender und Empfänger.

### <a name="enabling-flow-control"></a>Aktivieren der flusssteuerung

*Flusssteuerung* ist ein Mechanismus, der sicherstellt, dass Sender und Empfänger halten Sie Schritt miteinander, das heißt, die Nachrichten genutzt und eine Aktion ausgeführt werden so schnell, wie sie erstellt haben. Eine vernünftige Größe des Übertragungsfensters von Client und Dienst stellt sicher, dass Sender und Empfänger ausreichend synchron arbeiten.

Es wird dringend empfohlen, dass Sie die Eigenschaft festlegen <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A> zu `true` bei Verwendung eine zuverlässige Sitzung zwischen einem WCF-Client und einem WCF-Dienst.

## <a name="setting-maxpendingchannels"></a>Festlegen von MaxPendingChannels

Wenn Sie einen Dienst schreiben, der zuverlässige Sitzungskommunikation von anderen Clients ermöglicht, ist es möglich, viele Clients, die eine zuverlässige Sitzung mit dem Dienst zur gleichen Zeit eingerichtet haben. Die Antwort des Diensts hängt in diesen Fällen von der `MaxPendingChannels`-Eigenschaft ab.

Wenn der Sender einen zuverlässige Sitzungskanal zum Empfänger erstellt, dann begründet ein Handshake zwischen ihnen eine zuverlässige Sitzung. Ist die zuverlässige Sitzung eingerichtet, wird der Kanal für seine Annahme durch den Dienst in eine Warteschlange ausstehender Kanäle eingereiht. Die `MaxPendingChannels`-Eigenschaft gibt an, wie viele Kanäle in diesem Zustand sein können.

Es ist möglich, dass der Dienst in einem Zustand, in denen sie weitere Kanäle nicht akzeptieren kann. Wenn die Warteschlange voll ist, wird beim Versuch, eine zuverlässige Sitzung einzurichten wird abgelehnt, und der Client muss wiederholen.

Es ist auch möglich, dass die in der Warteschlange befindenden Kanäle für längere Zeit in der Warteschlange verbleiben. In der Zwischenzeit kann ein Timeout bei Inaktivität bei der zuverlässigen Sitzung auftreten, wodurch der Kanal in einem fehlerhaften Zustand.

Wenn Sie einen Dienst schreiben, der mehrere Clients gleichzeitig bedient, sollten Sie einen Wert festlegen, der für Ihre Anforderungen geeignet ist. Festlegen der zu hohen Wert für die `MaxPendingChannels` Eigenschaft wirkt sich auf Ihr Workingset.

Der Standardwert für <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A> sind vier Kanäle.

## <a name="reliable-sessions-and-hosting"></a>Zuverlässige Sitzungen und hosting

Beim Hosten eines Diensts, das zuverlässige Sitzungen verwendet wird, sollten Sie die folgenden wichtigen Überlegungen im Hinterkopf behalten:

- Zuverlässige Sitzungen sind zustandsbehaftet, und der Zustand wird in der AppDomain beibehalten. Dies bedeutet, dass alle Nachrichten, die Teil einer zuverlässigen Sitzung sind, in der gleichen AppDomain verarbeitet werden müssen. Diese Einschränkung können nicht garantieren, Webfarmen und Webgärten, in denen die Größe der Farm oder des Gartens größer als ein Knoten ist.

- Zuverlässige Sitzungen, die duale HTTP-Kanäle (z. B. `WsDualHttpBinding`) kann mehr als den Standardwert von zwei HTTP-Verbindungen pro Client erforderlich sein. Dies bedeutet, dass eine zuverlässige duplexsitzung bis zu zwei Verbindungen in jede Richtung erfordern kann, da es sich bei gleichzeitige Anwendungen und Protokollnachrichten zu jedem Zeitpunkt jeder Methode übertragen werden können. Unter bestimmten Bedingungen abhängig von der SOAP-nachrichtenaustauschmusters des Dienstes bedeutet dies, dass es möglich ist, einen im Internet gehosteten Dienst mit dualem HTTP und zuverlässige Sitzungen ein Deadlock auftreten. Um die Anzahl der zulässigen HTTP-Verbindungen pro Client zu erhöhen, fügen Sie Folgendes in die entsprechenden Konfigurationsdatei (z. B. *"Web.config"* von den jeweiligen Dienst):

  ```xml
  <configuration>
    <system.net>
      <connectionManagement>
        <add name="*" maxconnection="4" />
      </connectionManagement>
    </system.net>
  </configuration>
  ```

  Der Wert des der `maxconnection` -Attribut ist die Anzahl der Verbindungen erforderlich sind. Mindestens sollte in diesem Fall vier Verbindungen.
