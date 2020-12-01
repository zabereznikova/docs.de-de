---
title: Integrierte Windows-Authentifizierung mit erweitertem Schutz
ms.date: 03/30/2017
ms.assetid: 81731998-d5e7-49e4-ad38-c8e6d01689d0
ms.openlocfilehash: 74f421131da0e5b11fd676ff23229f5ff6ec7eca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241622"
---
# <a name="integrated-windows-authentication-with-extended-protection"></a>Integrierte Windows-Authentifizierung mit erweitertem Schutz

Es wurden Verbesserungen vorgenommen, die beeinflussen, wie die integrierte Windows-Authentifizierung durch <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpListener>, <xref:System.Net.Mail.SmtpClient>, <xref:System.Net.Security.SslStream>, <xref:System.Net.Security.NegotiateStream> und verknüpfte Klassen in <xref:System.Net> sowie verknüpfte Namespaces behandelt wird. Unterstützung für erweiterten Schutz wurde zur Verbesserung der Sicherheit hinzugefügt.  
  
 Diese Änderungen können sich auf Anwendungen auswirken, die diese Klassen für Webanforderungen und den Empfang der Antworten verwenden, in denen die integrierte Windows-Authentifizierung verwendet wird. Die Änderung kann sich auch auf Webserver und Clientanwendungen auswirken, die für die Verwendung der integrierten Windows-Authentifizierung konfiguriert sind.  
  
 Zudem können sich die Änderungen auf Anwendungen auswirken, die diese Klassen für andere Anforderungstypen verwenden und Antworten erhalten, in denen die integrierte Windows-Authentifizierung verwendet wird.  
  
 Die Änderungen zur Unterstützung des erweiterten Schutzes sind nur für Anwendungen verfügbar, die Windows 7 und Windows Server 2008 R2 ausführen. Die erweiterten Schutzfunktionen sind nicht für frühere Windows-Versionen verfügbar.  
  
## <a name="overview"></a>Übersicht  

 Durch die Gestaltung der integrierten Windows-Authentifizierung sind einige Abfragerückmeldungen zu Anmeldeinformationen universell, d.h. sie können wiederverwendet oder weitergeleitet werden. Die Abfragerückmeldungen sollten so konstruiert sein, dass sie mindestens über zielspezifische Informationen verfügen, vorzugsweise auch über einige kanalspezifische Informationen. Der erweiterte Schutz kann dann von Diensten bereitgestellt werden, damit Abfragerückmeldungen zu Anmeldeinformationen auch sicher dienstspezifische Informationen, wie z.B. einen Dienstprinzipalnamen (Service Principal Name, SPN), enthalten. Enthält der Austausch von Anmeldedaten diese Informationen, können die Dienste besser vor einer böswilligen Verwendung von Abfragerückmeldungen zu Anmeldeinformationen schützen, die möglicherweise nicht ordnungsgemäß verwendet wurden.  
  
 Die Gestaltung des erweiterten Schutzes stellt eine Verbesserung der Authentifizierungsprotokolle dar, um Relay-Angriffe auf die Authentifizierung zu verringern. Sie basiert auf Kanalbindungs- und Dienstbindungsinformationen.  
  
 Die Hauptziele lauten wie folgt:  
  
1. Unterstützt der Client nach der Aktualisierung den erweiterten Schutz, sollten die Anwendungen allen unterstützten Authentifizierungsprotokollen Kanalbindungs- und Dienstbindungsinformationen bereitstellen. Kanalbindungsinformationen können nur bereitgestellt werden, wenn ein Kanal (TLS) vorhanden ist, an den sie sich binden können. Dienstbindungsinformationen sollten immer bereitgestellt werden.  
  
2. Aktualisierte und ordnungsgemäß konfigurierte Server überprüfen möglicherweise die Kanalbindungs- und die Dienstbindungsinformationen, wenn sie im Clientauthentifizierungstoken vorhanden sind. Stimmen die Kanalbindungen nicht überein, wird der Authentifizierungsversuch abgelehnt. Je nach Bereitstellungsszenario überprüfen die Server möglicherweise die Kanalbindung, die Dienstbindung oder beides.  
  
