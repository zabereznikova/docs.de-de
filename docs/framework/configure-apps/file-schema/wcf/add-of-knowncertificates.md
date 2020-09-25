---
title: <add> von <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 453593918de15613edb801cca8a16c9dbf71aa90
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176083"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="0e305-102">\<add> von \<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="0e305-102">\<add> of \<knownCertificates></span></span>

<span data-ttu-id="0e305-103">Fügt ein X.509-Zertifikat zur Auflistung bekannter Zertifikate hinzu.</span><span class="sxs-lookup"><span data-stu-id="0e305-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="0e305-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e305-104">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e305-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0e305-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0e305-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e305-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e305-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="0e305-107">Attributes</span></span>  
  
|<span data-ttu-id="0e305-108">attribute</span><span class="sxs-lookup"><span data-stu-id="0e305-108">Attribute</span></span>|<span data-ttu-id="0e305-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e305-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e305-110">findValue</span><span class="sxs-lookup"><span data-stu-id="0e305-110">findValue</span></span>|<span data-ttu-id="0e305-111">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0e305-111">String.</span></span> <span data-ttu-id="0e305-112">Der zu suchende Wert.</span><span class="sxs-lookup"><span data-stu-id="0e305-112">The value to search for.</span></span>|  
|<span data-ttu-id="0e305-113">storeLocation</span><span class="sxs-lookup"><span data-stu-id="0e305-113">storeLocation</span></span>|<span data-ttu-id="0e305-114">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0e305-114">Enumeration.</span></span> <span data-ttu-id="0e305-115">Einer der beiden zu durchsuchenden Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="0e305-115">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="0e305-116">storeName</span><span class="sxs-lookup"><span data-stu-id="0e305-116">storeName</span></span>|<span data-ttu-id="0e305-117">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0e305-117">Enumeration.</span></span> <span data-ttu-id="0e305-118">Einer der zu durchsuchenden Systemspeicher.</span><span class="sxs-lookup"><span data-stu-id="0e305-118">One of the system stores to search.</span></span>|  
|<span data-ttu-id="0e305-119">x509FindType</span><span class="sxs-lookup"><span data-stu-id="0e305-119">x509FindType</span></span>|<span data-ttu-id="0e305-120">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0e305-120">Enumeration.</span></span> <span data-ttu-id="0e305-121">Eines der zu durchsuchenden Zertifikatfelder.</span><span class="sxs-lookup"><span data-stu-id="0e305-121">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="0e305-122">findValue-Attribut</span><span class="sxs-lookup"><span data-stu-id="0e305-122">findValue Attribute</span></span>  
  
|<span data-ttu-id="0e305-123">Wert</span><span class="sxs-lookup"><span data-stu-id="0e305-123">Value</span></span>|<span data-ttu-id="0e305-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0e305-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0e305-125">String</span><span class="sxs-lookup"><span data-stu-id="0e305-125">String</span></span>|<span data-ttu-id="0e305-126">Der Wert ist vom zu durchsuchenden Feld (das durch das X509FindType-Attribut angegeben wird) abhängig.</span><span class="sxs-lookup"><span data-stu-id="0e305-126">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="0e305-127">Wenn Sie beispielsweise nach einem Fingerabdruck suchen, muss der Wert eine Zeichenfolge aus hexadezimalen Zahlen sein.</span><span class="sxs-lookup"><span data-stu-id="0e305-127">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="0e305-128">x509FindType-Attribut</span><span class="sxs-lookup"><span data-stu-id="0e305-128">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="0e305-129">Wert</span><span class="sxs-lookup"><span data-stu-id="0e305-129">Value</span></span>|<span data-ttu-id="0e305-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e305-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0e305-131">Enumeration</span><span class="sxs-lookup"><span data-stu-id="0e305-131">Enumeration</span></span>|<span data-ttu-id="0e305-132">Zu den gültigen Werten gehören: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="0e305-132">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="0e305-133">storeLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="0e305-133">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="0e305-134">Wert</span><span class="sxs-lookup"><span data-stu-id="0e305-134">Value</span></span>|<span data-ttu-id="0e305-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e305-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0e305-136">Enumeration</span><span class="sxs-lookup"><span data-stu-id="0e305-136">Enumeration</span></span>|<span data-ttu-id="0e305-137">CurrentUser oder LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="0e305-137">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="0e305-138">storeName-Attribut</span><span class="sxs-lookup"><span data-stu-id="0e305-138">storeName Attribute</span></span>  
  
