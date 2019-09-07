---
title: <add>of <scopedCertificates> -Element
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: b00a342108beca69a906fbf6212915768e98778f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398344"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="98b57-102">\<> von \<"scopedzertifikate" > Element hinzufügen</span><span class="sxs-lookup"><span data-stu-id="98b57-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="98b57-103">Fügt ein X.509-Zertifikat zur Auflistung der Zertifikate mit Gültigkeitsbereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="98b57-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
<span data-ttu-id="98b57-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="98b57-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="98b57-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="98b57-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="98b57-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="98b57-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="98b57-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="98b57-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="98b57-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="98b57-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="98b57-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client Anmelde Informationen >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="98b57-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="98b57-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate->** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="98b57-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="98b57-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<scopedzertifikate->** ](scopedcertificates-element.md)</span><span class="sxs-lookup"><span data-stu-id="98b57-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)</span></span>\
<span data-ttu-id="98b57-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="98b57-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98b57-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="98b57-113">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98b57-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="98b57-114">Attributes and Elements</span></span>  
 <span data-ttu-id="98b57-115">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="98b57-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98b57-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="98b57-116">Attributes</span></span>  
  
|<span data-ttu-id="98b57-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="98b57-117">Attribute</span></span>|<span data-ttu-id="98b57-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98b57-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="98b57-119">targetUri</span><span class="sxs-lookup"><span data-stu-id="98b57-119">targetUri</span></span>|<span data-ttu-id="98b57-120">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="98b57-120">String.</span></span> <span data-ttu-id="98b57-121">Gibt den URI des Diensts an, der mit dem Zertifikat verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="98b57-121">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="98b57-122">findValue</span><span class="sxs-lookup"><span data-stu-id="98b57-122">findValue</span></span>|<span data-ttu-id="98b57-123">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="98b57-123">String.</span></span> <span data-ttu-id="98b57-124">Der zu suchende Wert.</span><span class="sxs-lookup"><span data-stu-id="98b57-124">The value to search for.</span></span>|  
|<span data-ttu-id="98b57-125">x509FindType</span><span class="sxs-lookup"><span data-stu-id="98b57-125">x509FindType</span></span>|<span data-ttu-id="98b57-126">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="98b57-126">Enumeration.</span></span> <span data-ttu-id="98b57-127">Eines der zu durchsuchenden Zertifikatfelder.</span><span class="sxs-lookup"><span data-stu-id="98b57-127">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="98b57-128">storeLocation</span><span class="sxs-lookup"><span data-stu-id="98b57-128">storeLocation</span></span>|<span data-ttu-id="98b57-129">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="98b57-129">Enumeration.</span></span> <span data-ttu-id="98b57-130">Einer der beiden zu durchsuchenden Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="98b57-130">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="98b57-131">storeName</span><span class="sxs-lookup"><span data-stu-id="98b57-131">storeName</span></span>|<span data-ttu-id="98b57-132">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="98b57-132">Enumeration.</span></span> <span data-ttu-id="98b57-133">Einer der zu durchsuchenden Systemspeicher.</span><span class="sxs-lookup"><span data-stu-id="98b57-133">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="98b57-134">findValue-Attribut</span><span class="sxs-lookup"><span data-stu-id="98b57-134">findValue Attribute</span></span>  
  