3. Aktualisierte Server können abwärtskompatible Clientanforderungen, die die Kanalbindungsinformationen der Richtlinie nicht enthalten, annehmen oder ablehnen.  
  
 Die durch den erweiterten Schutz verwendeten Informationen bestehen aus einem oder beiden der folgenden zwei Elemente:  
  
1. einem Kanalbindungstoken oder CBT (Channel Binding Token)  
  
2. Dienstbindungsinformationen in Form eines Dienstprinzipalnamens oder SPN (Service Principal Name)  
  
 Dienstbindungsinformationen deuten darauf hin, dass sich ein Client bei einem bestimmten Dienstendpunkt authentifizieren möchte. Sie werden mit den folgenden Eigenschaften vom Client zum Server übermittelt:  
  
- Der SPN-Wert muss für den Server, der die Clientauthentifizierung durchführt, als Klartext verfügbar sein.  
  
- Der SPN-Wert ist öffentlich.  
  
- Der SPN muss während der Übertragung kryptografisch geschützt sein, damit der Wert bei einem Man-in-the-Middle-Angriff nicht eingefügt, entfernt oder geändert werden kann.  
  
 Ein CBT ist eine Eigenschaft des gesicherten Außenkanals (z.B. TLS), die zur Kopplung (Bindung) an eine Konversation über einen clientauthentifizierten Innenkanal verwendet wird. Das CBT muss über die folgenden Eigenschaften verfügen (auch durch IETF RFC 5056 definiert):  
  
- Ist ein Außenkanal vorhanden, muss der CBT-Wert eine Eigenschaft sein, die entweder den Außenkanal oder den Serverendpunkt identifiziert. Sie muss auf beiden Seiten der Konversation unabhängig empfangen werden, sowohl beim Client als auch beim Server.  
  
- Der Wert des vom Client gesendeten CBT darf nicht von einem Angreifer beeinflusst werden können.  
  
- Es kann nicht garantiert werden, dass der CBT-Wert geheim bleibt. Dies bedeutet jedoch nicht, dass der Wert der Dienstbindungs- sowie der Kanalbindungsinformationen immer von einem beliebigen anderen Server als dem überprüft werden kann, der die Authentifizierung ausführt. Das Protokoll, das das CBT enthält, verschlüsselt ihn möglicherweise.  
  
- Das CBT muss während der Übertragung kryptografisch geschützt sein, damit der Wert von einem Angreifer nicht eingefügt, entfernt oder geändert werden kann.  
  
 Die Kanalbindung erfolgt durch den Client, der den SPN und das CBT manipulationsgeschützt an den Server überträgt. Der Server überprüft die Kanalbindungsinformationen anhand der Richtlinie und lehnt Authentifizierungsversuche ab, die er als nicht an ihn gerichtet einstuft. So werden die beiden Kanäle kryptografisch miteinander verbunden.  
  
 Damit die Kompatibilität mit vorhandenen Clients und Anwendungen erhalten bleibt, kann ein Server so konfiguriert werden, dass er Authentifizierungsversuche von Clients zulässt, die noch nicht den erweiterten Schutz unterstützen. Diese Konfiguration wird als „teilweise gehärtet“ bezeichnet, im Gegensatz zu einer „vollständig gehärteten“ Konfiguration.  
  
 Mehrere Komponenten der Namespaces <xref:System.Net> und <xref:System.Net.Security> führen die integrierte Windows-Authentifizierung für eine aufrufende Anwendung aus. In diesem Abschnitt werden die erforderlichen Änderungen an System.Net-Komponenten beschrieben, um den erweiterten Schutz ihrer Verwendung der integrierten Windows-Authentifizierung hinzuzufügen.  
  
 Der erweiterte Schutz wird derzeit für Windows 7 unterstützt. Über einen bereitgestellten Mechanismus ermittelt eine Anwendung, ob das Betriebssystem den erweiterten Schutz unterstützt.  
  
