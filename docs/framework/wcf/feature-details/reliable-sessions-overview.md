---
title: Übersicht über zuverlässige Sitzungen
ms.date: 03/30/2017
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
ms.openlocfilehash: 1c5344c2804cf4c17fdc46a7fea5a4a360122b6e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="reliable-sessions-overview"></a>Übersicht über zuverlässige Sitzungen

Windows Communication Foundation (WCF) SOAP reliable messaging stellt End-to-End-Übertragung zwischen SOAP-Endpunkte bereit. Dies erfolgt in nicht zuverlässigen Netzwerken, indem Transportfehler und SOAP-Fehler auf Nachrichtenebene behoben werden. Insbesondere wird sitzungsbasierte, einzelne und (optional) geordnete Zustellung für Nachrichten bereitgestellt, die über SOAP- oder Transportvermittler übertragen werden. Sitzungsbasierte Zustellung bietet zum Gruppieren von Nachrichten in einer Sitzung und ordnet die Nachrichten optional.

Dieses Thema beschreibt zuverlässige Sitzungen, wie und wann Sie zu verwenden und diese sichern.

## <a name="wcf-reliable-sessions"></a>Zuverlässige WCF-Sitzungen

Zuverlässige WCF-Sitzungen wird eine Implementierung von zuverlässigem SOAP-messaging gemäß der WS-ReliableMessaging-Protokolls.

WCF-SOAP reliable messaging bietet eine zuverlässige End-to-End-Sitzung zwischen zwei Endpunkten, unabhängig von der Anzahl und Typ der Vermittler verwendet, die die messagingendpunkte getrennt. Dies umfasst alle transportvermittler, die SOAP (z. B. HTTP-Proxys) verwenden, oder Vermittler, die SOAP (z. B. SOAP-basierte Router oder Brücken) verwenden, die Nachrichten zwischen den Endpunkten erforderlich sind. Ein zuverlässiger Sitzungskanal unterstützt *interaktive* Kommunikation, damit die über einen solchen Kanal verbundenen Dienste gleichzeitig ausgeführt werden und austauschen und Verarbeiten von Nachrichten in Situationen mit geringer Latenz, also in relativ geringen Zeitintervalle. Diese Kopplung bedeutet, dass diese Komponenten zusammen weiterarbeiten oder zusammen fehlschlagen; es gibt also keine voneinander isoliert.

Eine zuverlässige Sitzung maskiert zwei Arten von Fehlern:

- SOAP-Fehler auf Nachrichtenebene, zu denen verloren gegangene oder doppelte Nachrichten gehören sowie Nachrichten, die in einer anderen Reihenfolge eintreffen als der, in der sie gesendet wurden.

- Transportfehler.

Eine zuverlässige Sitzung implementiert das WS-ReliableMessaging-Protokoll und ein Übertragungsfenster im Arbeitsspeicher, um SOAP-Fehler auf Nachrichtenebene zu maskieren und Verbindungen im Falle von Transportfehlern neu herzustellen.

Eine zuverlässige Sitzung stellt für SOAP-Nachrichten das bereit, was TCP für IP-Pakete bereitstellt. Eine TCP-Socketverbindung stellt eine einzelne, geordnete Übertragung von IP-Paketen zwischen Knoten bereit. Der zuverlässige Kanal stellt denselben Typ zuverlässiger Übertragung bereit, die sich aber von der TCP-Socket-Zuverlässigkeit in folgenden Punkten unterscheidet:

- Die Zuverlässigkeit gilt für die SOAP-Nachrichten-Ebene, nicht für ein Byte-Paket zufälliger Größe.

- Die Zuverlässigkeit ist transportneutral, nicht nur für die Übertragung über TCP.

- Die Zuverlässigkeit ist nicht an eine bestimmte transportsitzung (z. B. die Sitzung, die eine TCP-Verbindung bereitstellt) gebunden und kann mehrere transportsitzungen gleichzeitig oder nacheinander während der gesamten Lebensdauer einer zuverlässigen Sitzung.

- Die zuverlässige Sitzung besteht zwischen den sendenden und den empfangenden SOAP-Endpunkten, unabhängig von der Anzahl der Transportverbindungen, die für die Konnektivität zwischen ihnen erforderlich ist. Kurz gesagt, endet TCP-Zuverlässigkeit, wo die transportverbindung endet, während eine zuverlässige Sitzung End-to-End-Zuverlässigkeit bereitstellt, wird.

