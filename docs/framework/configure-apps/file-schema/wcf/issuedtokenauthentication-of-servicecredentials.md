---
title: '&lt;issuedTokenAuthentication&gt; von &lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: 4a9087e319c278ea396b5611b2f7f923bd00b6d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509336"
---
# <a name="ltissuedtokenauthenticationgt-of-ltservicecredentialsgt"></a><span data-ttu-id="6cde3-102">&lt;issuedTokenAuthentication&gt; von &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="6cde3-102">&lt;issuedTokenAuthentication&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="6cde3-103">Gibt ein als Dienstanmeldeinformationen ausgegebenes Token an.</span><span class="sxs-lookup"><span data-stu-id="6cde3-103">Specifies a custom token issued as a service credential.</span></span>  
  
 <span data-ttu-id="6cde3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6cde3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6cde3-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="6cde3-105">\<behaviors></span></span>  
<span data-ttu-id="6cde3-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="6cde3-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="6cde3-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6cde3-107">\<behavior></span></span>  
<span data-ttu-id="6cde3-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="6cde3-108">\<serviceCredentials></span></span>  
<span data-ttu-id="6cde3-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="6cde3-109">\<issuedTokenAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cde3-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="6cde3-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6cde3-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6cde3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6cde3-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6cde3-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6cde3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="6cde3-113">Attributes</span></span>  
  
|<span data-ttu-id="6cde3-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="6cde3-114">Attribute</span></span>|<span data-ttu-id="6cde3-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6cde3-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="6cde3-116">Ruft den Satz von Ziel-URIs ab, für die das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass diese von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="6cde3-116">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="6cde3-117">Weitere Informationen zur Verwendung dieses Attributs finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span><span class="sxs-lookup"><span data-stu-id="6cde3-117">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="6cde3-118">Ein boolescher Wert, der angibt, ob nicht vertrauenswürdige RSA-Zertifikataussteller zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="6cde3-118">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="6cde3-119">Zertifikate werden von Zertifizierungsstellen signiert, damit die Echtheit überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="6cde3-119">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="6cde3-120">Ein nicht vertrauenswürdiger Aussteller ist eine Zertifizierungsstelle, die zum Signieren von Zertifikaten als nicht vertrauenswürdig gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="6cde3-120">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="6cde3-121">Ruft einen Wert ab, der angibt, ob <xref:System.IdentityModel.Tokens.SamlSecurityToken> des <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>-Sicherheitstokens überprüft werden sollte.</span><span class="sxs-lookup"><span data-stu-id="6cde3-121">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="6cde3-122">Dieser Wert ist vom Typ <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span><span class="sxs-lookup"><span data-stu-id="6cde3-122">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="6cde3-123">Weitere Informationen zur Verwendung dieses Attributs finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="6cde3-123">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="6cde3-124">Legt den Zertifikatüberprüfungsmodus fest.</span><span class="sxs-lookup"><span data-stu-id="6cde3-124">Sets the certificate validation mode.</span></span> <span data-ttu-id="6cde3-125">Einer der gültigen Werte von <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="6cde3-125">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="6cde3-126">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6cde3-126">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="6cde3-127">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="6cde3-127">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="6cde3-128">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6cde3-128">Optional string.</span></span> <span data-ttu-id="6cde3-129">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6cde3-129">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="6cde3-130">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="6cde3-130">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="6cde3-131">Legt den Sperrmodus fest, der angibt, ob eine Sperrüberprüfung ausgeführt wird und ob diese online oder offline erfolgt.</span><span class="sxs-lookup"><span data-stu-id="6cde3-131">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="6cde3-132">Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="6cde3-132">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="6cde3-133">Ein optionales Zeichenfolgenattribut, das den SamlSerializer-Typ angibt, der für die Dienstanmeldeinformationen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6cde3-133">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="6cde3-134">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6cde3-134">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="6cde3-135">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="6cde3-135">Optional enumeration.</span></span> <span data-ttu-id="6cde3-136">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="6cde3-136">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6cde3-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6cde3-137">Child Elements</span></span>  
  
|<span data-ttu-id="6cde3-138">Element</span><span class="sxs-lookup"><span data-stu-id="6cde3-138">Element</span></span>|<span data-ttu-id="6cde3-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6cde3-139">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="6cde3-140">Gibt eine Auflistung von <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>-Elementen an, die vertrauenswürdige Aussteller für die Dienstanmeldeinformationen definieren.</span><span class="sxs-lookup"><span data-stu-id="6cde3-140">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6cde3-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6cde3-141">Parent Elements</span></span>  
  
|<span data-ttu-id="6cde3-142">Element</span><span class="sxs-lookup"><span data-stu-id="6cde3-142">Element</span></span>|<span data-ttu-id="6cde3-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6cde3-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6cde3-144">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="6cde3-144">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="6cde3-145">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="6cde3-145">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6cde3-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6cde3-146">Remarks</span></span>  
 <span data-ttu-id="6cde3-147">Das Szenario für ausgestellte Token weist drei Phasen auf.</span><span class="sxs-lookup"><span data-stu-id="6cde3-147">The issued token scenario has three stages.</span></span> <span data-ttu-id="6cde3-148">In der ersten Phase wird ein Client einen Dienst zugreifen möchten bezeichnet einen *secure token Service*.</span><span class="sxs-lookup"><span data-stu-id="6cde3-148">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="6cde3-149">Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus.</span><span class="sxs-lookup"><span data-stu-id="6cde3-149">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="6cde3-150">Der Client kehrt dann mit dem Token zum Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="6cde3-150">The client then returns to the service with the token.</span></span> <span data-ttu-id="6cde3-151">Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben.</span><span class="sxs-lookup"><span data-stu-id="6cde3-151">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="6cde3-152">Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="6cde3-152">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="6cde3-153">Dieses Element ist das Repository für die Zertifikate des Sicherheitstokendiensts.</span><span class="sxs-lookup"><span data-stu-id="6cde3-153">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="6cde3-154">Verwenden Sie zum Hinzufügen von Zertifikaten der [ \<KnownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="6cde3-154">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="6cde3-155">Fügen Sie eine [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) für jedes Zertifikat, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cde3-155">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="6cde3-156">Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden.</span><span class="sxs-lookup"><span data-stu-id="6cde3-156">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="6cde3-157">Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="6cde3-157">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="6cde3-158">Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="6cde3-158">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cde3-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6cde3-159">See also</span></span>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>
- [<span data-ttu-id="6cde3-160">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="6cde3-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6cde3-161">Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="6cde3-161">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
