---
title: "Integrierte Windows-Authentifizierung mit erweitertem Schutz | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 81731998-d5e7-49e4-ad38-c8e6d01689d0
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Integrierte Windows-Authentifizierung mit erweitertem Schutz
Erweiterungen wurden diesen Auswirkungen gemacht, wie die integrierte Windows\-Authentifizierung durch <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpListener>, <xref:System.Net.Mail.SmtpClient>, <xref:System.Net.Security.SslStream>, <xref:System.Net.Security.NegotiateStream> und die verknüpften Klassen in <xref:System.Net> und die verknüpften Namespaces behandelt wird.  Unterstützung wurde hinzugefügt, damit erweiterter Schutz die Sicherheit erhöhen.  
  
 Diese Änderungen können Anwendungen auswirken, die diese Klassen verwenden, um Webanforderungen zu stellen und Antworten zu empfangen, in denen die integrierte Windows\-Authentifizierung verwendet wird.  Diese Änderung kann Webserver und Clientanwendungen auch auswirken, die so konfiguriert werden, um die Windows\-Authentifizierung zu verwenden.  
  
 Diese Änderungen können Anwendungen auch beeinflussen, die diese Klassen verwenden, um andere Typen von den Anforderungen zu machen und Antworten zu empfangen, in denen die integrierte Windows\-Authentifizierung verwendet wird.  
  
 Die Änderungen, um den erweiterten Schutz zu unterstützen sind nur für Anwendungen unter Windows 7 und Windows Server 2008 R2 verfügbar.  Die erweiterten Schutzfunktionen sind auf früheren Versionen von Windows nicht verfügbar.  
  
## Übersicht  
 Der Entwurf der Integrierten Windows\-Authentifizierung ermöglicht, dass einige Anmeldeinformationsantworten universell sind, was bedeutet, dass sie wieder verwendet oder weitergeleitet werden können.  Die Herausforderungsantworten sollten an einem Minimum mit bestimmten Informationen des Ziels und mit einigen Channelbesondereinformationen vorzugsweise auch erstellt werden.  Dienste können erweiterten Schutz dann bieten, um sicherzustellen, dass Anmeldeinformationen Herausforderungsantworten bestimmte Informationen des Diensts wie ein Dienstprinzipalname \(SPN\) enthalten.  Mit diesen Informationen in den Anmeldeinformationen Austausch, sind Dienste, vor böswilligen Verwendung von Anmeldeinformationen Herausforderungsantworten besser schützen, die möglicherweise nicht ordnungsgemäß verwendet wurde.  
  
 Der erweiterte Schutzentwurf ist eine Erweiterung zu den Authentifizierungsprotokollen, die entwickelt wurden, um Authentifizierungsrelayangriffe zu verringern.  Er bezieht sich auf das Konzept der Bindungsinformationen des Kanals und des Diensts.  
  
 Die allgemeinen Ziele sind die folgenden:  
  
1.  Wenn der Client aktualisiert wird, um den erweiterten Schutz zu unterstützen, sollten Anwendungen Bindungsinformationen der Channelbindung und \-Diensts an alle unterstützten Authentifizierungsprotokolle bereitstellen.  Bindungsinformationen des Kanals können nur angegeben werden, wenn ein zu binden Channel \(TLS\) gibt.  Bindungsinformationen des Diensts sollten immer angegeben werden.  
  
2.  Die Server, die ordnungsgemäß konfiguriert, die Bindungsinformationen des Kanals und des Diensts überprüfen, wenn es im Clientauthentifizierungstoken vorhanden ist und weisen möglicherweise den Authentifizierungsversuch zurück, wenn die Channelbindungen nicht übereinstimmen.  Je nach Bereitstellungsszenario überprüfen Server möglicherweise Channelbindung, Dienstbindung oder beides.  
  
3.  Aktualisierte Server haben die Möglichkeit, Anforderungen der Client früherer Versionen annehmen oder ablehnen, die die Bindungsinformationen des Kanals nicht entsprechend Richtlinie enthalten.  
  
 Die Informationen, die von erweiterten Schutz verwendet werden, bestehen aus einem oder beiden der folgenden zwei Teile:  
  
