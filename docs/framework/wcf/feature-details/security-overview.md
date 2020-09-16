---
title: Sicherheitsübersicht
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, security
- WCF, security
ms.assetid: f478c80d-792d-4e7a-96bd-a2ff0b6f65f9
ms.openlocfilehash: e7dd73b755c7aed91a1fd59baaf9d5e090a36768
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541460"
---
# <a name="windows-communication-foundation-security-overview"></a>Übersicht über Windows Communication Foundation Sicherheit
Windows Communication Foundation (WCF) ist eine auf SOAP-Nachrichten basierende verteilte Programmierplattform, und das Sichern von Nachrichten zwischen Clients und Diensten ist für den Schutz von Daten entscheidend. WCF bietet eine vielseitige und interoperable Plattform für den Austausch sicherer Nachrichten auf der Grundlage der vorhandenen Sicherheitsinfrastruktur und der anerkannten Sicherheitsstandards für SOAP-Nachrichten.  
  
> [!NOTE]
> Eine umfassende Anleitung zur WCF-Sicherheit finden Sie unter [WCF-Sicherheits Leit](https://archive.codeplex.com/?p=WCFSecurity)Faden.  
  
 WCF verwendet Konzepte, die vertraut sind, wenn Sie sichere, verteilte Anwendungen mit vorhandenen Technologien wie HTTPS, integrierter Windows-Sicherheit oder Benutzernamen und Kenn Wörtern zum Authentifizieren von Benutzern erstellt haben. WCF ist nicht nur in vorhandene Sicherheitsinfrastrukturen integriert, sondern erweitert auch verteilte Sicherheit über nur Windows-Domänen hinaus mithilfe von sicheren SOAP-Nachrichten. Beachten Sie, dass WCF eine Implementierung vorhandener Sicherheitsmechanismen mit dem größten Vorteil der Verwendung von SOAP als Protokoll zusätzlich zu den vorhandenen Protokollen bietet. Beispielsweise verfügen Anmeldeinformationen zur Identifizierung eines Clients oder Diensts, wie Benutzername, Kennwort oder X.509-Zertifikate, über interoperable XML-basierte SOAP-Profile. Mithilfe dieser Profile werden Nachrichten durch Nutzen offener Spezifikationen wie digitalen XML-Signaturen und XML-Verschlüsselung sicher ausgetauscht. Eine Liste der Spezifikationen finden Sie [unter von den vom System bereitgestellte Interoperabilitäts Bindungen unterstützte Webdienst Protokolle](web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
 Eine andere Parallele ist das Component Object Model (COM) auf der Windows-Plattform, mit dem sichere verteilte Anwendungen aktiviert werden. COM besitzt einen komplexen Sicherheitsmechanismus, in dem der Sicherheitskontext zwischen Komponenten übergehen kann; dieser Mechanismus gewährleistet Integrität, Vertraulichkeit und Authentifizierung. COM ermöglicht jedoch keine plattformübergreifende, sichere Messaging-wie WCF. Mithilfe von WCF können Sie Dienste und Clients erstellen, die sich von Windows-Domänen über das Internet erstrecken. Die interoperablen Nachrichten von WCF sind für das entwickeln dynamischer, geschäftsorientierter Dienste von entscheidender Bedeutung, die Ihnen dabei helfen, die Sicherheit Ihrer Informationen zu vertrauen.  
  
## <a name="windows-communication-foundation-security-benefits"></a>Vorzüge der Windows Communication Foundation-Sicherheit  
 WCF ist eine auf SOAP-Nachrichten basierende verteilte Programmierplattform. Mithilfe von WCF können Sie Anwendungen erstellen, die sowohl als Dienste als auch als Dienst Clients fungieren und Nachrichten von einer unbegrenzten Anzahl anderer Dienste und Clients erstellen und verarbeiten. In einer derartigen verteilten Anwendung können Nachrichten zwischen Knoten, durch Firewalls, im Internet und durch zahlreiche SOAP-Vermittler fließen. Dies führt zu einer Vielzahl von Nachrichtensicherheitsrisiken. In den folgenden Beispielen werden einige allgemeine Bedrohungen veranschaulicht, die die WCF-Sicherheit beim Austauschen von Nachrichten zwischen Entitäten verringern kann:  
  
- Beobachtung des Netzwerkverkehrs zum Erhalt vertraulicher Informationen. In einem Onlinebanking-Szenario fordert ein Client die Übertragung von Geldmitteln von einem Konto zu einem anderen an. Ein böswilliger Benutzer fängt die Nachricht ab und gelangt dadurch in den Besitz der Kontonummer und des Kennworts. Später überträgt er vom kompromittierten Konto Geldmittel.  
  
- Nicht autorisierte Entitäten, die ohne Wissen des Clients als Dienste fungieren. In diesem Szenario fungiert ein böswilliger Benutzer (die nicht autorisierte Person) als Onlinedienst und fängt Nachrichten vom Client ab, um an vertrauliche Informationen zu gelangen. Dann verwendet der böswillige Benutzer die gestohlenen Daten, um Geldmittel vom kompromittierten Konto zu übertragen. Dieser Angriff wird auch als *Phishingangriff*bezeichnet.  
  
- Vom Aufrufenden nicht beabsichtigte Ergebnisse aufgrund von Nachrichtenänderung. Beispielsweise ermöglicht die Änderung der Nummer eines Kontos, auf das ein Betrag eingezahlt wird, die Übertragung der Geldmittel auf ein nicht autorisiertes Konto.  
  
- Durch Hackermanipulation mehrfach ausgeführte Aktionen. Beispielsweise verschickt ein Hacker mehrmals die gleiche Bestellung. Beispielsweise erhält ein Onlinebuchladen Hunderte von Bestellungen und schickt die Bücher an einen Kunden, der diese Bücher nicht bestellt hat.  
  
- Unmöglichkeit einer Clientauthentifizierung durch einen Dienst. In diesem Fall kann der Dienst nicht gewährleisten, dass die Transaktion von der richtigen Person ausgeführt wurde.  
  
 Zusammenfassung: Übertragungssicherheit bietet folgende Gewährleistungen:  
  
- Dienstendpunkt-Authentifizierung (Empfänger)  
  
- Clientprinzipal-Authentifizierung (Initiator)  
  
- Nachrichtenintegrität  
  
- Nachrichtenvertraulichkeit  
  
- Wiederholungserkennung  
  
### <a name="integration-with-existing-security-infrastructures"></a>Integration in vorhandene Sicherheitsinfrastrukturen  
 Oftmals verfügen Webdienstbereitstellungen bereits über Sicherheitslösungen, beispielsweise Secure Sockets Layer (SSL) oder das Kerberos-Protokoll. Einige nutzen eine bereits zur Verfügung stehende Sicherheitsinfrastruktur; so verwenden Windows-Domänen beispielsweise Active Directory. Häufig ist eine Integration in diese vorhandenen Technologien erforderlich, während neuere Technologien bewertet und übernommen werden müssen.  
  
 WCF-Sicherheit lässt sich in vorhandene Transport Sicherheitsmodelle integrieren und nutzt die vorhandene Infrastruktur für neuere Übertragungs Sicherheitsmodelle basierend auf der SOAP-Nachrichten Sicherheit.  
  
### <a name="integration-with-existing-authentication-models"></a>Integration in vorhandene Authentifizierungsmodelle  
 Ein wichtiger Bestandteil jedes Kommunikationssicherheitsmodells ist die Fähigkeit zur Identifizierung und Authentifizierung von Entitäten in der Kommunikation. Diese Entitäten in der Kommunikation verwenden "digitale Identitäten" oder Anmeldeinformationen, um sich bei den kommunizierenden Peers zu authentifizieren. Im Zuge der Entwicklung verteilter Kommunikationsplattformen wurden verschiedene Modelle für Anmeldeinformations-Authentifizierung und verwandte Sicherheitsmodelle implementiert. Beispielsweise ist das Angeben eines Benutzernamens und Kennworts eine weit verbreitete Methode zur Identifizierung von Benutzern im Internet. In Intranets setzt sich die Verwendung eines Kerberos-Domänencontrollers zur Sicherung von Benutzer- und Dienstauthentifizierung durch. In bestimmten Szenarien, wie beim Kontakt zweier Geschäftspartner, können Zertifikate zur gegenseitigen Authentifizierung verwendet werden.  
  
 Im Bereich der Webdienste, in denen derselbe Dienst unter Umständen sowohl internen Unternehmenskunden als auch externen Partnern oder Internetkunden zur Verfügung steht, ist es wichtig, dass die Infrastruktur eine Integration in diese vorhandenen Sicherheitsauthentifizierungsmodelle ermöglicht. WCF-Sicherheit unterstützt eine Vielzahl von Anmelde Informationstypen (Authentifizierungs Modelle), einschließlich:  
  
- Anonymer Aufrufer  
  
- Anmeldeinformationen für Benutzernamenclient  
  
- Anmeldeinformationen für Zertifikatclient  
  
- Windows (sowohl Kerberos-Protokoll als auch NT LanMan [NTLM]).  
  
### <a name="standards-and-interoperability"></a>Standards und Interoperabilität  
 In einer Welt mit umfangreichen vorhandenen Bereitstellungen ist Homogenität selten. Zwischen verteilten Berechnungs-/Kommunikationsplattformen und den Technologien anderer Anbieter müssen Interaktionen möglich sein. Ebenso muss auch Sicherheit interoperabel sein.  
  
 Um interoperable Sicherheitssysteme verwenden zu können, haben Unternehmen aus der Webdienstbranche verschiedene Standards entwickelt. Insbesondere im Hinblick auf Sicherheitsfragen wurden einige wichtige Standards eingeführt: WS-Sicherheit: SOAP-Nachrichtensicherheit (akzeptiert vom OASIS-Standardausschuss, früher als WS-Sicherheit bezeichnet), WS-Trust, WS-SecureConversation und WS-SecurityPolicy.  
  
 WCF unterstützt eine Vielzahl von Interoperabilitäts Szenarien. Die <xref:System.ServiceModel.BasicHttpBinding>-Klasse bezieht sich auf das Basic Security Profile (BSP), und die <xref:System.ServiceModel.WSHttpBinding>-Klasse bezieht sich auf die aktuellen Sicherheitsstandards (zum Beispiel WS-Security 1.1 und WS-SecureConversation). Durch Einhalten dieser Standards kann die WCF-Sicherheit zusammenarbeiten und in Webdienste integriert werden, die auf Betriebssystemen und anderen Plattformen als Microsoft Windows gehostet werden.  
  
## <a name="wcf-security-functional-areas"></a>WCF-Sicherheit &#8211; Funktionsbereiche  
 Die WCF-Sicherheit ist in drei Funktionsbereiche unterteilt: Übertragungssicherheit, Zugriffs Steuerung und Überwachung. In den folgenden Abschnitten finden Sie eine kurze Erläuterung dieser Bereiche und Links auf weitere Informationen.  
  
### <a name="transfer-security"></a>Übertragungssicherheit  
 Übertragungssicherheit umfasst drei Hauptsicherheitsfunktionen: Integrität, Vertraulichkeit und Authentifizierung. *Integrität* ist die Fähigkeit, zu erkennen, ob eine Nachricht manipuliert wurde. *Vertraulichkeit* ist die Möglichkeit, eine Nachricht von anderen Personen als dem vorgesehenen Empfänger nicht lesbar zu machen. Dies wird durch Kryptografie erreicht. *Authentifizierung* ist die Fähigkeit, eine beanspruchte Identität zu überprüfen. Durch die Kombination dieser drei Funktionen wird sichergestellt, dass Nachrichten sicher zwischen verschiedenen Punkten übertragen werden.  
  
#### <a name="transport-and-message-security-modes"></a>Transport- und Nachrichtensicherheitsmodi  
 Zwei Hauptmechanismen werden verwendet, um die Übertragungssicherheit in WCF zu implementieren: *Transport* Sicherheitsmodus und *Nachrichten* Sicherheitsmodus.  
  
- Der *Transport Sicherheitsmodus* verwendet ein Protokoll auf Transport Ebene, z. b. HTTPS, um die Übertragungssicherheit zu erreichen. Der Transportmodus besitzt den Vorteil seiner großen Verbreitung, der Verfügbarkeit auf zahlreichen Plattformen und seiner geringeren rechnerischen Komplexität. Der Modus besitzt jedoch den Nachteil, dass Nachrichten nur von Punkt zu Punkt (Point-to-Point) gesichert werden.  
  
- Der *Nachrichten Sicherheitsmodus*verwendet dagegen WS-Security (und andere Spezifikationen), um die Übertragungssicherheit zu implementieren. Da die Nachrichtensicherheit direkt für die SOAP-Nachrichten übernommen wird und zusammen mit den Anwendungsdaten in den SOAP-Umschlägen enthalten ist, besitzt sie den Vorteil der Unabhängigkeit von Transportprotokollen, der größeren Erweiterbarkeit und der Gewährleistung von End-to-End-Sicherheit (im Vergleich zu Point-to-Point); der Modus hat den Nachteil deutlich langsamer als der Transportsicherheitsmodus zu sein, da das XML-Format der SOAP-Nachrichten verarbeitet werden muss.  
  
 Weitere Informationen zu diesen Unterschieden finden Sie unter [Sichern von Diensten und Clients](securing-services-and-clients.md).  
  
 Ein dritter Sicherheitsmodus verwendet beide zuvor beschriebenen Modi und vereint deren Vorteile. Dieser Modus wird als `TransportWithMessageCredential` bezeichnet. In diesem Modus wird die Nachrichtensicherheit zum Authentifizieren des Clients verwendet, wohingegen die Transportsicherheit zum Authentifizieren des Servers und zum Sicherstellen von Nachrichtenvertraulichkeit und -integrität dient. Daher ist der `TransportWithMessageCredential`-Sicherheitsmodus beinahe so schnell wie der Transportsicherheitsmodus und ermöglicht die Erweiterbarkeit der Clientauthentifizierung auf dieselbe Weise wie die Nachrichtensicherheit. Im Gegensatz zum Nachrichtensicherheitsmodus bietet dieser Modus keine vollständige End-to-End-Sicherheit.  
  
### <a name="access-control"></a>Zugriffssteuerung  
 Die *Zugriffs Steuerung* wird auch als Autorisierung bezeichnet. Mithilfe der *Autorisierung* können unterschiedliche Benutzer über unterschiedliche Berechtigungen zum Anzeigen von Daten verfügen. Da die Dateien der Personalabteilung eines Unternehmens vertrauliche Mitarbeiterdaten enthalten, sind nur Abteilungsleiter zum Einsehen der Mitarbeiterdaten berechtigt. Zudem können Ableitungsleiter nur Daten für ihre direkten Berichte anzeigen. In diesem Fall basiert die Zugriffssteuerung sowohl auf der Rolle ("Abteilungsleiter") als auch auf der speziellen Identität des Abteilungsleiters (dadurch wird ein anderer Abteilungsleiter an der Einsicht in die Unterlagen eines Mitarbeiters gehindert).  
  
 In WCF werden Zugriffs Steuerungsfunktionen durch Integration in die Common Language Runtime (CLR) <xref:System.Security.Permissions.PrincipalPermissionAttribute> und durch eine Reihe von APIs bereitgestellt, die als *Identitäts Modell*bezeichnet werden. Ausführliche Informationen zur Zugriffs Steuerung und zur Anspruchs basierten Autorisierung finden Sie unter [Erweitern der Sicherheit](../extending/extending-security.md).  
  
### <a name="auditing"></a>Überwachung  
 Die *Überwachung ist die* Protokollierung von Sicherheits Ereignissen im Windows-Ereignisprotokoll. Sie können sicherheitsbezogene Ereignisse protokollieren, z. B. Authentifizierungsfehler (oder erfolgreiche Authentifizierungen). Weitere Informationen finden Sie unter [Auditing](auditing-security-events.md). Weitere Informationen zur Programmierung finden [Sie unter Gewusst wie:](how-to-audit-wcf-security-events.md)überwachen von Sicherheits Ereignissen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [Sichern von Diensten](../securing-services.md)
- [Häufige Sicherheitsszenarien](common-security-scenarios.md)
- [Bindungen und Sicherheit](bindings-and-security.md)
- [Sichern von Diensten und Clients](securing-services-and-clients.md)
- [Authentifizierung](authentication-in-wcf.md)
- [Autorisierung](authorization-in-wcf.md)
- [Verbund und ausgestellte Token](federation-and-issued-tokens.md)
- [Überwachung](auditing-security-events.md)
- [Sicherheitsleitfaden und empfohlene Vorgehensweisen](security-guidance-and-best-practices.md)
- [Konfigurieren von Diensten mit Konfigurationsdateien](../configuring-services-using-configuration-files.md)
- [Vom System bereitgestellte Bindungen](../system-provided-bindings.md)
- [Übersicht über die Endpunkterstellung](../endpoint-creation-overview.md)
- [Erweitern der Sicherheit](../extending/extending-security.md)
- [Sicherheitsmodell für Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))
