---
title: <add> of- <scopedCertificates> Element
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 28777ecac130295a8ba82a8e4d67cc519d088d8a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195141"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="ec6e2-102">\<add> of- \<scopedCertificates> Element</span><span class="sxs-lookup"><span data-stu-id="ec6e2-102">\<add> of \<scopedCertificates> Element</span></span>

<span data-ttu-id="ec6e2-103">Fügt ein X.509-Zertifikat zur Auflistung der Zertifikate mit Gültigkeitsbereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="ec6e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec6e2-104">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec6e2-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ec6e2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ec6e2-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec6e2-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="ec6e2-107">Attributes</span></span>  
  
|<span data-ttu-id="ec6e2-108">attribute</span><span class="sxs-lookup"><span data-stu-id="ec6e2-108">Attribute</span></span>|<span data-ttu-id="ec6e2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec6e2-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec6e2-110">targetUri</span><span class="sxs-lookup"><span data-stu-id="ec6e2-110">targetUri</span></span>|<span data-ttu-id="ec6e2-111">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-111">String.</span></span> <span data-ttu-id="ec6e2-112">Gibt den URI des Diensts an, der mit dem Zertifikat verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-112">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="ec6e2-113">findValue</span><span class="sxs-lookup"><span data-stu-id="ec6e2-113">findValue</span></span>|<span data-ttu-id="ec6e2-114">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-114">String.</span></span> <span data-ttu-id="ec6e2-115">Der zu suchende Wert.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-115">The value to search for.</span></span>|  
|<span data-ttu-id="ec6e2-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="ec6e2-116">x509FindType</span></span>|<span data-ttu-id="ec6e2-117">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-117">Enumeration.</span></span> <span data-ttu-id="ec6e2-118">Eines der zu durchsuchenden Zertifikatfelder.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-118">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="ec6e2-119">storeLocation</span><span class="sxs-lookup"><span data-stu-id="ec6e2-119">storeLocation</span></span>|<span data-ttu-id="ec6e2-120">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-120">Enumeration.</span></span> <span data-ttu-id="ec6e2-121">Einer der beiden zu durchsuchenden Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-121">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="ec6e2-122">storeName</span><span class="sxs-lookup"><span data-stu-id="ec6e2-122">storeName</span></span>|<span data-ttu-id="ec6e2-123">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-123">Enumeration.</span></span> <span data-ttu-id="ec6e2-124">Einer der zu durchsuchenden Systemspeicher.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-124">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="ec6e2-125">findValue-Attribut</span><span class="sxs-lookup"><span data-stu-id="ec6e2-125">findValue Attribute</span></span>  
  
|<span data-ttu-id="ec6e2-126">Wert</span><span class="sxs-lookup"><span data-stu-id="ec6e2-126">Value</span></span>|<span data-ttu-id="ec6e2-127">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ec6e2-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ec6e2-128">String</span><span class="sxs-lookup"><span data-stu-id="ec6e2-128">String</span></span>|<span data-ttu-id="ec6e2-129">Der Wert ist vom zu durchsuchenden Feld (das durch das X509FindType-Attribut angegeben wird) abhängig.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-129">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="ec6e2-130">Wenn Sie beispielsweise nach einem Fingerabdruck suchen, muss der Wert eine Zeichenfolge aus hexadezimalen Zahlen sein.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-130">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="ec6e2-131">x509FindType-Attribut</span><span class="sxs-lookup"><span data-stu-id="ec6e2-131">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="ec6e2-132">Wert</span><span class="sxs-lookup"><span data-stu-id="ec6e2-132">Value</span></span>|<span data-ttu-id="ec6e2-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec6e2-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ec6e2-134">Enumeration</span><span class="sxs-lookup"><span data-stu-id="ec6e2-134">Enumeration</span></span>|<span data-ttu-id="ec6e2-135">Zu den gültigen Werten gehören: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-135">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="ec6e2-136">storeLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="ec6e2-136">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="ec6e2-137">Wert</span><span class="sxs-lookup"><span data-stu-id="ec6e2-137">Value</span></span>|<span data-ttu-id="ec6e2-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec6e2-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ec6e2-139">Enumeration</span><span class="sxs-lookup"><span data-stu-id="ec6e2-139">Enumeration</span></span>|<span data-ttu-id="ec6e2-140">CurrentUser oder LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-140">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="ec6e2-141">storeName-Attribut</span><span class="sxs-lookup"><span data-stu-id="ec6e2-141">storeName Attribute</span></span>  
  
|<span data-ttu-id="ec6e2-142">Wert</span><span class="sxs-lookup"><span data-stu-id="ec6e2-142">Value</span></span>|<span data-ttu-id="ec6e2-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec6e2-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ec6e2-144">Enumeration</span><span class="sxs-lookup"><span data-stu-id="ec6e2-144">Enumeration</span></span>|<span data-ttu-id="ec6e2-145">Zu den gültigen Werten gehören: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople und TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-145">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec6e2-146">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ec6e2-146">Child Elements</span></span>  

 <span data-ttu-id="ec6e2-147">Keine</span><span class="sxs-lookup"><span data-stu-id="ec6e2-147">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec6e2-148">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ec6e2-148">Parent Elements</span></span>  
  
|<span data-ttu-id="ec6e2-149">Element</span><span class="sxs-lookup"><span data-stu-id="ec6e2-149">Element</span></span>|<span data-ttu-id="ec6e2-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec6e2-150">Description</span></span>|  
|-------------|-----------------|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="ec6e2-151">Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-151">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec6e2-152">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ec6e2-152">Remarks</span></span>  

 <span data-ttu-id="ec6e2-153">Dieses Element ermöglicht dem Client, ein zu verwendendes Dienstzertifikat basierend auf der URL des Dienstes, mit dem er kommuniziert, zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-153">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="ec6e2-154">Dies ist vor allem hilfreich bei Szenarien mit ausgestellten Token, in denen ein Client mit verschiedenen Diensten kommuniziert (dem Endservice und den zwischengeschalteten Sicherheitstokendiensten).</span><span class="sxs-lookup"><span data-stu-id="ec6e2-154">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="ec6e2-155">Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird dieses Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-155">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="ec6e2-156">Wenn eine Bindung ein Zertifikat für den Dienst erfordert und kein bestimmtes Zertifikat für die Dienst-URL in ScopedCertificates gefunden wird, wird das Standardzertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-156">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="ec6e2-157">Weitere Informationen finden Sie im Abschnitt "Bereichs bezogene Zertifikate" unter Gewusst [wie: Erstellen eines Verbund Clients](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="ec6e2-157">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec6e2-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec6e2-158">Example</span></span>  

 <span data-ttu-id="ec6e2-159">Im folgenden Beispiel wird der Auflistung ein X.509-Zertifikat hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ec6e2-159">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ec6e2-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec6e2-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="ec6e2-161">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="ec6e2-161">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="ec6e2-162">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="ec6e2-162">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="ec6e2-163">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="ec6e2-163">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="ec6e2-164">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="ec6e2-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
