---
title: Windows Communication Foundation-Datenschutzinformationen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
ms.openlocfilehash: e278b28e5c0015eeab549b04d3870dfa247a57ed
ms.sourcegitcommit: e8dc507cfdaad504fc9d4c83d28d24569dcef91c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2018
ms.locfileid: "33808870"
---
# <a name="windows-communication-foundation-privacy-information"></a>Windows Communication Foundation-Datenschutzinformationen
Microsoft verpflichtet sich, die persönlichen Daten von Endbenutzern vertraulich zu behandeln. Bei der Erstellung einer Anwendung mithilfe von Windows Communication Foundation (WCF), Version 3.0, kann Ihre Anwendung Datenschutz der Endbenutzer beeinträchtigen. Die Anwendung erfasst z. B. unter Umständen explizit Kontaktinformationen des Benutzers oder fordert Informationen an und sendet diese über das Internet an Ihre Website. Wenn Sie Microsoft-Technologie in Ihre Anwendung einbetten, kann sich das Verhalten dieser Technologie ebenfalls auf den Datenschutz auswirken. WCF sendet nicht an Microsoft aus Ihrer Anwendung Informationen, sofern Ihnen oder dem Endbenutzer Sie uns senden möchten.  
  
## <a name="wcf-in-brief"></a>WCF in Kürze  
 WCF ist ein verteiltes Messagingframework, das mithilfe von Microsoft .NET Framework, die Entwickler verteilte Anwendungen erstellen kann. Zwischen zwei Anwendungen übermittelte Nachrichten enthalten Header- und Textinformationen.  
  
 Header können je nach von der Anwendung verwendeten Diensten unter anderem Meldungsrouting, Sicherheitsinformationen und Transaktionen enthalten. Nachrichten werden in der Regel standardmäßig verschlüsselt. Eine Ausnahme ist die Verwendung der `BasicHttpBinding`, die für nicht gesicherte, ältere Webdienste konzipiert wurde. Als Anwendungs-Designer sind Sie für den abschließenden Entwurf verantwortlich. Nachrichten in der SOAP-Text enthalten anwendungsspezifische Daten; Allerdings können diese Daten, z. B. Anwendung definierte persönliche Daten gesichert werden, mithilfe von verschlüsselungs- oder vertraulichkeitsfunktionen WCF-Funktionen. In den folgenden Abschnitten werden die Funktionen beschrieben, die sich auf den Datenschutz auswirken können.  
  
## <a name="messaging"></a>Messaging  
 Jede WCF-Nachricht besitzt einen Adressheader, der angibt, das Ziel der Nachricht und, in dem die Antwort.  
  
 Die Adresskomponente einer Endpunktadresse ist ein URI (Uniform Resource Identifier), der den Endpunkt identifiziert. Die Adresse kann eine Netzwerkadresse oder eine logische Adresse sein. Die Adresse kann den Computernamen (Hostname, vollqualifizierter Domänenname) und eine IP-Adresse einschließen. Die Endpunktadresse kann außerdem eine GUID (Globally Unique Identifier) oder eine Auflistung von GUIDs für die temporäre Adressierung zum Ermitteln jeder Adresse enthalten. Jede Nachricht enthält eine Nachrichten-ID, die eine GUID ist. Diese Funktion folgt dem WS-Addressierungs-Verweisstandard.  
  
 Der WCF-Messagingebene schreibt keine persönlichen Informationen nicht auf dem lokalen Computer. Sie kann jedoch persönliche Daten auf der Netzwerkebene weitergeben, wenn ein Diensteentwickler einen Dienst erstellt hat, der solche Informationen verfügbar macht (z. B. durch das Verwenden des Namens einer Person in einem Endpunktnamen oder durch das Aufnehmen persönlicher Daten in die WSDL des Endpunkts, ohne dass Clients zum Zugriff auf die WSDL HTTPS verwenden müssen). Auch wenn ein Entwickler ausgeführt wird. die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) -Tool gegen einen Endpunkt, die persönlichen Daten, die Ausgabe des Tools verfügbar macht, kann diese Informationen enthalten, und in die Ausgabedatei geschrieben der lokale Festplatte.  
  
