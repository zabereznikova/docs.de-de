---
title: "Nicht unterst&#252;tzte Szenarien | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 72027d0f-146d-40c5-9d72-e94392c8bb40
caps.latest.revision: 43
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 39
---
# Nicht unterst&#252;tzte Szenarien
Aus verschiedenen Gründen unterstützt [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] einige bestimmte Sicherheitsszenarien nicht. Beispielsweise implementiert [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition die SSPI\- oder Kerberos\-Authentifizierungsprotokolle nicht, weshalb [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] auch die Ausführung eines Diensts mit der Windows\-Authentifizierung auf dieser Plattform nicht unterstützt. Andere Authentifizierungsmechanismen, beispielsweise Benutzername\/Kennwort und die HTTP\/HTTPS\-integrierte Authentifizierung, werden beim Ausführen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unter Windows&\#160;XP Home Edition unterstützt.  
  
## Identitätswechselszenarien  
  
### Keine Weitergabe der gewechselten Identität bei asynchronen Aufrufen am Client  
 Wenn ein WCF\-Client unter Verwendung der Windows\-Authentifizierung mit einem Identitätswechsel asynchrone Aufrufe eines WCF\-Dienstes ausführt, kann die Authentifizierung mit der Identität des Clientprozesses anstelle der gewechselten Identität erfolgen.  
  
### Windows XP und Sicherheitskontexttoken\-Cookie aktiviert  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt keinen Identitätswechsel, und unter den folgenden Bedingungen wird eine <xref:System.InvalidOperationException> ausgelöst:  
  
-   Das Betriebssystem ist [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
-   Der Authentifizierungsmodus ruft eine Windows\-Identität hervor.  
  
-   Die <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>\-Eigenschaft von <xref:System.ServiceModel.OperationBehaviorAttribute> wird auf <xref:System.ServiceModel.ImpersonationOption> festgelegt.  
  
-   Ein statusbasiertes Sicherheitszustandskontexttoken \(SCT\) wird erstellt. \(Standardmäßig ist die Erstellung deaktiviert.\)  
  
 Das statusbasierte SCT kann nur mit einer benutzerdefinierten Bindung erstellt werden.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Vorgehensweise: Erstellen eines Tokens für den Sicherheitskontext einer sicheren Sitzung](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).\) Im Code wird das Token aktiviert, indem ein Sicherheitsbindungselement erstellt wird \(<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> oder <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>\), wobei die <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%28System.Boolean%29?displayProperty=fullName>\-Methode oder die <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%28System.ServiceModel.Channels.SecurityBindingElement%2CSystem.Boolean%29?displayProperty=fullName>\-Methode verwendet wird und der `requireCancellation`\-Parameter auf `false` festgelegt wird. Der Parameter bezieht sich auf die Zwischenspeicherung des SCT. Wenn Sie den Wert auf `false` festlegen, wird die statusbasierte SCT\-Funktion aktiviert.  
  
 Alternativ wird das Token in der Konfiguration aktiviert, indem eine \<`customBinding`\> erstellt, ein \<`security`\>\-Element hinzugefügt, das `authenticationMode`\-Attribut auf "SecureConversation" festgelegt und das `requireSecurityContextCancellation`\-Attribut auf `true` festgelegt wird.  
  
> [!NOTE]
>  Die zuvor genannten Anforderungen sind spezifisch. Beispielsweise erstellt das <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> ein Bindungselement, das zu einer Windows\-Identität führt, wobei aber kein SCT eingerichtet wird. Sie können es daher mit der `Required`\-Option unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] verwenden.  
  
### Möglicher ASP.NET\-Konflikt  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] können beide den Identitätswechsel aktivieren oder deaktivieren. Wenn [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Host für eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendung ist, kann ein Konflikt zwischen der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Konfigurationseinstellung und der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Konfigurationseinstellung auftreten. Bei einem Konflikt hat die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Einstellung Vorrang, es sei denn die <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>\-Eigenschaft ist auf <xref:System.ServiceModel.ImpersonationOption> festgelegt, wobei in diesem Fall die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Identitätswechseleinstellung Vorrang hat.  
  
### Assembly\-Ladevorgänge können beim Identitätswechsel fehlschlagen  
 Wenn der Identitätswechselkontext keine Zugriffsberechtigungen zum Laden einer Assembly hat und es das erste Mal ist, dass die Common Language Runtime \(CLR\) versucht, die Assembly für diese Anwendungsdomäne zu laden, speichert die <xref:System.AppDomain> den Fehler zwischen. Nachfolgende Versuche, diese Assembly\(s\) zu laden, schlagen fehl, selbst nach dem Zurücksetzen des Identitätswechsels und sogar wenn der zurückgesetzte Kontext die Zugriffsberechtigungen hat, die Assembly zu laden. Die Ursache dafür ist, dass die CLR nach der Änderung des Benutzerkontextes keinen weiteren Ladeversuch unternimmt. Sie müssen die Anwendungsdomäne neu starten, um nach dem Fehler wiederhergestellt zu werden.  
  
