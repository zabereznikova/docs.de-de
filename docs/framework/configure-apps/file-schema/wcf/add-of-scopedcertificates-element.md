---
title: <add>of- <scopedCertificates> Element
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: b00a342108beca69a906fbf6212915768e98778f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398344"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="e3c2a-102">\<add>of- \<scopedCertificates> Element</span><span class="sxs-lookup"><span data-stu-id="e3c2a-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="e3c2a-103">Fügt ein X.509-Zertifikat zur Auflistung der Zertifikate mit Gültigkeitsbereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="e3c2a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3c2a-104">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3c2a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e3c2a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e3c2a-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3c2a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e3c2a-107">Attributes</span></span>  
  
|<span data-ttu-id="e3c2a-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e3c2a-108">Attribute</span></span>|<span data-ttu-id="e3c2a-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e3c2a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e3c2a-110">targetUri</span><span class="sxs-lookup"><span data-stu-id="e3c2a-110">targetUri</span></span>|<span data-ttu-id="e3c2a-111">Eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-111">String.</span></span> <span data-ttu-id="e3c2a-112">Gibt den URI des Diensts an, der mit dem Zertifikat verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-112">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="e3c2a-113">findValue</span><span class="sxs-lookup"><span data-stu-id="e3c2a-113">findValue</span></span>|<span data-ttu-id="e3c2a-114">Eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-114">String.</span></span> <span data-ttu-id="e3c2a-115">Der zu suchende Wert.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-115">The value to search for.</span></span>|  
|<span data-ttu-id="e3c2a-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="e3c2a-116">x509FindType</span></span>|<span data-ttu-id="e3c2a-117">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-117">Enumeration.</span></span> <span data-ttu-id="e3c2a-118">Eines der zu durchsuchenden Zertifikatfelder.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-118">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="e3c2a-119">storeLocation</span><span class="sxs-lookup"><span data-stu-id="e3c2a-119">storeLocation</span></span>|<span data-ttu-id="e3c2a-120">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-120">Enumeration.</span></span> <span data-ttu-id="e3c2a-121">Einer der beiden zu durchsuchenden Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-121">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="e3c2a-122">storeName</span><span class="sxs-lookup"><span data-stu-id="e3c2a-122">storeName</span></span>|<span data-ttu-id="e3c2a-123">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-123">Enumeration.</span></span> <span data-ttu-id="e3c2a-124">Einer der zu durchsuchenden Systemspeicher.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-124">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="e3c2a-125">findValue-Attribut</span><span class="sxs-lookup"><span data-stu-id="e3c2a-125">findValue Attribute</span></span>  
  
|<span data-ttu-id="e3c2a-126">Wert</span><span class="sxs-lookup"><span data-stu-id="e3c2a-126">Value</span></span>|<span data-ttu-id="e3c2a-127">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e3c2a-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e3c2a-128">String</span><span class="sxs-lookup"><span data-stu-id="e3c2a-128">String</span></span>|<span data-ttu-id="e3c2a-129">Der Wert ist vom zu durchsuchenden Feld (das durch das X509FindType-Attribut angegeben wird) abhängig.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-129">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="e3c2a-130">Wenn Sie beispielsweise nach einem Fingerabdruck suchen, muss der Wert eine Zeichenfolge aus hexadezimalen Zahlen sein.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-130">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="e3c2a-131">x509FindType-Attribut</span><span class="sxs-lookup"><span data-stu-id="e3c2a-131">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="e3c2a-132">Wert</span><span class="sxs-lookup"><span data-stu-id="e3c2a-132">Value</span></span>|<span data-ttu-id="e3c2a-133">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e3c2a-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e3c2a-134">Enumeration</span><span class="sxs-lookup"><span data-stu-id="e3c2a-134">Enumeration</span></span>|<span data-ttu-id="e3c2a-135">Zu den gültigen Werten gehören: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-135">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="e3c2a-136">storeLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="e3c2a-136">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="e3c2a-137">Wert</span><span class="sxs-lookup"><span data-stu-id="e3c2a-137">Value</span></span>|<span data-ttu-id="e3c2a-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e3c2a-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e3c2a-139">Enumeration</span><span class="sxs-lookup"><span data-stu-id="e3c2a-139">Enumeration</span></span>|<span data-ttu-id="e3c2a-140">CurrentUser oder LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-140">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="e3c2a-141">storeName-Attribut</span><span class="sxs-lookup"><span data-stu-id="e3c2a-141">storeName Attribute</span></span>  
  
|<span data-ttu-id="e3c2a-142">Wert</span><span class="sxs-lookup"><span data-stu-id="e3c2a-142">Value</span></span>|<span data-ttu-id="e3c2a-143">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e3c2a-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e3c2a-144">Enumeration</span><span class="sxs-lookup"><span data-stu-id="e3c2a-144">Enumeration</span></span>|<span data-ttu-id="e3c2a-145">Zu den gültigen Werten gehören: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople und TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-145">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3c2a-146">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e3c2a-146">Child Elements</span></span>  
 <span data-ttu-id="e3c2a-147">Keine</span><span class="sxs-lookup"><span data-stu-id="e3c2a-147">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3c2a-148">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e3c2a-148">Parent Elements</span></span>  
  
|<span data-ttu-id="e3c2a-149">Element</span><span class="sxs-lookup"><span data-stu-id="e3c2a-149">Element</span></span>|<span data-ttu-id="e3c2a-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3c2a-150">Description</span></span>|  
|-------------|-----------------|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="e3c2a-151">Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-151">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3c2a-152">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e3c2a-152">Remarks</span></span>  
 <span data-ttu-id="e3c2a-153">Dieses Element ermöglicht dem Client, ein zu verwendendes Dienstzertifikat basierend auf der URL des Dienstes, mit dem er kommuniziert, zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-153">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="e3c2a-154">Dies ist vor allem hilfreich bei Szenarien mit ausgestellten Token, in denen ein Client mit verschiedenen Diensten kommuniziert (dem Endservice und den zwischengeschalteten Sicherheitstokendiensten).</span><span class="sxs-lookup"><span data-stu-id="e3c2a-154">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="e3c2a-155">Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird dieses Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-155">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="e3c2a-156">Wenn eine Bindung ein Zertifikat für den Dienst erfordert und kein bestimmtes Zertifikat für die Dienst-URL in ScopedCertificates gefunden wird, wird das Standardzertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-156">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="e3c2a-157">Weitere Informationen finden Sie im Abschnitt "Bereichs bezogene Zertifikate" unter Gewusst [wie: Erstellen eines Verbund Clients](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="e3c2a-157">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3c2a-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e3c2a-158">Example</span></span>  
 <span data-ttu-id="e3c2a-159">Im folgenden Beispiel wird der Auflistung ein X.509-Zertifikat hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e3c2a-159">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e3c2a-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3c2a-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="e3c2a-161">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="e3c2a-161">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="e3c2a-162">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="e3c2a-162">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="e3c2a-163">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="e3c2a-163">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="e3c2a-164">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="e3c2a-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
