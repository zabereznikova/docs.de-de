---
title: Windows Communication Foundation-Datenschutzinformationen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
ms.openlocfilehash: 30ea92f09bc655796b6bc268212b6d9e0e05bd9b
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76919331"
---
# <a name="windows-communication-foundation-privacy-information"></a>Windows Communication Foundation-Datenschutzinformationen
Microsoft verpflichtet sich, die persönlichen Daten von Endbenutzern vertraulich zu behandeln. Wenn Sie eine Anwendung mit Windows Communication Foundation (WCF), Version 3,0, erstellen, wirkt sich die Anwendung möglicherweise auf den Datenschutz der Endbenutzer aus. Die Anwendung erfasst z. B. unter Umständen explizit Kontaktinformationen des Benutzers oder fordert Informationen an und sendet diese über das Internet an Ihre Website. Wenn Sie Microsoft-Technologie in Ihre Anwendung einbetten, kann sich das Verhalten dieser Technologie ebenfalls auf den Datenschutz auswirken. WCF sendet keine Informationen von Ihrer Anwendung an Microsoft, es sei denn, Sie oder der Endbenutzer haben diese an uns gesendet.  
  
## <a name="wcf-in-brief"></a>WCF in Kürze  
 WCF ist ein verteiltes Messaging Framework, das das Microsoft .NET Framework verwendet, das Entwicklern das Erstellen verteilter Anwendungen ermöglicht. Zwischen zwei Anwendungen übermittelte Nachrichten enthalten Header- und Textinformationen.  
  
 Header können je nach von der Anwendung verwendeten Diensten unter anderem Meldungsrouting, Sicherheitsinformationen und Transaktionen enthalten. Nachrichten werden in der Regel standardmäßig verschlüsselt. Eine Ausnahme ist die Verwendung der `BasicHttpBinding`, die für nicht gesicherte, ältere Webdienste konzipiert wurde. Als Anwendungs-Designer sind Sie für den abschließenden Entwurf verantwortlich. Nachrichten im SOAP-Text enthalten anwendungsspezifische Daten. Allerdings können diese Daten, z. b. Anwendungs definierte persönliche Informationen, mithilfe von WCF-Verschlüsselungs-oder Vertraulichkeits Features gesichert werden. In den folgenden Abschnitten werden die Funktionen beschrieben, die sich auf den Datenschutz auswirken können.  
  
## <a name="messaging"></a>Messaging  
 Jede WCF-Nachricht verfügt über einen Adress Header, der das Nachrichten Ziel angibt, und wo die Antwort gesendet werden soll.  
  
 Die Adresskomponente einer Endpunktadresse ist ein URI (Uniform Resource Identifier), der den Endpunkt identifiziert. Die Adresse kann eine Netzwerkadresse oder eine logische Adresse sein. Die Adresse kann den Computernamen (Hostname, vollqualifizierter Domänenname) und eine IP-Adresse einschließen. Die Endpunktadresse kann außerdem eine GUID (Globally Unique Identifier) oder eine Auflistung von GUIDs für die temporäre Adressierung zum Ermitteln jeder Adresse enthalten. Jede Nachricht enthält eine Nachrichten-ID, die eine GUID ist. Dieses Feature folgt dem WS-Addressierungs-Verweisstandard.  
  
 Die WCF-Messaging Schicht schreibt keine persönlichen Informationen auf den lokalen Computer. Sie kann jedoch persönliche Daten auf der Netzwerkebene weitergeben, wenn ein Diensteentwickler einen Dienst erstellt hat, der solche Informationen verfügbar macht (z. B. durch das Verwenden des Namens einer Person in einem Endpunktnamen oder durch das Aufnehmen persönlicher Daten in die WSDL des Endpunkts, ohne dass Clients zum Zugriff auf die WSDL HTTPS verwenden müssen). Wenn ein Entwickler außerdem das [Service Model Metadata Utility Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) -Tool für einen Endpunkt ausführt, der persönliche Informationen verfügbar macht, könnte die Ausgabe des Tools diese Informationen enthalten, und die Ausgabedatei wird auf die lokale Festplatte geschrieben.  
  
