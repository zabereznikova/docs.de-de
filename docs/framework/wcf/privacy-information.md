---
title: "Windows Communication Foundation-Datenschutzinformationen | Microsoft Docs"
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
  - "Datenschutzinformationen [WCF]"
  - "WCF, Datenschutzinformationen"
  - "Windows Communication Foundation, Datenschutzinformationen"
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
caps.latest.revision: 34
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 34
---
# Windows Communication Foundation-Datenschutzinformationen
Microsoft verpflichtet sich, die persönlichen Daten von Endbenutzern vertraulich zu behandeln.  Wenn Sie mit [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Version 3.0 eine Anwendung erstellen, wirkt sich die Anwendung möglicherweise auf den Datenschutz der Endbenutzer aus.  Die Anwendung erfasst z. B. unter Umständen explizit Kontaktinformationen des Benutzers oder fordert Informationen an und sendet diese über das Internet an Ihre Website.  Wenn Sie Microsoft\-Technologie in Ihre Anwendung einbetten, kann sich das Verhalten dieser Technologie ebenfalls auf den Datenschutz auswirken.  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sendet aus Ihrer Anwendung keine Daten an Microsoft, sofern nicht von Ihnen oder dem Endbenutzer anders festgelegt.  
  
## WCF in Kürze  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ist ein verteiltes Messagingframework, das Microsoft .NET Framework verwendet, um Entwicklern das Erstellen verteilter Anwendungen zu ermöglichen.  Zwischen zwei Anwendungen übermittelte Nachrichten enthalten Header\- und Textinformationen.  
  
 Header können je nach von der Anwendung verwendeten Diensten unter anderem Meldungsrouting, Sicherheitsinformationen und Transaktionen enthalten.  Nachrichten werden in der Regel standardmäßig verschlüsselt.  Eine Ausnahme ist die Verwendung der `BasicHttpBinding`, die für nicht gesicherte, ältere Webdienste konzipiert wurde.  Als Anwendungs\-Designer sind Sie für den abschließenden Entwurf verantwortlich.  Nachrichten im SOAP\-Text enthalten anwendungsspezifische Daten; allerdings können diese Daten, z. B. von der Anwendung definierte persönliche Daten, mit Verschlüsselungs\- oder Vertraulichkeitsfeatures von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] gesichert werden.  In den folgenden Abschnitten werden die Features beschrieben, die sich auf den Datenschutz auswirken können.  
  
## Messaging  
 Jede [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Nachricht verfügt über einen Adressheader, der das Ziel der Nachricht und der Antwort angibt.  
  
 Die Adresskomponente einer Endpunktadresse ist ein URI \(Uniform Resource Identifier\), der den Endpunkt identifiziert.  Die Adresse kann eine Netzwerkadresse oder eine logische Adresse sein.  Die Adresse kann den Computernamen \(Hostname, vollqualifizierter Domänenname\) und eine IP\-Adresse einschließen.  Die Endpunktadresse kann außerdem eine GUID \(Globally Unique Identifier\) oder eine Auflistung von GUIDs für die temporäre Adressierung zum Ermitteln jeder Adresse enthalten.  Jede Nachricht enthält eine Nachrichten\-ID, die eine GUID ist.  Dieses Feature folgt dem WS\-Addressierungs\-Verweisstandard.  
  
 Die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Messagingebene schreibt keine persönlichen Daten auf den lokalen Computer.  Sie kann jedoch persönliche Daten auf der Netzwerkebene weitergeben, wenn ein Diensteentwickler einen Dienst erstellt hat, der solche Informationen verfügbar macht \(z. B. durch das Verwenden des Namens einer Person in einem Endpunktnamen oder durch das Aufnehmen persönlicher Daten in die WSDL des Endpunkts, ohne dass Clients zum Zugriff auf die WSDL HTTPS verwenden müssen\).  Auch wenn ein Entwickler das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)\-Tool gegen einen Endpunkt ausführt, der persönliche Daten verfügbar macht, können die Ausgabedateien des Tools diese Daten enthalten, und die Ausgabedatei wird auf die lokale Festplatte geschrieben.  
  
