---
title: <issuedTokenAuthentication> von <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: d093b45269b230b4ff074d07a66290ab09592f60
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178567"
---
# <a name="issuedtokenauthentication-of-servicecredentials"></a><span data-ttu-id="1aa8f-102">\<issuedTokenAuthentication> of \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1aa8f-102">\<issuedTokenAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="1aa8f-103">Gibt ein als Dienstanmeldeinformationen ausgegebenes Token an.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-103">Specifies a custom token issued as a service credential.</span></span>  
  
 <span data-ttu-id="1aa8f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1aa8f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1aa8f-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="1aa8f-105">\<behaviors></span></span>  
<span data-ttu-id="1aa8f-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1aa8f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1aa8f-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1aa8f-107">\<behavior></span></span>  
<span data-ttu-id="1aa8f-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1aa8f-108">\<serviceCredentials></span></span>  
<span data-ttu-id="1aa8f-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="1aa8f-109">\<issuedTokenAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aa8f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="1aa8f-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1aa8f-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1aa8f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1aa8f-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1aa8f-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="1aa8f-113">Attributes</span></span>  
  
|<span data-ttu-id="1aa8f-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="1aa8f-114">Attribute</span></span>|<span data-ttu-id="1aa8f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1aa8f-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="1aa8f-116">Ruft den Satz von Ziel-URIs ab, für die das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass diese von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-116">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="1aa8f-117">Weitere Informationen zur Verwendung dieses Attributs finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-117">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="1aa8f-118">Ein boolescher Wert, der angibt, ob nicht vertrauenswürdige RSA-Zertifikataussteller zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-118">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="1aa8f-119">Zertifikate werden von Zertifizierungsstellen signiert, damit die Echtheit überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-119">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="1aa8f-120">Ein nicht vertrauenswürdiger Aussteller ist eine Zertifizierungsstelle, die zum Signieren von Zertifikaten als nicht vertrauenswürdig gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-120">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="1aa8f-121">Ruft einen Wert ab, der angibt, ob <xref:System.IdentityModel.Tokens.SamlSecurityToken> des <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>-Sicherheitstokens überprüft werden sollte.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-121">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="1aa8f-122">Dieser Wert ist vom Typ <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-122">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="1aa8f-123">Weitere Informationen zur Verwendung dieses Attributs finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-123">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="1aa8f-124">Legt den Zertifikatvalidierungsmodus fest.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-124">Sets the certificate validation mode.</span></span> <span data-ttu-id="1aa8f-125">Einer der gültigen Werte von <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-125">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="1aa8f-126">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-126">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="1aa8f-127">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-127">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="1aa8f-128">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-128">Optional string.</span></span> <span data-ttu-id="1aa8f-129">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-129">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="1aa8f-130">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-130">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="1aa8f-131">Legt den Sperrmodus fest, der angibt, ob eine Sperrüberprüfung ausgeführt wird und ob diese online oder offline erfolgt.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-131">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="1aa8f-132">Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-132">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="1aa8f-133">Ein optionales Zeichenfolgenattribut, das den SamlSerializer-Typ angibt, der für die Dienstanmeldeinformationen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-133">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="1aa8f-134">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-134">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="1aa8f-135">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-135">Optional enumeration.</span></span> <span data-ttu-id="1aa8f-136">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-136">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1aa8f-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1aa8f-137">Child Elements</span></span>  
  
|<span data-ttu-id="1aa8f-138">Element</span><span class="sxs-lookup"><span data-stu-id="1aa8f-138">Element</span></span>|<span data-ttu-id="1aa8f-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1aa8f-139">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="1aa8f-140">Gibt eine Auflistung von <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>-Elementen an, die vertrauenswürdige Aussteller für die Dienstanmeldeinformationen definieren.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-140">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1aa8f-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1aa8f-141">Parent Elements</span></span>  
  
|<span data-ttu-id="1aa8f-142">Element</span><span class="sxs-lookup"><span data-stu-id="1aa8f-142">Element</span></span>|<span data-ttu-id="1aa8f-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1aa8f-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1aa8f-144">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1aa8f-144">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="1aa8f-145">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-145">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1aa8f-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1aa8f-146">Remarks</span></span>  
 <span data-ttu-id="1aa8f-147">Das Szenario für ausgestellte Token weist drei Phasen auf.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-147">The issued token scenario has three stages.</span></span> <span data-ttu-id="1aa8f-148">In der ersten Phase wird ein Client einen Dienst zugreifen möchten bezeichnet einen *secure token Service*.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-148">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="1aa8f-149">Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-149">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="1aa8f-150">Der Client kehrt dann mit dem Token zum Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-150">The client then returns to the service with the token.</span></span> <span data-ttu-id="1aa8f-151">Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-151">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="1aa8f-152">Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-152">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="1aa8f-153">Dieses Element ist das Repository für die Zertifikate des Sicherheitstokendiensts.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-153">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="1aa8f-154">Verwenden Sie zum Hinzufügen von Zertifikaten der [ \<KnownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="1aa8f-154">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="1aa8f-155">Fügen Sie eine [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) für jedes Zertifikat, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-155">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="1aa8f-156">Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-156">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="1aa8f-157">Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-157">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="1aa8f-158">Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="1aa8f-158">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aa8f-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1aa8f-159">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>
- [<span data-ttu-id="1aa8f-160">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="1aa8f-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1aa8f-161">Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="1aa8f-161">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