## <a name="hosting"></a>Hosting  
 Das Hosting-Feature in WCF ermöglicht es Anwendungen, bei Bedarf zu starten oder die Port Freigabe zwischen mehreren Anwendungen zu aktivieren. Eine WCF-Anwendung kann in Internetinformationsdienste (IIS) gehostet werden, ähnlich wie ASP.net.  
  
 Das Hosting macht keine spezifischen Informationen im Netzwerk verfügbar und behält keine Daten auf dem Computer bei.  
  
## <a name="message-security"></a>Nachrichtensicherheit  
 WCF-Sicherheit stellt die Sicherheitsfunktionen für Messaging Anwendungen bereit. Die bereitgestellten Sicherheitsfunktionen bieten Authentifizierung und Autorisierung.  
  
 Die Authentifizierung wird ausgeführt, indem Anmeldeinformationen zwischen den Clients und Diensten übergeben werden. Die Authentifizierung kann entweder durch Sicherheit auf Transportebene oder durch SOAP-Sicherheit auf Nachrichtenebene erfolgen:  
  
- Bei der SOAP-Nachrichtensicherheit erfolgt die Authentifizierung durch Anmeldeinformationen wie Benutzername/Kennwörter, X.509-Zertifikate, Kerberos-Tickets und SAML-Token, die alle je nach Aussteller persönliche Daten enthalten können.  
  
- Bei der Transportsicherheit erfolgt die Authentifizierung durch herkömmliche Transportauthentifizierungsmechanismen wie HTTP-Authentifizierungsschemas (Basic, Hashwert, Negotiate, Integrierte Windows-Authentifizierung, NTLM, Keine, Anonym) und Formularauthentifizierung.  
  
 Die Authentifizierung kann zu einer sicheren Sitzung zwischen den kommunizierenden Endpunkten führen. Die Sitzung wird durch eine GUID identifiziert, die über die Lebensdauer der Sicherheitssitzung reicht. Die folgende Tabelle zeigt, welche Elemente wo gespeichert werden.  
  
|importieren|-Speicher|  
|----------|-------------|  
|Präsentationsanmeldeinformationen, z. B. Benutzername, X.509-Zertifikate, Kerberos-Token und Verweise auf Anmeldeinformationen.|Standardmäßige Windows-Verwaltungsmechanismen für Anmeldeinformationen, z. B. der Windows-Zertifikatspeicher.|  
|Benutzermitgliedschaftsinformationen, z. B. Benutzernamen und Kennwörter.|ASP.net-Mitgliedschafts Anbieter.|  
|Identitätsinformationen über den Dienst zum Authentifizieren des Diensts gegenüber Clients.|Endpunktadresse des Diensts.|  
|Aufruferdaten.|Überwachungsprotokolle.|  
  
## <a name="auditing"></a>-Überwachung  
 Bei der Überwachung wird der Erfolg und das Fehlschlagen von Authentifizierungs- und Autorisierungsereignissen aufgezeichnet. Überwachungsdatensätze enthalten die folgenden Daten: Dienst-URI, Aktions-URI und Identifikation des Aufrufers.  
  
 Bei der Überwachung werden Daten auch dann aufgezeichnet, wenn der Administrator die Konfiguration der Nachrichtenprotokollierung ändert (aktiviert oder deaktiviert), da bei der Nachrichtenprotokollierung anwendungsspezifische Daten im Header und Text erfasst werden können. Für Windows XP wird ein Datensatz im Anwendungs Ereignisprotokoll protokolliert. Für Windows Vista und Windows Server 2003 wird ein Datensatz im Sicherheits Ereignisprotokoll protokolliert.  
  
