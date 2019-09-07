---
title: <scopedCertificates>-Element
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: 3c06159709df0afe2a475de1e186b0114af32bc2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399956"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="5fbe9-102">\<scopedzertifikate-> Element</span><span class="sxs-lookup"><span data-stu-id="5fbe9-102">\<scopedCertificates> Element</span></span>
<span data-ttu-id="5fbe9-103">Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="5fbe9-104">Diese Auflistung wird normalerweise verwendet, um die Dienstzertifikate für Sicherheitstokendienste in einem Verbundsszenario anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
<span data-ttu-id="5fbe9-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5fbe9-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5fbe9-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5fbe9-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5fbe9-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5fbe9-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="5fbe9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5fbe9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="5fbe9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5fbe9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="5fbe9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client Anmelde Informationen >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="5fbe9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="5fbe9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate->** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="5fbe9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="5fbe9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<scopedzertifikate->**</span><span class="sxs-lookup"><span data-stu-id="5fbe9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopedCertificates>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fbe9-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="5fbe9-113">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5fbe9-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5fbe9-114">Attributes and Elements</span></span>  
 <span data-ttu-id="5fbe9-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5fbe9-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="5fbe9-116">Attributes</span></span>  
 <span data-ttu-id="5fbe9-117">Keine</span><span class="sxs-lookup"><span data-stu-id="5fbe9-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5fbe9-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5fbe9-118">Child Elements</span></span>  
  
|<span data-ttu-id="5fbe9-119">Element</span><span class="sxs-lookup"><span data-stu-id="5fbe9-119">Element</span></span>|<span data-ttu-id="5fbe9-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5fbe9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5fbe9-121">\<add></span><span class="sxs-lookup"><span data-stu-id="5fbe9-121">\<add></span></span>](add-of-scopedcertificates-element.md)|<span data-ttu-id="5fbe9-122">Fügt ein X.509-Zertifikat zur Auflistung der Zertifikate mit Gültigkeitsbereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-122">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5fbe9-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5fbe9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5fbe9-124">Element</span><span class="sxs-lookup"><span data-stu-id="5fbe9-124">Element</span></span>|<span data-ttu-id="5fbe9-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5fbe9-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5fbe9-126">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="5fbe9-126">\<serviceCertificate></span></span>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="5fbe9-127">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-127">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fbe9-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5fbe9-128">Remarks</span></span>  
 <span data-ttu-id="5fbe9-129">Diese Auflistung ermöglicht dem Client, die zu verwendenden Dienstzertifikate basierend auf der URL des Diensts, mit dem er kommuniziert, zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-129">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="5fbe9-130">Dies ist vor allem hilfreich bei Szenarien mit ausgestellten Token, in denen ein Client mit verschiedenen Diensten kommuniziert (dem Endservice und den zwischengeschalteten Sicherheitstokendiensten).</span><span class="sxs-lookup"><span data-stu-id="5fbe9-130">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="5fbe9-131">Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird dieses Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-131">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="5fbe9-132">Wenn eine Bindung ein Zertifikat für den Dienst erfordert und kein bestimmtes Zertifikat für die Dienst-URL in ScopedCertificates gefunden wird, wird das Standardzertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-132">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="5fbe9-133">Weitere Informationen finden Sie im Abschnitt "Bereichs bezogene Zertifikate" unter [Gewusst wie: Erstellen Sie einen Verbund Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="5fbe9-133">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fbe9-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5fbe9-134">Example</span></span>  
 <span data-ttu-id="5fbe9-135">Im folgenden Beispiel wird ein Dienst Zertifikat angegeben, das der Client bei der Kommunikation mit Endpunkten, deren Domänen Name über dem HTTP-Protokoll ist `http://www.contoso.com` , verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-135">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5fbe9-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fbe9-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="5fbe9-137">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="5fbe9-137">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5fbe9-138">Vorgehensweise: Erstellen eines Verbund Clients</span><span class="sxs-lookup"><span data-stu-id="5fbe9-138">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="5fbe9-139">\<add></span><span class="sxs-lookup"><span data-stu-id="5fbe9-139">\<add></span></span>](add-of-scopedcertificates-element.md)
- [<span data-ttu-id="5fbe9-140">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="5fbe9-140">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="5fbe9-141">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="5fbe9-141">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
