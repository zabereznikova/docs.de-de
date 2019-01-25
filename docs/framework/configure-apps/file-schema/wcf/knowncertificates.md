---
title: '&lt;knownCertificates&gt;'
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 49e5236abdc82fb4ca004c611e706e74fa99bf7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687348"
---
# <a name="ltknowncertificatesgt"></a><span data-ttu-id="fb810-102">&lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="fb810-102">&lt;knownCertificates&gt;</span></span>
<span data-ttu-id="fb810-103">Gibt eine Auflistung von X.509-Zertifikaten wieder, die zum Authentifizieren von Sicherheitsanmeldeinformationen eines Sicherheitstokendiensts bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fb810-103">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="fb810-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fb810-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fb810-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="fb810-105">\<behaviors></span></span>  
<span data-ttu-id="fb810-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="fb810-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="fb810-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fb810-107">\<behavior></span></span>  
<span data-ttu-id="fb810-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="fb810-108">\<serviceCredentials></span></span>  
<span data-ttu-id="fb810-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="fb810-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="fb810-110">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="fb810-110">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb810-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb810-111">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb810-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fb810-112">Attributes and Elements</span></span>  
 <span data-ttu-id="fb810-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fb810-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb810-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="fb810-114">Attributes</span></span>  
 <span data-ttu-id="fb810-115">Keine</span><span class="sxs-lookup"><span data-stu-id="fb810-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fb810-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb810-116">Child Elements</span></span>  
  
|<span data-ttu-id="fb810-117">Element</span><span class="sxs-lookup"><span data-stu-id="fb810-117">Element</span></span>|<span data-ttu-id="fb810-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb810-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb810-119">\<add></span><span class="sxs-lookup"><span data-stu-id="fb810-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="fb810-120">Fügt der Auflistung ein X.509-Zertifikat hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb810-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fb810-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb810-121">Parent Elements</span></span>  
  
|<span data-ttu-id="fb810-122">Element</span><span class="sxs-lookup"><span data-stu-id="fb810-122">Element</span></span>|<span data-ttu-id="fb810-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb810-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb810-124">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="fb810-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="fb810-125">Gibt ein Token an, das als Dienstanmeldeinformation ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fb810-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb810-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb810-126">Remarks</span></span>  
 <span data-ttu-id="fb810-127">Das Szenario für ausgestellte Token weist drei Phasen auf.</span><span class="sxs-lookup"><span data-stu-id="fb810-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="fb810-128">In der ersten Phase wird ein Client einen Dienst zugreifen möchten bezeichnet einen *secure token Service*.</span><span class="sxs-lookup"><span data-stu-id="fb810-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="fb810-129">Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus.</span><span class="sxs-lookup"><span data-stu-id="fb810-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="fb810-130">Der Client kehrt dann mit dem Token zum Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="fb810-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="fb810-131">Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben.</span><span class="sxs-lookup"><span data-stu-id="fb810-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="fb810-132">Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="fb810-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="fb810-133">Die [ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) Element ist das Repository für die Zertifikate des Sicherheitstokendiensts.</span><span class="sxs-lookup"><span data-stu-id="fb810-133">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="fb810-134">Verwenden Sie zum Hinzufügen von Zertifikaten der [ \<KnownCertificates >-Element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="fb810-134">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="fb810-135">Fügen Sie eine [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) für jedes Zertifikat, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb810-135">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="fb810-136">Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden.</span><span class="sxs-lookup"><span data-stu-id="fb810-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="fb810-137">Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="fb810-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="fb810-138">Bedingungen, die ein Client von einem Verbunddienst sowie weitere Informationen zur Verwendung dieses Konfigurationselements authentifiziert werden benötigt, finden Sie unter [Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="fb810-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="fb810-139">Weitere Informationen zu Verbundszenarien finden Sie unter [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="fb810-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="fb810-140">Ein Beispiel, der zum Auffüllen der Auflistung in der Konfiguration veranschaulicht, finden Sie unter [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="fb810-140">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb810-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb810-141">See also</span></span>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="fb810-142">\<add></span><span class="sxs-lookup"><span data-stu-id="fb810-142">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [<span data-ttu-id="fb810-143">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="fb810-143">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="fb810-144">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="fb810-144">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="fb810-145">Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="fb810-145">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="fb810-146">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="fb810-146">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="fb810-147">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="fb810-147">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fb810-148">\<add></span><span class="sxs-lookup"><span data-stu-id="fb810-148">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [<span data-ttu-id="fb810-149">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="fb810-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
