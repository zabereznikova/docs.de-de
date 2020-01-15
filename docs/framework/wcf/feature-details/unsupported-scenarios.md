---
title: Nicht unterstützte Szenarien
ms.date: 03/30/2017
ms.assetid: 72027d0f-146d-40c5-9d72-e94392c8bb40
ms.openlocfilehash: a963b46d22f2103cddcc8fd080feefc39070690c
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901268"
---
# <a name="unsupported-scenarios"></a>Nicht unterstützte Szenarien

Aus verschiedenen Gründen unterstützt Windows Communication Foundation (WCF) einige bestimmte Sicherheits Szenarios nicht. Beispielsweise implementiert [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition die SSPI-oder Kerberos-Authentifizierungsprotokolle nicht, weshalb WCF das Ausführen eines Dienstanbieter mit Windows-Authentifizierung auf dieser Plattform nicht unterstützt. Andere Authentifizierungsmechanismen, z. b. Benutzername/Kennwort und integrierte HTTP/HTTPS-Authentifizierung, werden bei der Ausführung von WCF unter Windows XP Home Edition unterstützt.

## <a name="impersonation-scenarios"></a>Identitätswechsel Szenarien

### <a name="impersonated-identity-might-not-flow-when-clients-make-asynchronous-calls"></a>Identität mit Identitätswechsel wird bei asynchronen Aufrufen von Clients möglicherweise nicht durchgeführt
 Wenn ein WCF-Client unter Verwendung der Windows-Authentifizierung mit einem Identitätswechsel asynchrone Aufrufe eines WCF-Dienstes ausführt, kann die Authentifizierung mit der Identität des Clientprozesses anstelle der gewechselten Identität erfolgen.

### <a name="windows-xp-and-secure-context-token-cookie-enabled"></a>Windows XP und sicheres Kontext Token-Cookie aktiviert

WCF unterstützt keinen Identitätswechsel, und es wird eine <xref:System.InvalidOperationException> ausgelöst, wenn die folgenden Bedingungen erfüllt sind:

- Das Betriebssystem ist [!INCLUDE[wxp](../../../../includes/wxp-md.md)].

- Der Authentifizierungsmodus ruft eine Windows-Identität hervor.

- Die <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>-Eigenschaft von <xref:System.ServiceModel.OperationBehaviorAttribute> wird auf <xref:System.ServiceModel.ImpersonationOption.Required> festgelegt.

- Ein statusbasiertes Sicherheitszustandskontexttoken (SCT) wird erstellt. (Standardmäßig ist die Erstellung deaktiviert.)

 Das statusbasierte SCT kann nur mit einer benutzerdefinierten Bindung erstellt werden. Weitere Informationen finden Sie unter Vorgehens [Weise: Erstellen eines Sicherheitskontext Tokens für eine sichere Sitzung](how-to-create-a-security-context-token-for-a-secure-session.md).) Im Code wird das Token aktiviert, indem ein sicherheitsbindungs Element (entweder <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> oder <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>) mithilfe des <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%28System.Boolean%29?displayProperty=nameWithType> oder der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%28System.ServiceModel.Channels.SecurityBindingElement%2CSystem.Boolean%29?displayProperty=nameWithType>-Methode erstellt und der `requireCancellation` Parameter auf `false`festgelegt wird. Der Parameter bezieht sich auf die Zwischenspeicherung des SCT. Wenn Sie den Wert auf `false` festlegen, wird die statusbasierte SCT-Funktion aktiviert.

 Alternativ wird das Token in der Konfiguration aktiviert, indem ein <`customBinding`> erstellt, dann ein <`security`> Element hinzugefügt und das `authenticationMode`-Attribut auf SecureConversation und das `requireSecurityContextCancellation`-Attribut auf `true`festgelegt wird.

> [!NOTE]
> Die zuvor genannten Anforderungen sind spezifisch. Beispielsweise erstellt das <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> ein Bindungselement, das zu einer Windows-Identität führt, wobei aber kein SCT eingerichtet wird. Sie können es daher mit der `Required`-Option unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] verwenden.