## <a name="reliable-sessions-and-bindings"></a>Zuverlässige Sitzungen und Bindungen

Wie bereits erwähnt, ist eine zuverlässige Sitzung transportneutral. Darüber hinaus können Sie eine zuverlässige Sitzung über viele Nachrichtenaustauschmuster, z. B. Anforderung-Antwort oder Duplex herstellen. Eine zuverlässige WCF-Sitzung wird als eine Eigenschaft eines Satzes von Bindungen verfügbar gemacht.

Verwenden Sie eine zuverlässige Sitzung auf Endpunkten, verwenden:

- HTTP-basierte Transport-Standardbindungen:

  - `WsHttpBinding` und verfügbar gemachte Anforderung-Antwort- oder unidirektionale Verträge.

  - Wenn die zuverlässige Sitzung über einen Anforderung / Antwort- oder einen einfachen unidirektionalen Dienstvertrag verwendet.

  - `WsDualHttpBinding` und verfügbar gemachte Duplex-, Anforderung-Antwort- oder unidirektionale Verträge.

  - `WsFederationHttpBinding` und verfügbar gemachte Anforderung-Antwort- oder unidirektionale Verträge.

- TCP-basierte Transport-Standardbindungen:

  - `NetTcpBinding` und verfügbar gemachte Duplex-, Anforderung-Antwort- oder unidirektionale Verträge.

Eine zuverlässige Sitzung für jede andere Bindung verwenden, erstellen Sie eine benutzerdefinierte Bindung, etwa HTTPS (Weitere Informationen zu Problemen finden Sie unter <a href="#reliable-sessions-and-security">zuverlässige Sitzungen und Sicherheit</a>) oder eine benannte Pipe-Bindung.

Sie können eine zuverlässige Sitzung auf verschiedene zugrunde liegende Kanaltypen gestapelt, und die resultierende kanalform für zuverlässige Sitzung variiert. Auf dem Client und dem Server hängt den Typ des zugrunde liegenden Kanäle zur Datenübergabe der Typ des zuverlässigen Sitzungskanal unterstützt. In der folgenden Tabelle werden die Typen von Sitzungskanälen aufgeführt, die vom Client auf der Basis des zugrunde liegenden Kanaltyps unterstützt werden.

| Unterstützte zuverlässige sitzungskanaltypen&#8224; | `IRequestChannel` | `IRequestSessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :---------------: | :----------------------: | :--------------: | :---------------------: |
| `IOutputSessionChannel`                         | Ja               | Ja                      | Ja              | Ja                     |
| `IRequestSessionChannel`                        | Ja               | Ja                      | Nein               | Nein                      |
| `IDuplexSessionChannel`                         | Nein                | Nein                       | Ja              | Ja                     |

&#8224;Die unterstützen Kanaltypen sind die Werte für die generische `TChannel` Parameterwert, der übergeben wird die <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29> Methode.

In der folgenden Tabelle werden die Typen von Sitzungskanälen aufgeführt, die vom Server auf der Basis des zugrunde liegenden Kanaltyps unterstützt werden.

| Unterstützte zuverlässige sitzungskanaltypen&#8225; | `IReplyChannel` | `IReplySessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :-------------: | :--------------------: | :--------------: | :---------------------: |
| `IInputSessionChannel`                          | Ja             | Ja                    | Ja              | Ja                     |
| `IReplySessionChannel`                          | Ja             | Ja                    | Nein               | Nein                      |
| `IDuplexSessionChannel`                         | Nein              | Nein                     | Ja              | Ja                     |

&#8225;Die unterstützen Kanaltypen sind die Werte für die generische `TChannel` Parameterwert, der übergeben wird die <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29> Methode.

## <a name="reliable-sessions-and-security"></a>Zuverlässige Sitzungen und Sicherheit

