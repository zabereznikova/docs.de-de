---
title: <issuedTokenAuthentication> von <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: 6d468a27ee05fb4dd8cf087d10e5d170783d3454
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400359"
---
# <a name="issuedtokenauthentication-of-servicecredentials"></a><span data-ttu-id="33a33-102">\<issuedTokenAuthentication> von \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="33a33-102">\<issuedTokenAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="33a33-103">Gibt ein als Dienstanmeldeinformationen ausgegebenes Token an.</span><span class="sxs-lookup"><span data-stu-id="33a33-103">Specifies a custom token issued as a service credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="33a33-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33a33-104">Syntax</span></span>  
  
```xml  
<issuedTokenAuthentication allowUntrustedRsaIssuers="Boolean"
                           audienceUriMode="Always/BearerKeyOnly/Never"
                           customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                           certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                           revocationMode="NoCheck/Online/Offline"
                           samlSerializer="String"
                           trustedStoreLocation="CurrentUser/LocalMachine">
  <allowedAudienceUris>
    <add allowedAudienceUri="String" />
  </allowedAudienceUris>
  <knownCertificates>
    <add findValue="String"
         storeLocation="CurrentUser/LocalMachine"
         storeName=" CurrentUser/LocalMachine"
         x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33a33-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="33a33-105">Attributes and Elements</span></span>  
 <span data-ttu-id="33a33-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="33a33-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33a33-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="33a33-107">Attributes</span></span>  
  
|<span data-ttu-id="33a33-108">attribute</span><span class="sxs-lookup"><span data-stu-id="33a33-108">Attribute</span></span>|<span data-ttu-id="33a33-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="33a33-109">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="33a33-110">Ruft den Satz von Ziel-URIs ab, für die das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass diese von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="33a33-110">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="33a33-111">Weitere Informationen zur Verwendung dieses Attributs finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span><span class="sxs-lookup"><span data-stu-id="33a33-111">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="33a33-112">Ein boolescher Wert, der angibt, ob nicht vertrauenswürdige RSA-Zertifikataussteller zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="33a33-112">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="33a33-113">Zertifikate werden von Zertifizierungsstellen signiert, damit die Echtheit überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="33a33-113">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="33a33-114">Ein nicht vertrauenswürdiger Aussteller ist eine Zertifizierungsstelle, die zum Signieren von Zertifikaten als nicht vertrauenswürdig gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="33a33-114">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="33a33-115">Ruft einen Wert ab, der angibt, ob <xref:System.IdentityModel.Tokens.SamlSecurityToken> des <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>-Sicherheitstokens überprüft werden sollte.</span><span class="sxs-lookup"><span data-stu-id="33a33-115">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="33a33-116">Dieser Wert ist vom Typ <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span><span class="sxs-lookup"><span data-stu-id="33a33-116">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="33a33-117">Weitere Informationen zur Verwendung dieses Attributs finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="33a33-117">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="33a33-118">Legt den Zertifikatvalidierungsmodus fest.</span><span class="sxs-lookup"><span data-stu-id="33a33-118">Sets the certificate validation mode.</span></span> <span data-ttu-id="33a33-119">Einer der gültigen Werte von <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="33a33-119">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="33a33-120">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="33a33-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="33a33-121">Der Standardwert lautet `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="33a33-121">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="33a33-122">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="33a33-122">Optional string.</span></span> <span data-ttu-id="33a33-123">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33a33-123">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="33a33-124">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="33a33-124">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="33a33-125">Legt den Sperrmodus fest, der angibt, ob eine Sperrüberprüfung ausgeführt wird und ob diese online oder offline erfolgt.</span><span class="sxs-lookup"><span data-stu-id="33a33-125">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="33a33-126">Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="33a33-126">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="33a33-127">Ein optionales Zeichenfolgenattribut, das den SamlSerializer-Typ angibt, der für die Dienstanmeldeinformationen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="33a33-127">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="33a33-128">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="33a33-128">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="33a33-129">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="33a33-129">Optional enumeration.</span></span> <span data-ttu-id="33a33-130">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="33a33-130">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33a33-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="33a33-131">Child Elements</span></span>  
  
|<span data-ttu-id="33a33-132">Element</span><span class="sxs-lookup"><span data-stu-id="33a33-132">Element</span></span>|<span data-ttu-id="33a33-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33a33-133">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="33a33-134">Gibt eine Auflistung von <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>-Elementen an, die vertrauenswürdige Aussteller für die Dienstanmeldeinformationen definieren.</span><span class="sxs-lookup"><span data-stu-id="33a33-134">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33a33-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="33a33-135">Parent Elements</span></span>  
  
|<span data-ttu-id="33a33-136">Element</span><span class="sxs-lookup"><span data-stu-id="33a33-136">Element</span></span>|<span data-ttu-id="33a33-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33a33-137">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="33a33-138">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="33a33-138">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33a33-139">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="33a33-139">Remarks</span></span>  
 <span data-ttu-id="33a33-140">Das Szenario für ausgestellte Token weist drei Phasen auf.</span><span class="sxs-lookup"><span data-stu-id="33a33-140">The issued token scenario has three stages.</span></span> <span data-ttu-id="33a33-141">In der ersten Phase wird ein Client, der versucht, auf einen Dienst zuzugreifen, als *sicherer Tokendienst*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="33a33-141">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="33a33-142">Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus.</span><span class="sxs-lookup"><span data-stu-id="33a33-142">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="33a33-143">Der Client kehrt dann mit dem Token zum Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="33a33-143">The client then returns to the service with the token.</span></span> <span data-ttu-id="33a33-144">Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben.</span><span class="sxs-lookup"><span data-stu-id="33a33-144">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="33a33-145">Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="33a33-145">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="33a33-146">Dieses Element ist das Repository für die Zertifikate des Sicherheitstokendiensts.</span><span class="sxs-lookup"><span data-stu-id="33a33-146">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="33a33-147">Verwenden Sie zum Hinzufügen von Zertifikaten [\<knownCertificates>](knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="33a33-147">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="33a33-148">Fügen Sie ein [\<add>](add-of-knowncertificates.md) für jedes Zertifikat ein, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="33a33-148">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="33a33-149">Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden.</span><span class="sxs-lookup"><span data-stu-id="33a33-149">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="33a33-150">Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="33a33-150">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="33a33-151">Weitere Informationen zur Verwendung dieses Konfigurations Elements finden Sie unter Vorgehens [Weise: Konfigurieren von Anmelde Informationen auf einem Verbunddienst](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="33a33-151">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33a33-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33a33-152">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>
- [<span data-ttu-id="33a33-153">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="33a33-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="33a33-154">Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="33a33-154">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