## <a name="transactions"></a>Transaktionen  
 Die Transaktions Funktion stellt Transaktionsdienste für eine WCF-Anwendung bereit.  
  
 Bei der Transaktionsweitergabe verwendete Transaktionsheader enthalten möglicherweise Transaktions-IDs oder Eintragung-IDs, die GUIDs sind.  
  
 Das Transaktionsfeature verwendet den MSDTC (Microsoft Distributed Transaction Coordinator)-Transaktions-Manager (eine Windows-Komponente) zum Verwalten des Transaktionszustands. Standardmäßig sind Kommunikationen zwischen Transaktions-Managern verschlüsselt. Transaktions-Manager protokollieren möglicherweise Endpunktverweise, TransaktionsIDs und Eintragung-IDs als Teil ihres permanenten Zustands. Die Lebensdauer dieses Zustands wird von der Lebensdauer der Protokolldatei des Transaktions-Managers bestimmt. Der MSDTC-Dienst besitzt dieses Protokoll und behält es bei.  
  
 Die Transaktionsfunktion implementiert die Standards WS-Coordination und WS-Atomic-Transaktion.  
  
## <a name="reliable-sessions"></a>Zuverlässige Sitzungen  
 Zuverlässige Sitzungen in WCF ermöglichen die Übertragung von Nachrichten, wenn Transport-oder Vermittler Fehler auftreten. Sie bieten auch dann genau eine Übertragung von Nachrichten, wenn die Verbindung zum zugrunde liegenden Transport unterbrochen wird (z. B. eine TCP-Verbindung in einem drahtlosen Netzwerk) oder eine Nachricht verloren geht (ein HTTP-Proxy verwirft eine aus- oder eingehende Nachricht). Zuverlässige Sitzungen heben außerdem die Neuordnung von Nachrichten auf (z. B. beim Multipfad-Routing), wodurch die Reihenfolge beibehalten wird, in der die Nachrichten gesendet wurden.  
  
 Zuverlässige Sitzungen werden mit dem WS-RM (WS-ReliableMessaging)-Protokoll implementiert. Sie fügen WS-RM-Header hinzu, die Sitzungsinformationen enthalten, die zum Identifizieren aller einer bestimmten zuverlässigen Sitzung zugeordneten Nachrichten verwendet werden. Jede WS-RM-Sitzung hat einen Bezeichner, der eine GUID ist.  
  
 Auf dem Computer des Endbenutzers werden keine persönlichen Informationen beibehalten.  
  
## <a name="queued-channels"></a>In der Warteschlange stehende Kanäle  
 Warteschlangen speichern Nachrichten von einer sendenden Anwendung für eine empfangende Anwendung und leiten sie später an die empfangende Anwendung weiter. Sie sichern die Nachrichtenübertragung von sendenden Anwendungen an empfangende Anwendungen, wenn z. B. die empfangende Anwendung flüchtig ist. WCF bietet Unterstützung für Warteschlangen mithilfe von Microsoft Message Queuing (MSMQ) als Transport.  
  
 Das Feature für in der Warteschlange stehende Kanäle fügt einer Nachricht keine Header hinzu. Es erstellt stattdessen eine Message Queuing-Nachricht mit entsprechenden Einstellungen und ruft Message Queuing-Methoden zum Platzieren der Nachricht in die Message Queuing-Warteschlange auf. Message Queuing ist eine in Windows enthaltene optionale Komponente.  
  
 Durch diese Funktion werden auf dem Computer des Endbenutzers keine Informationen beibehalten, da es Message Queuing als Warteschlangeninfrastruktur verwendet.  
  
## <a name="com-integration"></a>COM+-Integration  
 Diese Funktion umschließt vorhandene com-und com+-Funktionen, um Dienste zu erstellen, die mit WCF-Diensten kompatibel sind. Diese Funktion verwendet keine bestimmten Header, und es behält keine Daten auf dem Computer des Endbenutzers bei.  
  