## <a name="changes-to-support-extended-protection"></a>Erforderliche Änderungen für den erweiterten Schutz  

 Der bei der integrierten Windows-Authentifizierung verwendete Authentifizierungsvorgang enthält je nach Authentifizierungsprotokoll häufig eine Abfrage, die vom Zielcomputer ausgegeben und an den Clientcomputer zurückgesendet wird. Der erweiterte Schutz fügt diesem Authentifizierungsvorgang neue Funktionen hinzu.  
  
 Der Namespace <xref:System.Security.Authentication.ExtendedProtection> stellt Unterstützung für die Authentifizierung mit erweitertem Schutz für Anwendungen bereit. In diesem Namespace stellt die Klasse <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> die Kanalbindung dar. Die Klasse <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> stellt in diesem Namespace die erweiterte Schutzrichtlinie dar, die vom Server zur Validierung eingehender Clientverbindungen verwendet wird. Andere Klassenmember werden mit erweitertem Schutz verwendet.  
  
 Bei Serveranwendungen beinhalten diese Klassen:  
  
 Eine <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> mit den folgenden Elementen:  
  
- Eine <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.OSSupportsExtendedProtection%2A>-Eigenschaft, die angibt, ob das Betriebssystem die integrierte Windows-Authentifizierung mit erweitertem Schutz unterstützt.  
  
- Ein <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement>-Wert, der angibt, wann die erweiterte Schutzrichtlinie erzwungen werden soll.  
  
- Ein <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario>-Wert, der das Bereitstellungsszenario angibt. Dieser wirkt sich darauf aus, wie der erweiterte Schutz aktiviert wird.  
  
- Eine optionale <xref:System.Security.Authentication.ExtendedProtection.ServiceNameCollection> mit der benutzerdefinierten SPN-Liste für einen Abgleich mit dem vom Client bereitgestellten SPN als beabsichtigtem Ziel der Authentifizierung.  
  
- Eine optionale <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> mit einer benutzerdefinierten Kanalbindung zur Validierung. Dies ist kein häufiges Szenario.  
  
 Der Namespace <xref:System.Security.Authentication.ExtendedProtection.Configuration> stellt Unterstützung für die Konfiguration der Authentifizierung mit erweitertem Schutz für Anwendungen bereit.  
  
 Bei einer Reihe von Funktionen wurden Änderungen vorgenommen, um den erweiterten Schutz im vorhandenen Namespace <xref:System.Net> zu unterstützen. Dazu gehören folgende Änderungen:  
  
- Eine neue <xref:System.Net.TransportContext>-Klasse, die einen Transportkontext darstellt, im Namespace <xref:System.Net>.  
  
- Neue Überladungsmethoden <xref:System.Net.HttpWebRequest.EndGetRequestStream%2A> und <xref:System.Net.HttpWebRequest.GetRequestStream%2A> in der Klasse <xref:System.Net.HttpWebRequest> zum Abrufen von <xref:System.Net.TransportContext> für die Unterstützung des erweiterten Schutzes bei Clientanwendungen.  
  
- Erweiterungen für die Klassen <xref:System.Net.HttpListener> und <xref:System.Net.HttpListenerRequest> zur Unterstützung von Serveranwendungen.  
  
 Eine Funktionsänderung wurde vorgenommen, um den erweiterten Schutz für SMTP-Clientanwendungen im vorhandenen Namespace <xref:System.Net.Mail> zu unterstützen:  
  
- Eine <xref:System.Net.Mail.SmtpClient.TargetName%2A>-Eigenschaft in der Klasse <xref:System.Net.Mail.SmtpClient>, die den zur Authentifizierung verwendeten SPN bei der Verwendung des erweiterten Schutzes in SMTP-Clientanwendungen darstellt.  
  
 Bei einer Reihe von Funktionen wurden Änderungen vorgenommen, um den erweiterten Schutz im vorhandenen Namespace <xref:System.Net.Security> zu unterstützen. Dazu gehören folgende Änderungen:  
  
- Neue Überladungsmethoden <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A> und <xref:System.Net.Security.NegotiateStream.AuthenticateAsClient%2A> in der Klasse <xref:System.Net.Security.NegotiateStream> zur Übergabe eines CBT für die Unterstützung des erweiterten Schutzes bei Clientanwendungen.  
  
