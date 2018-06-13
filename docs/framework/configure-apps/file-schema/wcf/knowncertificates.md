---
title: '&lt;knownCertificates&gt;'
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 394ae246ad29a0747f3814b36fae2557b04c235a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748242"
---
# <a name="ltknowncertificatesgt"></a><span data-ttu-id="de445-102">&lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="de445-102">&lt;knownCertificates&gt;</span></span>
<span data-ttu-id="de445-103">Gibt eine Auflistung von X.509-Zertifikaten wieder, die zum Authentifizieren von Sicherheitsanmeldeinformationen eines Sicherheitstokendiensts bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="de445-103">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="de445-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="de445-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="de445-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="de445-105">\<behaviors></span></span>  
<span data-ttu-id="de445-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="de445-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="de445-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="de445-107">\<behavior></span></span>  
<span data-ttu-id="de445-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="de445-108">\<serviceCredentials></span></span>  
<span data-ttu-id="de445-109">\<IssuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="de445-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="de445-110">\<KnownCertificates ></span><span class="sxs-lookup"><span data-stu-id="de445-110">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de445-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="de445-111">Syntax</span></span>  
  
```xml  
<knownCertificates>   
      <add findValue="String"  
         storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
           x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de445-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="de445-112">Attributes and Elements</span></span>  
 <span data-ttu-id="de445-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="de445-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de445-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="de445-114">Attributes</span></span>  
 <span data-ttu-id="de445-115">Keine</span><span class="sxs-lookup"><span data-stu-id="de445-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="de445-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="de445-116">Child Elements</span></span>  
  
|<span data-ttu-id="de445-117">Element</span><span class="sxs-lookup"><span data-stu-id="de445-117">Element</span></span>|<span data-ttu-id="de445-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de445-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de445-119">\<add></span><span class="sxs-lookup"><span data-stu-id="de445-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="de445-120">Fügt der Auflistung ein X.509-Zertifikat hinzu.</span><span class="sxs-lookup"><span data-stu-id="de445-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="de445-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="de445-121">Parent Elements</span></span>  
  
|<span data-ttu-id="de445-122">Element</span><span class="sxs-lookup"><span data-stu-id="de445-122">Element</span></span>|<span data-ttu-id="de445-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de445-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de445-124">\<IssuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="de445-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="de445-125">Gibt ein Token an, das als Dienstanmeldeinformation ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="de445-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de445-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de445-126">Remarks</span></span>  
 <span data-ttu-id="de445-127">Das Szenario für ausgestellte Token weist drei Phasen auf.</span><span class="sxs-lookup"><span data-stu-id="de445-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="de445-128">In der ersten Phase wird ein Client versucht, auf einen Dienst zuzugreifen bezeichnet einen *sicheren Tokendienst*.</span><span class="sxs-lookup"><span data-stu-id="de445-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="de445-129">Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus.</span><span class="sxs-lookup"><span data-stu-id="de445-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="de445-130">Der Client kehrt dann mit dem Token zum Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="de445-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="de445-131">Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben.</span><span class="sxs-lookup"><span data-stu-id="de445-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="de445-132">Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="de445-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="de445-133">Die [ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) Element ist das Repository für solche Sicherheitstokendienst-Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="de445-133">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="de445-134">Verwenden Sie zum Hinzufügen von Zertifikaten der [ \<KnownCertificates >-Element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="de445-134">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="de445-135">Fügen Sie ein [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) für jedes Zertifikat, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="de445-135">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="de445-136">Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden.</span><span class="sxs-lookup"><span data-stu-id="de445-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="de445-137">Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="de445-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="de445-138">Für einen Client für die Authentifizierung durch ein Verbunddienst sowie weitere Informationen zur Verwendung dieses Konfigurationselement erforderlichen Bedingungen finden Sie unter [Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="de445-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="de445-139">Weitere Informationen über verbundene Szenarien finden Sie unter [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="de445-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="de445-140">Ein Beispiel, das beim Auffüllen der Auflistung in der Konfiguration veranschaulicht, finden Sie unter [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="de445-140">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de445-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de445-141">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="de445-142">\<add></span><span class="sxs-lookup"><span data-stu-id="de445-142">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="de445-143">\<IssuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="de445-143">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="de445-144">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="de445-144">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="de445-145">Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="de445-145">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="de445-146">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="de445-146">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="de445-147">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="de445-147">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="de445-148">\<add></span><span class="sxs-lookup"><span data-stu-id="de445-148">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="de445-149">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="de445-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
