---
title: Sicherheitsverhalten in WCF
ms.date: 03/30/2017
ms.assetid: 513232c0-39fd-4409-bda6-5ebd5e0ea7b0
ms.openlocfilehash: 12ae9bb90752fe3ee76404948693c501fc42efe6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76730942"
---
# <a name="security-behaviors-in-wcf"></a>Sicherheitsverhalten in WCF
In Windows Communication Foundation (WCF) ändern Verhalten das Laufzeitverhalten auf Dienst Ebene oder auf Endpunkt Ebene. (Weitere Informationen zu Verhaltensweisen im Allgemeinen finden Sie unter [angeben des Dienst Lauf Zeit Verhaltens](../../../../docs/framework/wcf/specifying-service-run-time-behavior.md).) Mithilfe von *Sicherheits Verhaltensweisen* können Anmelde Informationen, Authentifizierungs-, Autorisierungs-und Überwachungs Protokolle gesteuert werden. Sie können Verhalten entweder mittels Programmierung oder mittels Konfiguration verwenden. In diesem Thema wird die Konfiguration der folgenden, auf Sicherheitsfunktionen bezogenen Verhalten erläutert:  
  
- [\<servicecreden->](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).  
  
- [\<Clientanmelde Informationen >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).  
  
- [\<ServiceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md).  
  
- [\<serviceSecurityAudit >](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md).  
  
- [\<serviceMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md), mit dem Sie auch einen sicheren Endpunkt angeben können, auf den Clients für Metadaten zugreifen können.  
  
## <a name="setting-credentials-with-behaviors"></a>Festlegen von Anmeldeinformationen mithilfe von Verhalten  
 Verwenden Sie die [\<servicecredential >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) und [\<clientcredencreden>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) , um die Anmelde Informationen für einen Dienst oder Client festzulegen. Durch die zugrunde liegende Bindungskonfiguration wird vorgegeben, ob Anmeldeinformationen festgelegt werden müssen. Wenn beispielsweise für den Sicherheitsmodus der Wert `None` gewählt wurde, findet keine gegenseitige Authentifizierung von Clients und Diensten statt. Es sind daher keine Anmeldeinformationen erforderlich.  
  
 Andererseits kann es sein, dass die Dienstbindung eine Art von Clientanmeldeinformation erfordert. In diesem Fall müssen Sie eventuell mithilfe eines Verhaltens einen Wert für die Anmeldeinformationen festlegen. (Weitere Informationen zu den möglichen Arten von Anmelde Informationen finden Sie unter [Auswählen eines](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)Anmelde Informations Typs.) In einigen Fällen, z. b. wenn Windows-Anmelde Informationen für die Authentifizierung verwendet werden, legt die Umgebung automatisch den tatsächlichen Wert für die Anmelde Informationen fest, und Sie müssen den Wert für die Anmelde Informationen nicht explizit festlegen (es sei denn, Sie möchten einen anderen Satz von Anmelde Informationen angeben).  
  
 Alle Dienst Anmelde Informationen werden als untergeordnete Elemente der [\<serviceverhaltens>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)gefunden. Im folgenden Beispiel wird ein Zertifikat als Dienstanmeldeinformation verwendet:  
  
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
 Die [\<servicecreden->](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) enthält vier untergeordnete Elemente. Diese Elemente und ihre Verwendung werden in den folgenden Abschnitten vorgestellt.  
  
### <a name="servicecertificate-element"></a>\<serviceCertificate > Element  
 Geben Sie mit diesem Element ein X.509-Zertifikat an, mit dem der Dienst bei den Clients im Modus für die Nachrichtensicherheit authentifiziert wird. Falls Sie ein Zertifikat verwenden, das immer wieder erneuert wird, ändert sich sein Fingerabdruck. Verwenden Sie in diesem Fall den Antragstellernamen als `X509FindType`, da das Zertifikat erneut mit demselben Antragstellernamen ausgestellt werden kann.  
  
 Weitere Informationen zum Verwenden des-Elements finden Sie unter Gewusst [wie: Angeben von Client](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)Anmelde Informations Werten.  
  