## <a name="hosting"></a>Hosting  
 Die Hostingfunktion in WCF ermöglicht Anwendungen, um bei Bedarf starten oder Aktivieren der Anschlussfreigabe zwischen mehreren Anwendungen. Kann eine WCF-Anwendung in IIS (Internetinformationsdienste), ähnlich wie gehostet werden [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
 Das Hosting macht keine spezifischen Informationen im Netzwerk verfügbar und behält keine Daten auf dem Computer bei.  
  
## <a name="message-security"></a>Nachrichtensicherheit  
 WCF-Sicherheit stellt die Sicherheitsfunktionen für Messaginganwendungen bereit. Die bereitgestellten Sicherheitsfunktionen bieten Authentifizierung und Autorisierung.  
  
 Die Authentifizierung wird ausgeführt, indem Anmeldeinformationen zwischen den Clients und Diensten übergeben werden. Die Authentifizierung kann entweder durch Sicherheit auf Transportebene oder durch SOAP-Sicherheit auf Nachrichtenebene erfolgen:  
  
-   Bei der SOAP-Nachrichtensicherheit erfolgt die Authentifizierung durch Anmeldeinformationen wie Benutzername/Kennwörter, X.509-Zertifikate, Kerberos-Tickets und SAML-Token, die alle je nach Aussteller persönliche Daten enthalten können.  
  
-   Bei der Transportsicherheit erfolgt die Authentifizierung durch herkömmliche Transportauthentifizierungsmechanismen wie HTTP-Authentifizierungsschemas (Basic, Digest, Negotiate, Integrierte Windows-Authentifizierung, NTLM, Keine, Anonym) und Formularauthentifizierung.  
  
 Die Authentifizierung kann zu einer sicheren Sitzung zwischen den kommunizierenden Endpunkten führen. Die Sitzung wird durch eine GUID identifiziert, die über die Lebensdauer der Sicherheitssitzung reicht. Die folgende Tabelle zeigt, welche Elemente wo gespeichert werden.  
  
|Daten|Speicher|  
|----------|-------------|  
|Präsentationsanmeldeinformationen, z. B. Benutzername, X.509-Zertifikate, Kerberos-Token und Verweise auf Anmeldeinformationen.|Standardmäßige Windows-Verwaltungsmechanismen für Anmeldeinformationen, z. B. der Windows-Zertifikatspeicher.|  
|Benutzermitgliedschaftsinformationen, z. B. Benutzernamen und Kennwörter.|[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]-Mitgliedschaftsanbieter.|  
|Identitätsinformationen über den Dienst zum Authentifizieren des Diensts gegenüber Clients.|Endpunktadresse des Diensts.|  
|Aufruferdaten.|Überwachungsprotokolle.|  
  
## <a name="auditing"></a>Überwachung  
 Bei der Überwachung wird der Erfolg und das Fehlschlagen von Authentifizierungs- und Autorisierungsereignissen aufgezeichnet. Überwachungsdatensätze enthalten die folgenden Daten: Dienst-URI, Aktions-URI und Identifikation des Aufrufers.  
  
 Bei der Überwachung werden Daten auch dann aufgezeichnet, wenn der Administrator die Konfiguration der Nachrichtenprotokollierung ändert (aktiviert oder deaktiviert), da bei der Nachrichtenprotokollierung anwendungsspezifische Daten im Header und Text erfasst werden können. In [!INCLUDE[wxp](../../../includes/wxp-md.md)] wird ein Datensatz im Anwendungsereignisprotokoll protokolliert. In [!INCLUDE[wv](../../../includes/wv-md.md)] und [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] wird ein Datensatz im Sicherheitsereignisprotokoll protokolliert.  
  
## <a name="transactions"></a>Transaktionen  
 Die Transaktionsfunktion stellt Transaktionsdienste für eine WCF-Anwendung bereit.  
  
 Bei der Transaktionsweitergabe verwendete Transaktionsheader enthalten möglicherweise TransaktionsIDs oder Eintragung-IDs, die GUIDs sind.  
  
 Das Tansaktionsfeature verwendet den MSDTC (Microsoft Distributed Transaction Coordinator)-Transaktions-Manager (eine Windows-Komponente) zum Verwalten des Transaktionszustands. Standardmäßig sind Kommunikationen zwischen Transaktions-Managern verschlüsselt. Transaktions-Manager protokollieren möglicherweise Endpunktverweise, Transaktions-IDs und Eintragung-IDs als Teil ihres permanenten Zustands. Die Lebensdauer dieses Zustands wird von der Lebensdauer der Protokolldatei des Transaktions-Managers bestimmt. Der MSDTC-Dienst besitzt dieses Protokoll und behält es bei.  
  
 Die Transaktionsfunktion implementiert die Standards WS-Coordination und WS-Atomic Transaction.  
  
## <a name="reliable-sessions"></a>Zuverlässige Sitzungen  
 Zuverlässige Sitzungen in WCF bieten die Übertragung von Nachrichten an, wenn Transport- oder Vermittler Fehler auftreten. Sie bieten auch dann genau eine Übertragung von Nachrichten, wenn die Verbindung zum zugrunde liegenden Transport unterbrochen wird (z. B. eine TCP-Verbindung in einem drahtlosen Netzwerk) oder eine Nachricht verloren geht (ein HTTP-Proxy verwirft eine aus- oder eingehende Nachricht). Zuverlässige Sitzungen heben außerdem die Neuordnung von Nachrichten auf (z. B. beim Multipfad-Routing), wodurch die Reihenfolge beibehalten wird, in der die Nachrichten gesendet wurden.  
  
 Zuverlässige Sitzungen werden mit dem WS-RM (WS-ReliableMessaging)-Protokoll implementiert. Sie fügen WS-RM-Header hinzu, die Sitzungsinformationen enthalten, die zum Identifizieren aller einer bestimmten zuverlässigen Sitzung zugeordneten Nachrichten verwendet werden. Jede WS-RM-Sitzung hat einen Bezeichner, der eine GUID ist.  
  
 Auf dem Computer des Endbenutzers werden keine persönlichen Informationen beibehalten.  
  
## <a name="queued-channels"></a>In der Warteschlange stehende Kanäle  
 Warteschlangen speichern Nachrichten von einer sendenden Anwendung für eine empfangende Anwendung und leiten sie später an die empfangende Anwendung weiter. Sie sichern die Nachrichtenübertragung von sendenden Anwendungen an empfangende Anwendungen, wenn z. B. die empfangende Anwendung flüchtig ist. WCF bietet Unterstützung für Warteschlangenvorgänge durch die Nutzung von Microsoft Message Queuing (MSMQ) als Transport.  
  
 Die Funktion für in der Warteschlange stehende Kanäle fügt einer Nachricht keine Header hinzu. Es erstellt stattdessen eine Message Queuing-Nachricht mit entsprechenden Einstellungen und ruft Message Queuing-Methoden zum Platzieren der Nachricht in die Message Queuing-Warteschlange auf. Message Queuing ist eine in Windows enthaltene optionale Komponente.  
  
 Durch dieses Feature werden auf dem Computer des Endbenutzers keine Informationen beibehalten, da es Message Queuing als Warteschlangeninfrastruktur verwendet.  
  
## <a name="com-integration"></a>COM+-Integration  
 Diese Funktion schließt vorhandene COM- und COM+-Funktionen zum Erstellen von Diensten, die mit WCF-Diensten kompatibel sind. Diese Funktion verwendet keine bestimmten Header, und es behält keine Daten auf dem Computer des Endbenutzers bei.  
  
## <a name="com-service-moniker"></a>COM-Dienstmoniker  
 Dies bietet einen nicht verwalteten Wrapper um einem standard-WCF-Client. Diese Funktion verwendet keine bestimmten Header, und sie behält keine Daten auf dem Computer bei.  
  
## <a name="peer-channel"></a>Peerkanal  
 Ein Peerkanal ermöglicht die Entwicklung von mehrparteienanwendungen mithilfe von WCF. Mehrparteienmessaging tritt im Kontext eines Netzes auf. Netze werden mit einem Namen identifiziert, den Knoten verknüpfen können. Jeder Knoten im Peerkanal erstellt einen TCP-Listener an einem vom Benutzer angegebenen Anschluss und stellt Verbindungen mit anderen Knoten im Netz her, um die Flexibilität zu sichern. Für diese Verbindungen tauschen Knoten auch bestimmte Daten wie die Listeneradresse und die IP-Adresse des Computers mit anderen Knoten im Netz aus. Innerhalb des Netzes gesendete Nachrichten können Sicherheitsinformationen enthalten, die sich auf den Absender beziehen, um Nachrichtenspoofing und -manipulation zu verhindern.  
  
 Auf dem Computer des Endbenutzers werden keine persönlichen Informationen gespeichert.  
  
## <a name="it-professional-experience"></a>Arbeit von IT-Fachleuten  
  
### <a name="tracing"></a>Ablaufverfolgung  
 Die Diagnosefunktion der WCF-Infrastruktur protokolliert Nachrichten, die über den Transport und Dienstebenen Ausführen-Modell, und die Aktivitäten und Ereignisse im Zusammenhang mit diesen Nachrichten übergeben. Diese Funktion ist standardmäßig deaktiviert. Mithilfe der Anwendungskonfigurationsdatei aktiviert und Verhalten für die Ablaufverfolgung kann mithilfe des WCF WMI-Anbieters zur Laufzeit geändert werden. Wenn das Feature aktiviert ist, gibt die Ablaufverfolgungsinfrastruktur eine Diagnoseablaufverfolgung mit Nachrichten, Aktivitäten und Verarbeitungsereignissen an konfigurierte Listener aus. Format und Speicherort der Ausgabe werden durch die Listener-Konfigurationsauswahl des Administrators bestimmt; normalerweise ist es eine Datei im XML-Format. Der Administrator ist verantwortlich für das Festlegen der Zugriffssteuerungsliste (ACL) für die Ablaufverfolgungsdateien. Insbesondere beim Hosten durch WAS (Windows Activation System) muss der Administrator sicherstellen, dass die Dateien nicht im öffentlichen virtuellen Stammverzeichnis befinden, falls dies nicht gewünscht ist.  
  
 Es gibt zwei Typen von Ablaufverfolgung, Nachrichtenprotokollierung und Dienstmodell-Diagnoseablaufverfolgung, die im folgenden Abschnitt beschrieben werden. Jeder Typ wird über seine eigene Ablaufverfolgungsquelle konfiguriert: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> und <xref:System.ServiceModel>. Beide Protokollierungs-Ablaufverfolgungsquellen erfassen Daten, die lokale Daten der Anwendung sind.  
  
### <a name="message-logging"></a>Nachrichtenprotokollierung  
 Die Ablaufverfolgungsquelle für die Nachrichtenprotokollierung (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) ermöglicht einem Administrator das Protokollieren der Nachrichten, die das System durchlaufen. Über die Konfiguration kann der Benutzer entscheiden, ob ganze Nachrichten oder nur Nachrichtenheader protokolliert werden, ob die Protokollierung auf der Transport- und/oder der Dienstmodellebene erfolgt und ob falsch formatierte Nachrichten erfasst werden. Außerdem kann der Benutzer die Filterung konfigurieren, um einzuschränken, welche Nachrichten protokolliert werden.  
  
 Standardmäßig ist die Nachrichtenprotokollierung deaktiviert. Der Administrator auf dem lokalen Computer kann verhindern, dass der Administrator auf Anwendungsebene die Nachrichtenprotokollierung aktiviert.  
  
#### <a name="encrypted-and-decrypted-message-logging"></a>Verschlüsselte und entschlüsselte Nachrichtenprotokollierung  
 Nachrichten werden wie in den folgenden Begriffen beschrieben protokolliert, verschlüsselt oder entschlüsselt.  
  
 Transportprotokollierung  
 Protokolliert auf der Transportebene empfangene und gesendete Nachrichten. Diese Nachrichten enthalten alle Header und werden möglicherweise vor dem Versenden und beim Empfangen verschlüsselt.  
  
 Wenn Nachrichten vor dem Versenden und beim Empfangen verschlüsselt werden, werden sie auch verschlüsselt protokolliert. Eine Ausnahme ist die Verwendung eines Sicherheitsprotokolls (HTTPS); die Nachrichten werden vor dem Senden und nach dem Empfangen entschlüsselt protokolliert, auch wenn sie beim Versenden verschlüsselt sind.  
  
 Dienstprotokollierung  
 Protokolliert auf der Dienstmodellebene empfangene oder gesendete Nachrichten nach der Kanalheader-Verarbeitung, unmittelbar vor und nach der Eingabe von Benutzercode.  
  
 Auf dieser Ebene protokollierte Nachrichten werden entschlüsselt, auch wenn sie für die Übertragung gesichert und verschlüsselt wurden.  
  
 Protokollierung falsch formatierter Nachrichten  
 Protokolliert Meldungen, die die WCF-Infrastruktur zu verstehen oder verarbeitet werden kann.  
  
 Nachrichten werden unverändert protokolliert, d. h. verschlüsselt oder nicht verschlüsselt.  
  
 Wenn Meldungen, in protokolliert werden entfernt entschlüsselter oder unverschlüsselter Form standardmäßig WCF Sicherheitsschlüssel und mögliche persönliche Informationen aus den Nachrichten vor dem protokollieren. In den nächsten Abschnitten wird beschrieben, welche Informationen wann entfernt werden. Der Computeradministrator und der Anwendungsbereitsteller müssen bestimmte Konfigurationsschritte durchführen, um das Standardverhalten so zu ändern, dass Schlüssel und mögliche persönliche Informationen protokolliert werden.  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a>Aus Nachrichtenheadern bei der Protokollierung entschlüsselter/unverschlüsselter Nachrichten entfernte Informationen  
 Wenn Nachrichten in entschlüsselter/unverschlüsselter Form protokolliert werden, werden standardmäßig vor dem Protokollieren Sicherheitsschlüssel und mögliche persönliche Informationen aus Nachrichtenheadern und Nachrichtentext entfernt. Die folgende Liste zeigt die WCF-Schlüssel und mögliche persönliche Informationen betrachtet.  
  
 Schlüssel, die entfernt werden:  
  
 \- Für Xmlns:wst = "http://schemas.xmlsoap.org/ws/2004/04/trust" und Xmlns:wst = "http://schemas.xmlsoap.org/ws/2005/02/trust"  
  
 wst:BinarySecret  
  
 wst:Entropy  
  
 \- Für Xmlns:wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" und Xmlns:wsse = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"  
  
 wsse:Password  
  
 wsse:Nonce  
  
 Mögliche persönliche Informationen, die entfernt werden:  
  
 \- Für Xmlns:wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" und Xmlns:wsse = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"  
  
 wsse:Username  
  
 wsse:BinarySecurityToken  
  
 \- Für xmlns = "Urn: Oasis: Namen: Tc: SAML:1.0:assertion" werden die Objekte in Fettschrift angezeigt (siehe unten) entfernt:  
  
 \<Assertion  
  
 MajorVersion="1"  
  
 MinorVersion="1"  
  
 AssertionId="[ID]"  
  
 Issuer="[string]"  
  
 IssueInstant="[dateTime]"  
  
 >  
  
 \<Bedingungen NotBefore = "[" DateTime "]" NotOnOrAfter "DateTime" = >  
  
 \<AudienceRestrictionCondition>  
  
 \<Zielgruppe > [Uri]\</Audience > +  
  
 \</AudienceRestrictionCondition>*  
  
 \<DoNotCacheCondition / > *  
  
 <\!--abstrakten Basistyp.  
  
 \<Bedingung / > *  
  
 -->  
  
 \</ Bedingungen >?  
  
 \<Ratschläge >  
  
 \<AssertionIDReference > [ID]\</AssertionIDReference > *  
  
 \<Assertion > [Assertion]\</Assertion > *  
  
 [any]*  
  
 \</-Meldung >?  
  
 <\!--Abstrakter Basistypen  
  
 \<Anweisung / > *  
  
 \<SubjectStatement >  
  
 \<Betreff >  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 \<SubjectConfirmation >  
  
 \<ConfirmationMethod > [AnyUri]\</ConfirmationMethod > +  
  
 \<SubjectConfirmationData > [any]\</SubjectConfirmationData >?  
  
 \<DS: KeyInfo >... \</ds:KeyInfo >?  
  
 \</ SubjectConfirmation >?  
  
 \</ Betreff >  
  
 \</ SubjectStatement > *  
  
 -->  
  
 \<AuthenticationStatement  
  
 AuthenticationMethod="[uri]"  
  
 AuthenticationInstant="[dateTime]"  
  
 >  
  
 [Subject]  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 <AuthorityBinding  
  
 AuthorityKind="[QName]"  
  
 Location="[uri]"  
  
 Binding="[uri]"  
  
 />*  
  
 \</ AuthenticationStatement > *  
  
 \<AttributeStatement>  
  
 [Subject]  
  
 \<Attribut  
  
 AttributeName="[string]"  
  
 AttributeNamespace="[uri]"  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 \</-Attribut > +  
  
 \</AttributeStatement>*  
  
 \<AuthorizationDecisionStatement  
  
 Resource="[uri]"  
  
 Entscheidung = "[zulassen&#124;Verweigern&#124;unbestimmten]"  
  
 >  
  
 [Subject]  
  
 \<Aktion-Namespace = "[Uri]" > [String] \< /Action > +  
  
 \<Beweise >  
  
 \<AssertionIDReference > [ID]\</AssertionIDReference > +  
  
 \<Assertion > [Assertion]\</Assertion > +  
  
 \</ Beweis >?  
  
 \</AuthorizationDecisionStatement>*  
  
 \</Assertion>  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a>Aus Nachrichtentext bei der Protokollierung entschlüsselter/unverschlüsselter Nachrichten entfernte Informationen  
 Wie zuvor beschrieben, WCF entfernt Schlüssel und bekannte mögliche persönliche Informationen aus Nachrichtenheadern für Protokollierung entschlüsselter/unverschlüsselter Nachrichten. Darüber hinaus entfällt WCF Schlüssel und bekannte mögliche persönliche Informationen aus Nachrichtentext für die Textelemente und Aktionen in der folgenden Liste, die sicherheitsmeldungen beim Schlüsselaustausch beschreiben.  
  
 Für die folgenden Namespaces:  
  
 Xmlns:WST = "http://schemas.xmlsoap.org/ws/2004/04/trust" und Xmlns:wst = "http://schemas.xmlsoap.org/ws/2005/02/trust" (z. B., wenn keine Aktion verfügbar ist)  
  
 Informationen werden für diese Textelemente entfernt, die Schlüsselaustausch einschließen:  
  
 wst:RequestSecurityToken  
  
 wst:RequestSecurityTokenResponse  
  
 wst:RequestSecurityTokenResponseCollection  
  
 Informationen werden auch für jede der folgenden Aktionen entfernt:  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Renew  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Renew  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Validate  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Validate  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Renew  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Renew  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel  
  
 http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT  
  
 http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT  
  
 http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT-Amend  
  
 http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT-Amend  
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a>Aus anwendungsspezifischen Headern und Textdaten werden keine Informationen entfernt.  
 WCF verfolgt keine persönlichen Informationen in anwendungsspezifischen Headern (z. B. Abfragezeichenfolgen) oder Textdaten (z. B. Kreditkartennummer).  
  
 Bei aktivierter Nachrichtenprotokollierung sind persönliche Informationen in anwendungsspezifischen Headern und Textdaten unter Umständen in den Protokollen sichtbar. Der Anwendungsbereitsteller ist für das Festlegen der ACLs für die Konfigurations- und Protokolldateien verantwortlich. Er kann auch die Protokollierung deaktivieren, wenn diese Informationen nicht sichtbar sein sollen, oder diese Informationen aus den Protokolldateien herausfiltern.  
  
### <a name="service-model-tracing"></a>Dienstmodell-Ablaufverfolgung  
 Die Dienstmodell-Ablaufverfolgungsquelle (<xref:System.ServiceModel>) aktiviert die Ablaufverfolgung von mit der Nachrichtenverarbeitung verknüpften Aktivitäten und Ereignissen. Dieses Feature verwendet die .NET Framework-Diagnosefunktionalität von <xref:System.Diagnostics>. Wie bei der <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>-Eigenschaft können der Speicherort und die ACL mit den Konfigurationsdateien der .NET Framework-Anwendung vom Benutzer konfiguriert werden. Wie bei der Nachrichtenprotokollierung wird der Speicherort der Datei immer konfiguriert, wenn der Administrator die Ablaufverfolgung aktiviert; der Administrator steuert also die ACL.  
  
 Ablaufverfolgungen enthalten Nachrichtenheader, wenn sich eine Nachricht im Gültigkeitsbereich befindet. Dabei gilt die gleiche Regel für das Ausblenden möglicher persönlicher Informationen in Nachrichtenheadern wie im vorherigen Abschnitt: Die zuvor identifizierten persönlichen Informationen werden standardmäßig aus den Headern in Ablaufverfolgungen entfernt. Der Computeradministrator und der Anwendungsbereitsteller müssen die Konfiguration ändern, damit mögliche persönliche Informationen protokolliert werden. Allerdings werden in anwendungsspezifischen Headern enthaltene persönliche Informationen in Ablaufverfolgungen protokolliert. Der Anwendungsbereitsteller ist für das Festlegen der ACLs für die Konfigurations- und Ablaufverfolgungsdateien verantwortlich. Er kann auch die Ablaufverfolgung deaktivieren, wenn diese Informationen nicht sichtbar sein sollen, oder diese Informationen nach der Protokollierung aus den Ablaufverfolgungsdateien herausfiltern.  
  
 Als Teil der Dienstmodell-Ablaufverfolgung verknüpfen eindeutige IDs (die als Aktivitäts-IDs bezeichnet werden, in der Regel eine GUID) unterschiedliche Aktivitäten, wenn eine Nachricht verschiedene Teile der Infrastruktur durchläuft.  
  
#### <a name="custom-trace-listeners"></a>Benutzerdefinierte Ablaufverfolgungslistener  
 Sowohl für die Nachrichtenprotokollierung als auch die Ablaufverfolgung kann ein benutzerdefinierter Ablaufverfolgungslistener konfiguriert werden, der Ablaufverfolgungen und Nachrichten überträgt, z. B. an eine Remotedatenbank. Der Anwendungsbereitsteller ist für das Konfigurieren benutzerdefinierter Listener oder das Ermöglichen dieser Aktion durch Benutzer verantwortlich. Er ist außerdem für am Remotespeicherort verfügbar gemachte persönliche Informationen und für die korrekte Anwendung von ACLs auf diesen Speicherort verantwortlich.  
  
### <a name="other-features-for-it-professionals"></a>Andere Funktionen für IT-Fachleute  
 WCF bietet es sich um einen WMI-Anbieter, der die Konfigurationsinformationen des WCF-Infrastruktur über WMI (im Lieferumfang von Windows enthalten) verfügbar macht. Standardmäßig steht die WMI-Schnittstelle Administratoren zur Verfügung.  
  
 WCF-Konfiguration verwendet die .NET Framework-Konfigurationsverfahren. Die Konfigurationsdateien werden auf dem Computer gespeichert. Der Anwendungsentwickler und der Administrator erstellen die Konfigurationsdateien und die ACL für jede Anwendungsanforderung. Eine Konfigurationsdatei kann Endpunktadressen und Links zu Zertifikaten im Zertifikatspeicher enthalten. Mithilfe der Zertifikate können Anwendungsdaten zum Konfigurieren verschiedener Eigenschaften der von der Anwendung verwendeten Funktionen bereitgestellt werden.  
  
 WCF verwendet auch die prozesssicherungsfunktionalität von .NET Framework durch Aufrufen der <xref:System.Environment.FailFast%2A> Methode.  
  
### <a name="it-pro-tools"></a>Tools für IT-Fachleute  
 WCF bietet auch die folgenden IT professionelle Tools, die im Windows SDK ausgeliefert.  
  
#### <a name="svctraceviewerexe"></a>SvcTraceViewer.exe  
 Der Viewer zeigt die WCF-Ablaufverfolgungsdateien. Der Viewer zeigt an, welche Daten in den Ablaufverfolgungen enthalten sind.  
  
#### <a name="svcconfigeditorexe"></a>SvcConfigEditor.exe  
 Der Editor ermöglicht den Benutzer zum Erstellen und Bearbeiten von WCF-Konfigurationsdateien. Der Editor zeigt an, welche Daten in den Konfigurationsdateien enthalten sind. Für die gleiche Aufgabe kann auch ein Text-Editor verwendet werden.  
  
#### <a name="servicemodelreg"></a>ServiceModel_Reg  
 Mit diesem Tool kann der Benutzer ServiceModel-Installationen auf einem Computer verwalten. Das Tool zeigt statusmeldungen in einem Konsolenfenster ein, wenn es ausgeführt wird und in den Prozess möglicherweise Informationen zur Konfiguration der WCF-Installation angezeigt.  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a>WSATConfig.exe und WSATUI.dll  
 Mit diesen Tools können IT-Experten interoperable WS-AtomicTransaction Netzwerkunterstützung in WCF zu konfigurieren. Mithilfe der Tools kann der Benutzer die Werte der in der Registrierung gespeicherten am häufigsten verwendeten WS-AtomicTransaction-Einstellungen anzeigen und ändern.  
  
## <a name="cross-cutting-features"></a>Querschnittliche Features  
 Die folgenden Features sind querschnittliche Features. Das heißt, sie können mit allen vorangehenden Features zusammengesetzt werden.  
  
### <a name="service-framework"></a>Dienstframework  
 Header können eine Instanz-ID enthalten; dies ist eine GUID, die eine Nachricht einer Instanz einer CLR-Klasse zuordnet.  
  
 Die WSDL (Web Services Description Language) enthält eine Definition des Anschlusses. Jeder Anschluss verfügt über eine Endpunktadresse und eine Bindung, die die von der Anwendung verwendeten Dienste darstellt. Das Verfügbarmachen der WSDL kann mithilfe der Konfiguration deaktiviert werden. Auf dem Computer werden keine Informationen beibehalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Communication Foundation](http://msdn.microsoft.com/library/fd327ade-0260-4c40-adbe-b74645ba3277)  
 [Sicherheit](../../../docs/framework/wcf/feature-details/security.md)
