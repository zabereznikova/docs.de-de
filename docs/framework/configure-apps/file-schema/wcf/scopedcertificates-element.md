---
title: <scopedCertificates>-Element
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: ed53a42575a8d57c365f7a329a1a9c1df075d6d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935222"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="2d4cf-102">\<scopedzertifikate-> Element</span><span class="sxs-lookup"><span data-stu-id="2d4cf-102">\<scopedCertificates> Element</span></span>
<span data-ttu-id="2d4cf-103">Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="2d4cf-104">Diese Auflistung wird normalerweise verwendet, um die Dienstzertifikate für Sicherheitstokendienste in einem Verbundsszenario anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
 <span data-ttu-id="2d4cf-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2d4cf-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="2d4cf-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2d4cf-106">\<behaviors></span></span>  
<span data-ttu-id="2d4cf-107">endpointverhaltenbereich</span><span class="sxs-lookup"><span data-stu-id="2d4cf-107">endpointBehaviors section</span></span>  
<span data-ttu-id="2d4cf-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2d4cf-108">\<behavior></span></span>  
<span data-ttu-id="2d4cf-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="2d4cf-109">\<clientCredentials></span></span>  
<span data-ttu-id="2d4cf-110">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="2d4cf-110">\<serviceCertificate></span></span>  
<span data-ttu-id="2d4cf-111">\<scopedzertifikate-> Element</span><span class="sxs-lookup"><span data-stu-id="2d4cf-111">\<scopedCertificates> Element</span></span>  
<span data-ttu-id="2d4cf-112">\<Fügen Sie >- \<Element für scopedzertifikate hinzu ></span><span class="sxs-lookup"><span data-stu-id="2d4cf-112">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d4cf-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d4cf-113">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d4cf-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2d4cf-114">Attributes and Elements</span></span>  
 <span data-ttu-id="2d4cf-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d4cf-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="2d4cf-116">Attributes</span></span>  
 <span data-ttu-id="2d4cf-117">Keine</span><span class="sxs-lookup"><span data-stu-id="2d4cf-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2d4cf-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d4cf-118">Child Elements</span></span>  
  
|<span data-ttu-id="2d4cf-119">Element</span><span class="sxs-lookup"><span data-stu-id="2d4cf-119">Element</span></span>|<span data-ttu-id="2d4cf-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d4cf-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d4cf-121">\<add></span><span class="sxs-lookup"><span data-stu-id="2d4cf-121">\<add></span></span>](add-of-scopedcertificates-element.md)|<span data-ttu-id="2d4cf-122">Fügt ein X.509-Zertifikat zur Auflistung der Zertifikate mit Gültigkeitsbereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-122">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2d4cf-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d4cf-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2d4cf-124">Element</span><span class="sxs-lookup"><span data-stu-id="2d4cf-124">Element</span></span>|<span data-ttu-id="2d4cf-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d4cf-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d4cf-126">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="2d4cf-126">\<serviceCertificate></span></span>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="2d4cf-127">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-127">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d4cf-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d4cf-128">Remarks</span></span>  
 <span data-ttu-id="2d4cf-129">Diese Auflistung ermöglicht dem Client, die zu verwendenden Dienstzertifikate basierend auf der URL des Diensts, mit dem er kommuniziert, zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-129">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="2d4cf-130">Dies ist vor allem hilfreich bei Szenarien mit ausgestellten Token, in denen ein Client mit verschiedenen Diensten kommuniziert (dem Endservice und den zwischengeschalteten Sicherheitstokendiensten).</span><span class="sxs-lookup"><span data-stu-id="2d4cf-130">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="2d4cf-131">Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird dieses Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-131">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="2d4cf-132">Wenn eine Bindung ein Zertifikat für den Dienst erfordert und kein bestimmtes Zertifikat für die Dienst-URL in ScopedCertificates gefunden wird, wird das Standardzertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-132">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="2d4cf-133">Weitere Informationen finden Sie im Abschnitt "Bereichs bezogene Zertifikate" unter [Gewusst wie: Erstellen Sie einen Verbund Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="2d4cf-133">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d4cf-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2d4cf-134">Example</span></span>  
 <span data-ttu-id="2d4cf-135">Im folgenden Beispiel wird ein Dienst Zertifikat angegeben, das der Client bei der Kommunikation mit Endpunkten, deren Domänen Name über dem HTTP-Protokoll ist `http://www.contoso.com` , verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-135">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
```xml  
<serviceCertificate>
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="2d4cf-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d4cf-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="2d4cf-137">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="2d4cf-137">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="2d4cf-138">Vorgehensweise: Erstellen eines Verbund Clients</span><span class="sxs-lookup"><span data-stu-id="2d4cf-138">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="2d4cf-139">\<add></span><span class="sxs-lookup"><span data-stu-id="2d4cf-139">\<add></span></span>](add-of-scopedcertificates-element.md)
- [<span data-ttu-id="2d4cf-140">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="2d4cf-140">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="2d4cf-141">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="2d4cf-141">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
