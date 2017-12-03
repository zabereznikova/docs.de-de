---
title: Angriffe durch Rechteerweiterung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- elevation of privilege [WCF]
- security [WCF], elevation of privilege
ms.assetid: 146e1c66-2a76-4ed3-98a5-fd77851a06d9
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2e44d0ecf6afb81928d83ea925f836f8b6927d97
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="elevation-of-privilege"></a>Angriffe durch Rechteerweiterung
*Ausweitung von Berechtigungen* ergibt, wenn eine Autorisierung Angreifer Berechtigungen über die ihm ursprünglich gewährten hinaus erteilen. Dies ist zum Beispiel der Fall, wenn einem Angreifer mit einem Berechtigungssatz von "Nur-Lesen"-Berechtigungen es irgendwie gelingt, "Lesen-und-Schreiben"-Berechtigungen in seinen Berechtigungssatz aufzunehmen.  
  
## <a name="trusted-sts-should-sign-saml-token-claims"></a>Vertrauenswürdige STS sollten SAML-Tokenansprüche signieren  
 Ein SAML (Security Assertions Markup Language)-Token ist ein generisches XML-Token, das den Standardtyp für ausgestellte Token darstellt. SAML-Token können von einem Sicherheitstokendienst (Security Token Service, STS) erstellt werden, der für den empfangenden Webdienst in einem typischen Datenaustausch als vertrauenswürdig gilt. SAML-Token enthalten Ansprüche in Form von Anweisungen. Ein Angreifer kann die Ansprüche aus einem gültigen Token kopieren, ein neues SAML-Token erstellen und mit einem anderen Aussteller signieren. Das Ziel ist hierbei, festzustellen, ob der Server Aussteller validiert, und wenn nicht, diese Schwäche zum Erstellen von SAML-Token auszunutzen, die Berechtigungen über die von einem vertrauenswürdigen STS beabsichtigten hinaus gewähren.  
  
 Die <xref:System.IdentityModel.Tokens.SamlAssertion>-Klasse überprüft die digitale Signatur, die in einem SAML-Token enthalten ist, und der Standard-<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> erfordert, dass SAML-Token mit einem X.509-Zertifikat signiert sind, das gültig ist, wenn <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> der <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>-Klasse auf <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust> festgelegt ist. Mithilfe des `ChainTrust`-Modus allein kann nicht bestimmt werden, ob der Aussteller des SAML-Tokens vertrauenswürdig ist. Dienste, die ein stärker granuliertes Vertrauenswürdigkeitsmodell erfordern, können entweder mithilfe von Autorisierungs- oder Durchsetzungsrichtlinien den Aussteller der erzeugten Anspruchssätze durch die Authentifizierung der Token überprüfen oder die X.509-Validierungseinstellungen für <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> verwenden, um den Satz zulässiger Signaturzertifikate einzuschränken. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md) und [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
## <a name="switching-identity-without-a-security-context"></a>Wechseln der Identität ohne Sicherheitskontext  
 Die nachfolgenden Ausführungen gelten nur für [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
 Sobald eine Verbindung zwischen einem Client und einem Server hergestellt wurde, ändert sich die Identität des Clients nur in einem Fall, nämlich wenn nach dem Öffnen des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients alle folgenden Bedingungen erfüllt sind:  
  
-   Die Verfahren, um einen Sicherheitskontext (mithilfe einer transportsicherheitssitzung oder einer nachrichtensicherheitssitzung) herzustellen abgeschaltet (<xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> -Eigenschaftensatz auf `false` im Falle von nachrichtensicherheit oder Transport nicht fähig zum Einrichten der Sicherheit Sitzungen werden in Transport Sicherheit Groß-/Kleinschreibung verwendet. HTTPS ist ein Beispiel für ein solches Transportprotokoll).  
  
-   Sie verwenden die Windows-Authentifizierung.  
  
-   Sie legen die Anmeldeinformationen nicht explizit fest.  
  
-   Sie rufen den Dienst unter dem Identitätswechsel-Sicherheitskontext auf.  
  
 Wenn diese Bedingungen erfüllt sind, kann sich die Identität ändern, die zur Authentifizierung des Clients verwendet wird (möglicherweise wird nicht die imitierte Identität, sondern die Prozessidentität verwendet), nachdem der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client geöffnet wurde. Dies geschieht, weil die Windows-Anmeldeinformationen, mit denen der Client für den Dienst authentifiziert wird, mit jeder Nachricht übermittelt werden, und die zur Authentifizierung verwendeten Anmeldeinformationen von der Windows-Identität des aktuellen Threads bezogen werden. Wenn sich die Windows-Identität des aktuellen Threads ändert (beispielsweise durch einen Identitätswechsel, mit dem ein anderer Aufrufer imitiert wird), dann können sich auch die Anmeldeinformationen ändern, die an die Nachricht angefügt sind und die zur Authentifizierung des Clients gegenüber dem Dienst verwendet werden.  
  
 Wenn das Verhalten beim Einsatz der Windows-Authentifizierung in Verbindung mit dem Identitätswechsel deterministisch sein soll, müssen Sie die Windows-Anmeldeinformationen explizit festlegen, oder Sie müssen einen Sicherheitskontext für den Dienst einrichten. Hierzu verwenden Sie eine Nachrichtensicherheitssitzung oder eine Transportsicherheitssitzung. Zum Beispiel kann der net.tcp-Transport eine Transportsicherheitssitzung bereitstellen. Darüber hinaus dürfen Sie in Aufrufen des Diensts nur die synchrone Version von Clientvorgängen verwenden. Wenn Sie einen Nachrichtensicherheitskontext einrichten, sollten Sie die Verbindung mit dem Dienst nicht länger als den für die Sitzung konfigurierten Erneuerungszeitraum geöffnet halten, weil sich die Identität auch während des Sitzungserneuerungsprozesses ändern kann.  
  
### <a name="credentials-capture"></a>Aufzeichnung der Anmeldeinformationen  
 Die folgenden Ausführungen gelten für [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] und nachfolgende Versionen.  
  
 Die vom Client oder Dienst verwendeten Anmeldeinformationen basieren auf dem aktuellen Kontextthread. Die Anmeldeinformationen werden durch einen Aufruf der `Open`-Methode (bzw. `BeginOpen` für asynchrone Aufrufe) des Clients oder Diensts bezogen. Sowohl für die <xref:System.ServiceModel.ServiceHost>-Klasse als auch für die <xref:System.ServiceModel.ClientBase%601>-Klasse gilt, dass die `Open`-Methode bzw. die `BeginOpen`-Methode von der <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>-Methode bzw. der <xref:System.ServiceModel.Channels.CommunicationObject.BeginOpen%2A>-Methode der <xref:System.ServiceModel.Channels.CommunicationObject>-Klasse abgeleitet ist.  
  
> [!NOTE]
>  Bei Verwendung der `BeginOpen`-Methode kann nicht garantiert werden, dass es sich bei den aufgezeichneten Anmeldeinformationen um die Anmeldeinformationen des Prozesses handelt, von dem die Methode aufgerufen wird.  
  
## <a name="token-caches-allow-replay-using-obsolete-data"></a>Tokenzwischenspeicher ermöglichen Wiederholungen mit veralteten Daten  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die `LogonUser`-Funktion der lokalen Sicherheitsinstanz (Local Security Authority, LSA), um Benutzer durch Benutzernamen und Kennwort zu authentifizieren. Da die Anmeldung ein aufwändiger Vorgang ist, lässt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Zwischenspeicherung von Token zu, die authentifizierte Benutzer darstellen, um die Ausführungsgeschwindigkeit zu erhöhen. Mit dem Zwischenspeichermechanismus werden die Ergebnisse von `LogonUser` für die spätere Verwendung gespeichert. Dieser Mechanismus ist standardmäßig deaktiviert. Legen Sie zum Aktivieren der <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.CacheLogonTokens%2A> Eigenschaft, um `true`, oder verwenden Sie die `cacheLogonTokens` Attribut des der [ \<UserNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md).  
  
 Sie können eine Gültigkeitsdauer (Time to Live, TTL) für die zwischengespeicherten Token festlegen, indem Sie <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.CachedLogonTokenLifetime%2A>-Eigenschaft auf eine <xref:System.TimeSpan>-Zeitspanne festlegen oder das `cachedLogonTokenLifetime`-Attribut des `userNameAuthentication`-Elements verwenden. Der Standardwert beträgt 15 Minuten. Beachten Sie Folgendes: Solange ein Token zwischengespeichert ist, kann jeder Client, der den gleichen Benutzernamen und das gleiche Kennwort angibt, das Token nutzen, auch wenn das betreffende Benutzerkonto in Windows gelöscht oder dessen Kennwort geändert wurde. Bis die Gültigkeitsdauer abgelaufen ist und das Token aus dem Zwischenspeicher entfernt wurde, lässt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Authentifizierung des (möglicherweise böswilligen) Benutzers zu.  
  
 So lässt sich dieses Problem abschwächen: Verkleinern Sie die Angriffsfläche, indem Sie den `cachedLogonTokenLifetime`-Wert auf die kürzeste Zeitspanne festlegen, die von den Benutzern benötigt wird.  
  
## <a name="issued-token-authorization-expiration-reset-to-large-value"></a>Ausgestellte Tokenautorisierung: Ablaufzeit auf großem Wert zurückgesetzt  
 Unter bestimmten Bedingungen kann die <xref:System.IdentityModel.Policy.AuthorizationContext.ExpirationTime%2A>-Eigenschaft des <xref:System.IdentityModel.Policy.AuthorizationContext>-Objekts auf einen unerwartet großen Wert (z.&#160;B. der Wert des <xref:System.DateTime.MaxValue>-Felds minus einem Tag oder der 20. Dezember 9999) festgelegt werden.  
  
 Dieser Fall tritt ein, wenn <xref:System.ServiceModel.WSFederationHttpBinding> und eine der vom System bereitgestellten Bindungen verwendet werden, für die ausgestellte Token als Clientanmeldeinformationen zulässig sind.  
  
 Dieser Fall tritt auch ein, wenn Sie mit einer der folgenden Methoden benutzerdefinierte Bindungen erstellen:  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenBindingElement%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForCertificateBindingElement%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForSslBindingElement%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenOverTransportBindingElement%2A>  
  
 Um dem entgegenzuwirken, muss die Autorisierungsrichtlinie die Aktion und Gültigkeitsdauer jeder Autorisierungsrichtlinie überprüfen.  
  
## <a name="the-service-uses-a-different-certificate-than-the-client-intended"></a>Der Dienst verwendet ein anderes Zertifikat, als das vom Client beabsichtigte  
 Unter bestimmten Umständen kann ein Client eine Nachricht mit einem X.509-Zertifikat signieren und den Dienst ein anderes als das vorgesehene Zertifikat abrufen lassen.  
  
 Dieser Fall kann unter den folgenden Umständen eintreten:  
  
-   Der Client signiert eine Nachricht mit einem X.509-Zertifikat und fügt das X.509-Zertifikat nicht an die Nachricht an, sondern verweist über dessen Subjektschlüsselbezeichner darauf.  
  
-   Auf dem Computer, auf dem der Dienst ausgeführt wird, sind zwei oder mehr Zertifikate mit dem gleichen öffentlichen Schlüssel vorhanden, die jedoch unterschiedliche Daten enthalten.  
  
-   Der Dienst ruft ein Zertifikat ab, das zwar den gleichen Subjektschlüsselbezeichner aufweist, aber nicht das vom Client für die Verwendung vorgesehene Zertifikat ist. Wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Nachricht empfängt und die Signatur verifiziert, ordnet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die im unbeabsichtigten X.509-Zertifikat enthaltenen Informationen einem Satz von Ansprüchen zu, der sich von dem vom Client erwarteten Satz unterscheidet und möglicherweise umfangreicher ist.  
  
 Um dieses Problem zu entschärfen, verweisen Sie auf eine andere Art auf das X.509-Zertifikat, z.&#160;B. mithilfe von <xref:System.ServiceModel.Security.Tokens.X509KeyIdentifierClauseType.IssuerSerial>.  
  
## <a name="see-also"></a>Siehe auch  
 [Überlegungen zur Sicherheit](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Offenlegung von Informationen](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [Denial of Service](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [Replay-Angriffe](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 [Manipulation](../../../../docs/framework/wcf/feature-details/tampering.md)  
 [Nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
