---
title: Übersicht über zuverlässige Sitzungen
ms.date: 03/30/2017
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
ms.openlocfilehash: a85a34c5e2ec7928c01586e4b01cdf5e90e896a7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601087"
---
# <a name="reliable-sessions-overview"></a>Übersicht über zuverlässige Sitzungen

Windows Communication Foundation (WCF)-SOAP-zuverlässiges Messaging bietet eine End-to-End-Nachrichten Übertragungs Zuverlässigkeit zwischen SOAP-Endpunkten. Dies erfolgt in nicht zuverlässigen Netzwerken, indem Transportfehler und SOAP-Fehler auf Nachrichtenebene behoben werden. Insbesondere wird sitzungsbasierte, einzelne und (optional) geordnete Zustellung für Nachrichten bereitgestellt, die über SOAP- oder Transportvermittler übertragen werden. Die Sitzungs basierte Übermittlung ermöglicht das Gruppieren von Nachrichten in einer Sitzung mit optionaler Reihenfolge der Nachrichten.

In diesem Thema werden zuverlässige Sitzungen beschrieben, wie und wann Sie verwendet werden und wie Sie geschützt werden.

## <a name="wcf-reliable-sessions"></a>Zuverlässige WCF-Sitzungen

Zuverlässige WCF-Sitzungen sind eine Implementierung von zuverlässigem SOAP-Messaging, wie durch das WS-ReliableMessaging-Protokoll definiert.

Zuverlässiges WCF-SOAP-Messaging bietet eine zuverlässige End-to-End-Sitzung zwischen zwei Endpunkten, unabhängig von der Anzahl oder dem Typ der Vermittler, von denen die Messaging Endpunkte getrennt werden. Dies schließt alle Transportvermittler ein, die keine SOAP verwenden (z. b. HTTP-Proxys), oder Vermittler, die SOAP verwenden (z. b. SOAP-basierte Router oder Bridges), die erforderlich sind, damit Nachrichten zwischen den Endpunkten übertragen werden. Ein zuverlässiger Sitzungs Kanal unterstützt die *interaktive* Kommunikation, sodass die Dienste, die von einem solchen Kanal verbunden sind, gleichzeitig ausgeführt werden und Nachrichten unter Bedingungen niedriger Latenz, d. h. innerhalb relativ kurzer Zeitintervalle, austauschen und verarbeiten. Diese Kopplung bedeutet, dass diese Komponenten den Fortschritt gemeinsam ausführen oder einen Failover ausführen, sodass keine Isolation zwischen Ihnen bereitgestellt wird.

Eine zuverlässige Sitzung maskiert zwei Arten von Fehlern:

- SOAP-Fehler auf Nachrichtenebene, zu denen verloren gegangene oder doppelte Nachrichten gehören sowie Nachrichten, die in einer anderen Reihenfolge eintreffen als der, in der sie gesendet wurden.

- Transportfehler.

Eine zuverlässige Sitzung implementiert das WS-ReliableMessaging-Protokoll und ein Übertragungsfenster im Arbeitsspeicher, um SOAP-Fehler auf Nachrichtenebene zu maskieren und Verbindungen im Falle von Transportfehlern neu herzustellen.

Eine zuverlässige Sitzung stellt für SOAP-Nachrichten das bereit, was TCP für IP-Pakete bereitstellt. Eine TCP-Socketverbindung stellt eine einzelne, geordnete Übertragung von IP-Paketen zwischen Knoten bereit. Der zuverlässige Kanal stellt denselben Typ zuverlässiger Übertragung bereit, die sich aber von der TCP-Socket-Zuverlässigkeit in folgenden Punkten unterscheidet:

- Die Zuverlässigkeit gilt für die SOAP-Nachrichten-Ebene, nicht für ein Byte-Paket zufälliger Größe.

- Die Zuverlässigkeit ist Transport Neutral, nicht nur für die Übertragung über TCP.

- Die Zuverlässigkeit ist nicht an eine bestimmte Transport Sitzung gebunden (z. b. die Sitzung, die eine TCP-Verbindung bereitstellt) und kann mehrere Transport Sitzungen gleichzeitig oder sequenziell über die Lebensdauer der zuverlässigen Sitzung verwenden.

