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
<span data-ttu-id="cd05e-101">Gibt eine Auflistung von X.509-Zertifikaten wieder, die zum Authentifizieren von Sicherheitsanmeldeinformationen eines Sicherheitstokendiensts bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cd05e-101">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="cd05e-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd05e-102">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd05e-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cd05e-103">Attributes and Elements</span></span>  
 <span data-ttu-id="cd05e-104">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd05e-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd05e-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="cd05e-105">Attributes</span></span>  
 <span data-ttu-id="cd05e-106">Keine</span><span class="sxs-lookup"><span data-stu-id="cd05e-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cd05e-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd05e-107">Child Elements</span></span>  
  
|<span data-ttu-id="cd05e-108">Element</span><span class="sxs-lookup"><span data-stu-id="cd05e-108">Element</span></span>|<span data-ttu-id="cd05e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cd05e-109">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-knowncertificates.md)|<span data-ttu-id="cd05e-110">Fügt der Auflistung ein X.509-Zertifikat hinzu.</span><span class="sxs-lookup"><span data-stu-id="cd05e-110">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd05e-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd05e-111">Parent Elements</span></span>  
  
|<span data-ttu-id="cd05e-112">Element</span><span class="sxs-lookup"><span data-stu-id="cd05e-112">Element</span></span>|<span data-ttu-id="cd05e-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cd05e-113">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="cd05e-114">Gibt ein Token an, das als Dienstanmeldeinformation ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cd05e-114">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd05e-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cd05e-115">Remarks</span></span>  
 <span data-ttu-id="cd05e-116">Das Szenario für ausgestellte Token weist drei Phasen auf.</span><span class="sxs-lookup"><span data-stu-id="cd05e-116">The issued token scenario has three stages.</span></span> <span data-ttu-id="cd05e-117">In der ersten Phase wird ein Client, der versucht, auf einen Dienst zuzugreifen, als *sicherer Tokendienst*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="cd05e-117">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="cd05e-118">Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus.</span><span class="sxs-lookup"><span data-stu-id="cd05e-118">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="cd05e-119">Der Client kehrt dann mit dem Token zum Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="cd05e-119">The client then returns to the service with the token.</span></span> <span data-ttu-id="cd05e-120">Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben.</span><span class="sxs-lookup"><span data-stu-id="cd05e-120">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="cd05e-121">Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="cd05e-121">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="cd05e-122">Das- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) Element ist das Repository für alle solchen Zertifikate des Sicherheitstokendiensts.</span><span class="sxs-lookup"><span data-stu-id="cd05e-122">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="cd05e-123">Verwenden Sie das- [ \<knownCertificates> Element](knowncertificates.md), um Zertifikate hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="cd05e-123">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="cd05e-124">Fügen Sie ein [\<add>](add-of-knowncertificates.md) für jedes Zertifikat ein, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd05e-124">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="cd05e-125">Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden.</span><span class="sxs-lookup"><span data-stu-id="cd05e-125">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="cd05e-126">Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="cd05e-126">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="cd05e-127">Informationen zum Überprüfen der Bedingungen, die für die Authentifizierung eines Clients durch einen Verbund Dienst erforderlich sind, sowie weitere Informationen zur Verwendung dieses Konfigurations Elements finden Sie unter Vorgehens [Weise: Konfigurieren von Anmelde Informationen auf einem Verbunddienst](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="cd05e-127">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="cd05e-128">Weitere Informationen zu Verbund Szenarien finden Sie unter Verbund [-und ausgestellte Token](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="cd05e-128">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="cd05e-129">Ein Beispiel, das zeigt, wie die-Auflistung in der-Konfiguration aufgefüllt wird, finden Sie unter [\<add>](add-of-knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="cd05e-129">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd05e-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd05e-130">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<add>](add-of-knowncertificates.md)
- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="cd05e-131">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="cd05e-131">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="cd05e-132">Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="cd05e-132">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="cd05e-133">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="cd05e-133">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="cd05e-134">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="cd05e-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-knowncertificates.md)
- [<span data-ttu-id="cd05e-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="cd05e-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
