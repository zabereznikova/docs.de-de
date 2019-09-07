---
title: <add> von <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 29b067e6ec20992084f9ab3bab087222bdd56da2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400620"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="0b757-102">\<Fügen Sie > \<von knownzertifikate hinzu ></span><span class="sxs-lookup"><span data-stu-id="0b757-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="0b757-103">Fügt ein X.509-Zertifikat zur Auflistung bekannter Zertifikate hinzu.</span><span class="sxs-lookup"><span data-stu-id="0b757-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
<span data-ttu-id="0b757-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0b757-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0b757-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0b757-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0b757-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0b757-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="0b757-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0b757-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="0b757-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0b757-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="0b757-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<servicecreden->** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="0b757-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="0b757-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<IssuedTokenAuthentication->** ](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="0b757-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="0b757-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<knownzertifikate->** ](knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="0b757-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)</span></span>\
<span data-ttu-id="0b757-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="0b757-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b757-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b757-113">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b757-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0b757-114">Attributes and Elements</span></span>  
 <span data-ttu-id="0b757-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b757-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b757-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="0b757-116">Attributes</span></span>  
  
|<span data-ttu-id="0b757-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="0b757-117">Attribute</span></span>|<span data-ttu-id="0b757-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b757-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b757-119">findValue</span><span class="sxs-lookup"><span data-stu-id="0b757-119">findValue</span></span>|<span data-ttu-id="0b757-120">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0b757-120">String.</span></span> <span data-ttu-id="0b757-121">Der zu suchende Wert.</span><span class="sxs-lookup"><span data-stu-id="0b757-121">The value to search for.</span></span>|  
|<span data-ttu-id="0b757-122">storeLocation</span><span class="sxs-lookup"><span data-stu-id="0b757-122">storeLocation</span></span>|<span data-ttu-id="0b757-123">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0b757-123">Enumeration.</span></span> <span data-ttu-id="0b757-124">Einer der beiden zu durchsuchenden Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="0b757-124">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="0b757-125">storeName</span><span class="sxs-lookup"><span data-stu-id="0b757-125">storeName</span></span>|<span data-ttu-id="0b757-126">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0b757-126">Enumeration.</span></span> <span data-ttu-id="0b757-127">Einer der zu durchsuchenden Systemspeicher.</span><span class="sxs-lookup"><span data-stu-id="0b757-127">One of the system stores to search.</span></span>|  
|<span data-ttu-id="0b757-128">x509FindType</span><span class="sxs-lookup"><span data-stu-id="0b757-128">x509FindType</span></span>|<span data-ttu-id="0b757-129">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0b757-129">Enumeration.</span></span> <span data-ttu-id="0b757-130">Eines der zu durchsuchenden Zertifikatfelder.</span><span class="sxs-lookup"><span data-stu-id="0b757-130">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="0b757-131">findValue-Attribut</span><span class="sxs-lookup"><span data-stu-id="0b757-131">findValue Attribute</span></span>  
  
|<span data-ttu-id="0b757-132">Wert</span><span class="sxs-lookup"><span data-stu-id="0b757-132">Value</span></span>|<span data-ttu-id="0b757-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b757-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b757-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b757-134">String</span></span>|<span data-ttu-id="0b757-135">Der Wert ist vom zu durchsuchenden Feld (das durch das X509FindType-Attribut angegeben wird) abhängig.</span><span class="sxs-lookup"><span data-stu-id="0b757-135">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="0b757-136">Wenn Sie beispielsweise nach einem Fingerabdruck suchen, muss der Wert eine Zeichenfolge aus hexadezimalen Zahlen sein.</span><span class="sxs-lookup"><span data-stu-id="0b757-136">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="0b757-137">x509FindType-Attribut</span><span class="sxs-lookup"><span data-stu-id="0b757-137">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="0b757-138">Wert</span><span class="sxs-lookup"><span data-stu-id="0b757-138">Value</span></span>|<span data-ttu-id="0b757-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b757-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b757-140">Enumeration</span><span class="sxs-lookup"><span data-stu-id="0b757-140">Enumeration</span></span>|<span data-ttu-id="0b757-141">Mögliche Werte: FindByThumbprint, findbysubjetname, findbysubjetissushedname, FindByIssuerName, findbyissuererkennbar shedname, findbyserialnumber, FindByTimeValid, FindByTimeNotYetValid, findbyserialnumber, findbytimeabgelauf, findbytemplatename , Findbyapplicationpolicy, findbycertificatepolicy, findbyextension, findbykeyusage, findbysubjetkeyidentifier.</span><span class="sxs-lookup"><span data-stu-id="0b757-141">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="0b757-142">storeLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="0b757-142">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="0b757-143">Wert</span><span class="sxs-lookup"><span data-stu-id="0b757-143">Value</span></span>|<span data-ttu-id="0b757-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b757-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b757-145">Enumeration</span><span class="sxs-lookup"><span data-stu-id="0b757-145">Enumeration</span></span>|<span data-ttu-id="0b757-146">CurrentUser oder LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="0b757-146">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="0b757-147">storeName-Attribut</span><span class="sxs-lookup"><span data-stu-id="0b757-147">storeName Attribute</span></span>  
  
|<span data-ttu-id="0b757-148">Wert</span><span class="sxs-lookup"><span data-stu-id="0b757-148">Value</span></span>|<span data-ttu-id="0b757-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b757-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b757-150">Enumeration</span><span class="sxs-lookup"><span data-stu-id="0b757-150">Enumeration</span></span>|<span data-ttu-id="0b757-151">Mögliche Werte: Addressbook, AuthRoot, CertificateAuthority, unallowed, my, root, treuhändpeople und Treuhänder Publisher.</span><span class="sxs-lookup"><span data-stu-id="0b757-151">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b757-152">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b757-152">Child Elements</span></span>  
 <span data-ttu-id="0b757-153">Keine</span><span class="sxs-lookup"><span data-stu-id="0b757-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b757-154">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b757-154">Parent Elements</span></span>  
  
|<span data-ttu-id="0b757-155">Element</span><span class="sxs-lookup"><span data-stu-id="0b757-155">Element</span></span>|<span data-ttu-id="0b757-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b757-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b757-157">\<knownzertifikate-></span><span class="sxs-lookup"><span data-stu-id="0b757-157">\<knownCertificates></span></span>](knowncertificates.md)|<span data-ttu-id="0b757-158">Gibt eine Auflistung von X.509-Zertifikaten wieder, die von einem Sicherheitstokendienst für die Validierung von Sicherheitstoken bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0b757-158">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b757-159">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b757-159">Remarks</span></span>  
 <span data-ttu-id="0b757-160">Das Szenario für ausgestellte Token weist drei Phasen auf.</span><span class="sxs-lookup"><span data-stu-id="0b757-160">The issued token scenario has three stages.</span></span> <span data-ttu-id="0b757-161">In der ersten Phase wird ein Client, der versucht, auf einen Dienst zuzugreifen, als *sicherer Tokendienst*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0b757-161">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="0b757-162">Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus.</span><span class="sxs-lookup"><span data-stu-id="0b757-162">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="0b757-163">Der Client kehrt dann mit dem Token zum Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="0b757-163">The client then returns to the service with the token.</span></span> <span data-ttu-id="0b757-164">Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben.</span><span class="sxs-lookup"><span data-stu-id="0b757-164">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="0b757-165">Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="0b757-165">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="0b757-166">[ Das\<IssuedTokenAuthentication->](issuedtokenauthentication-of-servicecredentials.md) -Element ist das Repository für alle solchen Zertifikate des Sicherheitstokendiensts.</span><span class="sxs-lookup"><span data-stu-id="0b757-166">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="0b757-167">Verwenden Sie zum Hinzufügen von Zertifikaten die [ \<> Known-Zertifikate](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="0b757-167">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="0b757-168">Fügen Sie für jedes Zertifikat, wie im folgenden Beispiel gezeigt, ein [ \<Add >- \<Element >-Element](add-of-knowncertificates.md) für jedes Zertifikat hinzu.</span><span class="sxs-lookup"><span data-stu-id="0b757-168">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="0b757-169">Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden.</span><span class="sxs-lookup"><span data-stu-id="0b757-169">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="0b757-170">Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="0b757-170">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="0b757-171">Informationen zum Überprüfen der Bedingungen, die für die Authentifizierung eines Clients durch einen Verbund Dienst erforderlich sind, sowie weitere Informationen zur Verwendung dieses Konfigurations Elements finden [Sie unter Gewusst wie: Konfigurieren Sie die Anmelde Informationen](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)für einen Verbunddienst.</span><span class="sxs-lookup"><span data-stu-id="0b757-171">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="0b757-172">Weitere Informationen zu Verbund Szenarien finden Sie unter Verbund [-und ausgestellte Token](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="0b757-172">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b757-173">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b757-173">Example</span></span>  
 <span data-ttu-id="0b757-174">Im folgenden Beispiel wird ein Zertifikat dem Repository für beliebige STS-Zertifikate hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0b757-174">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0b757-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b757-175">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="0b757-176">\<knownzertifikate-></span><span class="sxs-lookup"><span data-stu-id="0b757-176">\<knownCertificates></span></span>](knowncertificates.md)
- [<span data-ttu-id="0b757-177">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="0b757-177">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0b757-178">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="0b757-178">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0b757-179">Vorgehensweise: Konfigurieren von Anmelde Informationen für eine Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="0b757-179">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="0b757-180">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="0b757-180">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