- Die zuverlässige Sitzung besteht zwischen den sendenden und den empfangenden SOAP-Endpunkten, unabhängig von der Anzahl der Transportverbindungen, die für die Konnektivität zwischen ihnen erforderlich ist. Kurz gesagt, endet die TCP-Zuverlässigkeit, wenn die Transport Verbindung endet, während eine zuverlässige Sitzung eine End-to-End-Zuverlässigkeit bietet.

## <a name="reliable-sessions-and-bindings"></a>Zuverlässige Sitzungen und Bindungen

Wie bereits erwähnt, ist eine zuverlässige Sitzung Transport Neutral. Außerdem können Sie eine zuverlässige Sitzung über viele Nachrichtenaustausch Muster einrichten, z. b. Anforderung-Antwort oder Duplex. Eine zuverlässige WCF-Sitzung wird als Eigenschaft eines Satzes von Bindungen verfügbar gemacht.

Verwenden Sie eine zuverlässige Sitzung auf Endpunkten, von denen Folgendes verwendet wird:

- HTTP-basierte Transport-Standardbindungen:

  - `WsHttpBinding` und verfügbar gemachte Anforderung-Antwort- oder unidirektionale Verträge.

  - Bei Verwendung einer zuverlässigen Sitzung über einen Anforderung-Antwort-oder einen einfachen unidirektionalen Dienstvertrag.

  - `WsDualHttpBinding` und verfügbar gemachte Duplex-, Anforderung-Antwort- oder unidirektionale Verträge.

  - `WsFederationHttpBinding` und verfügbar gemachte Anforderung-Antwort- oder unidirektionale Verträge.

- TCP-basierte Transport-Standardbindungen:

  - `NetTcpBinding` und verfügbar gemachte Duplex-, Anforderung-Antwort- oder unidirektionale Verträge.

Verwenden Sie eine zuverlässige Sitzung für jede andere Bindung, indem Sie eine benutzerdefinierte Bindung erstellen, z. b. HTTPS (Weitere Informationen zu Problemen finden Sie unter <a href="#reliable-sessions-and-security">zuverlässige Sitzungen und Sicherheit</a>) oder eine Named Pipe Bindung.

Sie können eine zuverlässige Sitzung auf verschiedene zugrunde liegende Kanaltypen Stapeln, und die resultierende zuverlässige sitzungskanalform variiert. Sowohl auf dem Client als auch auf dem Server hängt der Typ des unterstützten zuverlässigen Sitzungs Kanals vom Typ des verwendeten zugrunde liegenden Kanals ab. In der folgenden Tabelle werden die Typen von Sitzungskanälen aufgeführt, die vom Client auf der Basis des zugrunde liegenden Kanaltyps unterstützt werden.

| Unterstützte zuverlässige Sitzungskanaltypen&#8224; | `IRequestChannel` | `IRequestSessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :---------------: | :----------------------: | :--------------: | :---------------------: |
| `IOutputSessionChannel`                         | Ja               | Ja                      | Ja              | Ja                     |
| `IRequestSessionChannel`                        | Ja               | Ja                      | Nein               | Nein                      |
| `IDuplexSessionChannel`                         | Nein                | Nein                        | Ja              | Ja                     |

&#8224;die unterstützten Kanaltypen sind die Werte, die für den generischen Parameterwert verfügbar sind, der an `TChannel` die-Methode übergeben wird <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29> .

In der folgenden Tabelle werden die Typen von Sitzungskanälen aufgeführt, die vom Server auf der Basis des zugrunde liegenden Kanaltyps unterstützt werden.

| Unterstützte zuverlässige Sitzungskanaltypen&#8225; | `IReplyChannel` | `IReplySessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :-------------: | :--------------------: | :--------------: | :---------------------: |
| `IInputSessionChannel`                          | Ja             | Ja                    | Ja              | Ja                     |
| `IReplySessionChannel`                          | Ja             | Ja                    | Nein               | Nein                      |
| `IDuplexSessionChannel`                         | Nein              | Nein                      | Ja              | Ja                     |

&#8225;die unterstützten Kanaltypen sind die Werte, die für den generischen Parameterwert verfügbar sind, der an `TChannel` die-Methode übergeben wird <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29> .

## <a name="reliable-sessions-and-security"></a>Zuverlässige Sitzungen und Sicherheit