- Neue Überladungsmethoden <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A> und <xref:System.Net.Security.NegotiateStream.AuthenticateAsServer%2A> in der Klasse <xref:System.Net.Security.NegotiateStream> zur Übergabe einer <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> für die Unterstützung des erweiterten Schutzes bei Serveranwendungen.  
  
- Eine neue <xref:System.Net.Security.SslStream.TransportContext%2A>-Eigenschaft in der Klasse <xref:System.Net.Security.SslStream> für die Unterstützung des erweiterten Schutzes bei Client- und Serveranwendungen.  
  
 Eine <xref:System.Net.Configuration.SmtpNetworkElement>-Eigenschaft wurde hinzugefügt, um die Konfiguration des erweiterten Schutzes für SMTP-Clients im Namespace <xref:System.Net.Security> zu unterstützen.  
  
## <a name="extended-protection-for-client-applications"></a>Erweiterter Schutz für Clientanwendungen  

 Der erweiterte Schutz wird bei den meisten Clientanwendungen automatisch unterstützt. Die Klassen <xref:System.Net.HttpWebRequest> und <xref:System.Net.Mail.SmtpClient> unterstützen den erweiterten Schutz, wenn die zugrunde liegende Windows-Version den erweiterten Schutz unterstützt. Eine <xref:System.Net.HttpWebRequest>-Instanz sendet einen SPN, der aus dem <xref:System.Uri> erstellt wird. Eine <xref:System.Net.Mail.SmtpClient>-Instanz sendet standardmäßig einen SPN, der aus dem Hostnamen des SMTP-Mailservers erstellt wird.  
  
 Clientanwendungen können zur benutzerdefinierten Authentifizierung die Methoden <xref:System.Net.HttpWebRequest.EndGetRequestStream%28System.IAsyncResult%2CSystem.Net.TransportContext%40%29?displayProperty=nameWithType> oder <xref:System.Net.HttpWebRequest.GetRequestStream%28System.Net.TransportContext%40%29?displayProperty=nameWithType> in der Klasse <xref:System.Net.HttpWebRequest> verwenden, die den <xref:System.Net.TransportContext> und das CBT mithilfe der Methode <xref:System.Net.TransportContext.GetChannelBinding%2A> abrufen.  
  
 Sie können den von einer <xref:System.Net.HttpWebRequest>-Instanz an einen bestimmten Server gesendeten SPN zur integrierten Windows-Authentifizierung überschreiben, indem Sie die Eigenschaft <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A> festlegen.  
  
 Mit der Eigenschaft <xref:System.Net.Mail.SmtpClient.TargetName%2A> kann ein benutzerdefinierter SPN zur integrierten Windows-Authentifizierung für die SMTP-Verbindung festgelegt werden.  
  
## <a name="extended-protection-for-server-applications"></a>Erweiterter Schutz für Serveranwendungen  

 <xref:System.Net.HttpListener> stellt automatisch Mechanismen zur Validierung von Dienstbindungen bereit, wenn die HTTP-Authentifizierung ausgeführt wird.  
  
 Das sicherste Szenario ist die Aktivierung des erweiterten Schutzes für die Präfixe `HTTPS://`. Legen Sie in diesem Fall <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=nameWithType> auf <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> fest, für das <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> auf <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> oder <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always> festgelegt ist, sowie <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> auf <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario.TransportSelected>. Ein Wert von <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> versetzt <xref:System.Net.HttpListener> in den teilweise gehärteten Modus, während <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always> dem vollständig gehärteten Modus entspricht.  
  
 Wird in dieser Konfiguration eine Anforderung über einen sicheren Außenkanal an den Server gesendet, wird der Außenkanal nach einer Kanalbindung abgefragt. Diese Kanalbindung wird an die SSPI-Authentifizierungsaufrufe übergeben, die überprüfen, ob die Kanalbindung im Authentifizierungsblob übereinstimmt. Es gibt drei mögliche Ergebnisse:  
  