## <a name="com-service-moniker"></a>COM-Dienstmoniker  
 Dadurch wird ein nicht verwalteter Wrapper für einen WCF-Standard Client bereitstellt. Dieses Feature verwendet keine bestimmten Header, und es behält keine Daten auf dem Computer bei.  
  
## <a name="peer-channel"></a>Peerkanal  
 Ein Peerkanal ermöglicht die Entwicklung von Anwendungen mit mehreren Parteien mithilfe von WCF. Mehrparteienmessaging tritt im Kontext eines Netzes auf. Netze werden mit einem Namen identifiziert, den Knoten verknüpfen können. Jeder Knoten im Peerkanal erstellt einen TCP-Listener an einem vom Benutzer angegebenen Anschluss und stellt Verbindungen mit anderen Knoten im Netz her, um die Flexibilität zu sichern. Für diese Verbindungen tauschen Knoten auch bestimmte Daten wie die Listeneradresse und die IP-Adresse des Computers mit anderen Knoten im Netz aus. Innerhalb des Netzes gesendete Nachrichten können Sicherheitsinformationen enthalten, die sich auf den Absender beziehen, um Nachrichtenspoofing und -manipulation zu verhindern.  
  
 Auf dem Computer des Endbenutzers werden keine persönlichen Informationen gespeichert.  
  
## <a name="it-professional-experience"></a>Arbeit von IT-Fachleuten  
  
