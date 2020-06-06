---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 23fe19258e09e9e8a5e05a94ccef0e40ee1cb5fd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400334"
---
# \<knownCertificates>
Gibt eine Auflistung von X.509-Zertifikaten wieder, die zum Authentifizieren von Sicherheitsanmeldeinformationen eines Sicherheitstokendiensts bereitgestellt werden.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<add>](add-of-knowncertificates.md)|Fügt der Auflistung ein X.509-Zertifikat hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|Gibt ein Token an, das als Dienstanmeldeinformation ausgegeben wird.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das Szenario für ausgestellte Token weist drei Phasen auf. In der ersten Phase wird ein Client, der versucht, auf einen Dienst zuzugreifen, als *sicherer Tokendienst*bezeichnet. Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus. Der Client kehrt dann mit dem Token zum Dienst zurück. Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben. Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.  
  
 Das- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) Element ist das Repository für alle solchen Zertifikate des Sicherheitstokendiensts. Verwenden Sie das- [ \<knownCertificates> Element](knowncertificates.md), um Zertifikate hinzuzufügen. Fügen Sie ein [\<add>](add-of-knowncertificates.md) für jedes Zertifikat ein, wie im folgenden Beispiel gezeigt.  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden. Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.  
  
 Informationen zum Überprüfen der Bedingungen, die für die Authentifizierung eines Clients durch einen Verbund Dienst erforderlich sind, sowie weitere Informationen zur Verwendung dieses Konfigurations Elements finden Sie unter Vorgehens [Weise: Konfigurieren von Anmelde Informationen auf einem Verbunddienst](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md). Weitere Informationen zu Verbund Szenarien finden Sie unter Verbund [-und ausgestellte Token](../../../wcf/feature-details/federation-and-issued-tokens.md).  
  
 Ein Beispiel, das zeigt, wie die-Auflistung in der-Konfiguration aufgefüllt wird, finden Sie unter [\<add>](add-of-knowncertificates.md) .  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<add>](add-of-knowncertificates.md)
- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)
- [Sicherheitsverhalten](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Verwenden von Zertifikaten](../../../wcf/feature-details/working-with-certificates.md)
- [Verbund und ausgestellte Token](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-knowncertificates.md)
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