1.  Ein Channelbindungstoken oder ein CBT.  
  
2.  Bindungsinformationen des Diensts in Form eines Dienstprinzipalnamens oder eines SPN.  
  
 Bindungsinformationen des Diensts sind ein Anzeichen für die Absicht eines Clients, zu einem bestimmten Dienstendpunkt zu authentifizieren.  Es wird von Client zu Server mit den folgenden Eigenschaften verwendet:  
  
-   Der SPN\-Wert muss für den Server verfügbar sein, der in der Clientauthentifizierung Klartextform ausführt.  
  
-   Der Wert des SPN ist öffentlich.  
  
-   Das SPN muss bei dem Transport kryptografisch geschützt werden so, dass ein Man\-in\-the\-middle\-Angriff seinen Wert nicht einfügen, entfernen oder ändern kann.  
  
 Ein CBT ist eine Eigenschaft des äußeren sicheren Channels \(wie TLS\) verwendet, um \(Bindung\) sie an einer Konversation zu einem inneren, Client\-authentifizierten Channel zu binden.  Das CBT muss die folgenden Eigenschaften aufweisen \(auch definiert durch IETF RFC 5056\):  
  
-   Wenn ein äußerer Channel vorhanden ist, muss der Wert des CBT eine Eigenschaft sein, die einen der äußere Channel oder der Serverendpunkt identifiziert, erzielen Sie unabhängig von Clients und Serverseiten einer Konversation.  
  
-   Wert des CBT, das vom Client gesendet wird, darf nicht einige sein, den ein Angreifer auswirken kann.  
  
-   Keine Garantien werden über Geheimhaltung des CBT\-Werts gemacht.  Dies bedeutet jedoch nicht, dass der Wert der Dienstbindung und Binden von der Informationen des Kanals von einer anderen jedoch den Server immer überprüft werden kann, der Authentifizierung ausgeführt wird, als das Protokoll, das das CBT enthält, kann es verschlüsselt.  
  
-   Das CBT muss die Integrität kryptografisch sein, die in geschützt ist, durchfährt so, dass ein Angreifer den Wert nicht einfügen, entfernen oder ändern kann.  
  
 Channelbindung wird vom Client erreicht, der das SPN und das CBT zum Server in einer tamperproof Weise übertragen wird.  Der Server überprüft die Bindungsinformationen des Kanals in Übereinstimmung mit der Richtlinie und weist Authentifizierungsversuche zurück, für die sie sich nicht glaubt, das beabsichtigte Ziel worden zu sein.  Auf diese Weise, die zwei Channels werden kryptografisch zusammen gebunden.  
  
 Um die Kompatibilität mit vorhandenen Anwendungen beibehalten, und Clients wird ein Server konfiguriert sein Authentifizierungsversuchen um zuzulassen von Clients die noch nicht erweiterten Schutz unterstützen.  Dies wird als "teilweise verhärtete" Konfiguration, im Gegensatz zu einer "vollständig verhärteten" Konfiguration.  
  
 Mehrere Komponenten in <xref:System.Net> und <xref:System.Net.Security>\-Namespaces führen integrierte Windows\-Authentifizierung im Namen eines aufrufende Anwendung aus.  In diesem Abschnitt werden Änderungen an System.Net\-Komponenten, um erweiterten Schutz in ihrem Verwendung von der integrierten Windows\-Authentifizierung hinzuzufügen.  
  
 Erweiterter Schutz wird nur unter Windows 7. unterstützt.  Ein Mechanismus wird bereitgestellt, sodass eine Anwendung bestimmen, wenn das Betriebssystem erweiterten Schutz unterstützt.  
  