### <a name="tracing"></a>Ablaufverfolgung  
 Das Diagnose Feature der WCF-Infrastruktur protokolliert Nachrichten, die die Transport-und Dienstmodell Schichten durchlaufen, sowie die Aktivitäten und Ereignisse, die diesen Nachrichten zugeordnet sind. Diese Funktion ist standardmäßig deaktiviert. Sie wird mithilfe der Konfigurationsdatei der Anwendung aktiviert, und das Ablauf Verfolgungs Verhalten kann mithilfe des WCF-WMI-Anbieters zur Laufzeit geändert werden. Wenn das Feature aktiviert ist, gibt die Ablaufverfolgungsinfrastruktur eine Diagnoseablaufverfolgung mit Nachrichten, Aktivitäten und Verarbeitungsereignissen an konfigurierte Listener aus. Format und Speicherort der Ausgabe werden durch die Listener-Konfigurationsauswahl des Administrators bestimmt; normalerweise ist es eine Datei im XML-Format. Der Administrator ist verantwortlich für das Festlegen der Zugriffssteuerungsliste (ACL) für die Ablaufverfolgungsdateien. Insbesondere beim Hosten durch WAS (Windows Activation System) muss der Administrator sicherstellen, dass die Dateien nicht im öffentlichen virtuellen Stammverzeichnis befinden, falls dies nicht gewünscht ist.  
  
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
 Protokolliert Meldungen, die von der WCF-Infrastruktur nicht verstanden oder verarbeitet werden können.  
  
 Nachrichten werden unverändert protokolliert, d. h. verschlüsselt oder nicht verschlüsselt.  
  
 Wenn Nachrichten in entschlüsselter oder unverschlüsselter Form protokolliert werden, entfernt WCF standardmäßig Sicherheitsschlüssel und potenziell persönliche Informationen aus den Nachrichten, bevor diese protokolliert werden. In den nächsten Abschnitten wird beschrieben, welche Informationen wann entfernt werden. Der Computeradministrator und der Anwendungsbereitsteller müssen bestimmte Konfigurationsschritte durchführen, um das Standardverhalten so zu ändern, dass Schlüssel und mögliche persönliche Informationen protokolliert werden.  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a>Aus Nachrichtenheadern bei der Protokollierung entschlüsselter/unverschlüsselter Nachrichten entfernte Informationen  
 Wenn Nachrichten in entschlüsselter/unverschlüsselter Form protokolliert werden, werden standardmäßig vor dem Protokollieren Sicherheitsschlüssel und mögliche persönliche Informationen aus Nachrichtenheadern und Nachrichtentext entfernt. In der folgenden Liste wird gezeigt, was WCF Schlüssel und potenziell persönliche Informationen berücksichtigt.  
  
 Schlüssel, die entfernt werden:  
  
 \- für xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" und xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"  
  
 wst:BinarySecret  
  
 wst:Entropy  
  
 \- für xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" und xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"  
  
 wsse:Password  
  
 wsse:Nonce  
  
 Mögliche persönliche Informationen, die entfernt werden:  
  
 \- für xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" und xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"  
  
 wsse:Username  
  
 wsse:BinarySecurityToken  
  
 \- für xmlns: SAML = "urn: Oasis: names: TC: SAML: 1.0: Assert": die fett formatierten Elemente (unten) werden entfernt:  
  
 \<-Assertionen  
  
 MajorVersion="1"  
  
 MinorVersion="1"  
  
 AssertionId="[ID]"  
  
 Issuer="[string]"  
  
 IssueInstant="[dateTime]"  
  
 >  
  
 \<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]">  
  
 \<AudienceRestrictionCondition>  
  
 \<Audience > [URI]\</Audience > +  
  
 \</AudienceRestrictionCondition>*  
  
 \<donotcachecondition/> *  
  
 <\!--abstrakter Basistyp  
  
 \<Bedingung/> *  
  
 -->  
  
 \</Conditions >?  
  
 \<Ratschläge >  
  
 \<assertionidreferenzierung > [ID]\</AssertionIDReference > *  
  
 \<Assert > [Assert]\</Assertion > *  
  
 [any]*  
  
 \</Advice >?  
  
 <\!--abstrakte Basis Typen  
  
 \<-Anweisung/> *  
  
 \<"subjetstatement" >  
  
 \<Betreff >  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 \<"subjetconfirmation" >  
  
 \<ConfirmationMethod > [anyURI]\</ConfirmationMethod > +  
  
 \<' subjetconfirmationdata ' > [any]\</SubjectConfirmationData >?  
  
 \<ds:KeyInfo>...\</ds:KeyInfo>?  
  
 \</SubjectConfirmation >?  
  
 \</Subject >  
  
 \</SubjectStatement > *  
  
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
  
 < Autorität Bindung  
  
 AuthorityKind="[QName]"  
  
 Location="[uri]"  
  
 Binding="[uri]"  
  
 />*  
  
 \</AuthenticationStatement > *  
  
 \<AttributeStatement>  
  
 [Subject]  
  
 \<-Attribut  
  
 AttributeName="[string]"  
  
 AttributeNamespace="[uri]"  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 \</Attribute > +  
  
 \</AttributeStatement>*  
  
 \<authorizationdecisionstatement  
  
 Resource="[uri]"  
  
 Decision = "[deny&#124;&#124;unbestimmt zulassen]"  
  
 >  
  
 [Subject]  
  
 \<Action Namespace = "[URI]" > [String]\</Action > +  
  
 \<Beweis >  
  
 \<assertionidreferenzierung > [ID]\</AssertionIDReference > +  
  
 \<Assert > [Assert]\</Assertion > +  
  
 \</Evidence >?  
  
 \</AuthorizationDecisionStatement>*  
  
 \</Assertion>  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a>Aus Nachrichtentext bei der Protokollierung entschlüsselter/unverschlüsselter Nachrichten entfernte Informationen  
 Wie bereits beschrieben, entfernt WCF Schlüssel und bekannte potenziell persönliche Informationen aus Nachrichten Headern für protokollierte entschlüsselte/unverschlüsselte Nachrichten. Außerdem entfernt WCF Schlüssel und bekannte potenziell persönliche Informationen aus Nachrichten Textteilen für die Textelemente und Aktionen in der folgenden Liste, in denen die an den Schlüsselaustausch beteiligten Sicherheitsmeldungen beschrieben werden.  
  
 Für die folgenden Namespaces:  
  
 xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" und xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" (z. b. wenn keine Aktion verfügbar ist)  
  
 Informationen werden für diese Textelemente entfernt, die Schlüsselaustausch einschließen:  
  
 wst:RequestSecurityToken  
  
 wst:RequestSecurityTokenResponse  
  
 wst:RequestSecurityTokenResponseCollection  
  
 Informationen werden auch für jede der folgenden Aktionen entfernt:  
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT-Amend`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT-Amend`
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a>Aus anwendungsspezifischen Headern und Textdaten werden keine Informationen entfernt.  
 WCF verfolgt keine persönlichen Informationen in anwendungsspezifischen Headern (z. b. Abfrage Zeichenfolgen) oder Textdaten (z. b. Kreditkartennummer).  
  
 Bei aktivierter Nachrichtenprotokollierung sind persönliche Informationen in anwendungsspezifischen Headern und Textdaten unter Umständen in den Protokollen sichtbar. Der Anwendungsbereitsteller ist für das Festlegen der ACLs für die Konfigurations- und Protokolldateien verantwortlich. Er kann auch die Protokollierung deaktivieren, wenn diese Informationen nicht sichtbar sein sollen, oder diese Informationen aus den Protokolldateien herausfiltern.  
  
