---
title: Sicherheitsverhalten in WCF
ms.date: 03/30/2017
ms.assetid: 513232c0-39fd-4409-bda6-5ebd5e0ea7b0
ms.openlocfilehash: 9f96abac0f5f32279c5579dd01c3dd7f2dc1786c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464048"
---
# <a name="security-behaviors-in-wcf"></a>Sicherheitsverhalten in WCF
In Windows Communication Foundation (WCF) ändern Verhaltensweisen das Laufzeitverhalten auf Dienstebene oder auf Endpunktebene. (Weitere Informationen zu Verhaltensweisen im Allgemeinen finden Sie unter [Angeben des Dienstlaufzeitverhaltens](../../../../docs/framework/wcf/specifying-service-run-time-behavior.md).) *Sicherheitsverhalten* ermöglichen die Kontrolle über Anmeldeinformationen, Authentifizierungs-, Autorisierungs- und Überwachungsprotokolle. Sie können Verhalten entweder mittels Programmierung oder mittels Konfiguration verwenden. In diesem Thema wird die Konfiguration der folgenden, auf Sicherheitsfunktionen bezogenen Verhalten erläutert:  
  
- serviceCredentials>. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)  
  
- clientCredentials>. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)  
  
- serviceAuthorization>. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)  
  
- serviceSecurityAudit>. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)  
  
- serviceMetadata>, mit dem Sie auch einen sicheren Endpunkt angeben können, auf den Clients für Metadaten zugreifen können. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)  
  
## <a name="setting-credentials-with-behaviors"></a>Festlegen von Anmeldeinformationen mithilfe von Verhalten  
 Verwenden Sie die [ \<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) und [ \<clientCredentials>,](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) um Anmeldeinformationswerte für einen Dienst oder Client festzulegen. Durch die zugrunde liegende Bindungskonfiguration wird vorgegeben, ob Anmeldeinformationen festgelegt werden müssen. Wenn beispielsweise für den Sicherheitsmodus der Wert `None` gewählt wurde, findet keine gegenseitige Authentifizierung von Clients und Diensten statt. Es sind daher keine Anmeldeinformationen erforderlich.  
  
 Andererseits kann es sein, dass die Dienstbindung eine Art von Clientanmeldeinformation erfordert. In diesem Fall müssen Sie eventuell mithilfe eines Verhaltens einen Wert für die Anmeldeinformationen festlegen. (Weitere Informationen zu den möglichen Anmeldeinformationen finden Sie [unter Auswählen eines Anmeldeinformationstyps](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).) In einigen Fällen, z. B. wenn Windows-Anmeldeinformationen zur Authentifizierung verwendet werden, legt die Umgebung automatisch den tatsächlichen Anmeldeinformationswert fest, und Sie müssen den Anmeldeinformationswert nicht explizit festlegen (es sei denn, Sie möchten einen anderen Satz von Anmeldeinformationen angeben).  
  
 Alle Dienstanmeldeinformationen werden als untergeordnete Elemente des [ \<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)gefunden. Im folgenden Beispiel wird ein Zertifikat als Dienstanmeldeinformation verwendet:  
  
