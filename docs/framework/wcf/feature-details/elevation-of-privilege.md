---
title: Angriffe durch Rechteerweiterung
ms.date: 03/30/2017
helpviewer_keywords:
- elevation of privilege [WCF]
- security [WCF], elevation of privilege
ms.assetid: 146e1c66-2a76-4ed3-98a5-fd77851a06d9
ms.openlocfilehash: 8838b139efa20bc796fc21567cc6fc9ee8691eee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283249"
---
# <a name="elevation-of-privilege"></a>Angriffe durch Rechteerweiterung
Die *Erhöhung der* Berechtigungen führt dazu, dass einem Angreifer über die ursprünglich gewährten Autorisierungs Berechtigungen hinausgehen. Dies ist zum Beispiel der Fall, wenn einem Angreifer mit einem Berechtigungssatz von "Nur-Lesen"-Berechtigungen es irgendwie gelingt, "Lesen-und-Schreiben"-Berechtigungen in seinen Berechtigungssatz aufzunehmen.  
  
## <a name="trusted-sts-should-sign-saml-token-claims"></a>Vertrauenswürdige STS sollten SAML-Tokenansprüche signieren  
 Ein SAML (Security Assertions Markup Language)-Token ist ein generisches XML-Token, das den Standardtyp für ausgestellte Token darstellt. SAML-Token können von einem Sicherheitstokendienst (Security Token Service, STS) erstellt werden, der für den empfangenden Webdienst in einem typischen Datenaustausch als vertrauenswürdig gilt. SAML-Token enthalten Ansprüche in Form von Anweisungen. Ein Angreifer kann die Ansprüche aus einem gültigen Token kopieren, ein neues SAML-Token erstellen und mit einem anderen Aussteller signieren. Das Ziel ist hierbei, festzustellen, ob der Server Aussteller validiert, und wenn nicht, diese Schwäche zum Erstellen von SAML-Token auszunutzen, die Berechtigungen über die von einem vertrauenswürdigen STS beabsichtigten hinaus gewähren.  
  
 Die <xref:System.IdentityModel.Tokens.SamlAssertion>-Klasse überprüft die digitale Signatur, die in einem SAML-Token enthalten ist, und der Standard-<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> erfordert, dass SAML-Token mit einem X.509-Zertifikat signiert sind, das gültig ist, wenn <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> der <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>-Klasse auf <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust> festgelegt ist. der `ChainTrust` Modus allein genügt nicht, um zu bestimmen, ob der Aussteller des SAML-Tokens vertrauenswürdig ist. Dienste, die ein stärker granuliertes Vertrauenswürdigkeitsmodell erfordern, können entweder mithilfe von Autorisierungs- oder Durchsetzungsrichtlinien den Aussteller der erzeugten Anspruchssätze durch die Authentifizierung der Token überprüfen oder die X.509-Validierungseinstellungen für <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> verwenden, um den Satz zulässiger Signaturzertifikate einzuschränken. Weitere Informationen finden Sie unter [Verwalten von Ansprüchen und Autorisierung mit dem Identitäts Modell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md) und Verbund [Token und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
## <a name="switching-identity-without-a-security-context"></a>Wechseln der Identität ohne Sicherheitskontext  
 Folgendes gilt nur für WinFX.  
  
 Wenn eine Verbindung zwischen einem Client und einem Server hergestellt wird, ändert sich die Identität des Clients nicht, es sei denn, es besteht eine Situation: Nachdem der WCF-Client geöffnet wurde, sind alle folgenden Bedingungen erfüllt:  
  
- Die Verfahren zum Einrichten eines Sicherheits Kontexts (über eine Transport Sicherheits Sitzung oder eine Nachrichten Sicherheits Sitzung) werden deaktiviert (<xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A>-Eigenschaft ist auf `false` festgelegt, wenn die Nachrichten Sicherheit oder der Transport, der keine Sicherheits Sitzungen einrichten kann, in der Transportsicherheit verwendet wird. HTTPS ist ein Beispiel für ein solches Transportprotokoll).  
  
- Sie verwenden die Windows-Authentifizierung.  
  
- Sie legen die Anmeldeinformationen nicht explizit fest.  
  
- Sie rufen den Dienst unter dem Identitätswechsel-Sicherheitskontext auf.  
  
 Wenn diese Bedingungen zutreffen, kann sich die Identität, die zum Authentifizieren des Clients beim Dienst verwendet wird, möglicherweise ändern (es kann sich dabei nicht um die Identitäts Identitäts Identität, sondern um die Prozess Identität handeln), nachdem der WCF-Client geöffnet wurde. Dies geschieht, weil die Windows-Anmeldeinformationen, mit denen der Client für den Dienst authentifiziert wird, mit jeder Nachricht übermittelt werden, und die zur Authentifizierung verwendeten Anmeldeinformationen von der Windows-Identität des aktuellen Threads bezogen werden. Wenn sich die Windows-Identität des aktuellen Threads ändert (beispielsweise durch einen Identitätswechsel, mit dem ein anderer Aufrufer imitiert wird), dann können sich auch die Anmeldeinformationen ändern, die an die Nachricht angefügt sind und die zur Authentifizierung des Clients gegenüber dem Dienst verwendet werden.  
  
 Wenn das Verhalten beim Einsatz der Windows-Authentifizierung in Verbindung mit dem Identitätswechsel deterministisch sein soll, müssen Sie die Windows-Anmeldeinformationen explizit festlegen, oder Sie müssen einen Sicherheitskontext für den Dienst einrichten. Hierzu verwenden Sie eine Nachrichtensicherheitssitzung oder eine Transportsicherheitssitzung. Zum Beispiel kann der net.tcp-Transport eine Transportsicherheitssitzung bereitstellen. Darüber hinaus dürfen Sie in Aufrufen des Diensts nur die synchrone Version von Clientvorgängen verwenden. Wenn Sie einen Nachrichtensicherheitskontext einrichten, sollten Sie die Verbindung mit dem Dienst nicht länger als den für die Sitzung konfigurierten Erneuerungszeitraum geöffnet halten, weil sich die Identität auch während des Sitzungserneuerungsprozesses ändern kann.  
  
### <a name="credentials-capture"></a>Aufzeichnung der Anmeldeinformationen  
 Folgendes gilt für .NET Framework 3,5 und nachfolgende Versionen.  
  
 Die vom Client oder Dienst verwendeten Anmeldeinformationen basieren auf dem aktuellen Kontextthread. Die Anmeldeinformationen werden durch einen Aufruf der `Open`-Methode (bzw. `BeginOpen` für asynchrone Aufrufe) des Clients oder Diensts bezogen. Sowohl für die <xref:System.ServiceModel.ServiceHost>-Klasse als auch für die <xref:System.ServiceModel.ClientBase%601>-Klasse gilt, dass die `Open`-Methode bzw. die `BeginOpen`-Methode von der <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>-Methode bzw. der <xref:System.ServiceModel.Channels.CommunicationObject.BeginOpen%2A>-Methode der <xref:System.ServiceModel.Channels.CommunicationObject>-Klasse abgeleitet ist.  
  
> [!NOTE]
> Bei Verwendung der `BeginOpen`-Methode kann nicht garantiert werden, dass es sich bei den aufgezeichneten Anmeldeinformationen um die Anmeldeinformationen des Prozesses handelt, von dem die Methode aufgerufen wird.  
  
## <a name="token-caches-allow-replay-using-obsolete-data"></a>Tokenzwischenspeicher ermöglichen Wiederholungen mit veralteten Daten  
 WCF verwendet die `LogonUser` Funktion der lokalen Sicherheits Autorität (Local Security Authority, LSA) zum Authentifizieren von Benutzern anhand von Benutzername und Kennwort. Da die LOGON-Funktion ein kostspieliger Vorgang ist, ermöglicht Ihnen WCF das Zwischenspeichern von Token, die authentifizierte Benutzer darstellen, um die Leistung zu verbessern. Mit dem Zwischenspeichermechanismus werden die Ergebnisse von `LogonUser` für die spätere Verwendung gespeichert. Dieser Mechanismus ist standardmäßig deaktiviert. Legen Sie die <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.CacheLogonTokens%2A>-Eigenschaft auf `true`fest, oder verwenden Sie das `cacheLogonTokens`-Attribut der [\<userNameAuthentication->](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md), um dies zu aktivieren.  
  
 Sie können eine Gültigkeitsdauer (Time to Live, TTL) für die zwischengespeicherten Token festlegen, indem Sie <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.CachedLogonTokenLifetime%2A>-Eigenschaft auf eine <xref:System.TimeSpan>-Zeitspanne festlegen oder das `cachedLogonTokenLifetime`-Attribut des `userNameAuthentication`-Elements verwenden. Der Standardwert beträgt 15 Minuten. Beachten Sie Folgendes: Solange ein Token zwischengespeichert ist, kann jeder Client, der den gleichen Benutzernamen und das gleiche Kennwort angibt, das Token nutzen, auch wenn das betreffende Benutzerkonto in Windows gelöscht oder dessen Kennwort geändert wurde. Bis die Gültigkeitsdauer abläuft und das Token aus dem Cache entfernt wird, ermöglicht WCF dem (möglicherweise böswilligen) Benutzer, sich zu authentifizieren.  
  
 So lässt sich dieses Problem abschwächen: Verkleinern Sie die Angriffsfläche, indem Sie den `cachedLogonTokenLifetime`-Wert auf die kürzeste Zeitspanne festlegen, die von den Benutzern benötigt wird.  
  
## <a name="issued-token-authorization-expiration-reset-to-large-value"></a>Ausgestellte Tokenautorisierung: Ablaufzeit auf großem Wert zurückgesetzt  
 Unter bestimmten Bedingungen kann die <xref:System.IdentityModel.Policy.AuthorizationContext.ExpirationTime%2A>-Eigenschaft des <xref:System.IdentityModel.Policy.AuthorizationContext>-Objekts auf einen unerwartet großen Wert (z.&#160;B. der Wert des <xref:System.DateTime.MaxValue>-Felds minus einem Tag oder der 20. Dezember 9999) festgelegt werden.  
  
 Dieser Fall tritt ein, wenn <xref:System.ServiceModel.WSFederationHttpBinding> und eine der vom System bereitgestellten Bindungen verwendet werden, für die ausgestellte Token als Clientanmeldeinformationen zulässig sind.  
  
 Dieser Fall tritt auch ein, wenn Sie mit einer der folgenden Methoden benutzerdefinierte Bindungen erstellen:  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenBindingElement%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForCertificateBindingElement%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForSslBindingElement%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenOverTransportBindingElement%2A>  
  
 Um dem entgegenzuwirken, muss die Autorisierungsrichtlinie die Aktion und Gültigkeitsdauer jeder Autorisierungsrichtlinie überprüfen.  
  
## <a name="the-service-uses-a-different-certificate-than-the-client-intended"></a>Der Dienst verwendet ein anderes Zertifikat, als das vom Client beabsichtigte  
 Unter bestimmten Umständen kann ein Client eine Nachricht mit einem X.509-Zertifikat signieren und den Dienst ein anderes als das vorgesehene Zertifikat abrufen lassen.  
  
 Dieser Fall kann unter den folgenden Umständen eintreten:  
  
- Der Client signiert eine Nachricht mit einem X.509-Zertifikat und fügt das X.509-Zertifikat nicht an die Nachricht an, sondern verweist über dessen Subjektschlüsselbezeichner darauf.  
  
- Auf dem Computer, auf dem der Dienst ausgeführt wird, sind zwei oder mehr Zertifikate mit dem gleichen öffentlichen Schlüssel vorhanden, die jedoch unterschiedliche Daten enthalten.  
  
- Der Dienst ruft ein Zertifikat ab, das zwar den gleichen Subjektschlüsselbezeichner aufweist, aber nicht das vom Client für die Verwendung vorgesehene Zertifikat ist. Wenn WCF die Nachricht empfängt und die Signatur überprüft, ordnet WCF die Informationen im unbeabsichtigten X. 509-Zertifikat einem Satz von Ansprüchen zu, die sich unterscheiden und möglicherweise von dem vom Client erwarteten Wert herauf gestuft werden.  
  
 Um dieses Problem zu entschärfen, verweisen Sie auf eine andere Art auf das X.509-Zertifikat, z.&#160;B. mithilfe von <xref:System.ServiceModel.Security.Tokens.X509KeyIdentifierClauseType.IssuerSerial>.  
  
## <a name="see-also"></a>Siehe auch

- [Sicherheitsüberlegungen](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)
- [Offenlegung vertraulicher Informationen](../../../../docs/framework/wcf/feature-details/information-disclosure.md)
- [Denial-of-Service-Angriffe](../../../../docs/framework/wcf/feature-details/denial-of-service.md)
- [Replayangriffe](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
- [Manipulation](../../../../docs/framework/wcf/feature-details/tampering.md)
- [Nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