## Hosting  
 Das Hostingfeature in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ermöglicht Anwendungen das Starten bei Bedarf oder das Aktivieren der Anschlussfreigabe zwischen mehreren Anwendungen.  Eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Anwendung kann in Internetinformationsdiensten \(IIS\) gehostet werden, ähnlich wie [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
 Das Hosting macht keine spezifischen Informationen im Netzwerk verfügbar und behält keine Daten auf dem Computer bei.  
  
## Nachrichtensicherheit  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Sicherheit stellt die Sicherheitsfunktionen für Messaginganwendungen bereit.  Die bereitgestellten Sicherheitsfunktionen bieten Authentifizierung und Autorisierung.  
  
 Die Authentifizierung wird ausgeführt, indem Anmeldeinformationen zwischen den Clients und Diensten übergeben werden.  Die Authentifizierung kann entweder durch Sicherheit auf Transportebene oder durch SOAP\-Sicherheit auf Nachrichtenebene erfolgen:  
  
-   Bei der SOAP\-Nachrichtensicherheit erfolgt die Authentifizierung durch Anmeldeinformationen wie Benutzername\/Kennwörter, X.509\-Zertifikate, Kerberos\-Tickets und SAML\-Token, die alle je nach Aussteller persönliche Daten enthalten können.  
  
-   Bei der Transportsicherheit erfolgt die Authentifizierung durch herkömmliche Transportauthentifizierungsmechanismen wie HTTP\-Authentifizierungsschemas \(Basic, Digest, Negotiate, Integrierte Windows\-Authentifizierung, NTLM, Keine, Anonym\) und Formularauthentifizierung.  
  
 Die Authentifizierung kann zu einer sicheren Sitzung zwischen den kommunizierenden Endpunkten führen.  Die Sitzung wird durch eine GUID identifiziert, die über die Lebensdauer der Sicherheitssitzung reicht.  Die folgende Tabelle zeigt, welche Elemente wo gespeichert werden.  
  
|Daten|Speicher|  
|-----------|--------------|  
|Präsentationsanmeldeinformationen, z. B. Benutzername, X.509\-Zertifikate, Kerberos\-Token und Verweise auf Anmeldeinformationen.|Standardmäßige Windows\-Verwaltungsmechanismen für Anmeldeinformationen, z. B. der Windows\-Zertifikatspeicher.|  
|Benutzermitgliedschaftsinformationen, z. B. Benutzernamen und Kennwörter.|[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]\-Mitgliedschaftsanbieter.|  
|Identitätsinformationen über den Dienst zum Authentifizieren des Diensts gegenüber Clients.|Endpunktadresse des Diensts.|  
|Aufruferdaten.|Überwachungsprotokolle.|  
  
## Überwachung  
 Bei der Überwachung wird der Erfolg und das Fehlschlagen von Authentifizierungs\- und Autorisierungsereignissen aufgezeichnet.  Überwachungsdatensätze enthalten die folgenden Daten: Dienst\-URI, Aktions\-URI und Identifikation des Aufrufers.  
  
 Bei der Überwachung werden Daten auch dann aufgezeichnet, wenn der Administrator die Konfiguration der Nachrichtenprotokollierung ändert \(aktiviert oder deaktiviert\), da bei der Nachrichtenprotokollierung anwendungsspezifische Daten im Header und Text erfasst werden können.  In [!INCLUDE[wxp](../../../includes/wxp-md.md)] wird ein Datensatz im Anwendungsereignisprotokoll protokolliert.  In [!INCLUDE[wv](../../../includes/wv-md.md)] und [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] wird ein Datensatz im Sicherheitsereignisprotokoll protokolliert.  
  
## Transaktionen  
 Das Transaktionsfeature stellt Transaktionsdienste für eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Anwendung bereit.  
  
 Bei der Transaktionsweitergabe verwendete Transaktionsheader enthalten möglicherweise Transaktions\-IDs oder Eintragung\-IDs, die GUIDs sind.  
  
 Das Tansaktionsfeature verwendet den MSDTC \(Microsoft Distributed Transaction Coordinator\)\-Transaktions\-Manager \(eine Windows\-Komponente\) zum Verwalten des Transaktionszustands.  Standardmäßig sind Kommunikationen zwischen Transaktions\-Managern verschlüsselt.  Transaktions\-Manager protokollieren möglicherweise Endpunktverweise, Transaktions\-IDs und Eintragung\-IDs als Teil ihres permanenten Zustands.  Die Lebensdauer dieses Zustands wird von der Lebensdauer der Protokolldatei des Transaktions\-Managers bestimmt.  Der MSDTC\-Dienst besitzt dieses Protokoll und behält es bei.  
  
 Die Transaktionsfunktion implementiert die Standards WS\-Coordination und WS\-Atomic Transaction.  
  
## Zuverlässige Sitzungen  
 Zuverlässige Sitzungen in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] stellen die Übertragung von Nachrichten bereit, wenn Transport\- oder Vermittlerfehler auftreten.  Sie bieten auch dann genau eine Übertragung von Nachrichten, wenn die Verbindung zum zugrunde liegenden Transport unterbrochen wird \(z. B. eine TCP\-Verbindung in einem drahtlosen Netzwerk\) oder eine Nachricht verloren geht \(ein HTTP\-Proxy verwirft eine aus\- oder eingehende Nachricht\).  Zuverlässige Sitzungen heben außerdem die Neuordnung von Nachrichten auf \(z. B. beim Multipfad\-Routing\), wodurch die Reihenfolge beibehalten wird, in der die Nachrichten gesendet wurden.  
  
 Zuverlässige Sitzungen werden mit dem WS\-RM \(WS\-ReliableMessaging\)\-Protokoll implementiert.  Sie fügen WS\-RM\-Header hinzu, die Sitzungsinformationen enthalten, die zum Identifizieren aller einer bestimmten zuverlässigen Sitzung zugeordneten Nachrichten verwendet werden.  Jede WS\-RM\-Sitzung hat einen Bezeichner, der eine GUID ist.  
  
 Auf dem Computer des Endbenutzers werden keine persönlichen Informationen beibehalten.  
  