### <a name="possible-aspnet-conflict"></a>Möglicher ASP.net-Konflikt

WCF und ASP.net können den Identitätswechsel aktivieren oder deaktivieren. Wenn ASP.net eine WCF-Anwendung hostet, besteht möglicherweise ein Konflikt zwischen den WCF-und ASP.NET-Konfigurationseinstellungen. Bei einem Konflikt hat die WCF-Einstellung Vorrang, es sei denn, die <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>-Eigenschaft ist auf <xref:System.ServiceModel.ImpersonationOption.NotAllowed>festgelegt. in diesem Fall hat die ASP.NET-Identitätswechsel Einstellung Vorrang.

### <a name="assembly-loads-may-fail-under-impersonation"></a>Beim Identitätswechsel können assemblylade Vorgänge fehlschlagen.

Wenn der Identitätswechselkontext keine Zugriffsberechtigungen zum Laden einer Assembly hat und es das erste Mal ist, dass die Common Language Runtime (CLR) versucht, die Assembly für diese Anwendungsdomäne zu laden, speichert die <xref:System.AppDomain> den Fehler zwischen. Nachfolgende Versuche, diese Assembly(s) zu laden, schlagen fehl, selbst nach dem Zurücksetzen des Identitätswechsels und sogar wenn der zurückgesetzte Kontext die Zugriffsberechtigungen hat, die Assembly zu laden. Dies liegt daran, dass die CLR den Ladevorgang nicht erneut versucht, nachdem der Benutzer Kontext geändert wurde. Sie müssen die Anwendungsdomäne neu starten, um nach dem Fehler wiederhergestellt zu werden.

> [!NOTE]
> Der Standardwert für die <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>-Eigenschaft der <xref:System.ServiceModel.Security.WindowsClientCredential>-Klasse ist <xref:System.Security.Principal.TokenImpersonationLevel.Identification>. In den meisten Fällen hat ein Identitätswechsel auf Identifizierungsebene nicht die Berechtigung, zusätzliche Assemblys zu laden. Dies ist der Standardwert. Es handelt sich somit um eine sehr übliche Bedingung, derer Sie sich bewusst sein sollten. Der Identitätswechsel auf Identifizierungsebene kann auch dann auftreten, wenn der Identitätswechselvorgang nicht die `SeImpersonate`-Berechtigung hat. Weitere Informationen finden Sie unter [Delegierung und](delegation-and-impersonation-with-wcf.md)Identitätswechsel.

### <a name="delegation-requires-credential-negotiation"></a>Delegierung erfordert die Aushandlung von Anmelde Informationen

Um das Kerberos-Authentifizierungsprotokoll mit Delegierung zu verwenden, müssen Sie das Kerberos-Protokoll mit Anmeldeinformationen-Aushandlung (mitunter als bilaterales oder mehrstufiges Kerberos bezeichnet) implementieren. Wenn Sie die Kerberos-Authentifizierung ohne Anmeldeinformationen-Aushandlung (mitunter als One-Shot-Kerberos bezeichnet) implementieren, wird eine Ausnahme ausgelöst. Weitere Informationen zum Implementieren der Aushandlung von Anmelde Informationen finden Sie unter [Debuggen von Windows-Authentifizierungs Fehlern](debugging-windows-authentication-errors.md).

## <a name="cryptography"></a>Kryptografie

### <a name="sha-256-supported-only-for-symmetric-key-usages"></a>SHA-256 wird nur für die Verwendung von symmetrischen Schlüsseln unterstützt.

