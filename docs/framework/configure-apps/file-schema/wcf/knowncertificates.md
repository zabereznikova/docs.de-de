---
title: '&lt;knownCertificates&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9f62a43f1f8d3d025f62efca341c35e4af590abd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltknowncertificatesgt"></a><span data-ttu-id="1fbc6-102">&lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="1fbc6-102">&lt;knownCertificates&gt;</span></span>
<span data-ttu-id="1fbc6-103">Gibt eine Auflistung von X.509-Zertifikaten wieder, die zum Authentifizieren von Sicherheitsanmeldeinformationen eines Sicherheitstokendiensts bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-103">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="1fbc6-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1fbc6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1fbc6-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="1fbc6-105">\<behaviors></span></span>  
<span data-ttu-id="1fbc6-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1fbc6-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1fbc6-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="1fbc6-107">\<behavior></span></span>  
<span data-ttu-id="1fbc6-108">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="1fbc6-108">\<serviceCredentials></span></span>  
<span data-ttu-id="1fbc6-109">\<IssuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="1fbc6-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="1fbc6-110">\<KnownCertificates ></span><span class="sxs-lookup"><span data-stu-id="1fbc6-110">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fbc6-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="1fbc6-111">Syntax</span></span>  
  
```xml  
<knownCertificates>   
      <add findValue="String"  
         storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
           x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fbc6-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1fbc6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1fbc6-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fbc6-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="1fbc6-114">Attributes</span></span>  
 <span data-ttu-id="1fbc6-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1fbc6-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1fbc6-116">Child Elements</span></span>  
  
|<span data-ttu-id="1fbc6-117">Element</span><span class="sxs-lookup"><span data-stu-id="1fbc6-117">Element</span></span>|<span data-ttu-id="1fbc6-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1fbc6-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fbc6-119">\<add></span><span class="sxs-lookup"><span data-stu-id="1fbc6-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="1fbc6-120">Fügt der Auflistung ein X.509-Zertifikat hinzu.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1fbc6-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1fbc6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1fbc6-122">Element</span><span class="sxs-lookup"><span data-stu-id="1fbc6-122">Element</span></span>|<span data-ttu-id="1fbc6-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1fbc6-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fbc6-124">\<IssuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="1fbc6-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="1fbc6-125">Gibt ein Token an, das als Dienstanmeldeinformation ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fbc6-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1fbc6-126">Remarks</span></span>  
 <span data-ttu-id="1fbc6-127">Das Szenario für ausgestellte Token weist drei Phasen auf.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="1fbc6-128">In der ersten Phase wird ein Client versucht, auf einen Dienst zuzugreifen bezeichnet einen *sicheren Tokendienst*.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="1fbc6-129">Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="1fbc6-130">Der Client kehrt dann mit dem Token zum Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="1fbc6-131">Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="1fbc6-132">Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="1fbc6-133">Die [ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) Element ist das Repository für solche Sicherheitstokendienst-Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-133">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="1fbc6-134">Verwenden Sie zum Hinzufügen von Zertifikaten der [ \<KnownCertificates >-Element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="1fbc6-134">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="1fbc6-135">Fügen Sie ein [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) für jedes Zertifikat, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-135">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="1fbc6-136">Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="1fbc6-137">Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1fbc6-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="1fbc6-138">Für einen Client für die Authentifizierung durch ein Verbunddienst sowie weitere Informationen zur Verwendung dieses Konfigurationselement erforderlichen Bedingungen finden Sie unter [Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="1fbc6-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="1fbc6-139">Weitere Informationen über verbundene Szenarien finden Sie unter [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="1fbc6-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="1fbc6-140">Ein Beispiel, das beim Auffüllen der Auflistung in der Konfiguration veranschaulicht, finden Sie unter [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="1fbc6-140">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fbc6-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fbc6-141">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="1fbc6-142">\<add></span><span class="sxs-lookup"><span data-stu-id="1fbc6-142">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="1fbc6-143">\<IssuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="1fbc6-143">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="1fbc6-144">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="1fbc6-144">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="1fbc6-145">Vorgehensweise: Konfigurieren Sie Anmeldeinformationen in einem Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="1fbc6-145">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="1fbc6-146">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="1fbc6-146">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="1fbc6-147">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="1fbc6-147">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="1fbc6-148">\<add></span><span class="sxs-lookup"><span data-stu-id="1fbc6-148">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="1fbc6-149">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="1fbc6-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