> [!NOTE]
>  Der Standardwert für die <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>\-Eigenschaft der <xref:System.ServiceModel.Security.WindowsClientCredential>\-Klasse ist <xref:System.Security.Principal.TokenImpersonationLevel>. In den meisten Fällen hat ein Identitätswechsel auf Identifizierungsebene nicht die Berechtigung, zusätzliche Assemblys zu laden. Dies ist der Standardwert. Es handelt sich somit um eine sehr übliche Bedingung, derer Sie sich bewusst sein sollten. Der Identitätswechsel auf Identifizierungsebene kann auch dann auftreten, wenn der Identitätswechselvorgang nicht die `SeImpersonate`\-Berechtigung hat.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
### Delegierung erfordert eine Anmeldeinformationen\-Aushandlung  
 Um das Kerberos\-Authentifizierungsprotokoll mit Delegierung zu verwenden, müssen Sie das Kerberos\-Protokoll mit Anmeldeinformationen\-Aushandlung \(mitunter als bilaterales oder mehrstufiges Kerberos bezeichnet\) implementieren. Wenn Sie die Kerberos\-Authentifizierung ohne Anmeldeinformationen\-Aushandlung \(mitunter als One\-Shot\-Kerberos bezeichnet\) implementieren, wird eine Ausnahme ausgelöst.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Implementieren der Anmeldeinformationen\-Aushandlung finden Sie unter [Debuggen von Windows\-Authentifizierungsfehlern](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md).  
  
## Kryptografie  
  
### Unterstützt HA\-256 nur für den Einsatz mit symmetrischen Schlüsseln  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt mehrere Verschlüsselungsalgorithmen und Signatur\-Digest\-Erstellungsalgorithmen, die Sie mit der Algorithmussuite in den vom System bereitgestellten Bindungen festlegen können. Für eine höhere Sicherheit unterstützt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Secure Hash Algorithm \(SHA\) 2\-Algorithmen, vor allem SHA\-256, für die Erstellung von Signatur\-Digest\-Hashes. Diese Version unterstützt SHA\-256 nur für Einsätze mit symmetrischen Schlüsseln, z. B. Kerberos\-Schlüssel und wenn kein X.509\-Zertifikat zum Signieren der Nachricht verwendet wird.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt keine RSA\-Signaturen \(in X.509\-Zertifikaten\) mit SHA\-256\-Hash aufgrund des derzeit fehlenden Supports für RSA\-SHA256 in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
### FIPS\-kompatible SHA\-256\-Hashes werden nicht unterstützt  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt keine SHA256\-FIPS\-kompatiblen Hashes, sodass Algorithmussuites, die SHA256 verwenden, von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nicht auf Systemen unterstützt werden, bei denen der Einsatz von FIPS\-kompatiblen Algorithmen erforderlich ist.  
  
### FIPS\-kompatible Algorithmen schlagen ggf. fehl, wenn die Registrierung bearbeitet wird  
 Sie können Federal Information Processing Standards \(FIPS\)\-kompatible Algorithmen aktivieren und deaktivieren, indem Sie das Snap\-In Lokale Sicherheitseinstellungen der Microsoft Management Console \(MMC\) verwenden. Sie können auch auf die Einstellung in der Registrierung zugreifen. Beachten Sie jedoch, dass [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nicht den Einsatz der Registrierung zum Zurücksetzen der Einstellung unterstützt. Wenn ein anderer Wert als 1 oder 0 festgelegt wurde, können zwischen CLR und dem Betriebssystem inkonsistente Ergebnisse auftreten.  
  
### FIPS\-kompatible AES\-Verschlüsselungseinschränkungen  
 Die FIPS\-kompatible AES\-Verschlüsselung funktioniert nicht bei Duplexrückrufen unter dem Identitätswechsel auf Identifizierungsebene.  
  
### CNG\-\/KSP\-Zertifikate unter Windows Server&\#160;2008  
 *Kryptografie\-API: Next Generation \(CNG\)* ist der langfristige Ersatz für die CryptoAPI. Diese API ist in nicht verwaltetem Code unter [!INCLUDE[wv](../../../../includes/wv-md.md)] und unter [!INCLUDE[lserver](../../../../includes/lserver-md.md)] verfügbar.  
  
 Unter älteren Plattformen \([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)]\) erkennt .NET Framework&\#160;2.0 dieses Protokoll nicht und verwendet stattdessen die ältere *CryptoAPI* für die Behandlung von CNG\-\/KSP\-Zertifikaten. Unter [!INCLUDE[lserver](../../../../includes/lserver-md.md)] und [!INCLUDE[wv](../../../../includes/wv-md.md)] unterstützt .NET Framework&\#160;3.5 diese Zertifikate nicht: ihre Verwendung verursacht eine Ausnahme.  
  
 Ob KSP von einem Zertifikat verwendet wird, kann auf zwei Arten ermittelt werden:  
  