WCF unterstützt eine Vielzahl von Algorithmen zum Erstellen von Verschlüsselungs-und Signatur Digest, die Sie mithilfe der Algorithmussuite in den vom System bereitgestellten Bindungen angeben können. Um die Sicherheit zu verbessern, unterstützt WCF Secure Hash Algorithmus (SHA) 2-Algorithmen (insbesondere SHA-256) zum Erstellen von Signatur Hash Hashs. Dieses Release unterstützt SHA-256 nur für Einsätze mit symmetrischen Schlüsseln, z. B. Kerberos-Schlüssel und wenn kein X.509-Zertifikat zum Signieren der Nachricht verwendet wird. WCF unterstützt keine RSA-Signaturen (in X. 509-Zertifikaten verwendet) mithilfe von SHA-256-Hash aufgrund der aktuellen fehlenden Unterstützung für RSA-SHA256 in WinFX.

### <a name="fips-compliant-sha-256-hashes-not-supported"></a>Mit dem PPS kompatible SHA-256-Hashes werden nicht unterstützt.

WCF unterstützt keine SHA-256-fps-kompatiblen Hashes, sodass Algorithmussuites, die SHA-256 verwenden, von WCF nicht auf Systemen unterstützt werden, in denen die Verwendung von mit der Verwendung von PPS kompatiblen Algorithmen erforderlich ist.

### <a name="fips-compliant-algorithms-may-fail-if-registry-is-edited"></a>Bei der Bearbeitung der Registrierung treten möglicherweise Fehler auf.

Sie können Federal Information Processing Standards (FIPS)-kompatible Algorithmen aktivieren und deaktivieren, indem Sie das Snap-In Lokale Sicherheitseinstellungen der Microsoft Management Console (MMC) verwenden. Sie können auch auf die Einstellung in der Registrierung zugreifen. Beachten Sie jedoch, dass WCF das Zurücksetzen der Einstellung mithilfe der Registrierung nicht unterstützt. Wenn ein anderer Wert als 1 oder 0 festgelegt wurde, können zwischen CLR und dem Betriebssystem inkonsistente Ergebnisse auftreten.

### <a name="fips-compliant-aes-encryption-limitation"></a>Einschränkung der Konformität mit der Konformität mit der Konformität mit der Konformität

Die mit der PPS-kompatible AES-Verschlüsselung funktioniert nicht bei Duplex Rückrufen bei Identitätswechsel auf Identifizierungs Ebene.

### <a name="cngksp-certificates"></a>CNG/KSP-Zertifikate

*Cryptography API: Next Generation (CNG)* ist die langfristige Ersetzung der CryptoAPI. Diese API ist in nicht verwaltetem Code unter Windows Vista, Windows Server 2008 und späteren Windows-Versionen verfügbar.

 .NET Framework 4.6.1 und frühere Versionen unterstützen diese Zertifikate nicht, da Sie die Legacy-CryptoAPI verwenden, um CNG/KSP-Zertifikate zu verarbeiten. Die Verwendung dieser Zertifikate mit .NET Framework 4.6.1 und früheren Versionen führt zu einer Ausnahme.

 Ob KSP von einem Zertifikat verwendet wird, kann auf zwei Arten ermittelt werden:

- Führen Sie `p/invoke` für die `CertGetCertificateContextProperty` aus, und überprüfen Sie `dwProvType` in der zurückgegebenen `CertGetCertificateContextProperty`.

