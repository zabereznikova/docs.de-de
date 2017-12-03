---
title: '&lt;issuedTokenAuthentication&gt; von &lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 75c3caa128018877b95824b4bad34aee331c4dab
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuedtokenauthenticationgt-of-ltservicecredentialsgt"></a>&lt;issuedTokenAuthentication&gt; von &lt;serviceCredentials&gt;
Gibt ein als Dienstanmeldeinformationen ausgegebenes Token an.  
  
 \<System. ServiceModel >  
\<Verhalten >  
\<ServiceBehaviors >  
\<Verhalten >  
\<ServiceCredentials >  
\<IssuedTokenAuthentication >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<issuedTokenAuthentication   
   allowUntrustedRsaIssuers="Boolean"  
   audienceUriMode="Always/BearerKeyOnly/Never"  
      customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   samlSerializer="String"  
    trustedStoreLocation="CurrentUser/LocalMachine">  
      <allowedAudienceUris>  
      <add allowedAudienceUri="String"/>  
      </allowedAudienceUris>  
      <knownCertificates>   
         <add findValue="String"  
                 storeLocation="CurrentUser/LocalMachine"  
                storeName=" CurrentUser/LocalMachine"  
                x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
      </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`allowedAudienceUris`|Ruft den Satz von Ziel-URIs ab, für die das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass diese von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft werden. Weitere Informationen zur Verwendung dieses Attributs finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.|  
|`allowUntrustedRsaIssuers`|Ein boolescher Wert, der angibt, ob nicht vertrauenswürdige RSA-Zertifikataussteller zulässig sind.<br /><br /> Zertifikate werden von Zertifizierungsstellen signiert, damit die Echtheit überprüft wird. Ein nicht vertrauenswürdiger Aussteller ist eine Zertifizierungsstelle, die zum Signieren von Zertifikaten als nicht vertrauenswürdig gekennzeichnet ist.|  
|`audienceUriMode`|Ruft einen Wert ab, der angibt, ob <xref:System.IdentityModel.Tokens.SamlSecurityToken> des <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>-Sicherheitstokens überprüft werden sollte. Dieser Wert ist vom Typ <xref:System.IdentityModel.Selectors.AudienceUriMode>. Weitere Informationen zur Verwendung dieses Attributs finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.|  
|`certificateValidationMode`|Legt den Zertifikatüberprüfungsmodus fest. Einer der gültigen Werte von <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden. Die Standardeinstellung ist `ChainTrust`.|  
|`customCertificateValidatorType`|Optionale Zeichenfolge. Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden. Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.|  
|`revocationMode`|Legt den Sperrmodus fest, der angibt, ob eine Sperrüberprüfung ausgeführt wird und ob diese online oder offline erfolgt. Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.|  
|`samlSerializer`|Ein optionales Zeichenfolgenattribut, das den SamlSerializer-Typ angibt, der für die Dienstanmeldeinformationen verwendet wird. Der Standardwert ist eine leere Zeichenfolge.|  
|`trustedStoreLocation`|Optionale Enumeration. Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`knownCertificates`|Gibt eine Auflistung von <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>-Elementen an, die vertrauenswürdige Aussteller für die Dienstanmeldeinformationen definieren.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ServiceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.|  
  
## <a name="remarks"></a>Hinweise  
 Das Szenario für ausgestellte Token weist drei Phasen auf. In der ersten Phase wird ein Client versucht, auf einen Dienst zuzugreifen bezeichnet einen *sicheren Tokendienst*. Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus. Der Client kehrt dann mit dem Token zum Dienst zurück. Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben. Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.  
  
 Dieses Element ist das Repository für die Zertifikate des Sicherheitstokendiensts. Verwenden Sie zum Hinzufügen von Zertifikaten der [ \<KnownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md). Fügen Sie ein [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) für jedes Zertifikat, wie im folgenden Beispiel gezeigt.  
  
```xml  
<issuedTokenAuthorization>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden. Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.  
  
 Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Vorgehensweise: Konfigurieren Sie Anmeldeinformationen in einem Verbunddienst](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