## Änderungen am Stützerweiterten schutz  
 Der Authentifizierungsprozess, der mit der integrierten Windows\-Authentifizierung, abhängig vom Authentifizierungsprotokoll verwendet wird verwendet wird, enthält häufig eine Herausforderung, die durch den Zielcomputer und das zurückgeschickte auf den Clientcomputer ausgegeben wird.  Erweiterter Schutz fügt neue Funktionen diesem Authentifizierungsprozess hinzu  
  
 Der <xref:System.Security.Authentication.ExtendedProtection> \-Namespace unterstützt Authentifizierung mithilfe von erweitertem Schutz für Anwendungen.  Die <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding>\-Klasse in diesem Namespace stellt eine Channelbindung dar.  Die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>\-Klasse in diesem Namespace stellt die erweiterte Schutzrichtlinie dar, der vom Server verwendet wird, um eingehende Clientverbindungen zu überprüfen.  Andere Klassenmember sind mit erweitertem Schutz verwendet.  
  
 Für Serveranwendungen enthalten diese Klassen Folgendes:  
  
 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>, das die folgenden Elemente verfügt:  
  
-   Eine <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.OSSupportsExtendedProtection%2A>\-Eigenschaft, die angibt, ob das Betriebssystem die integrierte Windows\-Authentifizierung mit erweitertem Schutz unterstützt.  
  
-   Ein <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement>\-Wert, der angibt, wann die erweiterte Schutzrichtlinie erzwungen werden soll.  
  
-   Ein <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario>\-Wert, der das Bereitstellungsszenario angibt.  Dies beeinflusst, wie erweiterter Schutz aktiviert ist.  
  
-   Optionales <xref:System.Security.Authentication.ExtendedProtection.ServiceNameCollection>, das die Liste der benutzerdefinierten SPN enthält, die verwendet wird, um an das SPN anzupassen, kann vom Client als das beabsichtigte Ziel der Authentifizierung bereit.  
  
-   Optionales <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding>, das eine benutzerdefinierte Channelbindung enthält, die für die Validierung zu verwenden.  Dieses Szenario ist kein gängiger Fall  
  
 Der <xref:System.Security.Authentication.ExtendedProtection.Configuration> \-Namespace unterstützt die Konfiguration der Authentifizierung mithilfe von erweitertem Schutz für Anwendungen.  
  
 Einige jeweiligen wurden vorgenommen, um erweiterten Schutz im vorhandenen <xref:System.Net>\-Namespace zu unterstützen.  Diese Änderungen gehören:  
  
-   Eine neue <xref:System.Net.TransportContext>\-Klasse hinzugefügt <xref:System.Net>\-Namespace, der einen Transportkontext darstellt.  
  
-   Neues <xref:System.Net.HttpWebRequest.EndGetRequestStream%2A> und <xref:System.Net.HttpWebRequest.GetRequestStream%2A> Überladungsmethoden in der <xref:System.Net.HttpWebRequest>\-Klasse, die das Abrufen <xref:System.Net.TransportContext> ermöglichen, um erweiterten Schutz für Clientanwendungen zu unterstützen.  
  
-   Ergänzungen zu den <xref:System.Net.HttpListener> und <xref:System.Net.HttpListenerRequest>\-Klassen, die von Serveranwendungen zu unterstützen.  
  
 Eine Funktionsänderung wurde vorgenommen, um erweiterten Schutz für SMTP\-Clientanwendungen im vorhandenen <xref:System.Net.Mail>\-Namespace zu unterstützen:  
  
-   Eine <xref:System.Net.Mail.SmtpClient.TargetName%2A>\-Eigenschaft in der <xref:System.Net.Mail.SmtpClient>\-Klasse, die das SPN darstellt, die für die Authentifizierung bei der Anwendung verwenden, erweiterte Schutz für SMTP\-Clientanwendungen.  
  
 Einige jeweiligen wurden vorgenommen, um erweiterten Schutz im vorhandenen <xref:System.Net.Security>\-Namespace zu unterstützen.  Diese Änderungen gehören:  
  
-   Neues <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A> und <xref:System.Net.Security.NegotiateStream.AuthenticateAsClient%2A> Überladungsmethoden in <xref:System.Net.Security.NegotiateStream>\-Klasse, die das Übergeben eines CBT ermöglichen, um erweiterten Schutz für Clientanwendungen zu unterstützen.  
  