```xml  
<configuration>  
 <system.serviceModel>  
  <behaviors>  
   <serviceBehaviors>  
    <behavior name="ServiceBehavior1">  
     <serviceCredentials>  
      <serviceCertificate findValue="000000000000000000000000000"
                          storeLocation="CurrentUser"  
      storeName="Root" x509FindType="FindByThumbprint" />  
     </serviceCredentials>  
    </behavior>  
   </serviceBehaviors>  
  </behaviors>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="service-credentials"></a>Dienstanmeldeinformationen  
 Der [ \<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) enthält vier untergeordnete Elemente. Diese Elemente und ihre Verwendung werden in den folgenden Abschnitten vorgestellt.  
  
### <a name="servicecertificate-element"></a>\<serviceCertificate> Element  
 Geben Sie mit diesem Element ein X.509-Zertifikat an, mit dem der Dienst bei den Clients im Modus für die Nachrichtensicherheit authentifiziert wird. Falls Sie ein Zertifikat verwenden, das immer wieder erneuert wird, ändert sich sein Fingerabdruck. Verwenden Sie in diesem Fall den Antragstellernamen als `X509FindType`, da das Zertifikat erneut mit demselben Antragstellernamen ausgestellt werden kann.  
  
 Weitere Informationen zur Verwendung des Elements finden Sie unter [Gewusst wie: Angeben von Clientanmeldeinformationen-](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)  
  
### <a name="certificate-of-clientcertificate-element"></a>\<Zertifikat> \<von clientCertificate> Element  
 Verwenden [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md) Sie das Zertifikat>Element, wenn der Dienst im Voraus über das Zertifikat des Clients verfügen muss, um sicher mit dem Client kommunizieren zu können. Dies ist bei der Duplexkommunikation der Fall. Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Schutz seiner Antwort an den Client verwendet wird. Bei der Duplexkommunikation gibt es keine Anforderungen und Antworten. Der Dienst kann das Zertifikat des Clients nicht aus der Kommunikation ableiten. Daher muss der Dienst bereits im Voraus über das Clientzertifikat verfügen, um seine Nachricht an den Client schützen zu können. Sie müssen das Zertifikat des Clients in einem Out-of-Band-Verfahren beziehen und das Zertifikat mit diesem Element angeben. Weitere Informationen zu Duplexdiensten finden Sie unter [Gewusst wie: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
### <a name="authentication-of-clientcertificate-element"></a>\<Authentifizierungs> von \<clientCertificate> Element  
 Mit [ \<dem>-Element](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) können Sie anpassen, wie Clients authentifiziert werden. Sie können als Wert für das `CertificateValidationMode`-Attribut `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` oder `Custom` festlegen. Standardmäßig wird die Ebene `ChainTrust`auf festgelegt, die angibt, dass jedes Zertifikat in einer Hierarchie von Zertifikaten gefunden werden muss, die in einer *Stammautorität* am oberen Rand der Kette enden. Dies ist der sicherste Modus. Sie können auch den Wert `PeerOrChainTrust` verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate (Peervertrauen) akzeptiert werden. Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen. Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert `ChainTrust`. Sie können den Wert auch auf `Custom` setzen. Wenn Sie den Wert `Custom` verwenden, müssen Sie für das `CustomCertificateValidatorType`-Attribut zudem ein Assembly und einen Typ, mit dem das Zertifikat überprüft wird, festlegen. Wenn Sie Ihre eigene Überprüfung erstellen möchten, müssen Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator>-Klasse vererben.  
  
### <a name="issuedtokenauthentication-element"></a>\<issuedTokenAuthentication> Element  
 Das Szenario für ausgestellte Token weist drei Phasen auf. In der ersten Phase wird ein Client, der versucht, auf einen Dienst zuzugreifen, auf einen sicheren Tokendienst (SECURE *Token Service,* STS) verwiesen. Der STS authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus. Der Client kehrt dann mit dem Token zum Dienst zurück. Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben. Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein. Das [ \<issuedTokenAuthentication>-Element](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) ist das Repository für solche sicheren Tokendienstzertifikate. Um Zertifikate hinzuzufügen, verwenden Sie die [ \<knownCertificates>](../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md). Fügen Sie für jedes Zertifikat ein [ \<hinzufügen>,](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) wie im folgenden Beispiel gezeigt.  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"
           storeLocation="LocalMachine" storeName="My"
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden. Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.  
  
 Sie sollten die `SamlSecurityToken` [ \<allowedAudienceUris>-Auflistung](../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md) in einer Verbundanwendung verwenden, die einen sicheren Tokendienst (SECURE Token *Service,* STS) verwendet, der Sicherheitstoken ausgibt. Wenn der STS das Sicherheitstoken ausstellt, kann er den URI des Webdiensts angeben, für den das Sicherheitstoken verwendet werden soll, indem `SamlAudienceRestrictionCondition` dem Sicherheitstoken hinzugefügt wird. Der `SamlSecurityTokenAuthenticator` für den Webdienst kann so überprüfen, ob das ausgestellte Sicherheitstoken für diesen Webdienst ausgelegt ist, indem diese Überprüfung durchgeführt wird. Führen Sie hierzu die folgenden Schritte aus:  
  
- Legen `audienceUriMode` Sie das Attribut [ \<issuedTokenAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) auf oder `Always` `BearerKeyOnly`fest.  
  
- Geben Sie den Satz gültiger URIs an, indem Sie die URIs dieser Auflistung hinzufügen. Fügen Sie dazu [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md) einen>für jeden URI ein.  
  
 Weitere Informationen finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.  
  
 Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [Gewusst wie: Konfigurieren von Anmeldeinformationen für einen Verbunddienst](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
#### <a name="allowing-anonymous-cardspace-users"></a>Zulassen anonymer CardSpace-Benutzer  
 Wenn Sie das `AllowUntrustedRsaIssuers`-Attribut des `<IssuedTokenAuthentication>`-Elements auf `true` setzen, dürfen alle Clients ein selbst ausgestelltes und mit einem beliebigen RSA-Schlüsselpaar signiertes Token vorweisen. Der Aussteller ist *nicht vertrauenswürdig,* da dem Schlüssel keine Emittentendaten zugeordnet sind. Ein CardSpace-Benutzer kann eine selbst ausgestellte Karte erstellen, die selbst bereitgestellte Identitätsansprüche enthält. Daher sollte diese Funktion nur mit Vorsicht verwendet werden. Falls Sie diese Funktion verwenden möchten, stellen Sie sich den öffentlichen RSA-Schlüssel als sichereres Kennwort vor, das mit dem Benutzernamen in einer Datenbank gespeichert werden sollte. Überprüfen Sie den vom Client vorgelegten öffentlichen RSA-Schlüssel, indem Sie ihn mit dem für diesen Benutzernamen gespeicherten öffentlichen Schlüssel vergleichen, bevor Sie einem Client Zugriff auf den Dienst gewähren. Dies setzt voraus, dass Sie einen Registrierungsvorgang eingerichtet haben, bei dem Benutzer ihre Benutzernamen registrieren und diesen die selbst ausgestellten öffentlichen RSA-Schlüssel zuordnen können.  
  
## <a name="client-credentials"></a>Clientanmeldeinformationen  
 Durch die Clientanmeldeinformationen wird der Client bei den Diensten authentifiziert, wenn eine gegenseitige Authentifizierung erforderlich ist. Sie können den Abschnitt zur Angabe von Dienstzertifikaten in Szenarien verwenden, bei denen der Client seine Nachrichten an einen Dienst mithilfe des Dienstzertifikats schützen muss.  
  
 Sie können einen Client auch als Teil eines Verbundszenarien konfigurieren, in dem die Token eines Sicherheitstokendiensts oder eines lokalen Tokenausstellers verwendet werden. Weitere Informationen zu Verbundszenarien finden Sie unter [Föderation und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md). Alle Clientanmeldeinformationen finden Sie unter [ \<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md), wie im folgenden Code gezeigt.  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="EndpointBehavior1">  
   <clientCredentials>  
    <clientCertificate findValue="cn=www.contoso.com"
        storeLocation="LocalMachine"  
        storeName="AuthRoot" x509FindType="FindBySubjectName" />  
    <serviceCertificate>  
     <defaultCertificate findValue="www.cohowinery.com"
                    storeLocation="LocalMachine"  
                    storeName="Root" x509FindType="FindByIssuerName" />  
    <authentication revocationMode="Online"  
                    trustedStoreLocation="LocalMachine" />  
    </serviceCertificate>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
</behaviors>  
```  
  
