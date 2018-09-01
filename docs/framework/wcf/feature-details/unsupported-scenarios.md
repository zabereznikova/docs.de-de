---
title: Nicht unterstützte Szenarien
ms.date: 03/30/2017
ms.assetid: 72027d0f-146d-40c5-9d72-e94392c8bb40
ms.openlocfilehash: 6c0ee061f754e85244bffdc06cbe23aee68d2222
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388529"
---
# <a name="unsupported-scenarios"></a>Nicht unterstützte Szenarien
Aus verschiedenen Gründen unterstützt der Windows Communication Foundation (WCF) einige bestimmte Sicherheitsszenarien nicht. Z. B. [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition die SSPI- oder Kerberos-Authentifizierungsprotokolle nicht implementiert, und daher WCF unterstützt nicht das Ausführen eines Diensts mit Windows-Authentifizierung auf dieser Plattform. Andere Authentifizierungsmechanismen, wie z. B. Benutzername/Kennwort und die HTTP/HTTPS-integrierte Authentifizierung werden unterstützt, wenn WCF unter Windows XP Home Edition ausgeführt wird.  
  
## <a name="impersonation-scenarios"></a>Identitätswechselszenarien  
  
### <a name="impersonated-identity-might-not-flow-when-clients-make-asynchronous-calls"></a>Keine Weitergabe der gewechselten Identität bei asynchronen Aufrufen am Client  
 Wenn ein WCF-Client unter Verwendung der Windows-Authentifizierung mit einem Identitätswechsel asynchrone Aufrufe eines WCF-Dienstes ausführt, kann die Authentifizierung mit der Identität des Clientprozesses anstelle der gewechselten Identität erfolgen.  
  
### <a name="windows-xp-and-secure-context-token-cookie-enabled"></a>Windows XP und Sicherheitskontexttoken-Cookie aktiviert  
 WCF unterstützt keinen Identitätswechsel und <xref:System.InvalidOperationException> wird ausgelöst, wenn die folgenden Bedingungen erfüllt sein:  
  
-   Das Betriebssystem ist [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
-   Der Authentifizierungsmodus ruft eine Windows-Identität hervor.  
  
-   Die <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>-Eigenschaft von <xref:System.ServiceModel.OperationBehaviorAttribute> wird auf <xref:System.ServiceModel.ImpersonationOption.Required> festgelegt.  
  
-   Ein statusbasiertes Sicherheitszustandskontexttoken (SCT) wird erstellt. (Standardmäßig ist die Erstellung deaktiviert.)  
  
 Das statusbasierte SCT kann nur mit einer benutzerdefinierten Bindung erstellt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie ein Token für den Sicherheitskontext für eine Sicherheitssitzung](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).) Im Code wird das Token aktiviert, indem ein Sicherheitsbindungselement erstellt wird (<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> oder <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>), wobei die <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%28System.Boolean%29?displayProperty=nameWithType>-Methode oder die <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%28System.ServiceModel.Channels.SecurityBindingElement%2CSystem.Boolean%29?displayProperty=nameWithType>-Methode verwendet wird und der `requireCancellation`-Parameter auf `false` festgelegt wird. Der Parameter bezieht sich auf die Zwischenspeicherung des SCT. Wenn Sie den Wert auf `false` festlegen, wird die statusbasierte SCT-Funktion aktiviert.  
  
 Alternativ in der Konfiguration der Token aktiviert, durch das Erstellen einer <`customBinding`>, Hinzufügen einer <`security`> Element, und die Einstellung der `authenticationMode` SecureConversation Attribut und die `requireSecurityContextCancellation` -Attribut auf `true`.  
  
> [!NOTE]
>  Die zuvor genannten Anforderungen sind spezifisch. Beispielsweise erstellt das <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> ein Bindungselement, das zu einer Windows-Identität führt, wobei aber kein SCT eingerichtet wird. Sie können es daher mit der `Required`-Option unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] verwenden.  
  
