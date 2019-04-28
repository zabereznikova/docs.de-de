---
title: <add> der <scopedCertificates> Element
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 06a624d0146745581dfe907d044d1f7d3b857902
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673862"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="dc090-102">\<Hinzufügen > der \<ScopedCertificates >-Element</span><span class="sxs-lookup"><span data-stu-id="dc090-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="dc090-103">Fügt ein X.509-Zertifikat zur Auflistung der Zertifikate mit Gültigkeitsbereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc090-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
 <span data-ttu-id="dc090-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dc090-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dc090-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="dc090-105">\<behaviors></span></span>  
<span data-ttu-id="dc090-106">EndpointBehaviors-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dc090-106">endpointBehaviors section</span></span>  
<span data-ttu-id="dc090-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="dc090-107">\<behavior></span></span>  
<span data-ttu-id="dc090-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="dc090-108">\<clientCredentials></span></span>  
<span data-ttu-id="dc090-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="dc090-109">\<serviceCertificate></span></span>  
<span data-ttu-id="dc090-110">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="dc090-110">\<scopedCertificates></span></span>  
<span data-ttu-id="dc090-111">\<Hinzufügen >-Element für \<ScopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="dc090-111">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc090-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc090-112">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc090-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dc090-113">Attributes and Elements</span></span>  
 <span data-ttu-id="dc090-114">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dc090-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc090-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="dc090-115">Attributes</span></span>  
  
|<span data-ttu-id="dc090-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="dc090-116">Attribute</span></span>|<span data-ttu-id="dc090-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc090-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc090-118">targetUri</span><span class="sxs-lookup"><span data-stu-id="dc090-118">targetUri</span></span>|<span data-ttu-id="dc090-119">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="dc090-119">String.</span></span> <span data-ttu-id="dc090-120">Gibt den URI des Diensts an, der mit dem Zertifikat verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="dc090-120">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="dc090-121">findValue</span><span class="sxs-lookup"><span data-stu-id="dc090-121">findValue</span></span>|<span data-ttu-id="dc090-122">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="dc090-122">String.</span></span> <span data-ttu-id="dc090-123">Der zu suchende Wert.</span><span class="sxs-lookup"><span data-stu-id="dc090-123">The value to search for.</span></span>|  
|<span data-ttu-id="dc090-124">x509FindType</span><span class="sxs-lookup"><span data-stu-id="dc090-124">x509FindType</span></span>|<span data-ttu-id="dc090-125">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="dc090-125">Enumeration.</span></span> <span data-ttu-id="dc090-126">Eines der zu durchsuchenden Zertifikatfelder.</span><span class="sxs-lookup"><span data-stu-id="dc090-126">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="dc090-127">storeLocation</span><span class="sxs-lookup"><span data-stu-id="dc090-127">storeLocation</span></span>|<span data-ttu-id="dc090-128">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="dc090-128">Enumeration.</span></span> <span data-ttu-id="dc090-129">Einer der beiden zu durchsuchenden Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="dc090-129">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="dc090-130">storeName</span><span class="sxs-lookup"><span data-stu-id="dc090-130">storeName</span></span>|<span data-ttu-id="dc090-131">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="dc090-131">Enumeration.</span></span> <span data-ttu-id="dc090-132">Einer der zu durchsuchenden Systemspeicher.</span><span class="sxs-lookup"><span data-stu-id="dc090-132">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="dc090-133">findValue-Attribut</span><span class="sxs-lookup"><span data-stu-id="dc090-133">findValue Attribute</span></span>  
  
