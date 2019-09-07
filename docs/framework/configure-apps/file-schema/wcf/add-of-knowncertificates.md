---
title: <add> von <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 29b067e6ec20992084f9ab3bab087222bdd56da2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400620"
---
# <a name="add-of-knowncertificates"></a>\<Fügen Sie > \<von knownzertifikate hinzu >
Fügt ein X.509-Zertifikat zur Auflistung bekannter Zertifikate hinzu.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<servicecreden->** ](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<IssuedTokenAuthentication->** ](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<knownzertifikate->** ](knowncertificates.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|findValue|Zeichenfolge. Der zu suchende Wert.|  
|storeLocation|Enumeration. Einer der beiden zu durchsuchenden Speicherorte.|  
|storeName|Enumeration. Einer der zu durchsuchenden Systemspeicher.|  
|x509FindType|Enumeration. Eines der zu durchsuchenden Zertifikatfelder.|  
  
## <a name="findvalue-attribute"></a>findValue-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Zeichenfolge|Der Wert ist vom zu durchsuchenden Feld (das durch das X509FindType-Attribut angegeben wird) abhängig. Wenn Sie beispielsweise nach einem Fingerabdruck suchen, muss der Wert eine Zeichenfolge aus hexadezimalen Zahlen sein.|  
  
## <a name="x509findtype-attribute"></a>x509FindType-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Enumeration|Mögliche Werte: FindByThumbprint, findbysubjetname, findbysubjetissushedname, FindByIssuerName, findbyissuererkennbar shedname, findbyserialnumber, FindByTimeValid, FindByTimeNotYetValid, findbyserialnumber, findbytimeabgelauf, findbytemplatename , Findbyapplicationpolicy, findbycertificatepolicy, findbyextension, findbykeyusage, findbysubjetkeyidentifier.|  
  
## <a name="storelocation-attribute"></a>storeLocation-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Enumeration|CurrentUser oder LocalMachine.|  
  
## <a name="storename-attribute"></a>storeName-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Enumeration|Mögliche Werte: Addressbook, AuthRoot, CertificateAuthority, unallowed, my, root, treuhändpeople und Treuhänder Publisher.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<knownzertifikate->](knowncertificates.md)|Gibt eine Auflistung von X.509-Zertifikaten wieder, die von einem Sicherheitstokendienst für die Validierung von Sicherheitstoken bereitgestellt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Das Szenario für ausgestellte Token weist drei Phasen auf. In der ersten Phase wird ein Client, der versucht, auf einen Dienst zuzugreifen, als *sicherer Tokendienst*bezeichnet. Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus. Der Client kehrt dann mit dem Token zum Dienst zurück. Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben. Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.  
  
 [ Das\<IssuedTokenAuthentication->](issuedtokenauthentication-of-servicecredentials.md) -Element ist das Repository für alle solchen Zertifikate des Sicherheitstokendiensts. Verwenden Sie zum Hinzufügen von Zertifikaten die [ \<> Known-Zertifikate](knowncertificates.md). Fügen Sie für jedes Zertifikat, wie im folgenden Beispiel gezeigt, ein [ \<Add >- \<Element >-Element](add-of-knowncertificates.md) für jedes Zertifikat hinzu.  
  
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
  
 Informationen zum Überprüfen der Bedingungen, die für die Authentifizierung eines Clients durch einen Verbund Dienst erforderlich sind, sowie weitere Informationen zur Verwendung dieses Konfigurations Elements finden [Sie unter Gewusst wie: Konfigurieren Sie die Anmelde Informationen](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)für einen Verbunddienst. Weitere Informationen zu Verbund Szenarien finden Sie unter Verbund [-und ausgestellte Token](../../../wcf/feature-details/federation-and-issued-tokens.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Zertifikat dem Repository für beliebige STS-Zertifikate hinzugefügt.  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <serviceCredentials>
      <issuedTokenAuthentication>
        <knownCertificates>
          <add findValue="www.contoso.com"
               storeLocation="LocalMachine"
               storeName="CertificateAuthority"
               x509FindType="FindByIssuerName" />
        </knownCertificates>
      </issuedTokenAuthentication>
    </serviceCredentials>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<knownzertifikate->](knowncertificates.md)
- [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md)
- [Verbund und ausgestellte Token](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Vorgehensweise: Konfigurieren von Anmelde Informationen für eine Verbunddienst](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
