---
title: Nachrichtensicherheit in WCF
description: Erfahren Sie mehr über TransportWithMessageCredential, eine Art WCF-Nachrichten Sicherheit, die eine Kombination aus Transport-und Nachrichten Sicherheitsmodi verwendet.
ms.date: 03/30/2017
ms.assetid: a80efb59-591a-4a37-bb3c-8fffa6ca0b7d
ms.openlocfilehash: 315a12c73929bfe71340e42f122ae542d4fddc07
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245023"
---
# <a name="message-security-in-wcf"></a>Nachrichtensicherheit in WCF

Windows Communication Foundation (WCF) verfügt über zwei Haupt Modi für die Bereitstellung von Sicherheit ( `Transport` und `Message` ) sowie einen dritten Modus ( `TransportWithMessageCredential` ), der die beiden kombiniert. In diesem Thema werden die Nachrichtensicherheit und die Gründe für deren Verwendung erläutert.

## <a name="what-is-message-security"></a>Was ist Nachrichtensicherheit?

Durch Nachrichtensicherheit werden Nachrichten mithilfe der WS-Sicherheitsspezifikation gesichert. Die WS-Security-Spezifikation beschreibt Erweiterungen für SOAP-Messaging, um Vertraulichkeit, Integrität und Authentifizierung auf SOAP-Nachrichten Ebene (anstelle der Transport Ebene) sicherzustellen.

Der Unterschied zwischen Nachrichtensicherheit und Transportsicherheit besteht kurz gesagt darin, dass bei der Nachrichtensicherheit die Sicherheitsanmeldeinformationen und Ansprüche zusammen mit dem Nachrichtenschutz in jeder Nachricht gekapselt werden (Signierung oder Verschlüsselung). Die direkte Anwendung der Sicherheit auf die Nachricht durch das Ändern des Nachrichteninhalts ermöglicht gesicherte Nachrichten, die in Bezug auf Sicherheitsaspekte unabhängig sind. Hierdurch werden bestimmte Szenarien unterstützt, die bei Verwendung von Transportsicherheit nicht möglich sind.

## <a name="reasons-to-use-message-security"></a>Gründe für die Verwendung von Nachrichtensicherheit

Bei Verwendung von Sicherheit auf Nachrichtenebene sind alle Sicherheitsinformationen in der Nachricht gekapselt. Die Sicherung von Nachrichten mit Sicherheit auf Nachrichtenebene anstelle von Sicherheit auf Transportebene bietet folgende Vorteile:

- End-to-End-Sicherheit. Transportsicherheit, z. B. Secure Sockets Layer (SSL), schützt Nachrichten nur bei Punkt-zu-Punkt-Kommunikation. Wenn die Nachricht vor dem Erreichen des eigentlichen Empfängers an einen oder mehrere SOAP-Vermittler (z. B. einen Router) weitergeleitet wird, ist die Nachricht selbst nicht mehr geschützt, sobald ein Vermittler diese liest. Darüber hinaus stehen die Clientauthentifizierungsinformationen nur dem ersten Vermittler zur Verfügung und müssen bei Bedarf "Out-of-Band" erneut an den endgültigen Empfänger übertragen werden. Dies gilt auch dann, wenn auf dem gesamten Übertragungsweg SSL-Sicherheit zwischen den einzelnen Übertragungen verwendet wird. Da die Nachrichtensicherheit direkt auf die Nachricht angewendet wird und deren XML-Inhalt sichert, bleibt die Sicherheit der Nachricht unabhängig von der Anzahl der Vermittler gewahrt, an die die Nachricht vor Erreichen des endgültigen Empfängers übertragen wird. Dies ermöglicht ein echtes End-to-End-Sicherheitsszenario.

