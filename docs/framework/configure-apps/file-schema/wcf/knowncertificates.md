---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 1210e6282a7dd6c40198693d4948a89efe841d59
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913526"
---
# <a name="knowncertificates"></a><span data-ttu-id="791d9-101">\<knownzertifikate-></span><span class="sxs-lookup"><span data-stu-id="791d9-101">\<knownCertificates></span></span>
<span data-ttu-id="791d9-102">Gibt eine Auflistung von X.509-Zertifikaten wieder, die zum Authentifizieren von Sicherheitsanmeldeinformationen eines Sicherheitstokendiensts bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="791d9-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="791d9-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="791d9-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="791d9-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="791d9-104">\<behaviors></span></span>  
<span data-ttu-id="791d9-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="791d9-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="791d9-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="791d9-106">\<behavior></span></span>  
<span data-ttu-id="791d9-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="791d9-107">\<serviceCredentials></span></span>  
<span data-ttu-id="791d9-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="791d9-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="791d9-109">\<knownzertifikate-></span><span class="sxs-lookup"><span data-stu-id="791d9-109">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="791d9-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="791d9-110">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="791d9-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="791d9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="791d9-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="791d9-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="791d9-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="791d9-113">Attributes</span></span>  
 <span data-ttu-id="791d9-114">Keine</span><span class="sxs-lookup"><span data-stu-id="791d9-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="791d9-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="791d9-115">Child Elements</span></span>  
  
|<span data-ttu-id="791d9-116">Element</span><span class="sxs-lookup"><span data-stu-id="791d9-116">Element</span></span>|<span data-ttu-id="791d9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="791d9-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="791d9-118">\<add></span><span class="sxs-lookup"><span data-stu-id="791d9-118">\<add></span></span>](add-of-knowncertificates.md)|<span data-ttu-id="791d9-119">Fügt der Auflistung ein X.509-Zertifikat hinzu.</span><span class="sxs-lookup"><span data-stu-id="791d9-119">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="791d9-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="791d9-120">Parent Elements</span></span>  
  
|<span data-ttu-id="791d9-121">Element</span><span class="sxs-lookup"><span data-stu-id="791d9-121">Element</span></span>|<span data-ttu-id="791d9-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="791d9-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="791d9-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="791d9-123">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="791d9-124">Gibt ein Token an, das als Dienstanmeldeinformation ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="791d9-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="791d9-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="791d9-125">Remarks</span></span>  
 <span data-ttu-id="791d9-126">Das Szenario für ausgestellte Token weist drei Phasen auf.</span><span class="sxs-lookup"><span data-stu-id="791d9-126">The issued token scenario has three stages.</span></span> <span data-ttu-id="791d9-127">In der ersten Phase wird ein Client, der versucht, auf einen Dienst zuzugreifen, als *sicherer Tokendienst*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="791d9-127">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="791d9-128">Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus.</span><span class="sxs-lookup"><span data-stu-id="791d9-128">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="791d9-129">Der Client kehrt dann mit dem Token zum Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="791d9-129">The client then returns to the service with the token.</span></span> <span data-ttu-id="791d9-130">Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben.</span><span class="sxs-lookup"><span data-stu-id="791d9-130">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="791d9-131">Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="791d9-131">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="791d9-132">[ Das\<IssuedTokenAuthentication->](issuedtokenauthentication-of-servicecredentials.md) -Element ist das Repository für alle solchen Zertifikate des Sicherheitstokendiensts.</span><span class="sxs-lookup"><span data-stu-id="791d9-132">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="791d9-133">Zum Hinzufügen von Zertifikaten verwenden Sie das [ \<known-Zertifikate->-Element](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="791d9-133">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="791d9-134">[ \<Fügen Sie einen Add->](add-of-knowncertificates.md) für jedes Zertifikat ein, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="791d9-134">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="791d9-135">Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden.</span><span class="sxs-lookup"><span data-stu-id="791d9-135">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="791d9-136">Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="791d9-136">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="791d9-137">Informationen zum Überprüfen der Bedingungen, die für die Authentifizierung eines Clients durch einen Verbund Dienst erforderlich sind, sowie weitere Informationen zur Verwendung dieses Konfigurations Elements finden [Sie unter Gewusst wie: Konfigurieren Sie die Anmelde Informationen](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)für einen Verbunddienst.</span><span class="sxs-lookup"><span data-stu-id="791d9-137">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="791d9-138">Weitere Informationen zu Verbund Szenarien finden Sie unter Verbund [-und ausgestellte Token](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="791d9-138">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="791d9-139">Ein Beispiel, das zeigt, wie die-Auflistung in der Konfiguration aufgefüllt wird, finden [ \<Sie unter Hinzufügen >](add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="791d9-139">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="791d9-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="791d9-140">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="791d9-141">\<add></span><span class="sxs-lookup"><span data-stu-id="791d9-141">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="791d9-142">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="791d9-142">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="791d9-143">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="791d9-143">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="791d9-144">Vorgehensweise: Konfigurieren von Anmelde Informationen für eine Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="791d9-144">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="791d9-145">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="791d9-145">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="791d9-146">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="791d9-146">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="791d9-147">\<add></span><span class="sxs-lookup"><span data-stu-id="791d9-147">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="791d9-148">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="791d9-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