#### <a name="clientcertificate-element"></a>\<clientCertificate> Element  
 Legen Sie mit diesem Element das Zertifikat fest, mit dem der Client authentifiziert wird. Weitere Informationen finden Sie unter [Gewusst wie: Angeben von Clientanmeldeinformationen-](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)  
  
#### <a name="httpdigest"></a>\<httpDigest>  
 Diese Funktion muss mit Active Directory unter Windows und unter IIS (Internet Information Services) aktiviert werden. Weitere Informationen finden Sie unter [Digestauthentifizierung in IIS 6.0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).  
  
#### <a name="issuedtoken-element"></a>\<issuedToken> Element  
 Die [ \<issuedToken>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) enthält die Elemente, die zum Konfigurieren eines lokalen Ausstellers von Token verwendet werden, oder Verhaltensweisen, die mit einem Sicherheitstokendienst verwendet werden. Anweisungen zum Konfigurieren eines Clients für die Verwendung eines lokalen Ausstellers finden Sie unter [Gewusst wie: Konfigurieren eines lokalen Ausstellers](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
#### <a name="localissueraddress"></a>\<localIssuerAddress>  
 Gibt eine Standardadresse für den Sicherheitstokendienst an. Dies wird <xref:System.ServiceModel.WSFederationHttpBinding> verwendet, wenn der keine URL für den Sicherheitstokendienst liefert oder wenn `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` `null`die Ausstelleradresse einer Verbundbindung oder ist. In diesem Fall muss <xref:System.ServiceModel.Description.ClientCredentials> mit der Adresse des lokalen Ausstellers und der für die Kommunikation mit diesem Aussteller zu verwendenden Bindung konfiguriert werden.  
  
#### <a name="issuerchannelbehaviors"></a>\<IssuerChannelBehaviors>  
 Verwenden Sie den [ \<IssuerChannelBehaviors>,](../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md) um WCF-Clientverhalten hinzuzufügen, das bei der Kommunikation mit einem Sicherheitstokendienst verwendet wird. Definieren Sie Clientverhalten im [ \<Abschnitt endpointBehaviors>.](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) Um ein definiertes Verhalten `add` zu verwenden, `<issuerChannelBehaviors>` fügen Sie dem Element mit zwei Attributen ein <>-Element hinzu. Verwenden Sie für `issuerAddress` die URL des Sicherheitstokendiensts, und verwenden Sie für das `behaviorConfiguration`-Attribut den Namen des definierten Endpunktverhaltens, wie im folgenden Beispiel gezeigt:  
  
```xml  
<clientCredentials>  
   <issuedToken>  
      <issuerChannelBehaviors>  
         <add issuerAddress="http://www.contoso.com"  
               behaviorConfiguration="clientBehavior1" />
      </issuerChannelBehaviors>  
   </issuedToken>  
</clientCredentials>
```  
  
#### <a name="servicecertificate-element"></a>\<serviceCertificate> Element  
 Verwenden Sie dieses Element, um die Authentifizierung von Dienstzertifikaten zu steuern.  
  
 Das [ \<defaultCertificate>-Element](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) kann ein einzelnes Zertifikat speichern, das verwendet wird, wenn der Dienst kein Zertifikat angibt.  
  
 Verwenden Sie die [ \<scopedCertificates>,](../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md) und [ \<fügen Sie>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md) hinzu, um Dienstzertifikate festzulegen, die bestimmten Diensten zugeordnet sind. Das `<add>`-Element beinhaltet ein `targetUri`-Attribut, mit dem das Zertifikat dem Dienst zugeordnet wird.  
  
 Die [ \<Authentifizierung>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) Element gibt die Vertrauensstufe an, die zum Authentifizieren von Zertifikaten verwendet wird. Standardmäßig wird die Stufe "ChainTrust" verwendet, die angibt, dass jedes Zertifikat in einer Zertifizierungshierarchie zu finden sein muss, die in eine vertrauenswürdige Zertifizierungsstelle am Anfang der Kette mündet. Dies ist der sicherste Modus. Sie können auch den Wert "PeerOrChainTrust" verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate (Peervertrauen) akzeptiert werden. Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen. Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert "ChainTrust". Sie können auch den Wert "Custom" bzw. "None" verwenden. Wenn Sie "Custom" verwenden möchten, müssen Sie für das `CustomCertificateValidatorType`-Attribut zudem ein Assembly und einen Typ, mit dem das Zertifikat überprüft wird, festlegen. Wenn Sie Ihre eigene Überprüfung erstellen möchten, müssen Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator>-Klasse vererben. Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines Dienstes, der einen benutzerdefinierten Zertifikatsvalidator verwendet.](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
  
 Das [ \<>-Element](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) `RevocationMode` enthält ein Attribut, das angibt, wie Zertifikate auf Widerruf überprüft werden. Der Standardwert ist "online", wodurch angegeben wird, dass Zertifikate automatisch auf eine Sperre hin überprüft werden. Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## <a name="serviceauthorization"></a>ServiceAuthorization  
 Das [ \<>-Element serviceAuthorization](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) enthält Elemente, die sich auf Autorisierung, benutzerdefinierte Rollenanbieter und Identitätswechsel auswirken.  
  
 Die <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Klasse wird auf eine Dienstmethode angewendet. Das Attribut gibt die Benutzergruppen an, mit denen die Verwendung einer geschützten Methode autorisiert wird. Der Standardwert lautet "UseWindowsGroups". Er gibt an, das in Windows-Gruppen wie der der Administratoren oder Benutzer nach einer Identität gesucht wird, die versucht, auf eine Ressource zuzugreifen. Sie können auch "UseAspNetRoles" angeben, um einen benutzerdefinierten `system.web` Rollenanbieter zu verwenden, der unter dem <>-Element konfiguriert ist, wie im folgenden Code gezeigt.  
  
```xml  
<system.web>  
  <membership defaultProvider="SqlProvider"
   userIsOnlineTimeWindow="15">  
     <providers>  
       <clear />  
       <add
          name="SqlProvider"
          type="System.Web.Security.SqlMembershipProvider"
          connectionStringName="SqlConn"  
          applicationName="MembershipProvider"  
          enablePasswordRetrieval="false"  
          enablePasswordReset="false"  
          requiresQuestionAndAnswer="false"  
          requiresUniqueEmail="true"  
          passwordFormat="Hashed" />  
     </providers>  
   </membership>  
  <!-- Other configuration code not shown.-->  
</system.web>  
```  
  
 Im folgenden Code wird `roleProviderName` mit dem `principalPermissionMode`-Attribut verwendet.  
  
```xml  
<behaviors>  
 <behavior name="ServiceBehaviour">
  <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                        roleProviderName ="SqlProvider" />  
</behavior>
   <!-- Other configuration code not shown. -->  
</behaviors>  
```  
  
## <a name="configuring-security-audits"></a>Konfigurieren der Sicherheitsüberwachung  
 Verwenden Sie die [ \<>von serviceSecurityAudit,](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) um anzugeben, in welches Protokoll geschrieben wurde und welche Ereignistypen protokolliert werden sollen. Weitere Informationen finden Sie unter [Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
```xml  
<behaviors>
 <serviceBehaviors>  
  <behavior name="NewBehavior">  
    <serviceSecurityAudit auditLogLocation="Application"
             suppressAuditFailure="true"  
             serviceAuthorizationAuditLevel="Success"
             messageAuthenticationAuditLevel="Success" />  
  </behavior>  
 </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="secure-metadata-exchange"></a>Sicherer Metadatenaustausch  
 Das Exportieren von Metadaten auf Clients ist hilfreich für Dienst- und Cliententwickler, da so das Herunterladen von Konfigurations- und Clientcode möglich wird. Damit der Dienst möglichst gut vor böswilligen Benutzern geschützt wird, können Sie für die Übertragung den HTTPS-Mechanismus (SSL über HTTP) verwenden. Hierfür müssen Sie zunächst ein geeignetes X.509-Zertifikat an einen bestimmten Port des Computers, auf dem der Dienst gehostet wird, binden. (Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Fügen Sie zweitens der Dienstkonfiguration einen `HttpsGetEnabled` `true` [ \<serviceMetadata->](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) hinzu, und legen Sie das Attribut auf fest. Setzen Sie abschließend wie im folgenden Beispiel gezeigt das `HttpsGetUrl`-Attribut auf den URL des Dienstmetadaten-Endpunkts:  
  
```xml  
<behaviors>  
 <serviceBehaviors>  
  <behavior name="NewBehavior">  
    <serviceMetadata httpsGetEnabled="true"
     httpsGetUrl="https://myComputerName/myEndpoint" />  
  </behavior>  
 </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
- [Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