-   Neues <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A> und <xref:System.Net.Security.NegotiateStream.AuthenticateAsServer%2A> Überladungsmethoden in <xref:System.Net.Security.NegotiateStream>\-Klasse, die das Übergeben von <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> ermöglichen, um erweiterten Schutz für Serveranwendungen zu unterstützen.  
  
-   Eine neue <xref:System.Net.Security.SslStream.TransportContext%2A>\-Eigenschaft in der <xref:System.Net.Security.SslStream>\-Klasse, um den erweiterten Schutz für Client\- und Serveranwendungen zu unterstützen.  
  
 Eine <xref:System.Net.Configuration.SmtpNetworkElement>\-Eigenschaft wurde zur Stützkonfiguration des erweiterten Schutz für SMTP\-Clienten im <xref:System.Net.Security>\-Namespace hinzugefügt.  
  
## Erweiterter Schutz für Clientanwendungen  
 Erweiterte Schutzunterstützung für die meisten Clientanwendungen geschieht automatisch.  Die <xref:System.Net.HttpWebRequest> und <xref:System.Net.Mail.SmtpClient>\-Klasse einzelne erweiterte Schutz, wenn die zugrunde liegende Version von Windows erweiterten Schutz unterstützt.  Eine <xref:System.Net.HttpWebRequest>\-Instanz sendet ein SPN, das von <xref:System.Uri> erstellt wird.  Standardmäßig sendet eine <xref:System.Net.Mail.SmtpClient>\-Instanz ein SPN, das vom Hostnamen des SMTP\-E\-Mail\-Servers erstellt wird.  
  
 Für benutzerdefinierte Authentifizierung können Clientanwendungen <xref:System.Net.HttpWebRequest.EndGetRequestStream%28System.IAsyncResult%2CSystem.Net.TransportContext%40%29?displayProperty=fullName> verwenden, oder <xref:System.Net.HttpWebRequest.GetRequestStream%28System.Net.TransportContext%40%29?displayProperty=fullName>\-Methoden in <xref:System.Net.HttpWebRequest>\-Klasse, die das Abrufen <xref:System.Net.TransportContext> und des CBT mithilfe der <xref:System.Net.TransportContext.GetChannelBinding%2A>\-Methode ermöglichen.  
  
 Das für die integrierte Windows\-Authentifizierung verwendet, SPN, die von einer Instanz <xref:System.Net.HttpWebRequest> zu einem angegebenen Dienst gesendet wird, kann überschrieben werden, indem die <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A>\-Eigenschaft festlegt.  
  
 Die <xref:System.Net.Mail.SmtpClient.TargetName%2A>\-Eigenschaft kann verwendet werden, um einen benutzerdefinierten SPN festlegen, um für die integrierte Windows\-Authentifizierung für die SMTP\-Verbindung zu verwenden.  
  
## Erweiterter Schutz für Serveranwendungen  
 <xref:System.Net.HttpListener> wird automatisch Mechanismen zum Überprüfen von Dienstbindungen bereit, wenn es HTTP\-Authentifizierung ausführt.  
  
 Das sicherste Szenario ist, erweiterten Schutz für HTTPS:\/\/\- Präfixe zu aktivieren.  In diesem Fall legen Sie <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=fullName> zu <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> mit <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> fest, die an <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> oder zu <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> festgelegt wurde, und <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario>, das zu einem Wert <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> von <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> festgelegt ist, wird <xref:System.Net.HttpListener> in teilweise verhärteten Modus ein, während <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> in vollständig verhärtetem Modus entspricht.  
  
 In dieser Konfiguration, wenn eine Anforderung an den Server durch einen äußeren sicheren Kanal gemacht wird, wird der äußere Channel für eine Channelbindung abgefragt.  Diese Channelbindung wird für die Authentifizierung SSPI\-Aufrufen übergeben, die sicherstellen, dass die Channelbindung in der Authentifizierung BLOB übereinstimmt.  Es gibt drei mögliche Ergebnisse:  
  
