---
title: Sicherheitsverhalten in WCF
ms.date: 03/30/2017
ms.assetid: 513232c0-39fd-4409-bda6-5ebd5e0ea7b0
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 57bd34c72e98091c4a429d683a0da4ce2d3967c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33508643"
---
# <a name="security-behaviors-in-wcf"></a>Sicherheitsverhalten in WCF
In Windows Communication Foundation (WCF) Verhalten zu Laufzeitverhalten auf Dienstebene bzw. auf Endpunktebene ändern. (Weitere Informationen zum Verhalten im Allgemeinen finden Sie unter [Run-Time-Dienstverhalten angeben](../../../../docs/framework/wcf/specifying-service-run-time-behavior.md).) *Sicherheitsverhalten* Ihnen die Kontrolle über die Anmeldeinformationen, Authentifizierung und Autorisierung und über Überwachungsprotokolle. Sie können Verhalten entweder mittels Programmierung oder mittels Konfiguration verwenden. In diesem Thema wird die Konfiguration der folgenden, auf Sicherheitsfunktionen bezogenen Verhalten erläutert:  
  
-   [\<ServiceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).  
  
-   [\<ClientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).  
  
-   [\<ServiceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md).  
  
-   [\<ServiceSecurityAudit >](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md).  
  
-   [\<ServiceMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md), außerdem können Sie einen sicheren Endpunkt angeben, die Clients für Metadaten zugreifen können.  
  