## In der Warteschlange stehende Kanäle  
 Warteschlangen speichern Nachrichten von einer sendenden Anwendung für eine empfangende Anwendung und leiten sie später an die empfangende Anwendung weiter.  Sie sichern die Nachrichtenübertragung von sendenden Anwendungen an empfangende Anwendungen, wenn z. B. die empfangende Anwendung flüchtig ist.  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bietet Unterstützung für Warteschlangen durch die Nutzung von MSMQ \(Microsoft Message Queuing \) als Transport.  
  
 Das Feature für in der Warteschlange stehende Kanäle fügt einer Nachricht keine Header hinzu.  Es erstellt stattdessen eine Message Queuing\-Nachricht mit entsprechenden Einstellungen und ruft Message Queuing\-Methoden zum Platzieren der Nachricht in die Message Queuing\-Warteschlange auf.  Message Queuing ist eine in Windows enthaltene optionale Komponente.  
  
 Durch dieses Feature werden auf dem Computer des Endbenutzers keine Informationen beibehalten, da es Message Queuing als Warteschlangeninfrastruktur verwendet.  
  
## COM\+\-Integration  
 Dieses Feature schließt vorhandene COM\- und COM\+\-Funktionen ein, um Dienste zu erstellen, die mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensten kompatibel sind.  Dieses Feature verwendet keine bestimmten Header, und es behält keine Daten auf dem Computer des Endbenutzers bei.  
  