1. Das zugrunde liegende Betriebssystem des Servers unterstützt den erweiterten Schutz nicht. Die Anforderung wird der Anwendung nicht verfügbar gemacht, und die Antwort „Nicht autorisiert (401).“ wird an den Client zurückgegeben. Eine Nachricht mit dem Grund für den Fehler wird in der Ablaufverfolgungsquelle <xref:System.Net.HttpListener> protokolliert.  
  
2. Es tritt beim SSPI-Aufruf ein Fehler auf. Dies bedeutet entweder, dass die vom Client angegebene Kanalbindung nicht mit dem erwarteten Wert übereinstimmt, der aus dem Außenkanal abgerufen wurde, oder dass der Client bei der Konfiguration der erweiterten Schutzrichtlinie auf dem Server für <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always> keine Kanalbindung bereitgestellt hat. In beiden Fällen wird die Anforderung der Anwendung nicht verfügbar gemacht, und die Antwort „Nicht autorisiert (401)“ wird an den Client zurückgegeben. Eine Nachricht mit dem Grund für den Fehler wird in der Ablaufverfolgungsquelle <xref:System.Net.HttpListener> protokolliert.  
  
3. Der Client gibt die richtige Kanalbindung an oder kann ohne Angabe einer Kanalbindung die Verbindung herstellen, da die erweiterte Schutzrichtlinie auf dem Server mit <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> konfiguriert ist. Die Anforderung wird für die Verarbeitung an die Anwendung zurückgegeben. Die Dienstnamenüberprüfung wird nicht automatisch ausgeführt. Eine Anwendung führt möglicherweise eine eigene Überprüfung des Dienstnamens mithilfe der <xref:System.Net.HttpListenerRequest.ServiceName%2A>-Eigenschaft durch. Dies ist unter diesen Umständen jedoch redundant.  
  
 Führt eine Anwendung eigene SSPI-Aufrufe zur Durchführung der Authentifizierung auf der Basis von Blobs durch, die im Text einer HTTP-Anforderung ausgetauscht werden, und ist eine Unterstützung der Kanalbindung erwünscht, muss die Anwendung die erwartete Kanalbindung vom sicheren Außenkanal mithilfe von <xref:System.Net.HttpListener> abrufen, um sie an die native Win32-Funktion [AcceptSecurityContext](/windows/win32/api/sspi/nf-sspi-acceptsecuritycontext) zu übergeben. Verwenden Sie hierfür die Eigenschaft <xref:System.Net.HttpListenerRequest.TransportContext%2A>, und rufen Sie zum Abrufen des CBT die Methode <xref:System.Net.TransportContext.GetChannelBinding%2A> auf. Nur Endpunktbindungen werden unterstützt. Wird etwas anderes als <xref:System.Security.Authentication.ExtendedProtection.ChannelBindingKind.Endpoint> angegeben, wird eine <xref:System.NotSupportedException> ausgelöst. Unterstützt das zugrunde liegende Betriebssystem die Kanalbindung, gibt die Methode <xref:System.Net.TransportContext.GetChannelBinding%2A> ein <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding><xref:System.Runtime.InteropServices.SafeHandle> zurück, das einen Zeiger mit einer Kanalbindung umschließt, die an die Funktion [AcceptSecurityContext](/windows/win32/api/sspi/nf-sspi-acceptsecuritycontext) als im Parameter `pInput` übergebener Member „PvBuffer“ einer Struktur „SecBuffer“ übergeben wird. Die Eigenschaft <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding.Size%2A> enthält die Länge der Kanalbindung in Bytes. Unterstützt das zugrunde liegende Betriebssystem keine Kanalbindungen, gibt die Funktion `null` zurück.  
  
 Ein anderes mögliches Szenario ist die Aktivierung des erweiterten Schutz für die Präfixe `HTTP://`, wenn keine Proxys verwendet werden. Legen Sie in diesem Fall <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=nameWithType> auf <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> fest, für das <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> auf <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> oder <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always> festgelegt ist, sowie <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> auf <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario.TransportSelected>. Ein Wert von <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> versetzt <xref:System.Net.HttpListener> in den teilweise gehärteten Modus, während <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always> dem vollständig gehärteten Modus entspricht.  
  
 Eine Standardliste mit den zulässigen Dienstnamen wird auf Grundlage der Präfixe erstellt, die mit <xref:System.Net.HttpListener> registriert wurden. Diese Standardliste kann mit der Eigenschaft <xref:System.Net.HttpListener.DefaultServiceNames%2A> überprüft werden. Ist die Liste nicht vollständig, kann eine Anwendung im Konstruktor für die Klasse <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> eine benutzerdefinierte Dienstnamensammlung angeben, die anstelle der Standard-Dienstnamenliste verwendet wird.  
  
 Wird in dieser Konfiguration eine Anforderung ohne sicheren Außenkanal an den Server gesendet, erfolgt die Authentifizierung üblicherweise ohne Überprüfung der Kanalbindung. Bei erfolgreicher Authentifizierung wird der Kontext nach dem vom Client bereitgestellten Dienstnamen abgefragt und anhand der Liste der zulässigen Dienstnamen überprüft. Es gibt vier mögliche Ergebnisse:  
  