|<span data-ttu-id="98b57-135">Wert</span><span class="sxs-lookup"><span data-stu-id="98b57-135">Value</span></span>|<span data-ttu-id="98b57-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98b57-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="98b57-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="98b57-137">String</span></span>|<span data-ttu-id="98b57-138">Der Wert ist vom zu durchsuchenden Feld (das durch das X509FindType-Attribut angegeben wird) abhängig.</span><span class="sxs-lookup"><span data-stu-id="98b57-138">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="98b57-139">Wenn Sie beispielsweise nach einem Fingerabdruck suchen, muss der Wert eine Zeichenfolge aus hexadezimalen Zahlen sein.</span><span class="sxs-lookup"><span data-stu-id="98b57-139">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="98b57-140">x509FindType-Attribut</span><span class="sxs-lookup"><span data-stu-id="98b57-140">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="98b57-141">Wert</span><span class="sxs-lookup"><span data-stu-id="98b57-141">Value</span></span>|<span data-ttu-id="98b57-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98b57-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="98b57-143">Enumeration</span><span class="sxs-lookup"><span data-stu-id="98b57-143">Enumeration</span></span>|<span data-ttu-id="98b57-144">Mögliche Werte: FindByThumbprint, findbysubjetname, findbysubjetissushedname, FindByIssuerName, findbyissuererkennbar shedname, findbyserialnumber, FindByTimeValid, FindByTimeNotYetValid, findbyserialnumber, findbytimeabgelauf, findbytemplatename , Findbyapplicationpolicy, findbycertificatepolicy, findbyextension, findbykeyusage, findbysubjetkeyidentifier.</span><span class="sxs-lookup"><span data-stu-id="98b57-144">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="98b57-145">storeLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="98b57-145">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="98b57-146">Wert</span><span class="sxs-lookup"><span data-stu-id="98b57-146">Value</span></span>|<span data-ttu-id="98b57-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98b57-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="98b57-148">Enumeration</span><span class="sxs-lookup"><span data-stu-id="98b57-148">Enumeration</span></span>|<span data-ttu-id="98b57-149">CurrentUser oder LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="98b57-149">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="98b57-150">storeName-Attribut</span><span class="sxs-lookup"><span data-stu-id="98b57-150">storeName Attribute</span></span>  
  
|<span data-ttu-id="98b57-151">Wert</span><span class="sxs-lookup"><span data-stu-id="98b57-151">Value</span></span>|<span data-ttu-id="98b57-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98b57-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="98b57-153">Enumeration</span><span class="sxs-lookup"><span data-stu-id="98b57-153">Enumeration</span></span>|<span data-ttu-id="98b57-154">Mögliche Werte: Addressbook, AuthRoot, CertificateAuthority, unallowed, my, root, treuhändpeople und Treuhänder Publisher.</span><span class="sxs-lookup"><span data-stu-id="98b57-154">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="98b57-155">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="98b57-155">Child Elements</span></span>  
 <span data-ttu-id="98b57-156">Keine</span><span class="sxs-lookup"><span data-stu-id="98b57-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="98b57-157">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="98b57-157">Parent Elements</span></span>  
  
|<span data-ttu-id="98b57-158">Element</span><span class="sxs-lookup"><span data-stu-id="98b57-158">Element</span></span>|<span data-ttu-id="98b57-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98b57-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="98b57-160">\<scopedzertifikate-></span><span class="sxs-lookup"><span data-stu-id="98b57-160">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="98b57-161">Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="98b57-161">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98b57-162">Hinweise</span><span class="sxs-lookup"><span data-stu-id="98b57-162">Remarks</span></span>  
 <span data-ttu-id="98b57-163">Dieses Element ermöglicht dem Client, ein zu verwendendes Dienstzertifikat basierend auf der URL des Dienstes, mit dem er kommuniziert, zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="98b57-163">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="98b57-164">Dies ist vor allem hilfreich bei Szenarien mit ausgestellten Token, in denen ein Client mit verschiedenen Diensten kommuniziert (dem Endservice und den zwischengeschalteten Sicherheitstokendiensten).</span><span class="sxs-lookup"><span data-stu-id="98b57-164">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="98b57-165">Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird dieses Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="98b57-165">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="98b57-166">Wenn eine Bindung ein Zertifikat für den Dienst erfordert und kein bestimmtes Zertifikat für die Dienst-URL in ScopedCertificates gefunden wird, wird das Standardzertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="98b57-166">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="98b57-167">Weitere Informationen finden Sie im Abschnitt "Bereichs bezogene Zertifikate" unter [Gewusst wie: Erstellen Sie einen Verbund Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="98b57-167">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98b57-168">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98b57-168">Example</span></span>  
 <span data-ttu-id="98b57-169">Im folgenden Beispiel wird der Auflistung ein X.509-Zertifikat hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="98b57-169">The following example adds an X.509 certificate the collection.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <serviceCertificate>
          <scopedCertificates>
            <add targetUri="http://www.contoso.com"
                 findValue="www.Contoso.com"
                 storeLocation="LocalMachine"
                 storeName="Root"
                 x509FindType="FindByIssuerName" />
          </scopedCertificates>
        </serviceCertificate>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="98b57-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98b57-170">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="98b57-171">Vorgehensweise: Erstellen eines Verbund Clients</span><span class="sxs-lookup"><span data-stu-id="98b57-171">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="98b57-172">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="98b57-172">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="98b57-173">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="98b57-173">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="98b57-174">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="98b57-174">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
