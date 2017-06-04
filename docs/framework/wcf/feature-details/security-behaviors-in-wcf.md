---
title: "Sicherheitsverhalten in WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 513232c0-39fd-4409-bda6-5ebd5e0ea7b0
caps.latest.revision: 23
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 23
---
# Sicherheitsverhalten in WCF
In [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] beeinflussen Verhalten das Laufzeitverhalten auf Dienstebene bzw. auf Endpunktebene.\([!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Verhaltensweisen im Allgemeinen finden Sie unter [Angeben des Dienstlaufzeitverhaltens](../../../../docs/framework/wcf/specifying-service-run-time-behavior.md).\) *Sicherheitsverhalten* geben Ihnen die Kontrolle über Anmeldeinformationen, Authentifizierung und Autorisierung und über Überwachungsprotokolle.Sie können Verhalten entweder mittels Programmierung oder mittels Konfiguration verwenden.In diesem Thema wird die Konfiguration der folgenden, auf Sicherheitsfunktionen bezogenen Verhalten erläutert:  
  
-   [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).  
  
-   [\<clientCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).  
  
-   [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md).  
  
-   [\<serviceSecurityAudit\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md).  
  
-   [\<serviceMetadata\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md): Bei diesem Element haben Sie zudem die Möglichkeit, einen sicheren Endpunkt festzulegen, der Clients Zugriff auf Metadaten bietet.  
  
## Festlegen von Anmeldeinformationen mithilfe von Verhalten  
 Legen Sie die Anmeldeinformationswerte für einen Dienst oder Client über das [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) und das [\<clientCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) fest.Durch die zugrunde liegende Bindungskonfiguration wird vorgegeben, ob Anmeldeinformationen festgelegt werden müssen.Wenn beispielsweise für den Sicherheitsmodus der Wert `None` gewählt wurde, findet keine gegenseitige Authentifizierung von Clients und Diensten statt. Es sind daher keine Anmeldeinformationen erforderlich.  
  
 Andererseits kann es sein, dass die Dienstbindung eine Art von Clientanmeldeinformation erfordert.In diesem Fall müssen Sie eventuell mithilfe eines Verhaltens einen Wert für die Anmeldeinformationen festlegen.\([!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu den möglichen Arten von Anmeldeinformationen finden Sie unter [Wählen eines Typs von Anmeldeinformationen](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).\) Gelegentlich wird der tatsächliche Anmeldeinformationswert automatisch durch die Umgebung festgesetzt, zum Beispiel bei Verwendung von Windows\-Anmeldeinformationen für die Authentifizierung. In diesem Fall müssen Sie den Wert für die Anmeldeinformationen nicht explizit festlegen, außer Sie möchten andere Anmeldeinformationen verwenden.  
  
 Alle Dienstanmeldeinformationen sind untergeordnete Elemente und im [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) zu finden.Im folgenden Beispiel wird ein Zertifikat als Dienstanmeldeinformation verwendet:  
  
```  
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
  
## Dienstanmeldeinformationen  
 Das [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) verfügt über vier untergeordnete Elemente.Diese Elemente und ihre Verwendung werden in den folgenden Abschnitten vorgestellt.  
  
### \<serviceCertificate\>\-Element  
 Geben Sie mit diesem Element ein X.509\-Zertifikat an, mit dem der Dienst bei den Clients im Modus für die Nachrichtensicherheit authentifiziert wird.Falls Sie ein Zertifikat verwenden, das immer wieder erneuert wird, ändert sich sein Fingerabdruck.Verwenden Sie in diesem Fall den Antragstellernamen als `X509FindType`, da das Zertifikat erneut mit demselben Antragstellernamen ausgestellt werden kann.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Verwendung des Elements finden Sie unter [Gewusst wie: Angeben der Clientanmeldeinformationswerte](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
### \<certificate\>\-Element des \<clientCertificate\>\-Elements  
 Verwenden Sie das [\<certificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)\-Element, wenn dem Dienst das Zertifikat des Clients im Voraus bekannt sein muss, damit eine sichere Kommunikation mit dem Client stattfinden kann.Dies ist bei der Duplexkommunikation der Fall.Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Schutz seiner Antwort an den Client verwendet wird.Bei der Duplexkommunikation gibt es keine Anforderungen und Antworten.Der Dienst kann das Zertifikat des Clients nicht aus der Kommunikation ableiten. Daher muss der Dienst bereits im Voraus über das Clientzertifikat verfügen, um seine Nachricht an den Client schützen zu können.Sie müssen das Zertifikat des Clients in einer Out\-of\-Band\-Aushandlung beziehen und das Zertifikat mit diesem Element angeben.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Duplexdiensten finden Sie unter [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
### \<authentication\>\-Element des \<clientCertificate\>\-Elements  
 Mit dem [\<authentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)\-Element können Sie die Art der Clientauthentifizierung anpassen.Sie können als Wert für das `CertificateValidationMode`\-Attribut `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` oder `Custom` festlegen.Standardmäßig wird die Stufe `ChainTrust` verwendet, die angibt, dass jedes Zertifikat in einer Zertifizierungshierarchie zu finden sein muss, die in eine *Stammzertifizierungsstelle* am Anfang der Kette mündet.Dies ist der sicherste Modus.Sie können auch den Wert `PeerOrChainTrust` verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate \(Peervertrauen\) akzeptiert werden.Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen.Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert `ChainTrust`.Sie können den Wert auch auf `Custom` setzen.Wenn Sie den Wert `Custom` verwenden, müssen Sie für das `CustomCertificateValidatorType`\-Attribut zudem ein Assembly und einen Typ, mit dem das Zertifikat überprüft wird, festlegen.Wenn Sie Ihre eigene Validierung erstellen möchten, müssen Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator>\-Klasse vererben.  
  
### \<issuedTokenAuthentication\>\-Element  
 Das Szenario für ausgestellte Token weist drei Phasen auf.In der ersten Phase wird ein Client, der versucht, auf einen Dienst zuzugreifen, an einen *Sicherheitstokendienst* \(Security Token Service, STS\) verwiesen.Der STS authentifiziert den Client und stellt dann ein Token \(in der Regel ein SAML\-Token \(SAML \= Security Assertions Markup Language, XML\-basierte Auszeichnungssprache für Sicherheitsbestätigungen\) für den Client aus.Der Client kehrt dann mit dem Token zum Dienst zurück.Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben.Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.Das [\<issuedTokenAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)\-Element ist das Repository für die Zertifikate des Sicherheitstokendiensts.Verwenden Sie zum Hinzufügen von Zertifikaten das [\<knownCertificates\>](../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).Fügen Sie wie im folgenden Beispiel gezeigt ein [\<add\>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) für jedes Zertifikat ein.  
  
```  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden.Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.  
  
 Verwenden Sie die [\<allowedAudienceUris\>](../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)\-Auflistung in einer Verbundanwendung, die einen *Sicherheitstokendienst* \(Security Token Service, STS\) nutzt, der `SamlSecurityToken`\-Sicherheitstoken ausstellt.Wenn der STS das Sicherheitstoken ausstellt, kann er den URI des Webdiensts angeben, für den das Sicherheitstoken verwendet werden soll, indem `SamlAudienceRestrictionCondition` dem Sicherheitstoken hinzugefügt wird.Der `SamlSecurityTokenAuthenticator` für den Webdienst kann so überprüfen, ob das ausgestellte Sicherheitstoken für diesen Webdienst ausgelegt ist, indem diese Überprüfung durchgeführt wird. Führen Sie hierzu die folgenden Schritte aus:  
  
-   Legen Sie das `audienceUriMode`\-Attribut für [\<issuedTokenAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) auf `Always` oder auf `BearerKeyOnly` fest.  
  
-   Geben Sie den Satz gültiger URIs an, indem Sie die URIs dieser Auflistung hinzufügen.Fügen Sie hierzu für jeden URI ein [\<add\>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md) ein.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Verwendung dieses Konfigurationselements finden Sie unter [Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
#### Zulassen anonymer CardSpace\-Benutzer  
 Wenn Sie das `AllowUntrustedRsaIssuers`\-Attribut des `<IssuedTokenAuthentication>`\-Elements auf `true` setzen, dürfen alle Clients ein selbst ausgestelltes und mit einem beliebigen RSA\-Schlüsselpaar signiertes Token vorweisen.Der Aussteller ist *nicht vertrauenswürdig*, da dem Schlüssel keine Ausstellerdaten zugeordnet sind.[!INCLUDE[infocard](../../../../includes/infocard-md.md)]\-Benutzer können eine selbst ausgestellte Karte mit von ihnen selbst bereitgestellten Identitätsansprüchen erstellen.Daher sollte diese Funktion nur mit Vorsicht verwendet werden.Falls Sie diese Funktion verwenden möchten, stellen Sie sich den öffentlichen RSA\-Schlüssel als sichereres Kennwort vor, das mit dem Benutzernamen in einer Datenbank gespeichert werden sollte.Überprüfen Sie den vom Client vorgelegten öffentlichen RSA\-Schlüssel, indem Sie ihn mit dem für diesen Benutzernamen gespeicherten öffentlichen Schlüssel vergleichen, bevor Sie einem Client Zugriff auf den Dienst gewähren.Dies setzt voraus, dass Sie einen Registrierungsvorgang eingerichtet haben, bei dem Benutzer ihre Benutzernamen registrieren und diesen die selbst ausgestellten öffentlichen RSA\-Schlüssel zuordnen können.  
  
## Clientanmeldeinformationen  
 Durch die Clientanmeldeinformationen wird der Client bei den Diensten authentifiziert, wenn eine gegenseitige Authentifizierung erforderlich ist.Sie können den Abschnitt zur Angabe von Dienstzertifikaten in Szenarien verwenden, bei denen der Client seine Nachrichten an einen Dienst mithilfe des Dienstzertifikats schützen muss.  
  
 Sie können einen Client auch als Teil eines Verbundszenarien konfigurieren, in dem die Token eines Sicherheitstokendiensts oder eines lokalen Tokenausstellers verwendet werden.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Verbundszenarien finden Sie unter [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).Alle Clientanmeldeinformationen befinden sich wie im folgenden Code zu sehen im [\<endpointBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md).  
  
```  
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
  
#### \<clientCertifictate\>\-Element  
 Legen Sie mit diesem Element das Zertifikat fest, mit dem der Client authentifiziert wird.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Gewusst wie: Angeben der Clientanmeldeinformationswerte](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
#### \<httpDigest\>  
 Für diese Funktion müssen Active Directory unter Windows und die Internetinformationsdienste \(IIS\) aktiviert sein.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Digestauthentifizierung in IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88443) \(möglicherweise in englischer Sprache\).  
  
#### \<issuedToken\>\-Element  
 Das [\<issuedToken\>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) enthält die Elemente, die zum Konfigurieren eines lokalen Tokenausstellers verwendet werden, bzw. die mit einem Sicherheitstokendienst verwendeten Verhalten.Anweisungen, wie Sie einen Client für die Verwendung eines lokalen Ausstellers konfigurieren können, finden Sie unter [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
#### \<localIssuerAddress\>  
 Gibt eine Standardadresse für den Sicherheitstokendienst an.Diese Adresse wird verwendet, wenn die <xref:System.ServiceModel.WSFederationHttpBinding> keine URL für den Sicherheitstokendienst bereitstellt oder wenn die Ausstelleradresse einer Verbundbindung http:\/\/schemas.microsoft.com\/2005\/12\/ServiceModel\/Addressing\/Anonymous bzw. `null` lautet.In diesem Fall muss <xref:System.ServiceModel.Description.ClientCredentials> mit der Adresse des lokalen Ausstellers und der für die Kommunikation mit diesem Aussteller zu verwendenden Bindung konfiguriert werden.  
  
#### \<issuerChannelBehaviors\>  
 Fügen Sie mit dem [\<issuerChannelBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientverhalten hinzu, die bei der Kommunikation mit einem Sicherheitstokendienst verwendet werden.Definieren Sie Clientverhalten im [\<endpointBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)\-Abschnitt.Fügen Sie dem `<issuerChannelBehaviors>`\-Element ein \<`add`\>\-Element mit zwei Attributen hinzu, um ein definiertes Verhalten zu verwenden.Verwenden Sie für `issuerAddress` die URL des Sicherheitstokendiensts, und verwenden Sie für das `behaviorConfiguration`\-Attribut den Namen des definierten Endpunktverhaltens, wie im folgenden Beispiel gezeigt:  
  
```  
<clientCredentials>  
   <issuedToken>  
      <issuerChannelBehaviors>  
         <add issuerAddress="http://www.contoso.com"  
               behaviorConfiguration="clientBehavior1" />     
```  
  
#### \<serviceCertificate\>\-Element  
 Verwenden Sie dieses Element, um die Authentifizierung von Dienstzertifikaten zu steuern.  
  
 Das [\<defaultCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)\-Element kann ein einzelnes Zertifikat speichern, das verwendet wird, wenn der Dienst kein Zertifikat angibt.  
  
 Verwenden Sie das [\<scopedCertificates\>](../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)\-Element und das [\<add\>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md), um Dienstzertifikate festzulegen, die bestimmten Diensten zugeordnet sind.Das `<add>`\-Element beinhaltet ein `targetUri`\-Attribut, mit dem das Zertifikat dem Dienst zugeordnet wird.  
  
 Mit dem [\<Authentifizierung\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)\-Element wird die Ebene der Vertrauenswürdigkeit angegeben, mit der Zertifikate authentifiziert werden.Standardmäßig wird die Stufe "ChainTrust" verwendet, die angibt, dass jedes Zertifikat in einer Zertifizierungshierarchie zu finden sein muss, die in eine vertrauenswürdige Zertifizierungsstelle am Anfang der Kette mündet.Dies ist der sicherste Modus.Sie können auch den Wert "PeerOrChainTrust" verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate \(Peervertrauen\) akzeptiert werden.Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen.Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert "ChainTrust".Sie können auch den Wert "Custom" bzw. "None" verwenden. Wenn Sie "Custom" verwenden möchten, müssen Sie für das `CustomCertificateValidatorType`\-Attribut zudem ein Assembly und einen Typ, mit dem das Zertifikat überprüft wird, festlegen.Wenn Sie Ihre eigene Überprüfung erstellen möchten, müssen Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator>\-Klasse vererben.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vorgehensweise: Erstellen eines Dienstes, der ein benutzerdefiniertes Zertifikats\-Validierungssteuerelement verwendet](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
 Das [\<Authentifizierung\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)\-Element beinhaltet ein `RevocationMode`\-Attribut, das angibt, wie Zertifikate auf eine Sperre hin überprüft werden.Der Standardwert ist "online", wodurch angegeben wird, dass Zertifikate automatisch auf eine Sperre hin überprüft werden.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## ServiceAuthorization  
 Das [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)\-Element enthält Elemente, die sich auf die Autorisierung, benutzerspezifische Rollenanbieter und den Identitätswechsel auswirken.  
  
 Die <xref:System.Security.Permissions.PrincipalPermissionAttribute>\-Klasse wird auf eine Dienstmethode angewendet.Das Attribut gibt die Benutzergruppen an, mit denen die Verwendung einer geschützten Methode autorisiert wird.Der Standardwert lautet "UseWindowsGroups". Er gibt an, das in Windows\-Gruppen wie der der Administratoren oder Benutzer nach einer Identität gesucht wird, die versucht, auf eine Ressource zuzugreifen.Sie können auch "UseAspNetRoles" angeben, damit ein benutzerspezifischer, unter dem \<`system.web` \>\-Element konfigurierter Rollenanbieter verwendet wird, wie im folgenden Code zu sehen ist.  
  
```  
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
  
 Im folgenden Code wird `roleProviderName` mit dem `principalPermissionMode`\-Attribut verwendet.  
  
```  
<behaviors>  
 <behavior name="ServiceBehaviour">          
  <serviceAuthorization principalPermissionMode ="UseAspNetRoles"   
                        roleProviderName ="SqlProvider" />  
</behavior>   
   <!-- Other configuration code not shown. -->  
</behaviors>  
```  
  
## Konfigurieren der Sicherheitsüberwachung  
 Legen Sie mit dem [\<serviceSecurityAudit\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) fest, in welches Protokoll geschrieben wird und welche Arten von Ereignissen protokolliert werden sollen.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
```  
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
  
## Sicherer Metadatenaustausch  
 Das Exportieren von Metadaten auf Clients ist hilfreich für Dienst\- und Cliententwickler, da so das Herunterladen von Konfigurations\- und Clientcode möglich wird.Damit der Dienst möglichst gut vor böswilligen Benutzern geschützt wird, können Sie für die Übertragung den HTTPS\-Mechanismus \(SSL über HTTP\) verwenden.Hierfür müssen Sie zunächst ein geeignetes X.509\-Zertifikat an einen bestimmten Port des Computers, auf dem der Dienst gehostet wird, binden.\([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).\) Fügen Sie dann der Dienstkonfiguration ein [\<serviceMetadata\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) hinzu, und legen Sie für das `HttpsGetEnabled`\-Attribut den Wert `true` fest.Legen Sie abschließend, wie im folgenden Beispiel veranschaulicht, das `HttpsGetUrl`\-Attribut auf die URL des Dienstmetadatenendpunkts fest.  
  
```  
<behaviors>  
 <serviceBehaviors>  
  <behavior name="NewBehavior">  
    <serviceMetadata httpsGetEnabled="true"   
     httpsGetUrl="https://myComputerName/myEndpoint" />  
  </behavior>  
 </serviceBehaviors>  
</behaviors>  
```  
  
## Siehe auch  
 [Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)   
 [Sicherheitsmodell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)