|<span data-ttu-id="0e305-139">Wert</span><span class="sxs-lookup"><span data-stu-id="0e305-139">Value</span></span>|<span data-ttu-id="0e305-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e305-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0e305-141">Enumeration</span><span class="sxs-lookup"><span data-stu-id="0e305-141">Enumeration</span></span>|<span data-ttu-id="0e305-142">Zu den gültigen Werten gehören: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople und TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="0e305-142">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e305-143">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e305-143">Child Elements</span></span>  

 <span data-ttu-id="0e305-144">Keine</span><span class="sxs-lookup"><span data-stu-id="0e305-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e305-145">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e305-145">Parent Elements</span></span>  
  
|<span data-ttu-id="0e305-146">Element</span><span class="sxs-lookup"><span data-stu-id="0e305-146">Element</span></span>|<span data-ttu-id="0e305-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e305-147">Description</span></span>|  
|-------------|-----------------|  
|[\<knownCertificates>](knowncertificates.md)|<span data-ttu-id="0e305-148">Gibt eine Auflistung von X.509-Zertifikaten wieder, die von einem Sicherheitstokendienst für die Validierung von Sicherheitstoken bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0e305-148">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e305-149">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0e305-149">Remarks</span></span>  

 <span data-ttu-id="0e305-150">Das Szenario für ausgestellte Token weist drei Phasen auf.</span><span class="sxs-lookup"><span data-stu-id="0e305-150">The issued token scenario has three stages.</span></span> <span data-ttu-id="0e305-151">In der ersten Phase wird ein Client, der versucht, auf einen Dienst zuzugreifen, als *sicherer Tokendienst*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0e305-151">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="0e305-152">Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus.</span><span class="sxs-lookup"><span data-stu-id="0e305-152">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="0e305-153">Der Client kehrt dann mit dem Token zum Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="0e305-153">The client then returns to the service with the token.</span></span> <span data-ttu-id="0e305-154">Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben.</span><span class="sxs-lookup"><span data-stu-id="0e305-154">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="0e305-155">Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="0e305-155">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="0e305-156">Das- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) Element ist das Repository für alle solchen Zertifikate des Sicherheitstokendiensts.</span><span class="sxs-lookup"><span data-stu-id="0e305-156">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="0e305-157">Verwenden Sie zum Hinzufügen von Zertifikaten [\<knownCertificates>](knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="0e305-157">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="0e305-158">Fügen Sie ein [ \<add> Element \<knownCertificates> Element](add-of-knowncertificates.md) für jedes Zertifikat ein, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e305-158">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="0e305-159">Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden.</span><span class="sxs-lookup"><span data-stu-id="0e305-159">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="0e305-160">Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="0e305-160">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="0e305-161">Informationen zum Überprüfen der Bedingungen, die für die Authentifizierung eines Clients durch einen Verbund Dienst erforderlich sind, sowie weitere Informationen zur Verwendung dieses Konfigurations Elements finden Sie unter Vorgehens [Weise: Konfigurieren von Anmelde Informationen auf einem Verbunddienst](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="0e305-161">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="0e305-162">Weitere Informationen zu Verbund Szenarien finden Sie unter Verbund [-und ausgestellte Token](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="0e305-162">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e305-163">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e305-163">Example</span></span>  

 <span data-ttu-id="0e305-164">Im folgenden Beispiel wird ein Zertifikat dem Repository für beliebige STS-Zertifikate hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0e305-164">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0e305-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e305-165">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<knownCertificates>](knowncertificates.md)
- [<span data-ttu-id="0e305-166">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="0e305-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0e305-167">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="0e305-167">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0e305-168">Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="0e305-168">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="0e305-169">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="0e305-169">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