### <a name="possible-aspnet-conflict"></a>Möglicher ASP.NET-Konflikt  
 WCF und [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] können sowohl Identitätswechsel aktivieren oder deaktivieren. Wenn [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hostet eine WCF-Anwendung ist möglicherweise ein Konflikt zwischen dem WCF vorhanden und [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Konfigurationseinstellungen. Bei einem Konflikt hat die WCF-Einstellung Vorrang, es sei denn, die <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> -Eigenschaftensatz auf <xref:System.ServiceModel.ImpersonationOption.NotAllowed>, in diesem Fall die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -identitätswechseleinstellung Vorrang.  
  
### <a name="assembly-loads-may-fail-under-impersonation"></a>Assembly-Ladevorgänge können beim Identitätswechsel fehlschlagen  
 Wenn der Identitätswechselkontext keine Zugriffsberechtigungen zum Laden einer Assembly hat und es das erste Mal ist, dass die Common Language Runtime (CLR) versucht, die Assembly für diese Anwendungsdomäne zu laden, speichert die <xref:System.AppDomain> den Fehler zwischen. Nachfolgende Versuche, diese Assembly(s) zu laden, schlagen fehl, selbst nach dem Zurücksetzen des Identitätswechsels und sogar wenn der zurückgesetzte Kontext die Zugriffsberechtigungen hat, die Assembly zu laden. Die Ursache dafür ist, dass die CLR nach der Änderung des Benutzerkontextes keinen weiteren Ladeversuch unternimmt. Sie müssen die Anwendungsdomäne neu starten, um nach dem Fehler wiederhergestellt zu werden.  
  
> [!NOTE]
>  Der Standardwert für die <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>-Eigenschaft der <xref:System.ServiceModel.Security.WindowsClientCredential>-Klasse ist <xref:System.Security.Principal.TokenImpersonationLevel.Identification>. In den meisten Fällen hat ein Identitätswechsel auf Identifizierungsebene nicht die Berechtigung, zusätzliche Assemblys zu laden. Dies ist der Standardwert. Es handelt sich somit um eine sehr übliche Bedingung, derer Sie sich bewusst sein sollten. Der Identitätswechsel auf Identifizierungsebene kann auch dann auftreten, wenn der Identitätswechselvorgang nicht die `SeImpersonate`-Berechtigung hat. Weitere Informationen finden Sie unter [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
### <a name="delegation-requires-credential-negotiation"></a>Delegierung erfordert eine Anmeldeinformationen-Aushandlung  
 Um das Kerberos-Authentifizierungsprotokoll mit Delegierung zu verwenden, müssen Sie das Kerberos-Protokoll mit Anmeldeinformationen-Aushandlung (mitunter als bilaterales oder mehrstufiges Kerberos bezeichnet) implementieren. Wenn Sie die Kerberos-Authentifizierung ohne Anmeldeinformationen-Aushandlung (mitunter als One-Shot-Kerberos bezeichnet) implementieren, wird eine Ausnahme ausgelöst. Weitere Informationen dazu, wie Sie die Anmeldeinformationen-Aushandlung zu implementieren, finden Sie unter [Debuggen von Windows-Authentifizierungsfehlern](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md).  
  
## <a name="cryptography"></a>Kryptografie  
  
### <a name="sha-256-supported-only-for-symmetric-key-usages"></a>Unterstützt HA-256 nur für den Einsatz mit symmetrischen Schlüsseln  
 WCF unterstützt eine Vielzahl von Verschlüsselung und Signatur Digest-erstellungsalgorithmen, die Sie angeben können, mit der algorithmussuite in den vom System bereitgestellten Bindungen. Zur Verbesserung der Sicherheit unterstützt WCF Secure Hash Algorithm (SHA) 2-Algorithmen, insbesondere SHA-256, für die Erstellung von Signatur-Hashwert-Hashes. Dieses Release unterstützt SHA-256 nur für Einsätze mit symmetrischen Schlüsseln, z. B. Kerberos-Schlüssel und wenn kein X.509-Zertifikat zum Signieren der Nachricht verwendet wird. WCF unterstützt keine RSA-Signaturen (in x. 509-Zertifikaten) mit SHA-256-Hash aufgrund der derzeitigen fehlenden Supports für RSA-SHA256, in der [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
### <a name="fips-compliant-sha-256-hashes-not-supported"></a>FIPS-kompatible SHA-256-Hashes werden nicht unterstützt  
 WCF unterstützt keine SHA-256-FIPS-kompatiblen Hashes, sodass algorithmussuites, die SHA-256 Verwenden von WCF auf Systemen nicht unterstützt werden, wenn für die Verwendung von FIPS-konformen Algorithmus erforderlich ist.  
  
### <a name="fips-compliant-algorithms-may-fail-if-registry-is-edited"></a>FIPS-kompatible Algorithmen schlagen ggf. fehl, wenn die Registrierung bearbeitet wird  
 Sie können Federal Information Processing Standards (FIPS)-kompatible Algorithmen aktivieren und deaktivieren, indem Sie das Snap-In Lokale Sicherheitseinstellungen der Microsoft Management Console (MMC) verwenden. Sie können auch auf die Einstellung in der Registrierung zugreifen. Beachten Sie jedoch, dass WCF nicht unterstützt, mithilfe der Registrierung zum Zurücksetzen der Einstellung. Wenn ein anderer Wert als 1 oder 0 festgelegt wurde, können zwischen CLR und dem Betriebssystem inkonsistente Ergebnisse auftreten.  
  
### <a name="fips-compliant-aes-encryption-limitation"></a>FIPS-kompatible AES-Verschlüsselungseinschränkungen  
 Die FIPS-kompatible AES-Verschlüsselung funktioniert nicht bei Duplexrückrufen unter dem Identitätswechsel auf Identifizierungsebene.  
  
### <a name="cngksp-certificates"></a>CNG/KSP-Zertifikate  
 *Kryptografie-API: Next Generation (CNG)* ist der langfristige Ersatz für CryptoAPI. Diese API ist verfügbar in nicht verwaltetem Code auf [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)] und höheren Windows-Versionen.  
  
 .NET Framework 4.6.1 und früheren Versionen unterstützen nicht diese Zertifikate, da sie die alte CryptoAPI verwenden, um CNG/KSP-Zertifikate zu verarbeiten. Die Verwendung dieser Zertifikate mit .NET Framework 4.6.1 und früheren Versionen löst eine Ausnahme aus.  
  
 Ob KSP von einem Zertifikat verwendet wird, kann auf zwei Arten ermittelt werden:  
  
-   Führen Sie `p/invoke` für die `CertGetCertificateContextProperty` aus, und überprüfen Sie `dwProvType` in der zurückgegebenen `CertGetCertificateContextProperty`.  
  
-   Verwenden der `certutil` Befehl über die Befehlszeile zum Abfragen von Zertifikaten. Weitere Informationen finden Sie unter [Aufgaben von Certutil für die Problembehandlung bei Zertifikaten](https://go.microsoft.com/fwlink/?LinkId=120056).  
  
## <a name="message-security-fails-if-using-aspnet-impersonation-and-aspnet-compatibility-is-required"></a>Nachrichtensicherheit schlägt fehlt, wenn der ASP.NET-Identitätswechsel verwendet wird und die ASP.NET-Kompatibilität erforderlich ist  
 WCF unterstützt nicht die folgende Kombination von Einstellungen, da sie auftreten der Clientauthentifizierung verhindern können:  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Identitätswechsel ist aktiviert. Dies erfolgt in der Datei "Web.config" durch Festlegen der `impersonate` Attribut der <`identity`>-Element `true`.  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] im Kompatibilitätsmodus ist aktiviert, indem die `aspNetCompatibilityEnabled` Attribut der [ \<ServiceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) zu `true`.  
  
-   Die Nachrichtenmodussicherheit wird verwendet.  
  
 Sie können alternativ auch den [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Kompatibilitätsmodus deaktivieren. Oder, wenn Sie die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Kompatibilitätsmodus erforderlich ist, deaktivieren Sie die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Identitätswechsel feature aus, und verwenden Sie stattdessen die von WCF bereitgestellter Identitätswechsel. Weitere Informationen finden Sie unter [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## <a name="ipv6-literal-address-failure"></a>IPv6-Literal-Adressfehler  
 Bei Sicherheitsanforderungen tritt ein Fehler auf, wenn sich Client und Dienst auf dem gleichen Computer befinden und für den Dienst IPv6-Literaladressen verwendet werden.  
  
 IPv6-Literal-Adressen funktionieren, wenn der Dienst und der Client sich auf unterschiedlichen Computern befinden.  
  
## <a name="wsdl-retrieval-failures-with-federated-trust"></a>WSDL-Abruffehler bei Verbundvertrauen  
 WCF erfordert genau ein WSDL-Dokument für jeden Knoten in der Vertrauenskette des Verbunds. Achten Sie darauf, beim Angeben von Endpunkten keine Schleife einzurichten. Eine Schleife kann beispielsweise bei Verwendung eines WSDL-Downloads von Vertrauensketten des Verbunds entstehen, wenn das gleiche WSDL-Dokument mehrere Links enthält. Ein häufig auftretendes Szenario für dieses Problem ist ein Verbunddienst, bei dem sich der Sicherheitstokenserver und der Dienst im gleichen ServiceHost befinden.  
  
 Ein Beispiel für diese Situation ist ein Dienst mit den folgenden drei Endpunktadressen:  
  
-   http://localhost/CalculatorService/service (der Dienst)  
  
-   http://localhost/CalculatorService/issue_ticket (der STS)  
  
-   http://localhost/CalculatorService/mex (der Metadatenendpunkt)  
  
 Dadurch wird eine Ausnahme ausgelöst.  
  
 Verlegen Sie den `issue_ticket`-Endpunkt, damit dieses Szenario funktioniert.  
  
## <a name="wsdl-import-attributes-can-be-lost"></a>WSDL-Importattribute können verloren werden  
 WCF kann die Attribute eines `<wst:Claims>`-Elements in einer `RST`-Vorlage beim Ausführen eines WSDL-Imports nicht nachverfolgen. Dieses Problem tritt im Zuge eines WSDL-Importvorgangs auf, wenn `<Claims>` direkt in`WSFederationHttpBinding.Security.Message.TokenRequestParameters` oder in`IssuedSecurityTokenRequestParameters.AdditionalRequestParameters` und nicht unter direkter Verwendung der Anspruchstypauflistungen angegeben werden.  Da die Attribute beim Importieren verloren gehen, verläuft der Roundtrip der Bindung durch WSDL nicht ordnungsgemäß, und die Bindung ist auf der Clientseite ungültig.  
  
 Ändern Sie nach Abschluss des Importvorgangs die Bindung direkt auf dem Client, um dieses Problem zu korrigieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Sicherheitsüberlegungen](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Offenlegung vertraulicher Informationen](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [Erhöhen der Berechtigungen](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [Denial-of-Service-Angriffe](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [Manipulation](../../../../docs/framework/wcf/feature-details/tampering.md)  
 [Replayangriffe](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