### <a name="service-model-tracing"></a>Dienstmodell-Ablaufverfolgung  
 Die Dienstmodell-Ablaufverfolgungsquelle (<xref:System.ServiceModel>) aktiviert die Ablaufverfolgung von mit der Nachrichtenverarbeitung verknüpften Aktivitäten und Ereignissen. Diese Funktion verwendet die .NET Framework-Diagnosefunktionalität von <xref:System.Diagnostics>. Wie bei der <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>-Eigenschaft können der Speicherort und die ACL mit den Konfigurationsdateien der .NET Framework-Anwendung vom Benutzer konfiguriert werden. Wie bei der Nachrichtenprotokollierung wird der Speicherort der Datei immer konfiguriert, wenn der Administrator die Ablaufverfolgung aktiviert; der Administrator steuert also die ACL.  
  
 Ablaufverfolgungen enthalten Nachrichtenheader, wenn sich eine Nachricht im Gültigkeitsbereich befindet. Dabei gilt die gleiche Regel für das Ausblenden möglicher persönlicher Informationen in Nachrichtenheadern wie im vorherigen Abschnitt: Die zuvor identifizierten persönlichen Informationen werden standardmäßig aus den Headern in Ablaufverfolgungen entfernt. Der Computeradministrator und der Anwendungsbereitsteller müssen die Konfiguration ändern, damit mögliche persönliche Informationen protokolliert werden. Allerdings werden in anwendungsspezifischen Headern enthaltene persönliche Informationen in Ablaufverfolgungen protokolliert. Der Anwendungsbereitsteller ist für das Festlegen der ACLs für die Konfigurations- und Ablaufverfolgungsdateien verantwortlich. Er kann auch die Ablaufverfolgung deaktivieren, wenn diese Informationen nicht sichtbar sein sollen, oder diese Informationen nach der Protokollierung aus den Ablaufverfolgungsdateien herausfiltern.  
  
 Als Teil der Dienstmodell-Ablaufverfolgung verknüpfen eindeutige IDs (die als Aktivitäts-IDs bezeichnet werden, in der Regel eine GUID) unterschiedliche Aktivitäten, wenn eine Nachricht verschiedene Teile der Infrastruktur durchläuft.  
  
#### <a name="custom-trace-listeners"></a>Benutzerdefinierte Ablaufverfolgungslistener  
 Sowohl für die Nachrichtenprotokollierung als auch die Ablaufverfolgung kann ein benutzerdefinierter Ablaufverfolgungslistener konfiguriert werden, der Ablaufverfolgungen und Nachrichten überträgt, z. B. an eine Remotedatenbank. Der Anwendungsbereitsteller ist für das Konfigurieren benutzerdefinierter Listener oder das Ermöglichen dieser Aktion durch Benutzer verantwortlich. Er ist außerdem für am Remotespeicherort verfügbar gemachte persönliche Informationen und für die korrekte Anwendung von ACLs auf diesen Speicherort verantwortlich.  
  