Schutz einer zuverlässigen Sitzung ist wichtig, stellen Sie sicher, dass die Kommunikationspartner (Dienst und Client) authentifiziert werden und die in der Sitzung ausgetauschten Nachrichten manipuliert werden nicht. Darüber hinaus ist es wichtig, um die Integrität jeder einzelnen zuverlässigen Sitzung sicherzustellen. Eine zuverlässige Sitzung wird geschützt, indem es an einen Sicherheitskontext, die dargestellt und verwaltet vom Sicherheitskanal der Sitzung gebunden. Der Sicherheitskanal stellt eine Sicherheitssitzung bereit. Die Sicherheitstoken, die während der Einrichtung der Sitzung ausgetauscht werden, werden anschließend verwendet, um die Nachrichten in der zuverlässigen Sitzung zu schützen.

Wenn eine zuverlässige Sitzung über TCP-S ist, ist die TCP-Sitzung an die zuverlässige Sitzung gebunden. Aus diesem Grund wird transportsicherheit sichergestellt, dass Sicherheit auch an die zuverlässige Sitzung gebunden ist. In diesem Fall ist die erneute Einrichtung einer Verbindung abgeschaltet.

Die einzige Ausnahme besteht bei der Verwendung von HTTPS. Die Secure Sockets Layer (SSL)-Sitzung ist nicht an die zuverlässige Sitzung gebunden. Dies erzwingt eine Bedrohung darstellen, weil Sitzungen, die gemeinsam einen Sicherheitskontext (die SSL-Sitzung) voneinander geschützt sind; Dadurch möglicherweise oder ist möglicherweise nicht in der ein echtes Risiko darstellen, abhängig von der Anwendung.

## <a name="using-reliable-sessions"></a>Verwenden von zuverlässigen Sitzungen

Um zuverlässige WCF-Sitzungen zu verwenden, erstellen Sie einen Endpunkt mit einer Bindung, die eine zuverlässige Sitzung unterstützt. Verwenden Sie eine vom System bereitgestellten Bindungen, die WCF mit der zuverlässigen Sitzung bietet aktiviert, oder erstellen Sie eine eigene benutzerdefinierte Bindung, die dies tut.

Die systemdefinierten Bindungen, die standardmäßig eine zuverlässige Sitzung unterstützen und aktivieren, sind:

- <xref:System.ServiceModel.WSDualHttpBinding>

Die vom System bereitgestellte Bindungen, die eine zuverlässige Sitzung als Option unterstützen, aber nicht standardmäßig aktivieren sind:

- <xref:System.ServiceModel.WSHttpBinding>

- <xref:System.ServiceModel.WSFederationHttpBinding>

- <xref:System.ServiceModel.NetTcpBinding>

Ein Beispiel zum Erstellen einer benutzerdefinierten Bindung finden Sie unter [Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).

Eine Erläuterung der WCF-Bindungen, die zuverlässige Sitzungen unterstützen, finden Sie unter [sicherheitsbindungsarten Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md).

## <a name="when-to-use-reliable-sessions"></a>Wann zuverlässige Sitzungen verwendet

Es ist wichtig zu verstehen, wann zuverlässige Sitzungen in Ihrer Anwendung verwenden. WCF unterstützt zuverlässige Sitzungen zwischen Endpunkten, die gleichzeitig aktiv und gültig sind. Wenn Ihre Anwendung einen der Endpunkte erfordert für einen bestimmten Zeitraum nicht verfügbar sein, und klicken Sie dann mithilfe von Warteschlangen an um Zuverlässigkeit zu erreichen.

Wenn das Szenario mit zwei Endpunkte über TCP verbunden erforderlich ist, kann TCP ausreichen, um den zuverlässigen Nachrichtenaustausch gewähren sein. Zwar ist es nicht erforderlich, um eine zuverlässige Sitzung zu verwenden, da TCP wird, dass sichergestellt Eintreffen der Pakete in der Reihenfolge und nur einmal.

Verfügt Ihr Szenario die folgenden Merkmale, müssen Sie ernsthaft sollten Sie die Verwendung einer zuverlässigen Sitzungs.

- SOAP-Vermittler, z. B. SOAP-Router

- Proxyvermittler oder transportbrücken

- Periodische Konnektivität

- Sitzungen über HTTP

## <a name="see-also"></a>Siehe auch

[Verwenden von Bindungen, um Dienste und Clients konfigurieren](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
[Zuverlässige WS-Sitzung](../../../../docs/framework/wcf/samples/ws-reliable-session.md)