## COM\-Dienstmoniker  
 Dieser stellt einem Standard\-[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Client einen nicht verwalteten Wrapper bereit.  Dieses Feature verwendet keine bestimmten Header, und es behält keine Daten auf dem Computer bei.  
  
## Peerkanal  
 Ein Peerkanal ermöglicht die Entwicklung von Mehrparteienanwendungen mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  Mehrparteienmessaging tritt im Kontext eines Netzes auf.  Netze werden mit einem Namen identifiziert, den Knoten verknüpfen können.  Jeder Knoten im Peerkanal erstellt einen TCP\-Listener an einem vom Benutzer angegebenen Anschluss und stellt Verbindungen mit anderen Knoten im Netz her, um die Flexibilität zu sichern.  Für diese Verbindungen tauschen Knoten auch bestimmte Daten wie die Listeneradresse und die IP\-Adresse des Computers mit anderen Knoten im Netz aus.  Innerhalb des Netzes gesendete Nachrichten können Sicherheitsinformationen enthalten, die sich auf den Absender beziehen, um Nachrichtenspoofing und \-manipulation zu verhindern.  
  
 Auf dem Computer des Endbenutzers werden keine persönlichen Informationen gespeichert.  
  
## Arbeit von IT\-Fachleuten  
  
### Ablaufverfolgung  
 Mit dem Diagnosefeature der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Infrastruktur werden Nachrichten protokolliert, die Transport\- und Dienstmodellebene durchlaufen, sowie die diesen Nachrichten zugeordneten Aktivitäten und Ereignisse.  Diese Funktion ist standardmäßig deaktiviert.  Es wird mithilfe der Konfigurationsdatei der Anwendung aktiviert, und das Verhalten für die Ablaufverfolgung kann mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-WMI\-Anbieter zur Laufzeit geändert werden.  Wenn das Feature aktiviert ist, gibt die Ablaufverfolgungsinfrastruktur eine Diagnoseablaufverfolgung mit Nachrichten, Aktivitäten und Verarbeitungsereignissen an konfigurierte Listener aus.  Format und Speicherort der Ausgabe werden durch die Listener\-Konfigurationsauswahl des Administrators bestimmt; normalerweise ist es eine Datei im XML\-Format.  Der Administrator ist verantwortlich für das Festlegen der Zugriffssteuerungsliste \(ACL\) für die Ablaufverfolgungsdateien.  Insbesondere beim Hosten durch WAS \(Windows Activation System\) muss der Administrator sicherstellen, dass die Dateien nicht im öffentlichen virtuellen Stammverzeichnis befinden, falls dies nicht gewünscht ist.  
  
 Es gibt zwei Typen von Ablaufverfolgung, Nachrichtenprotokollierung und Dienstmodell\-Diagnoseablaufverfolgung, die im folgenden Abschnitt beschrieben werden.  Jeder Typ wird über seine eigene Ablaufverfolgungsquelle konfiguriert: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> und <xref:System.ServiceModel>.  Beide Protokollierungs\-Ablaufverfolgungsquellen erfassen Daten, die lokale Daten der Anwendung sind.  
  
### Nachrichtenprotokollierung  
 Die Ablaufverfolgungsquelle für die Nachrichtenprotokollierung \(<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>\) ermöglicht einem Administrator das Protokollieren der Nachrichten, die das System durchlaufen.  Über die Konfiguration kann der Benutzer entscheiden, ob ganze Nachrichten oder nur Nachrichtenheader protokolliert werden, ob die Protokollierung auf der Transport\- und\/oder der Dienstmodellebene erfolgt und ob falsch formatierte Nachrichten erfasst werden.  Außerdem kann der Benutzer die Filterung konfigurieren, um einzuschränken, welche Nachrichten protokolliert werden.  
  
 Standardmäßig ist die Nachrichtenprotokollierung deaktiviert.  Der Administrator auf dem lokalen Computer kann verhindern, dass der Administrator auf Anwendungsebene die Nachrichtenprotokollierung aktiviert.  
  
#### Verschlüsselte und entschlüsselte Nachrichtenprotokollierung  
 Nachrichten werden wie in den folgenden Begriffen beschrieben protokolliert, verschlüsselt oder entschlüsselt.  
  
 Transportprotokollierung  
 Protokolliert auf der Transportebene empfangene und gesendete Nachrichten.  Diese Nachrichten enthalten alle Header und werden möglicherweise vor dem Versenden und beim Empfangen verschlüsselt.  
  
 Wenn Nachrichten vor dem Versenden und beim Empfangen verschlüsselt werden, werden sie auch verschlüsselt protokolliert.  Eine Ausnahme ist die Verwendung eines Sicherheitsprotokolls \(HTTPS\); die Nachrichten werden vor dem Senden und nach dem Empfangen entschlüsselt protokolliert, auch wenn sie beim Versenden verschlüsselt sind.  
  
 Dienstprotokollierung  
 Protokolliert auf der Dienstmodellebene empfangene oder gesendete Nachrichten nach der Kanalheader\-Verarbeitung, unmittelbar vor und nach der Eingabe von Benutzercode.  
  
 Auf dieser Ebene protokollierte Nachrichten werden entschlüsselt, auch wenn sie für die Übertragung gesichert und verschlüsselt wurden.  
  
 Protokollierung falsch formatierter Nachrichten  
 Protokolliert Nachrichten, die die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Infrastruktur nicht verstehen oder verarbeiten kann.  
  
 Nachrichten werden unverändert protokolliert, d. h. verschlüsselt oder nicht verschlüsselt.  
  
 Wenn Nachrichten in entschlüsselter oder unverschlüsselter Form protokolliert werden, entfernt [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] standardmäßig vor dem Protokollieren Sicherheitsschlüssel und mögliche persönliche Informationen aus den Nachrichten.  In den nächsten Abschnitten wird beschrieben, welche Informationen wann entfernt werden.  Der Computeradministrator und der Anwendungsbereitsteller müssen bestimmte Konfigurationsschritte durchführen, um das Standardverhalten so zu ändern, dass Schlüssel und mögliche persönliche Informationen protokolliert werden.  
  
#### Aus Nachrichtenheadern bei der Protokollierung entschlüsselter\/unverschlüsselter Nachrichten entfernte Informationen  
 Wenn Nachrichten in entschlüsselter\/unverschlüsselter Form protokolliert werden, werden standardmäßig vor dem Protokollieren Sicherheitsschlüssel und mögliche persönliche Informationen aus Nachrichtenheadern und Nachrichtentext entfernt.  In der folgende Liste wird gezeigt, was [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] als Schlüssel und mögliche persönliche Informationen betrachtet.  
  
 Schlüssel, die entfernt werden:  
  
 \- Bei xmlns:wst \= "http:\/\/schemas.xmlsoap.org\/ws\/2004\/04\/trust" und xmlns:wst \= "http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust"  
  
 wst:BinarySecret  
  
 wst:Entropy  
  
 \- Bei xmlns:wsse \= "http:\/\/docs.oasis\-open.org\/wss\/2004\/01\/oasis\-200401\-wss\-wssecurity\-secext\-1.1.xsd" und xmlns:wsse \= "http:\/\/docs.oasis\-open.org\/wss\/2005\/xx\/oasis\-2005xx\-wss\-wssecurity\-secext\-1.1.xsd"  
  
 wsse:Password  
  
 wsse:Nonce  
  
 Mögliche persönliche Informationen, die entfernt werden:  
  
 \- Bei xmlns:wsse \= "http:\/\/docs.oasis\-open.org\/wss\/2004\/01\/oasis\-200401\-wss\-wssecurity\-secext\-1.1.xsd" und xmlns:wsse \= "http:\/\/docs.oasis\-open.org\/wss\/2005\/xx\/oasis\-2005xx\-wss\-wssecurity\-secext\-1.1.xsd"  
  
 wsse:Username  
  
 wsse:BinarySecurityToken  
  
 \- Bei xmlns:saml \= "urn:oasis:names:tc:SAML:1 .0: Assertion" werden die fett formatierten Elemente \(unten\) entfernt:  
  
 \<Assertion  
  
 MajorVersion\="1"  
  
 MinorVersion\="1"  
  
 AssertionId\="\[ID\]"  
  
 Issuer\="\[string\]"  
  
 IssueInstant\="\[dateTime\]"  
  
 \>  
  
 \<Conditions NotBefore\="\[dateTime\]" NotOnOrAfter\="\[dateTime\]"\>  
  
 \<AudienceRestrictionCondition\>  
  
 \<Audience\>\[uri\]\<\/Audience\>\+  
  
 \<\/AudienceRestrictionCondition\>\*  
  
 \<DoNotCacheCondition \/\>\*  
  
 \<\!\-\- abstract base type  
  
 \<Condition \/\>\*  
  
 \-\-\>  
  
 \<\/Conditions\>?  
  
 \<Advice\>  
  
 \<AssertionIDReference\>\[ID\]\<\/AssertionIDReference\>\*  
  
 \<Assertion\>\[assertion\]\<\/Assertion\>\*  
  
 \[any\]\*  
  
 \<\/Advice\>?  
  
 \<\!\-\- Abstract base types  
  
 \<Statement \/\>\*  
  
 \<SubjectStatement\>  
  
 \<Subject\>  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 \<SubjectConfirmation\>  
  
 \<ConfirmationMethod\>\[anyUri\]\<\/ConfirmationMethod\>\+  
  
 \<SubjectConfirmationData\>\[any\]\<\/SubjectConfirmationData\>?  
  
 \<ds:KeyInfo\>...\<\/ds:KeyInfo\>?  
  
 \<\/SubjectConfirmation\>?  
  
 \<\/Subject\>  
  
 \<\/SubjectStatement\>\*  
  
 \-\-\>  
  
 \<AuthenticationStatement  
  
 AuthenticationMethod\="\[uri\]"  
  
 AuthenticationInstant\="\[dateTime\]"  
  
 \>  
  
 \[Subject\]  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 \<AuthorityBinding  
  
 AuthorityKind\="\[QName\]"  
  
 Location\="\[uri\]"  
  
 Binding\="\[uri\]"  
  
 \/\>\*  
  
 \<\/AuthenticationStatement\>\*  
  
 \<AttributeStatement\>  
  
 \[Subject\]  
  
 \<Attribute  
  
 AttributeName\="\[string\]"  
  
 AttributeNamespace\="\[uri\]"  
  
 \>  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 \<\/Attribute\>\+  
  
 \<\/AttributeStatement\>\*  
  
 \<AuthorizationDecisionStatement  
  
 Resource\="\[uri\]"  
  
 Decision\="\[Permit&#124;Deny&#124;Indeterminate\]"  
  
 \>  
  
 \[Subject\]  
  
 \<Action Namespace\="\[uri\]"\>\[string\]\<\/Action\>\+  
  
 \<Evidence\>  
  
 \<AssertionIDReference\>\[ID\]\<\/AssertionIDReference\>\+  
  
 \<Assertion\>\[assertion\]\<\/Assertion\>\+  
  
 \<\/Evidence\>?  
  
 \<\/AuthorizationDecisionStatement\>\*  
  
 \<\/Assertion\>  
  
#### Aus Nachrichtentext bei der Protokollierung entschlüsselter\/unverschlüsselter Nachrichten entfernte Informationen  
 Wie weiter oben beschrieben, entfernt [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bei protokollierten entschlüsselten\/unverschlüsselten Nachrichten Schlüssel und bekannte mögliche persönliche Informationen aus Nachrichtenheadern.  Darüber hinaus entfernt [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Schlüssel und bekannte mögliche persönliche Informationen aus Nachrichtentext für die Textelemente und Aktionen in der folgenden Liste, die Sicherheitsmeldungen beim Schlüsselaustausch beschreiben.  
  
 Für die folgenden Namespaces:  
  
 xmlns:wst\="http:\/\/schemas.xmlsoap.org\/ws\/2004\/04\/trust" und xmlns:wst\="http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust" \(wenn z. B. keine Aktion verfügbar ist\)  
  
 Informationen werden für diese Textelemente entfernt, die Schlüsselaustausch einschließen:  
  
 wst:RequestSecurityToken  
  
 wst:RequestSecurityTokenResponse  
  
 wst:RequestSecurityTokenResponseCollection  
  
 Informationen werden auch für jede der folgenden Aktionen entfernt:  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RST\/Issue  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RSTR\/Issue  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RST\/Renew  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RSTR\/Renew  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RST\/Cancel  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RSTR\/Cancel  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RST\/Validate  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RSTR\/Validate  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RST\/SCT  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RSTR\/SCT  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RST\/SCT\/Amend  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RSTR\/SCT\/Amend  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RST\/SCT\/Renew  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RSTR\/SCT\/Renew  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RST\/SCT\/Cancel  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/trust\/RSTR\/SCT\/Cancel  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2004\/04\/security\/trust\/RST\/SCT  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2004\/04\/security\/trust\/RSTR\/SCT  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2004\/04\/security\/trust\/RST\/SCT\-Amend  
  
 http:\/\/schemas.xmlsoap.org\/ws\/2004\/04\/security\/trust\/RSTR\/SCT\-Amend  
  
#### Aus anwendungsspezifischen Headern und Textdaten werden keine Informationen entfernt.  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] verfolgt keine persönlichen Informationen in anwendungsspezifischen Headern \(z. B. Abfragezeichenfolgen\) oder Textdaten \(z. B. Kreditkartennummer\).  
  
 Bei aktivierter Nachrichtenprotokollierung sind persönliche Informationen in anwendungsspezifischen Headern und Textdaten unter Umständen in den Protokollen sichtbar.  Der Anwendungsbereitsteller ist für das Festlegen der ACLs für die Konfigurations\- und Protokolldateien verantwortlich.  Er kann auch die Protokollierung deaktivieren, wenn diese Informationen nicht sichtbar sein sollen, oder diese Informationen aus den Protokolldateien herausfiltern.  
  
### Dienstmodell\-Ablaufverfolgung  
 Die Dienstmodell\-Ablaufverfolgungsquelle \(<xref:System.ServiceModel>\) aktiviert die Ablaufverfolgung von mit der Nachrichtenverarbeitung verknüpften Aktivitäten und Ereignissen.  Dieses Feature verwendet die .NET Framework\-Diagnosefunktionalität von <xref:System.Diagnostics>.  Wie bei der <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>\-Eigenschaft können der Speicherort und die ACL mit den Konfigurationsdateien der .NET Framework\-Anwendung vom Benutzer konfiguriert werden.  Wie bei der Nachrichtenprotokollierung wird der Speicherort der Datei immer konfiguriert, wenn der Administrator die Ablaufverfolgung aktiviert; der Administrator steuert also die ACL.  
  
 Ablaufverfolgungen enthalten Nachrichtenheader, wenn sich eine Nachricht im Gültigkeitsbereich befindet.  Dabei gilt die gleiche Regel für das Ausblenden möglicher persönlicher Informationen in Nachrichtenheadern wie im vorherigen Abschnitt: Die zuvor identifizierten persönlichen Informationen werden standardmäßig aus den Headern in Ablaufverfolgungen entfernt.  Der Computeradministrator und der Anwendungsbereitsteller müssen die Konfiguration ändern, damit mögliche persönliche Informationen protokolliert werden.  Allerdings werden in anwendungsspezifischen Headern enthaltene persönliche Informationen in Ablaufverfolgungen protokolliert.  Der Anwendungsbereitsteller ist für das Festlegen der ACLs für die Konfigurations\- und Ablaufverfolgungsdateien verantwortlich.  Er kann auch die Ablaufverfolgung deaktivieren, wenn diese Informationen nicht sichtbar sein sollen, oder diese Informationen nach der Protokollierung aus den Ablaufverfolgungsdateien herausfiltern.  
  
 Als Teil der Dienstmodell\-Ablaufverfolgung verknüpfen eindeutige IDs \(die als Aktivitäts\-IDs bezeichnet werden, in der Regel eine GUID\) unterschiedliche Aktivitäten, wenn eine Nachricht verschiedene Teile der Infrastruktur durchläuft.  
  
#### Benutzerdefinierte Ablaufverfolgungslistener  
 Sowohl für die Nachrichtenprotokollierung als auch die Ablaufverfolgung kann ein benutzerdefinierter Ablaufverfolgungslistener konfiguriert werden, der Ablaufverfolgungen und Nachrichten überträgt, z. B. an eine Remotedatenbank.  Der Anwendungsbereitsteller ist für das Konfigurieren benutzerdefinierter Listener oder das Ermöglichen dieser Aktion durch Benutzer verantwortlich.  Er ist außerdem für am Remotespeicherort verfügbar gemachte persönliche Informationen und für die korrekte Anwendung von ACLs auf diesen Speicherort verantwortlich.  
  
### Andere Features für IT\-Fachleute  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] verfügt über einen WMI\-Anbieter, der die Konfigurationsinformationen der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Infrastruktur über WMI \(im Lieferumfang von Windows enthalten\) verfügbar macht.  Standardmäßig steht die WMI\-Schnittstelle Administratoren zur Verfügung.  
  
 Die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Konfiguration verwendet das .NET Framework\-Konfigurationsverfahren.  Die Konfigurationsdateien werden auf dem Computer gespeichert.  Der Anwendungsentwickler und der Administrator erstellen die Konfigurationsdateien und die ACL für jede Anwendungsanforderung.  Eine Konfigurationsdatei kann Endpunktadressen und Links zu Zertifikaten im Zertifikatspeicher enthalten.  Mithilfe der Zertifikate können Anwendungsdaten zum Konfigurieren verschiedener Eigenschaften der von der Anwendung verwendeten Funktionen bereitgestellt werden.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] verwendet auch die Prozesssicherungsfunktionalität von .NET Framework durch Aufrufen der <xref:System.Environment.FailFast%2A>\-Methode.  
  
### Tools für IT\-Fachleute  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] stellt auch die folgenden Tools für IT\-Fachleute bereit, die in Windows SDK enthalten sind.  
  
#### SvcTraceViewer.exe  
 Der Viewer zeigt [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Ablaufverfolgungsdateien an.  Der Viewer zeigt an, welche Daten in den Ablaufverfolgungen enthalten sind.  
  
#### SvcConfigEditor.exe  
 Der Editor ermöglicht dem Benutzer das Erstellen und Bearbeiten von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Konfigurationsdateien.  Der Editor zeigt an, welche Daten in den Konfigurationsdateien enthalten sind.  Für die gleiche Aufgabe kann auch ein Text\-Editor verwendet werden.  
  
#### ServiceModel\_Reg  
 Mit diesem Tool kann der Benutzer ServiceModel\-Installationen auf einem Computer verwalten.  Das Tool zeigt bei der Ausführung Statusmeldungen in einem Konsolenfenster an und kann im Prozess Informationen zur Konfiguration der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Installation anzeigen.  
  
#### WSATConfig.exe und WSATUI.dll  
 Mit diesen Tools können IT\-Experten interoperable WS\-AtomicTransaction\-Netzwerkunterstützung in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] konfigurieren.  Mithilfe der Tools kann der Benutzer die Werte der in der Registrierung gespeicherten am häufigsten verwendeten WS\-AtomicTransaction\-Einstellungen anzeigen und ändern.  
  
## Querschnittliche Features  
 Die folgenden Features sind querschnittliche Features.  Das heißt, sie können mit allen vorangehenden Features zusammengesetzt werden.  
  
### Dienstframework  
 Header können eine Instanz\-ID enthalten; dies ist eine GUID, die eine Nachricht einer Instanz einer CLR\-Klasse zuordnet.  
  
 Die WSDL \(Web Services Description Language\) enthält eine Definition des Anschlusses.  Jeder Anschluss verfügt über eine Endpunktadresse und eine Bindung, die die von der Anwendung verwendeten Dienste darstellt.  Das Verfügbarmachen der WSDL kann mithilfe der Konfiguration deaktiviert werden.  Auf dem Computer werden keine Informationen beibehalten.  
  
## Siehe auch  
 [Windows Communication Foundation](http://msdn.microsoft.com/de-de/fd327ade-0260-4c40-adbe-b74645ba3277)   
 [Sicherheit](../../../docs/framework/wcf/feature-details/security.md)