- Verwenden Sie den Befehl `certutil` in der Befehlszeile zum Abfragen von Zertifikaten. Weitere Informationen finden Sie unter [certutil-Aufgaben für die Problembehandlung von Zertifikaten](https://docs.microsoft.com/previous-versions/orphan-topics/ws.10/cc772619(v=ws.10)).

## <a name="message-security-fails-if-using-aspnet-impersonation-and-aspnet-compatibility-is-required"></a>Nachrichten Sicherheit schlägt fehl, wenn die Verwendung von ASP.NET-Identitätswechsel und ASP.NET-Kompatibilität erforderlich ist

WCF unterstützt die folgende Kombination von Einstellungen nicht, da Sie verhindern können, dass die Client Authentifizierung stattfindet:

- ASP.NET Identitätswechsel ist aktiviert. Dies erfolgt in der Datei Web. config, indem das `impersonate`-Attribut des <`identity`> Element auf `true`festgelegt wird.

- Der ASP.NET-Kompatibilitätsmodus wird aktiviert, indem das `aspNetCompatibilityEnabled`-Attribut des [\<ServiceHost->](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) auf `true`festgelegt wird.

- Die Nachrichtenmodussicherheit wird verwendet.

Die Problem Umgehung besteht darin, den ASP.NET-Kompatibilitätsmodus zu deaktivieren. Wenn der ASP.NET-Kompatibilitätsmodus erforderlich ist, deaktivieren Sie das Feature ASP.NET-Identitätswechsel, und verwenden Sie stattdessen den von WCF bereitgestellten Identitätswechsel. Weitere Informationen finden Sie unter [Delegierung und](delegation-and-impersonation-with-wcf.md)Identitätswechsel.

## <a name="ipv6-literal-address-failure"></a>IPv6-literaladressfehler

Bei Sicherheitsanforderungen tritt ein Fehler auf, wenn sich Client und Dienst auf dem gleichen Computer befinden und für den Dienst IPv6-Literaladressen verwendet werden.

 IPv6-Literal-Adressen funktionieren, wenn der Dienst und der Client sich auf unterschiedlichen Computern befinden.

## <a name="wsdl-retrieval-failures-with-federated-trust"></a>WSDL-Abruf Fehler mit Verbund Vertrauensstellung

WCF erfordert genau ein WSDL-Dokument für jeden Knoten in der Verbund Vertrauenskette. Achten Sie darauf, beim Angeben von Endpunkten keine Schleife einzurichten. Eine Schleife kann beispielsweise bei Verwendung eines WSDL-Downloads von Vertrauensketten des Verbunds entstehen, wenn das gleiche WSDL-Dokument mehrere Links enthält. Ein häufig auftretendes Szenario für dieses Problem ist ein Verbunddienst, bei dem sich der Sicherheitstokenserver und der Dienst im gleichen ServiceHost befinden.

 Ein Beispiel für diese Situation ist ein Dienst mit den folgenden drei Endpunktadressen:

- `http://localhost/CalculatorService/service` (Dienst)

- `http://localhost/CalculatorService/issue_ticket` (STS)

- `http://localhost/CalculatorService/mex` (der Metadatenendpunkt)

 Dadurch wird eine Ausnahme ausgelöst.

 Verlegen Sie den `issue_ticket`-Endpunkt, damit dieses Szenario funktioniert.

## <a name="wsdl-import-attributes-can-be-lost"></a>WSDL-Import Attribute können verloren gehen.

WCF kann die Attribute eines `<wst:Claims>` RST-Elements in einer `RST`-Vorlage beim Ausführen eines WSDL-Imports nicht verfolgen. Dieses Problem tritt im Zuge eines WSDL-Importvorgangs auf, wenn `<Claims>` WSFederationHttpBinding.Security.Message.TokenRequestParameters direkt in`WSFederationHttpBinding.Security.Message.TokenRequestParameters``IssuedSecurityTokenRequestParameters.AdditionalRequestParameters` IssuedSecurityTokenRequestParameters.AdditionalRequestParameters oder in und nicht unter direkter Verwendung der Anspruchstypauflistungen angegeben werden.  Da die Attribute beim Importieren verloren gehen, verläuft der Roundtrip der Bindung durch WSDL nicht ordnungsgemäß, und die Bindung ist auf der Clientseite ungültig.

 Ändern Sie nach Abschluss des Importvorgangs die Bindung direkt auf dem Client, um dieses Problem zu korrigieren.

## <a name="see-also"></a>Siehe auch

- [Sicherheitsüberlegungen](security-considerations-in-wcf.md)
- [Offenlegung vertraulicher Informationen](information-disclosure.md)
- [Erhöhen der Berechtigungen](elevation-of-privilege.md)
- [Denial-of-Service-Angriffe](denial-of-service.md)
- [Manipulation](tampering.md)
- [Replayangriffe](replay-attacks.md)