|<span data-ttu-id="dc090-134">Wert</span><span class="sxs-lookup"><span data-stu-id="dc090-134">Value</span></span>|<span data-ttu-id="dc090-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc090-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dc090-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="dc090-136">String</span></span>|<span data-ttu-id="dc090-137">Der Wert ist vom zu durchsuchenden Feld (das durch das X509FindType-Attribut angegeben wird) abhängig.</span><span class="sxs-lookup"><span data-stu-id="dc090-137">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="dc090-138">Wenn Sie beispielsweise nach einem Fingerabdruck suchen, muss der Wert eine Zeichenfolge aus hexadezimalen Zahlen sein.</span><span class="sxs-lookup"><span data-stu-id="dc090-138">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="dc090-139">x509FindType-Attribut</span><span class="sxs-lookup"><span data-stu-id="dc090-139">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="dc090-140">Wert</span><span class="sxs-lookup"><span data-stu-id="dc090-140">Value</span></span>|<span data-ttu-id="dc090-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc090-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dc090-142">Enumeration</span><span class="sxs-lookup"><span data-stu-id="dc090-142">Enumeration</span></span>|<span data-ttu-id="dc090-143">Mögliche Werte: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="dc090-143">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="dc090-144">storeLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="dc090-144">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="dc090-145">Wert</span><span class="sxs-lookup"><span data-stu-id="dc090-145">Value</span></span>|<span data-ttu-id="dc090-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc090-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dc090-147">Enumeration</span><span class="sxs-lookup"><span data-stu-id="dc090-147">Enumeration</span></span>|<span data-ttu-id="dc090-148">CurrentUser oder LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="dc090-148">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="dc090-149">storeName-Attribut</span><span class="sxs-lookup"><span data-stu-id="dc090-149">storeName Attribute</span></span>  
  
|<span data-ttu-id="dc090-150">Wert</span><span class="sxs-lookup"><span data-stu-id="dc090-150">Value</span></span>|<span data-ttu-id="dc090-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc090-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dc090-152">Enumeration</span><span class="sxs-lookup"><span data-stu-id="dc090-152">Enumeration</span></span>|<span data-ttu-id="dc090-153">Mögliche Werte: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople und TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="dc090-153">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc090-154">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc090-154">Child Elements</span></span>  
 <span data-ttu-id="dc090-155">Keine</span><span class="sxs-lookup"><span data-stu-id="dc090-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc090-156">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc090-156">Parent Elements</span></span>  
  
|<span data-ttu-id="dc090-157">Element</span><span class="sxs-lookup"><span data-stu-id="dc090-157">Element</span></span>|<span data-ttu-id="dc090-158">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc090-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc090-159">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="dc090-159">\<scopedCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|<span data-ttu-id="dc090-160">Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="dc090-160">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc090-161">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dc090-161">Remarks</span></span>  
 <span data-ttu-id="dc090-162">Dieses Element ermöglicht dem Client, ein zu verwendendes Dienstzertifikat basierend auf der URL des Dienstes, mit dem er kommuniziert, zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dc090-162">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="dc090-163">Dies ist vor allem hilfreich bei Szenarien mit ausgestellten Token, in denen ein Client mit verschiedenen Diensten kommuniziert (dem Endservice und den zwischengeschalteten Sicherheitstokendiensten).</span><span class="sxs-lookup"><span data-stu-id="dc090-163">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="dc090-164">Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird dieses Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc090-164">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="dc090-165">Wenn eine Bindung ein Zertifikat für den Dienst erfordert und kein bestimmtes Zertifikat für die Dienst-URL in ScopedCertificates gefunden wird, wird das Standardzertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc090-165">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="dc090-166">Weitere Informationen finden Sie im Abschnitt "Zertifikate mit Gültigkeitsbereich" [Vorgehensweise: Erstellen eines Verbundclients](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="dc090-166">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc090-167">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc090-167">Example</span></span>  
 <span data-ttu-id="dc090-168">Im folgenden Beispiel wird der Auflistung ein X.509-Zertifikat hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dc090-168">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dc090-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc090-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="dc090-170">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="dc090-170">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="dc090-171">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="dc090-171">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="dc090-172">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="dc090-172">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="dc090-173">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="dc090-173">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