Das Sichern einer zuverlässigen Sitzung ist wichtig, um sicherzustellen, dass die Kommunikationspartner (Dienst und Client) authentifiziert werden und dass die in der Sitzung ausgetauschten Nachrichten nicht manipuliert werden. Außerdem ist es wichtig, die Integrität jeder einzelnen zuverlässigen Sitzung sicherzustellen. Eine zuverlässige Sitzung wird gesichert, indem Sie an einen Sicherheitskontext gebunden wird, der von einem Sicherheits Sitzungs Kanal dargestellt und verwaltet wird. Der Sicherheitskanal stellt eine Sicherheitssitzung bereit. Die Sicherheitstoken, die während der Einrichtung der Sitzung ausgetauscht werden, werden anschließend verwendet, um die Nachrichten in der zuverlässigen Sitzung zu schützen.

Wenn eine zuverlässige Sitzung über TCP-S erfolgt, ist die TCP-Sitzung an die zuverlässige Sitzung gebunden. Aus diesem Grund stellt die Transportsicherheit sicher, dass die Sicherheit auch an die zuverlässige Sitzung gebunden ist. In diesem Fall ist die erneute Einrichtung einer Verbindung abgeschaltet.

Die einzige Ausnahme besteht bei der Verwendung von HTTPS. Die Secure Sockets Layer (SSL)-Sitzung ist nicht an die zuverlässige Sitzung gebunden. Dies erzwingt eine Bedrohung, da Sitzungen, die einen Sicherheitskontext (die SSL-Sitzung) gemeinsam nutzen, nicht voneinander geschützt sind. Dies ist abhängig von der Anwendung möglicherweise eine echte Bedrohung.

## <a name="using-reliable-sessions"></a>Verwenden zuverlässiger Sitzungen

Wenn Sie zuverlässige WCF-Sitzungen verwenden möchten, erstellen Sie einen Endpunkt mit einer Bindung, die eine zuverlässige Sitzung unterstützt. Verwenden Sie eine der vom System bereitgestellten Bindungen, die WCF mit aktivierter zuverlässiger Sitzung bereitstellt, oder erstellen Sie eine eigene benutzerdefinierte Bindung, die dies bewirkt.

Die systemdefinierten Bindungen, die standardmäßig eine zuverlässige Sitzung unterstützen und aktivieren, sind:

- <xref:System.ServiceModel.WSDualHttpBinding>

Die vom System bereitgestellten Bindungen, die eine zuverlässige Sitzung als Option unterstützen, jedoch nicht standardmäßig eine aktivieren, sind:

- <xref:System.ServiceModel.WSHttpBinding>

- <xref:System.ServiceModel.WSFederationHttpBinding>

- <xref:System.ServiceModel.NetTcpBinding>

Ein Beispiel für das Erstellen einer benutzerdefinierten Bindung finden Sie unter Gewusst [wie: Erstellen einer benutzerdefinierten zuverlässigen Sitzungs Bindung mit HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md).

Eine Erläuterung der WCF-Bindungen, die zuverlässige Sitzungen unterstützen, finden Sie unter vom [System bereitgestellte Bindungen](../system-provided-bindings.md).

## <a name="when-to-use-reliable-sessions"></a>Verwendung zuverlässiger Sitzungen

Es ist wichtig zu verstehen, wann Sie in Ihrer Anwendung zuverlässige Sitzungen verwenden sollten. WCF unterstützt zuverlässige Sitzungen zwischen Endpunkten, die gleichzeitig aktiv und aktiv sind. Wenn die Anwendung erfordert, dass einer der Endpunkte für einen Zeitraum nicht verfügbar ist, verwenden Sie Warteschlangen, um die Zuverlässigkeit zu erzielen.

Wenn für das Szenario zwei Endpunkte erforderlich sind, die über TCP verbunden sind, kann TCP ausreichen, um einen zuverlässigen Nachrichtenaustausch bereitzustellen. Es ist zwar nicht erforderlich, eine zuverlässige Sitzung zu verwenden, da TCP sicherstellt, dass die Pakete in der richtigen Reihenfolge eintreffen.

Wenn in Ihrem Szenario eine der folgenden Eigenschaften vorhanden ist, müssen Sie die Verwendung einer zuverlässigen Sitzung ernsthaft in Erwägung gezogen.

- SOAP-Vermittler, z. b. SOAP-Router

- Proxy Vermittler oder Transport Bridges

- Periodische Konnektivität

- Sitzungen über http

## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../using-bindings-to-configure-services-and-clients.md)
- [Zuverlässige WS-Sitzung](../samples/ws-reliable-session.md)