## <a name="setting-credentials-with-behaviors"></a>Festlegen von Anmeldeinformationen mithilfe von Verhalten  
 Verwenden der [ \<ServiceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) und [ \<ClientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Werte für die Anmeldeinformationen für einen Dienst oder Client festlegen. Durch die zugrunde liegende Bindungskonfiguration wird vorgegeben, ob Anmeldeinformationen festgelegt werden müssen. Wenn beispielsweise für den Sicherheitsmodus der Wert `None` gewählt wurde, findet keine gegenseitige Authentifizierung von Clients und Diensten statt. Es sind daher keine Anmeldeinformationen erforderlich.  
  
 Andererseits kann es sein, dass die Dienstbindung eine Art von Clientanmeldeinformation erfordert. In diesem Fall müssen Sie eventuell mithilfe eines Verhaltens einen Wert für die Anmeldeinformationen festlegen. (Weitere Informationen über die möglichen Typen von Anmeldeinformationen finden Sie unter [Auswählen eines Anmeldeinformationentyps](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).) Gelegentlich wird der tatsächliche Anmeldeinformationswert automatisch durch die Umgebung festgesetzt, zum Beispiel bei Verwendung von Windows-Anmeldeinformationen für die Authentifizierung. In diesem Fall müssen Sie den Wert für die Anmeldeinformationen nicht explizit festlegen, außer Sie möchten andere Anmeldeinformationen verwenden.  
  
 Befinden sich alle Dienstanmeldeinformationen als untergeordnete Elemente von der [ \<ServiceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md). Im folgenden Beispiel wird ein Zertifikat als Dienstanmeldeinformation verwendet:  
  
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
 Die [ \<ServiceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) enthält vier untergeordneten Elemente. Diese Elemente und ihre Verwendung werden in den folgenden Abschnitten vorgestellt.  
  
### <a name="servicecertificate-element"></a>\<ServiceCertificate >-Element  
 Geben Sie mit diesem Element ein X.509-Zertifikat an, mit dem der Dienst bei den Clients im Modus für die Nachrichtensicherheit authentifiziert wird. Falls Sie ein Zertifikat verwenden, das immer wieder erneuert wird, ändert sich sein Fingerabdruck. Verwenden Sie in diesem Fall den Antragstellernamen als `X509FindType`, da das Zertifikat erneut mit demselben Antragstellernamen ausgestellt werden kann.  
  
 Weitere Informationen zum Verwenden des Elements finden Sie unter [Vorgehensweise: Angeben der Clientanmeldeinformationswerte](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
### <a name="certificate-of-clientcertificate-element"></a>\<Zertifikat > der \<ClientCertificate >-Element  
 Verwenden der [ \<Zertifikat >](../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md) Element, wenn der Dienst das Zertifikat des Clients im voraus, zur sicheren Kommunikation mit dem Client verfügen muss. Dies ist bei der Duplexkommunikation der Fall. Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Schutz seiner Antwort an den Client verwendet wird. Bei der Duplexkommunikation gibt es keine Anforderungen und Antworten. Der Dienst kann das Zertifikat des Clients nicht aus der Kommunikation ableiten. Daher muss der Dienst bereits im Voraus über das Clientzertifikat verfügen, um seine Nachricht an den Client schützen zu können. Sie müssen das Zertifikat des Clients in einem Out-of-Band-Verfahren beziehen und das Zertifikat mit diesem Element angeben. Weitere Informationen über duplexdienste finden Sie unter [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
### <a name="authentication-of-clientcertificate-element"></a>\<Authentication > des \<ClientCertificate >-Element  
 Die [ \<Authentifizierung >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) Element können Sie anpassen, wie Clients authentifiziert werden. Sie können als Wert für das `CertificateValidationMode`-Attribut `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` oder `Custom` festlegen. Wird standardmäßig die Ebene festgelegt ist, um `ChainTrust`, was bedeutet, dass jedes Zertifikat in einer Hierarchie in mündet gefunden werden, muss eine *Stammzertifizierungsstelle* am Anfang der Kette. Dies ist der sicherste Modus. Sie können auch den Wert `PeerOrChainTrust` verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate (Peervertrauen) akzeptiert werden. Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen. Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert `ChainTrust`. Sie können den Wert auch auf `Custom` setzen. Wenn Sie den Wert `Custom` verwenden, müssen Sie für das `CustomCertificateValidatorType`-Attribut zudem ein Assembly und einen Typ, mit dem das Zertifikat überprüft wird, festlegen. Wenn Sie Ihre eigene Überprüfung erstellen möchten, müssen Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator>-Klasse vererben.  
  
### <a name="issuedtokenauthentication-element"></a>\<IssuedTokenAuthentication >-Element  
 Das Szenario für ausgestellte Token weist drei Phasen auf. In der ersten Phase wird ein Client versucht, auf einen Dienst zuzugreifen bezeichnet einen *sicheren Tokendienst* (STS). Der STS authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus. Der Client kehrt dann mit dem Token zum Dienst zurück. Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben. Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein. Die [ \<IssuedTokenAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) Element ist das Repository für solche Sicherheitstokendienst-Zertifikate. Verwenden Sie zum Hinzufügen von Zertifikaten der [ \<KnownCertificates >](../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md). Fügen Sie ein [ \<hinzufügen >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) für jedes Zertifikat, wie im folgenden Beispiel gezeigt.  
  
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
  
 Verwenden Sie die [ \<AllowedAudienceUris >](../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md) Auflistung in einer verbundanwendung, die nutzt eine *secure token Service* (STS) Probleme bei `SamlSecurityToken` Sicherheitstoken. Wenn der STS das Sicherheitstoken ausstellt, kann er den URI des Webdiensts angeben, für den das Sicherheitstoken verwendet werden soll, indem `SamlAudienceRestrictionCondition` dem Sicherheitstoken hinzugefügt wird. Der `SamlSecurityTokenAuthenticator` für den Webdienst kann so überprüfen, ob das ausgestellte Sicherheitstoken für diesen Webdienst ausgelegt ist, indem diese Überprüfung durchgeführt wird. Führen Sie hierzu die folgenden Schritte aus:  
  
-   Legen Sie die `audienceUriMode` Attribut des [ \<IssuedTokenAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) auf `Always` oder `BearerKeyOnly`.  
  
-   Geben Sie den Satz gültiger URIs an, indem Sie die URIs dieser Auflistung hinzufügen. Fügen Sie zu diesem Zweck ein [ \<hinzufügen >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md) für jeden URI  
  
 Weitere Informationen finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.  
  
 Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
#### <a name="allowing-anonymous-cardspace-users"></a>Zulassen anonymer CardSpace-Benutzer  
 Wenn Sie das `AllowUntrustedRsaIssuers`-Attribut des `<IssuedTokenAuthentication>`-Elements auf `true` setzen, dürfen alle Clients ein selbst ausgestelltes und mit einem beliebigen RSA-Schlüsselpaar signiertes Token vorweisen. Der Aussteller ist *nicht vertrauenswürdigen* , da der Schlüssel keine Aussteller Daten zugeordnet ist. [!INCLUDE[infocard](../../../../includes/infocard-md.md)]-Benutzer können eine selbst ausgestellte Karte mit von ihnen selbst bereitgestellten Identitätsansprüchen erstellen. Daher sollte diese Funktion nur mit Vorsicht verwendet werden. Falls Sie diese Funktion verwenden möchten, stellen Sie sich den öffentlichen RSA-Schlüssel als sichereres Kennwort vor, das mit dem Benutzernamen in einer Datenbank gespeichert werden sollte. Überprüfen Sie den vom Client vorgelegten öffentlichen RSA-Schlüssel, indem Sie ihn mit dem für diesen Benutzernamen gespeicherten öffentlichen Schlüssel vergleichen, bevor Sie einem Client Zugriff auf den Dienst gewähren. Dies setzt voraus, dass Sie einen Registrierungsvorgang eingerichtet haben, bei dem Benutzer ihre Benutzernamen registrieren und diesen die selbst ausgestellten öffentlichen RSA-Schlüssel zuordnen können.  
  
## <a name="client-credentials"></a>Clientanmeldeinformationen  
 Durch die Clientanmeldeinformationen wird der Client bei den Diensten authentifiziert, wenn eine gegenseitige Authentifizierung erforderlich ist. Sie können den Abschnitt zur Angabe von Dienstzertifikaten in Szenarien verwenden, bei denen der Client seine Nachrichten an einen Dienst mithilfe des Dienstzertifikats schützen muss.  
  
 Sie können einen Client auch als Teil eines Verbundszenarien konfigurieren, in dem die Token eines Sicherheitstokendiensts oder eines lokalen Tokenausstellers verwendet werden. Weitere Informationen über verbundene Szenarien finden Sie unter [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md). Anmeldeinformationen für alle Clients befinden sich unter dem [ \<EndpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md), wie im folgenden Code gezeigt.  
  
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
  
#### <a name="clientcertifictate-element"></a>\<ClientCertifictate >-Element  
 Legen Sie mit diesem Element das Zertifikat fest, mit dem der Client authentifiziert wird. Weitere Informationen finden Sie unter [Vorgehensweise: Angeben der Clientanmeldeinformationswerte](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
#### <a name="httpdigest"></a>\<HttpDigest >  
 Diese Funktion muss mit Active Directory unter Windows und unter IIS (Internet Information Services) aktiviert werden. Weitere Informationen finden Sie unter [Digestauthentifizierung in IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88443).  
  
#### <a name="issuedtoken-element"></a>\<IssuedToken >-Element  
 Die [ \<IssuedToken >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) enthält die Elemente, die zum Konfigurieren eines lokalen Tokenausstellers Token oder mit einem Sicherheitstokendienst verwendeten Verhalten verwendet. Anweisungen zum Konfigurieren eines Clients für einen lokalen Aussteller verwenden, finden Sie unter [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
#### <a name="localissueraddress"></a>\<localissueraddress-Eigenschaft >  
 Gibt eine Standardadresse für den Sicherheitstokendienst an. Wird verwendet, wenn die <xref:System.ServiceModel.WSFederationHttpBinding> stellt keine URL für den Sicherheitstokendienst oder wenn die Ausstelleradresse einer verbundbindung http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous oder `null`. In diesem Fall muss <xref:System.ServiceModel.Description.ClientCredentials> mit der Adresse des lokalen Ausstellers und der für die Kommunikation mit diesem Aussteller zu verwendenden Bindung konfiguriert werden.  
  
#### <a name="issuerchannelbehaviors"></a>\<IssuerChannelBehaviors >  
 Verwenden der [ \<IssuerChannelBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md) WCF Clientverhalten verwendet bei der Kommunikation mit einem Sicherheitstokendienst hinzufügen. Definieren von Clientverhalten in der [ \<EndpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) Abschnitt. Um einen definierten Verhalten verwenden, fügen eine <`add`>-Element der `<issuerChannelBehaviors>` Element mit zwei Attribute. Verwenden Sie für `issuerAddress` die URL des Sicherheitstokendiensts, und verwenden Sie für das `behaviorConfiguration`-Attribut den Namen des definierten Endpunktverhaltens, wie im folgenden Beispiel gezeigt:  
  
```xml  
<clientCredentials>  
   <issuedToken>  
      <issuerChannelBehaviors>  
         <add issuerAddress="http://www.contoso.com"  
               behaviorConfiguration="clientBehavior1" />     
```  
  
#### <a name="servicecertificate-element"></a>\<ServiceCertificate >-Element  
 Verwenden Sie dieses Element, um die Authentifizierung von Dienstzertifikaten zu steuern.  
  
 Die [ \<DefaultCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) Element kann ein einzelnes Zertifikat verwendet, wenn der Dienst kein Zertifikat gibt an, zu speichern.  
  
 Verwenden der [ \<ScopedCertificates >](../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md) und [ \<hinzufügen >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md) Dienstzertifikate festlegen, bestimmte Dienste zugeordnet sind. Das `<add>`-Element beinhaltet ein `targetUri`-Attribut, mit dem das Zertifikat dem Dienst zugeordnet wird.  
  
 Die [ \<Authentifizierung >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) Element gibt die Ebene der Vertrauenswürdigkeit verwendet, um Zertifikate zu authentifizieren. Standardmäßig wird die Stufe "ChainTrust" verwendet, die angibt, dass jedes Zertifikat in einer Zertifizierungshierarchie zu finden sein muss, die in eine vertrauenswürdige Zertifizierungsstelle am Anfang der Kette mündet. Dies ist der sicherste Modus. Sie können auch den Wert "PeerOrChainTrust" verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate (Peervertrauen) akzeptiert werden. Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen. Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert "ChainTrust". Sie können auch den Wert "Custom" bzw. "None" verwenden. Wenn Sie "Custom" verwenden möchten, müssen Sie für das `CustomCertificateValidatorType`-Attribut zudem ein Assembly und einen Typ, mit dem das Zertifikat überprüft wird, festlegen. Wenn Sie Ihre eigene Überprüfung erstellen möchten, müssen Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator>-Klasse vererben. Weitere Informationen finden Sie unter [Vorgehensweise: erstellen ein Diensts, der ein benutzerdefiniertes Zertifikats-Validierungssteuerelement verwendet](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
 Die [ \<Authentifizierung >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) Element enthält eine `RevocationMode` Attribut, das angibt, wie Zertifikate auf eine Sperre hin überprüft werden. Der Standardwert ist "online", wodurch angegeben wird, dass Zertifikate automatisch auf eine Sperre hin überprüft werden. Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## <a name="serviceauthorization"></a>ServiceAuthorization  
 Die [ \<ServiceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) -Element enthält Elemente, die Autorisierung, benutzerspezifische Rollenanbieter und den Identitätswechsel beeinflussen.  
  
 Die <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Klasse wird auf eine Dienstmethode angewendet. Das Attribut gibt die Benutzergruppen an, mit denen die Verwendung einer geschützten Methode autorisiert wird. Der Standardwert lautet "UseWindowsGroups". Er gibt an, das in Windows-Gruppen wie der der Administratoren oder Benutzer nach einer Identität gesucht wird, die versucht, auf eine Ressource zuzugreifen. Sie können auch "UseAspNetRoles" angeben, einen benutzerdefinierten Rollenanbieter verwenden, klicken Sie unter konfiguriert ist, das <`system.web` > Element, wie im folgenden Code dargestellt.  
  
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
 Verwenden der [ \<ServiceSecurityAudit >](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) an das Protokoll geschrieben, und welche Arten von zu protokollierende Ereignisse. Weitere Informationen finden Sie unter [Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
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
 Das Exportieren von Metadaten auf Clients ist hilfreich für Dienst- und Cliententwickler, da so das Herunterladen von Konfigurations- und Clientcode möglich wird. Damit der Dienst möglichst gut vor böswilligen Benutzern geschützt wird, können Sie für die Übertragung den HTTPS-Mechanismus (SSL über HTTP) verwenden. Hierfür müssen Sie zunächst ein geeignetes X.509-Zertifikat an einen bestimmten Port des Computers, auf dem der Dienst gehostet wird, binden. (Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Zweitens, Hinzufügen einer [ \<ServiceMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) auf der Dienstkonfiguration und die `HttpsGetEnabled` -Attribut auf `true`. Setzen Sie abschließend wie im folgenden Beispiel gezeigt das `HttpsGetUrl`-Attribut auf den URL des Dienstmetadaten-Endpunkts:  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [Sicherheitsmodell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