- Mehr Flexibilität. Es können statt der ganzen Nachricht auch nur Teile der Nachricht signiert oder verschlüsselt werden. Auf diese Weise können die Vermittler die Nachrichtenteile anzeigen, die für sie bestimmt sind. Wenn der Absender möchte, dass die Informationen in der Nachricht für die Vermittler teilweise sichtbar sind, deren Bearbeitung jedoch ausgeschlossen werden soll, kann er die Nachricht nur signieren und unverschlüsselt lassen. Da die Signatur Teil der Nachricht ist, kann der endgültige Empfänger überprüfen, ob die Informationen in der Nachricht unverändert geblieben sind. Ein Szenario könnte sein, dass ein SOAP-Vermittlungsdienst Nachrichten entsprechend dem Aktionsheaderwert weiterleitet. WCF verschlüsselt den Aktionswert standardmäßig nicht, signiert ihn jedoch, wenn die Nachrichten Sicherheit verwendet wird. Daher stehen die Informationen allen Vermittlern zur Verfügung, können von diesen jedoch nicht geändert werden.

- Unterstützung mehrerer Transporte. Sie können gesicherte Nachrichten über viele verschiedene Transporte senden, z. B. benannte Pipes und TCP, ohne sich hinsichtlich Sicherheit auf das Protokoll verlassen zu müssen. Bei Sicherheit auf Transportebene sind alle Sicherheitsinformationen auf eine einzelne Transportverbindung beschränkt und nicht im Nachrichteninhalt selbst verfügbar. Bei Nachrichtensicherheit wird die Nachricht unabhängig von dem für die Übertragung der Nachricht verwendeten Transport gesichert, und der Sicherheitskontext ist direkt in die Nachricht eingebettet.

- Unterstützung eines umfangreichen Satzes von Anmeldeinformationen und Ansprüchen. Die Nachrichtensicherheit basiert auf der WS-Sicherheitsspezifikation. Diese bietet ein erweiterungsfähiges Framework, mit dem jegliche Art von Anspruch innerhalb der SOAP-Nachricht übertragen werden kann. Im Gegensatz zur Transportsicherheit ist der Satz von Authentifizierungsmechanismen oder Ansprüchen, die Sie verwenden können, nicht durch die Transportfunktionen beschränkt. WCF-Nachrichten Sicherheit beinhaltet mehrere Authentifizierungs-und Anspruchs Übertragungsarten und kann so erweitert werden, dass bei Bedarf zusätzliche Typen unterstützt werden. Aus diesen Gründen ist beispielsweise ein Szenario mit verbundenen Anmeldeinformationen ohne Nachrichtensicherheit nicht möglich. Weitere Informationen zu Verbund Szenarien, die von WCF unterstützt werden, finden Sie unter Verbund [und ausgestellte Token](federation-and-issued-tokens.md).

## <a name="how-message-and-transport-security-compare"></a>Vergleich von Nachrichten- und Transportsicherheit

### <a name="pros-and-cons-of-transport-level-security"></a>Vor- und Nachteile der Sicherheit auf Transportebene

Die Transportsicherheit bietet folgende Vorteile:

- Es ist nicht erforderlich, dass die Kommunikationspartner mit den Konzepten der Sicherheit auf XML-Ebene vertraut sind. Dies trägt zu einer besseren Interoperabilität bei, z. B. wenn zum Sichern der Kommunikation HTTPS verwendet wird.

- Insgesamt höhere Leistung.

- Hardwarebeschleunigung ist verfügbar.

- Streaming ist möglich.

 Die Transportsicherheit hat folgende Nachteile:

- Nur Hop-to-Hop (übertragungsbasiert).

- Beschränkter und nicht erweiterbarer Satz von Anmeldeinformationen.

- Transportabhängig.

### <a name="disadvantages-of-message-level-security"></a>Nachteile von Sicherheit auf Nachrichtenebene

Die Nachrichtensicherheit hat folgende Nachteile:

- Leistung

- Nachrichtenstreaming kann nicht verwendet werden.

- Erfordert die Implementierung von Sicherheitsmechanismen auf XML-Ebene und Unterstützung der WS-Sicherheitsspezifikation. Dies kann sich auf die Interoperabilität auswirken.

## <a name="see-also"></a>Weitere Informationen

- [Sichern von Diensten und Clients](securing-services-and-clients.md)
- [Transport Sicherheit](transport-security.md)
- [Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen](how-to-use-transport-security-and-message-credentials.md)
- [Microsoft Patterns and Practices, Chapter 3: Implementing Transport and Message Layer Security (in englischer Sprache)](https://docs.microsoft.com/previous-versions/msp-n-p/ff647370(v=pandp.10))
