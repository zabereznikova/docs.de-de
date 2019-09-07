---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 23fe19258e09e9e8a5e05a94ccef0e40ee1cb5fd
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400334"
---
# <a name="knowncertificates"></a><span data-ttu-id="3c607-101">\<knownzertifikate-></span><span class="sxs-lookup"><span data-stu-id="3c607-101">\<knownCertificates></span></span>
<span data-ttu-id="3c607-102">Gibt eine Auflistung von X.509-Zertifikaten wieder, die zum Authentifizieren von Sicherheitsanmeldeinformationen eines Sicherheitstokendiensts bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3c607-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
<span data-ttu-id="3c607-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3c607-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3c607-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3c607-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3c607-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3c607-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="3c607-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3c607-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="3c607-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3c607-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="3c607-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<servicecreden->** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="3c607-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="3c607-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<IssuedTokenAuthentication->** ](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="3c607-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="3c607-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<knownzertifikate->**</span><span class="sxs-lookup"><span data-stu-id="3c607-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c607-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c607-111">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c607-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3c607-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3c607-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3c607-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c607-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="3c607-114">Attributes</span></span>  
 <span data-ttu-id="3c607-115">Keine</span><span class="sxs-lookup"><span data-stu-id="3c607-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3c607-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c607-116">Child Elements</span></span>  
  
|<span data-ttu-id="3c607-117">Element</span><span class="sxs-lookup"><span data-stu-id="3c607-117">Element</span></span>|<span data-ttu-id="3c607-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c607-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c607-119">\<add></span><span class="sxs-lookup"><span data-stu-id="3c607-119">\<add></span></span>](add-of-knowncertificates.md)|<span data-ttu-id="3c607-120">Fügt der Auflistung ein X.509-Zertifikat hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c607-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3c607-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c607-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3c607-122">Element</span><span class="sxs-lookup"><span data-stu-id="3c607-122">Element</span></span>|<span data-ttu-id="3c607-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c607-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c607-124">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="3c607-124">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="3c607-125">Gibt ein Token an, das als Dienstanmeldeinformation ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3c607-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c607-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c607-126">Remarks</span></span>  
 <span data-ttu-id="3c607-127">Das Szenario für ausgestellte Token weist drei Phasen auf.</span><span class="sxs-lookup"><span data-stu-id="3c607-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="3c607-128">In der ersten Phase wird ein Client, der versucht, auf einen Dienst zuzugreifen, als *sicherer Tokendienst*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3c607-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="3c607-129">Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus.</span><span class="sxs-lookup"><span data-stu-id="3c607-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="3c607-130">Der Client kehrt dann mit dem Token zum Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="3c607-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="3c607-131">Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben.</span><span class="sxs-lookup"><span data-stu-id="3c607-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="3c607-132">Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="3c607-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="3c607-133">[ Das\<IssuedTokenAuthentication->](issuedtokenauthentication-of-servicecredentials.md) -Element ist das Repository für alle solchen Zertifikate des Sicherheitstokendiensts.</span><span class="sxs-lookup"><span data-stu-id="3c607-133">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="3c607-134">Zum Hinzufügen von Zertifikaten verwenden Sie das [ \<known-Zertifikate->-Element](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="3c607-134">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="3c607-135">[ \<Fügen Sie einen Add->](add-of-knowncertificates.md) für jedes Zertifikat ein, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c607-135">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="3c607-136">Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden.</span><span class="sxs-lookup"><span data-stu-id="3c607-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="3c607-137">Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="3c607-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="3c607-138">Informationen zum Überprüfen der Bedingungen, die für die Authentifizierung eines Clients durch einen Verbund Dienst erforderlich sind, sowie weitere Informationen zur Verwendung dieses Konfigurations Elements finden [Sie unter Gewusst wie: Konfigurieren Sie die Anmelde Informationen](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)für einen Verbunddienst.</span><span class="sxs-lookup"><span data-stu-id="3c607-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="3c607-139">Weitere Informationen zu Verbund Szenarien finden Sie unter Verbund [-und ausgestellte Token](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="3c607-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="3c607-140">Ein Beispiel, das zeigt, wie die-Auflistung in der Konfiguration aufgefüllt wird, finden [ \<Sie unter Hinzufügen >](add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="3c607-140">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c607-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c607-141">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="3c607-142">\<add></span><span class="sxs-lookup"><span data-stu-id="3c607-142">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="3c607-143">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="3c607-143">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="3c607-144">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="3c607-144">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="3c607-145">Vorgehensweise: Konfigurieren von Anmelde Informationen für eine Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="3c607-145">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="3c607-146">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="3c607-146">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="3c607-147">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="3c607-147">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3c607-148">\<add></span><span class="sxs-lookup"><span data-stu-id="3c607-148">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="3c607-149">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="3c607-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