### <a name="certificate-of-clientcertificate-element"></a>\<Zertifikat > \<ClientCertificate-> Element  
 Verwenden Sie das [\<Zertifikat >](../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md) -Element, wenn der Dienst das Client Zertifikat im Voraus für die sichere Kommunikation mit dem Client verwenden muss. Dies ist bei der Duplexkommunikation der Fall. Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Schutz seiner Antwort an den Client verwendet wird. Bei der Duplexkommunikation gibt es keine Anforderungen und Antworten. Der Dienst kann das Zertifikat des Clients nicht aus der Kommunikation ableiten. Daher muss der Dienst bereits im Voraus über das Clientzertifikat verfügen, um seine Nachricht an den Client schützen zu können. Sie müssen das Zertifikat des Clients in einem Out-of-Band-Verfahren beziehen und das Zertifikat mit diesem Element angeben. Weitere Informationen zu Duplex Diensten finden Sie unter Gewusst [wie: Erstellen eines Duplex Vertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
### <a name="authentication-of-clientcertificate-element"></a>\<Authentifizierungs > des \<ClientCertificate-> Elements  
 Mit dem [\<Authentication >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) -Element können Sie anpassen, wie Clients authentifiziert werden. Sie können als Wert für das `CertificateValidationMode`-Attribut `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` oder `Custom` festlegen. Standardmäßig ist die Ebene auf `ChainTrust`festgelegt, wodurch angegeben wird, dass jedes Zertifikat in einer Hierarchie von Zertifikaten gefunden werden muss, die in einer Stamm Zertifizierungs *Stelle am Anfang* der Kette endet. Dies ist der sicherste Modus. Sie können auch den Wert `PeerOrChainTrust` verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate (Peervertrauen) akzeptiert werden. Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen. Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert `ChainTrust`. Sie können den Wert auch auf `Custom` setzen. Wenn Sie den Wert `Custom` verwenden, müssen Sie für das `CustomCertificateValidatorType`-Attribut zudem ein Assembly und einen Typ, mit dem das Zertifikat überprüft wird, festlegen. Wenn Sie Ihre eigene Überprüfung erstellen möchten, müssen Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator>-Klasse vererben.  
  
### <a name="issuedtokenauthentication-element"></a>\<IssuedTokenAuthentication-> Element  
 Das Szenario für ausgestellte Token weist drei Phasen auf. In der ersten Phase wird ein Client, der versucht, auf einen Dienst zuzugreifen, ein Sicherheitstokendienst ( *Secure Token Service* , STS) genannt. Der STS authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus. Der Client kehrt dann mit dem Token zum Dienst zurück. Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben. Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein. Das [\<IssuedTokenAuthentication->](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) Element ist das Repository für alle solchen Zertifikate des Sicherheitstokendiensts. Verwenden Sie zum Hinzufügen von Zertifikaten die [\<knownzertifikats >](../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md). [Fügen Sie ein\<>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) für jedes Zertifikat hinzufügen, wie im folgenden Beispiel gezeigt.  
  
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
  
 Sie sollten die [\<zugriffsdauserviceuris->](../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md) Auflistung in einer Verbund Anwendung verwenden, die einen Sicherheitstokendienst ( *Secure Token Service* , STS) verwendet, der `SamlSecurityToken` Sicherheits Token ausgibt. Wenn der STS das Sicherheitstoken ausstellt, kann er den URI des Webdiensts angeben, für den das Sicherheitstoken verwendet werden soll, indem `SamlAudienceRestrictionCondition` dem Sicherheitstoken hinzugefügt wird. Der `SamlSecurityTokenAuthenticator` für den Webdienst kann so überprüfen, ob das ausgestellte Sicherheitstoken für diesen Webdienst ausgelegt ist, indem diese Überprüfung durchgeführt wird. Führen Sie hierzu die folgenden Schritte aus:  
  
- Legen Sie das `audienceUriMode`-Attribut [\<IssuedTokenAuthentication->](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) auf `Always` oder `BearerKeyOnly`fest.  
  
- Geben Sie den Satz gültiger URIs an, indem Sie die URIs dieser Auflistung hinzufügen. Fügen Sie zu diesem Zweck eine [\<hinzufügen >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md) für jeden URI hinzu.  
  
 Weitere Informationen finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.  
  
 Weitere Informationen zur Verwendung dieses Konfigurations Elements finden Sie unter Vorgehens [Weise: Konfigurieren von Anmelde Informationen auf einem Verbunddienst](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
#### <a name="allowing-anonymous-cardspace-users"></a>Zulassen anonymer CardSpace-Benutzer  
 Wenn Sie das `AllowUntrustedRsaIssuers`-Attribut des `<IssuedTokenAuthentication>`-Elements auf `true` setzen, dürfen alle Clients ein selbst ausgestelltes und mit einem beliebigen RSA-Schlüsselpaar signiertes Token vorweisen. Der Aussteller ist *nicht vertrauenswürdig* , da dem Schlüssel keine Ausstellerdaten zugeordnet sind. Ein CardSpace-Benutzer kann eine selbst ausgegebene Karte erstellen, die selbst bereitgestellte Identitäts Ansprüche enthält. Daher sollte diese Funktion nur mit Vorsicht verwendet werden. Falls Sie diese Funktion verwenden möchten, stellen Sie sich den öffentlichen RSA-Schlüssel als sichereres Kennwort vor, das mit dem Benutzernamen in einer Datenbank gespeichert werden sollte. Überprüfen Sie den vom Client vorgelegten öffentlichen RSA-Schlüssel, indem Sie ihn mit dem für diesen Benutzernamen gespeicherten öffentlichen Schlüssel vergleichen, bevor Sie einem Client Zugriff auf den Dienst gewähren. Dies setzt voraus, dass Sie einen Registrierungsvorgang eingerichtet haben, bei dem Benutzer ihre Benutzernamen registrieren und diesen die selbst ausgestellten öffentlichen RSA-Schlüssel zuordnen können.  
  
## <a name="client-credentials"></a>Clientanmeldeinformationen  
 Durch die Clientanmeldeinformationen wird der Client bei den Diensten authentifiziert, wenn eine gegenseitige Authentifizierung erforderlich ist. Sie können den Abschnitt zur Angabe von Dienstzertifikaten in Szenarien verwenden, bei denen der Client seine Nachrichten an einen Dienst mithilfe des Dienstzertifikats schützen muss.  
  
 Sie können einen Client auch als Teil eines Verbundszenarien konfigurieren, in dem die Token eines Sicherheitstokendiensts oder eines lokalen Tokenausstellers verwendet werden. Weitere Informationen zu Verbund Szenarien finden Sie unter Verbund [-und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md). Alle Client Anmelde Informationen finden Sie unter der [\<endpointverhalten>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md), wie im folgenden Code dargestellt.  
  
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
```  
  
#### <a name="clientcertificate-element"></a>\<ClientCertificate >-Element  
 Legen Sie mit diesem Element das Zertifikat fest, mit dem der Client authentifiziert wird. Weitere Informationen finden Sie unter Gewusst [wie: Angeben von Client](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)Anmelde Informations Werten.  
  
#### <a name="httpdigest"></a>\<httpdigest->  
 Diese Funktion muss mit Active Directory unter Windows und unter IIS (Internet Information Services) aktiviert werden. Weitere Informationen finden Sie unter [Digest-Authentifizierung in IIS 6,0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).  
  
#### <a name="issuedtoken-element"></a>\<IssuedToken >-Element  
 Das [\<IssuedToken >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) enthält die Elemente, die zum Konfigurieren eines lokalen Ausstellers von Token oder Verhalten verwendet werden, die mit einem Sicherheitstokendienst verwendet werden. Anweisungen zum Konfigurieren eines Clients für die Verwendung eines lokalen Ausstellers finden Sie unter Vorgehens [Weise: Konfigurieren eines lokalen Ausstellers](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
#### <a name="localissueraddress"></a>\<LocalIssuerAddress >  
 Gibt eine Standardadresse für den Sicherheitstokendienst an. Diese wird verwendet, wenn das <xref:System.ServiceModel.WSFederationHttpBinding> keine URL für den Sicherheitstokendienst bereitstellt oder wenn die Aussteller Adresse einer Verbund Bindung `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` oder `null`ist. In diesem Fall muss <xref:System.ServiceModel.Description.ClientCredentials> mit der Adresse des lokalen Ausstellers und der für die Kommunikation mit diesem Aussteller zu verwendenden Bindung konfiguriert werden.  
  
#### <a name="issuerchannelbehaviors"></a>\<issuerchannelverhaltens>  
 Verwenden Sie die [\<issuerchannelverhaltens>](../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md) , um WCF-Client Verhalten hinzuzufügen, die bei der Kommunikation mit einem Sicherheitstokendienst Definieren Sie Client Verhalten im Abschnitt [\<endpointverhaltens>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) . Um ein definiertes Verhalten zu verwenden, fügen Sie dem `<issuerChannelBehaviors>`-Element mit zwei Attributen eine <`add`>-Element hinzu. Verwenden Sie für `issuerAddress` die URL des Sicherheitstokendiensts, und verwenden Sie für das `behaviorConfiguration`-Attribut den Namen des definierten Endpunktverhaltens, wie im folgenden Beispiel gezeigt:  
  
```xml  
<clientCredentials>  
   <issuedToken>  
      <issuerChannelBehaviors>  
         <add issuerAddress="http://www.contoso.com"  
               behaviorConfiguration="clientBehavior1" />     
```  
  
#### <a name="servicecertificate-element"></a>\<serviceCertificate > Element  
 Verwenden Sie dieses Element, um die Authentifizierung von Dienstzertifikaten zu steuern.  
  
 Das [\<defaultCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) -Element kann ein einzelnes Zertifikat speichern, das verwendet wird, wenn der Dienst kein Zertifikat angibt.  
  
 Verwenden Sie die [\<scopedzertifikats >](../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md) und [\<Add >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md) , um Dienst Zertifikate festzulegen, die bestimmten Diensten zugeordnet sind. Das `<add>`-Element beinhaltet ein `targetUri`-Attribut, mit dem das Zertifikat dem Dienst zugeordnet wird.  
  
 Das [\<Authentication >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) -Element gibt die Vertrauens Ebene an, die zum Authentifizieren von Zertifikaten verwendet wird. Standardmäßig wird die Stufe "ChainTrust" verwendet, die angibt, dass jedes Zertifikat in einer Zertifizierungshierarchie zu finden sein muss, die in eine vertrauenswürdige Zertifizierungsstelle am Anfang der Kette mündet. Dies ist der sicherste Modus. Sie können auch den Wert "PeerOrChainTrust" verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate (Peervertrauen) akzeptiert werden. Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen. Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert "ChainTrust". Sie können auch den Wert "Custom" bzw. "None" verwenden. Wenn Sie "Custom" verwenden möchten, müssen Sie für das `CustomCertificateValidatorType`-Attribut zudem ein Assembly und einen Typ, mit dem das Zertifikat überprüft wird, festlegen. Wenn Sie Ihre eigene Überprüfung erstellen möchten, müssen Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator>-Klasse vererben. Weitere Informationen finden Sie unter Vorgehens [Weise: Erstellen eines Dienstanbieter, der ein benutzerdefiniertes zertifikatvalidator verwendet](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
 Das [\<Authentication >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) -Element enthält ein `RevocationMode` Attribut, das angibt, wie Zertifikate auf eine Sperre geprüft werden. Der Standardwert ist "online", wodurch angegeben wird, dass Zertifikate automatisch auf eine Sperre hin überprüft werden. Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## <a name="serviceauthorization"></a>ServiceAuthorization  
 Das [\<ServiceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) -Element enthält Elemente, die sich auf die Autorisierung, benutzerdefinierte Rollen Anbieter und den Identitätswechsel auswirken.  
  
 Die <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Klasse wird auf eine Dienstmethode angewendet. Das Attribut gibt die Benutzergruppen an, mit denen die Verwendung einer geschützten Methode autorisiert wird. Der Standardwert lautet "UseWindowsGroups". Er gibt an, das in Windows-Gruppen wie der der Administratoren oder Benutzer nach einer Identität gesucht wird, die versucht, auf eine Ressource zuzugreifen. Sie können auch "useaspnettroles" angeben, um einen benutzerdefinierten Rollen Anbieter zu verwenden, der unter dem <`system.web` >-Element konfiguriert ist, wie im folgenden Code gezeigt.  
  
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
 Verwenden Sie den [\<serviceSecurityAudit->](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) , um das in geschriebene Protokoll anzugeben, und welche Arten von Ereignissen protokolliert werden sollen. Weitere Informationen finden Sie unter [Auditing](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
```xml  
<system.serviceModel>  
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
 Das Exportieren von Metadaten auf Clients ist hilfreich für Dienst- und Cliententwickler, da so das Herunterladen von Konfigurations- und Clientcode möglich wird. Damit der Dienst möglichst gut vor böswilligen Benutzern geschützt wird, können Sie für die Übertragung den HTTPS-Mechanismus (SSL über HTTP) verwenden. Hierfür müssen Sie zunächst ein geeignetes X.509-Zertifikat an einen bestimmten Port des Computers, auf dem der Dienst gehostet wird, binden. (Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Fügen Sie als nächstes der Dienst Konfiguration einen [\<serviceMetadata->](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) hinzu, und legen Sie das `HttpsGetEnabled`-Attribut auf `true`fest. Setzen Sie abschließend wie im folgenden Beispiel gezeigt das `HttpsGetUrl`-Attribut auf den URL des Dienstmetadaten-Endpunkts:  
  
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
- [Sicherheitsmodell für Windows Server-App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