### <a name="other-features-for-it-professionals"></a>Andere Features für IT-Fachleute  
 WCF verfügt über einen WMI-Anbieter, der die Konfigurationsinformationen der WCF-Infrastruktur über WMI (ausgeliefert in Windows) verfügbar macht. Standardmäßig steht die WMI-Schnittstelle Administratoren zur Verfügung.  
  
 Die WCF-Konfiguration verwendet den .NET Framework Konfigurations Mechanismus. Die Konfigurationsdateien werden auf dem Computer gespeichert. Der Anwendungsentwickler und der Administrator erstellen die Konfigurationsdateien und die ACL für jede Anwendungsanforderung. Eine Konfigurationsdatei kann Endpunktadressen und Links zu Zertifikaten im Zertifikatspeicher enthalten. Mithilfe der Zertifikate können Anwendungsdaten zum Konfigurieren verschiedener Eigenschaften der von der Anwendung verwendeten Funktionen bereitgestellt werden.  
  
 WCF verwendet auch die .NET Framework Prozess-dumpfunktion, indem die <xref:System.Environment.FailFast%2A>-Methode aufgerufen wird.  
  
### <a name="it-pro-tools"></a>Tools für IT-Fachleute  
 WCF stellt außerdem die folgenden IT-Experten bereit, die im Windows SDK ausgeliefert werden.  
  
#### <a name="svctraceviewerexe"></a>SvcTraceViewer.exe  
 Der Viewer zeigt WCF-Ablauf Verfolgungs Dateien an. Der Viewer zeigt an, welche Daten in den Ablaufverfolgungen enthalten sind.  
  
#### <a name="svcconfigeditorexe"></a>SvcConfigEditor.exe  
 Der Editor ermöglicht dem Benutzer das Erstellen und Bearbeiten von WCF-Konfigurationsdateien. Der Editor zeigt an, welche Daten in den Konfigurationsdateien enthalten sind. Für die gleiche Aufgabe kann auch ein Text-Editor verwendet werden.  
  
#### <a name="servicemodel_reg"></a>ServiceModel_Reg  
 Mit diesem Tool kann der Benutzer ServiceModel-Installationen auf einem Computer verwalten. Das Tool zeigt die Statusmeldungen bei der Ausführung in einem Konsolenfenster an und zeigt möglicherweise Informationen zur Konfiguration der WCF-Installation an.  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a>WSATConfig.exe und WSATUI.dll  
 Diese Tools ermöglichen es IT-Spezialisten, eine interoperable WS-AtomicTransaction-Netzwerkunterstützung in WCF zu konfigurieren. Mithilfe der Tools kann der Benutzer die Werte der in der Registrierung gespeicherten am häufigsten verwendeten WS-AtomicTransaction-Einstellungen anzeigen und ändern.  
  
## <a name="cross-cutting-features"></a>Querschnittliche Funktionen  
 Die folgenden Features sind querschnittliche Features. Das heißt, sie können mit allen vorangehenden Funktionen zusammengesetzt werden.  
  
### <a name="service-framework"></a>Dienstframework  
 Header können eine Instanz-ID enthalten; dies ist eine GUID, die eine Nachricht einer Instanz einer CLR-Klasse zuordnet.  
  
 Die WSDL (Web Services Description Language) enthält eine Definition des Anschlusses. Jeder Anschluss verfügt über eine Endpunktadresse und eine Bindung, die die von der Anwendung verwendeten Dienste darstellt. Das Verfügbarmachen der WSDL kann mithilfe der Konfiguration deaktiviert werden. Auf dem Computer werden keine Informationen beibehalten.  
  
## <a name="see-also"></a>Siehe auch

- [Windows Communication Foundation](index.md)
- [Sicherheit](./feature-details/security.md)