-   Führen Sie `p/invoke` für die `CertGetCertificateContextProperty` aus, und überprüfen Sie `dwProvType` in der zurückgegebenen `CertGetCertificateContextProperty`.  
  
-   Verwenden Sie zum Abfragen von Zertifikaten den `certutil`\-Befehl in der Eingabeaufforderung.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Aufgaben von Certutil für die Problembehandlung bei Zertifikaten](http://go.microsoft.com/fwlink/?LinkId=120056).  
  
## Nachrichtensicherheit schlägt fehlt, wenn der ASP.NET\-Identitätswechsel verwendet wird und die ASP.NET\-Kompatibilität erforderlich ist  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt die folgende Kombination an Einstellungen, da sie die Durchführung der Clientauthentifizierung verhindern können:  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Identitätswechsel ist aktiviert. Dies wird in der Web.config\-Datei durchgeführt, indem das `impersonate`\-Attribut des \<`identity`\>\-Elements auf `true` festgelegt wird.  
  
-   Der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Kompatibilitätsmodus wird aktiviert, indem das `aspNetCompatibilityEnabled`\-Attribut des [\<serviceHostingEnvironment\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) auf `true` festgelegt wird.  
  
-   Die Nachrichtenmodussicherheit wird verwendet.  
  
 Sie können alternativ auch den [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Kompatibilitätsmodus deaktivieren. Oder wenn der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Kompatibilitätsmodus erforderlich ist, können Sie die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Identitätswechselfunktion deaktivieren und stattdessen den von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten Identitätswechsel verwenden.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## IPv6\-Literal\-Adressfehler  
 Bei Sicherheitsanforderungen tritt ein Fehler auf, wenn sich Client und Dienst auf dem gleichen Computer befinden und für den Dienst IPv6\-Literaladressen verwendet werden.  
  
 IPv6\-Literal\-Adressen funktionieren, wenn der Dienst und der Client sich auf unterschiedlichen Computern befinden.  
  
## WSDL\-Abruffehler bei Verbundvertrauen  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erfordert für jeden Knoten in der Vertrauenskette des Verbunds genau ein WSDL\-Dokument. Achten Sie darauf, beim Angeben von Endpunkten keine Schleife einzurichten. Eine Schleife kann beispielsweise bei Verwendung eines WSDL\-Downloads von Vertrauensketten des Verbunds entstehen, wenn das gleiche WSDL\-Dokument mehrere Links enthält. Ein häufig auftretendes Szenario für dieses Problem ist ein Verbunddienst, bei dem sich der Sicherheitstokenserver und der Dienst im gleichen ServiceHost befinden.  
  
 Ein Beispiel für diese Situation ist ein Dienst mit den folgenden drei Endpunktadressen:  
  
-   "http:\/\/localhost\/CalculatorService\/service" \(der Dienst\)  
  
-   "http:\/\/localhost\/CalculatorService\/issue\_ticket" \(der STS\)  
  
-   "http:\/\/localhost\/CalculatorService\/mex" \(der Metadatenendpunkt\)  
  
 Dadurch wird eine Ausnahme ausgelöst.  
  
 Verlegen Sie den `issue_ticket`\-Endpunkt, damit dieses Szenario funktioniert.  
  
## WSDL\-Importattribute können verloren werden  
 WCF kann die Attribute eines `<wst:Claims>`\-Elements in einer `RST`\-Vorlage beim Ausführen eines WSDL\-Imports nicht nachverfolgen. Dieses Problem tritt im Zuge eines WSDL\-Importvorgangs auf, wenn `<Claims>` direkt in `WSFederationHttpBinding.Security.Message.TokenRequestParameters` oder in `IssuedSecurityTokenRequestParameters.AdditionalRequestParameters` und nicht unter direkter Verwendung der Anspruchstypauflistungen angegeben werden.  Da die Attribute beim Importieren verloren gehen, verläuft der Roundtrip der Bindung durch WSDL nicht ordnungsgemäß, und die Bindung ist auf der Clientseite ungültig.  
  
 Ändern Sie nach Abschluss des Importvorgangs die Bindung direkt auf dem Client, um dieses Problem zu korrigieren.  
  
## Siehe auch  
 [Sicherheitsüberlegungen](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)   
 [Veröffentlichung von Informationen](../../../../docs/framework/wcf/feature-details/information-disclosure.md)   
 [Ausweitung von Berechtigungen](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)   
 [Dienstverweigerung \(Denial of Service\)](../../../../docs/framework/wcf/feature-details/denial-of-service.md)   
 [Verfälschungen](../../../../docs/framework/wcf/feature-details/tampering.md)   
 [Wiederholungsangriffe](../../../../docs/framework/wcf/feature-details/replay-attacks.md)