1. Das zugrunde liegende Betriebssystem des Servers unterstützt den erweiterten Schutz nicht. Die Anforderung wird der Anwendung nicht verfügbar gemacht, und die Antwort „Nicht autorisiert (401).“ wird an den Client zurückgegeben. Eine Nachricht mit dem Grund für den Fehler wird in der Ablaufverfolgungsquelle <xref:System.Net.HttpListener> protokolliert.  
  
2. Das zugrunde liegende Betriebssystem des Clients unterstützt den erweiterten Schutz nicht. Der Authentifizierungsversuch wird in der <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported>-Konfiguration erfolgreich ausgeführt, und die Anforderung wird an die Anwendung zurückgegeben. Es tritt in der <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always>-Konfiguration beim Authentifizierungsversuch ein Fehler auf. Die Anforderung wird der Anwendung nicht verfügbar gemacht, und die Antwort „Nicht autorisiert (401).“ wird an den Client zurückgegeben. Eine Nachricht mit dem Grund für den Fehler wird in der Ablaufverfolgungsquelle <xref:System.Net.HttpListener> protokolliert.  
  
3. Das zugrunde liegende Betriebssystem des Clients unterstützt den erweiterten Schutz, doch in der Anwendung wurde keine Dienstbindung angegeben. Die Anforderung wird der Anwendung nicht verfügbar gemacht, und die Antwort „Nicht autorisiert (401).“ wird an den Client zurückgegeben. Eine Nachricht mit dem Grund für den Fehler wird in der Ablaufverfolgungsquelle <xref:System.Net.HttpListener> protokolliert.  
  
4. Es wurde vom Client eine Dienstbindung angegeben. Die Dienstbindung wird mit der Liste der zulässigen Dienstbindungen verglichen. Bei einer Übereinstimmung wird die Anforderung an die Anwendung zurückgegeben. Andernfalls wird die Anforderung der Anwendung nicht verfügbar gemacht, und die Antwort „Nicht autorisiert (401)“ wird automatisch an den Client zurückgegeben. Eine Nachricht mit dem Grund für den Fehler wird in der Ablaufverfolgungsquelle <xref:System.Net.HttpListener> protokolliert.  
  
 Reicht diese einfache Vorgehensweise mit einer Liste aus zulässigen Dienstnamen nicht aus, kann eine Anwendung durch Abfragen der Eigenschaft <xref:System.Net.HttpListenerRequest.ServiceName%2A> möglicherweise eine eigene Überprüfung der Dienstnamen bereitstellen. Im 1. und 2. Fall gibt die Eigenschaft `null` zurück. Im 3. Fall wird eine leere Zeichenfolge zurückgegeben. Im 4. Fall wird der vom Client angegebene Dienstname zurückgegeben.  
  
 Diese erweiterten Schutzfunktionen können auch von Serveranwendungen für die Authentifizierung mit anderen Anforderungstypen und bei vertrauenswürdigen Proxys verwendet werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Authentication.ExtendedProtection>
- <xref:System.Security.Authentication.ExtendedProtection.Configuration>