1.  Das zugrunde liegende Betriebssystem des Servers unterstützt keine erweiterten Schutz.  Die Anforderung wird nicht mit verfügbar gemacht, und eine unberechtigte \(401\) Antwort wird an den Client zurückgegeben.  Eine Meldung wird auf <xref:System.Net.HttpListener> Ablaufverfolgungsquelle protokolliert, die den Grund für den Fehler angibt.  
  
2.  Der SSPI\-Aufruf verlässt das Angeben, dass jedes der Client eine Channelbindung angegeben, die nicht den erwarteten Wert übereinstimmt, der aus dem äußeren Channel oder vom Client konnte nicht wurden eine Channelbindung angeben abgerufen wurde, als die erweiterte Schutzrichtlinie auf dem Server für <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> konfiguriert wurde.  In beiden Fällen wird die Anforderung nicht zur Anwendung verfügbar gemacht, und eine unberechtigte \(401\) Antwort wird an den Client zurückgegeben.  Eine Meldung wird auf <xref:System.Net.HttpListener> Ablaufverfolgungsquelle protokolliert, die den Grund für den Fehler angibt.  
  
3.  Der Client gibt die richtige Channelbindung oder an ermöglicht, dass herzustellen, ohne eine Channelbindung anzugeben, da die erweiterte Schutzrichtlinie auf dem Server mit <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> konfiguriert wird, das die Anforderung an die Anwendung für die Verarbeitung zurückgegeben wird.  Keine Dienstnameüberprüfung wird automatisch ausgeführt.  Eine Anwendung wählt, seine eigene Dienstnamevalidierung mithilfe der <xref:System.Net.HttpListenerRequest.ServiceName%2A>\-Eigenschaft auszuführen, jedoch unter diesen Umständen ist sie redundant.  
  
 Wenn eine Anwendung eigene SSPI\-Aufrufe Authentifizierung auf Grundlage der Kleckse ausführen können, die hin und her im Text einer HTTP\-Anforderung übergeben und Channelbindung unterstützen möchte, muss sie die erwartete Channelbindung aus dem äußeren sicheren Kanal mithilfe <xref:System.Net.HttpListener> abrufen, um es zu systemeigenen Win32\-Funktion [AcceptSecurityContext](http://go.microsoft.com/fwlink/?LinkId=147021) zu übergeben.  Um dies zu erreichen, verwenden Sie die <xref:System.Net.HttpListenerRequest.TransportContext%2A>\-Eigenschaft, und rufen Sie <xref:System.Net.TransportContext.GetChannelBinding%2A>\-Methode auf um das CBT abzurufen.  Nur Endpunktbindungen werden unterstützt.  Wenn die übrigen <xref:System.Security.Authentication.ExtendedProtection.ChannelBindingKind> angegeben wird, wird <xref:System.NotSupportedException> ausgelöst.  Wenn die zugrunde liegende Betriebssystemunterstützung Bindung lenkt, gibt die <xref:System.Net.TransportContext.GetChannelBinding%2A>\-Methode <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding><xref:System.Runtime.InteropServices.SafeHandle> zurück, das einen Zeiger auf einen Channelbinden entsprechend umschließt, damit das Übergeben [AcceptSecurityContext](http://go.microsoft.com/fwlink/?LinkId=147021) als der pvBuffer Member einer SecBuffer\-Struktur arbeiten, die in den `pInput`\-Parameter übergeben wird.  Die <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding.Size%2A>\-Eigenschaft enthält die Länge, in Bytes, der Channelbindung.  Wenn das zugrunde liegende Betriebssystem nicht Channelbindungen unterstützt, gibt die Funktion `null` zurück.  
  
 Ein weiteres mögliches Szenario ist, erweiterten Schutz für HTTP:\/\/\- Präfixe zu aktivieren, wenn Proxy nicht verwendet werden.  In diesem Fall legen Sie <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=fullName> zu <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> mit <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> fest, die an <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> oder zu <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> festgelegt wurde, und <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario>, das zu einem Wert <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> von <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> festgelegt ist, wird <xref:System.Net.HttpListener> in teilweise verhärteten Modus ein, während <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> in vollständig verhärtetem Modus entspricht.  
  
 Eine Standardliste der zulässigen Dienstnamen wird auf Grundlage der Präfixe erstellt, die mit <xref:System.Net.HttpListener> registriert wurden.  Diese Standardliste kann durch die <xref:System.Net.HttpListener.DefaultServiceNames%2A>\-Eigenschaft überprüft werden.  Wenn diese Liste nicht umfassend ist, kann eine Anwendung eine Zollamtnameauflistung im Konstruktor für die Klasse <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> angeben, die anstelle der standardmäßigen DienstSymboltabelle verwendet wird.  
  
 In dieser Konfiguration wenn eine Anforderung an den Server ohne zurückgehalten einer äußere des sicheren Channels Authentifizierung normalerweise ohne eine Channelbindungsüberprüfung gemacht wird.  Wenn die Authentifizierung erfolgreich ist, wird der Kontext für den Dienstnamen abgefragt, den der Client zu der Liste von zulässigen Dienstnamen vom und überprüfen.  Es gibt vier mögliche Ergebnisse:  
  
1.  Das zugrunde liegende Betriebssystem des Servers unterstützt keine erweiterten Schutz.  Die Anforderung wird nicht mit verfügbar gemacht, und eine unberechtigte \(401\) Antwort wird an den Client zurückgegeben.  Eine Meldung wird auf <xref:System.Net.HttpListener> Ablaufverfolgungsquelle protokolliert, die den Grund für den Fehler angibt.  
  
2.  Das zugrunde liegende Betriebssystem des Clients unterstützt keine erweiterten Schutz.  In der <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> Konfiguration folgt der Authentifizierungsversuch und die Anforderung an die Anwendung zurückgegeben.  In der <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> Konfiguration schlägt der Authentifizierungsversuch aus.  Die Anforderung wird nicht mit verfügbar gemacht, und eine unberechtigte \(401\) Antwort wird an den Client zurückgegeben.  Eine Meldung wird auf <xref:System.Net.HttpListener> Ablaufverfolgungsquelle protokolliert, die den Grund für den Fehler angibt.  
  
3.  Das zugrunde liegende Betriebssystem des Clients unterstützt erweiterten Schutz, aber die Anwendung wurde keine Dienstbindung an.  Die Anforderung wird nicht mit verfügbar gemacht, und eine unberechtigte \(401\) Antwort wird an den Client zurückgegeben.  Eine Meldung wird auf <xref:System.Net.HttpListener> Ablaufverfolgungsquelle protokolliert, die den Grund für den Fehler angibt.  
  
4.  Der Client hat eine Dienstbindung an.  Die Dienstbindung wird der Liste der zulässigen Dienstbindungen verglichen.  Wenn sie übereinstimmt, wird die Anforderung an die Anwendung zurückgegeben.  Andernfalls wird die Anforderung nicht zur Anwendung verfügbar gemacht, und eine unberechtigte \(401\) Antwort wird automatisch an den Client zurückgegeben.  Eine Meldung wird auf <xref:System.Net.HttpListener> Ablaufverfolgungsquelle protokolliert, die den Grund für den Fehler angibt.  
  
 Wenn dieser Ansatz einfache mithilfe einer Zulassungsliste von akzeptablen Dienstnamen nicht ausreicht, wird möglicherweise eine Anwendung eine eigene Dienstnamevalidierung vom Abfragen der <xref:System.Net.HttpListenerRequest.ServiceName%2A>\-Eigenschaft bereit.  In Fälle 1 und 2 oben, gibt die `null`\-Eigenschaft zurück.  Fall 3, wird eine leere Zeichenfolge zurückgeben.  Fall 4, der Dienstname, vom Client angegeben ist, zurückgegeben.  
  
 Diese erweiterten Schutzfunktionen können durch Serveranwendungen für die Authentifizierung mit anderen Arten von Anforderungen auch verwendet werden und wenn vertrauenswürdige Proxy verwendet werden.  
  
## Siehe auch  
 <xref:System.Security.Authentication.ExtendedProtection>   
 <xref:System.Security.Authentication.ExtendedProtection.Configuration>