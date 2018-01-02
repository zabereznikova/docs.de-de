---
title: '&lt;scopedCertificates&gt;-Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 719a52fb1a0f558bda2b337e1402f8aecafc6b8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltscopedcertificatesgt-element"></a><span data-ttu-id="6c270-102">&lt;scopedCertificates&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="6c270-102">&lt;scopedCertificates&gt; Element</span></span>
<span data-ttu-id="6c270-103">Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6c270-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="6c270-104">Diese Auflistung wird normalerweise verwendet, um die Dienstzertifikate für Sicherheitstokendienste in einem Verbundsszenario anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6c270-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
 <span data-ttu-id="6c270-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6c270-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="6c270-106">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="6c270-106">\<behaviors></span></span>  
<span data-ttu-id="6c270-107">EndpointBehaviors-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6c270-107">endpointBehaviors section</span></span>  
<span data-ttu-id="6c270-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="6c270-108">\<behavior></span></span>  
<span data-ttu-id="6c270-109">\<ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="6c270-109">\<clientCredentials></span></span>  
<span data-ttu-id="6c270-110">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="6c270-110">\<serviceCertificate></span></span>  
<span data-ttu-id="6c270-111">\<ScopedCertificates >-Element</span><span class="sxs-lookup"><span data-stu-id="6c270-111">\<scopedCertificates> Element</span></span>  
<span data-ttu-id="6c270-112">\<Hinzufügen >-Element für \<ScopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="6c270-112">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c270-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c270-113">Syntax</span></span>  
  
```xml  
<scopedCertificates>  
      <add findValue="String"  
                storeLocation="CurrentUser/LocalMachine"  
                storeName=" CurrentUser/LocalMachine"  
                targetUri="string"  
            x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />   
</scopedCertificates>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c270-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6c270-114">Attributes and Elements</span></span>  
 <span data-ttu-id="6c270-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c270-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c270-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="6c270-116">Attributes</span></span>  
 <span data-ttu-id="6c270-117">Keine</span><span class="sxs-lookup"><span data-stu-id="6c270-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6c270-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c270-118">Child Elements</span></span>  
  
|<span data-ttu-id="6c270-119">Element</span><span class="sxs-lookup"><span data-stu-id="6c270-119">Element</span></span>|<span data-ttu-id="6c270-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c270-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c270-121">\<add></span><span class="sxs-lookup"><span data-stu-id="6c270-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)|<span data-ttu-id="6c270-122">Fügt ein X.509-Zertifikat zur Auflistung der Zertifikate mit Gültigkeitsbereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="6c270-122">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c270-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c270-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6c270-124">Element</span><span class="sxs-lookup"><span data-stu-id="6c270-124">Element</span></span>|<span data-ttu-id="6c270-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c270-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c270-126">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="6c270-126">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="6c270-127">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6c270-127">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c270-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c270-128">Remarks</span></span>  
 <span data-ttu-id="6c270-129">Diese Auflistung ermöglicht dem Client, die zu verwendenden Dienstzertifikate basierend auf der URL des Diensts, mit dem er kommuniziert, zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6c270-129">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="6c270-130">Dies ist vor allem hilfreich bei Szenarien mit ausgestellten Token, in denen ein Client mit verschiedenen Diensten kommuniziert (dem Endservice und den zwischengeschalteten Sicherheitstokendiensten).</span><span class="sxs-lookup"><span data-stu-id="6c270-130">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="6c270-131">Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird dieses Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="6c270-131">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="6c270-132">Wenn eine Bindung ein Zertifikat für den Dienst erfordert und kein bestimmtes Zertifikat für die Dienst-URL in ScopedCertificates gefunden wird, wird das Standardzertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="6c270-132">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="6c270-133">Weitere Informationen finden Sie im Abschnitt "Zertifikate im Bereich" [Vorgehensweise: Erstellen eines Clients Federated](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="6c270-133">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c270-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c270-134">Example</span></span>  
 <span data-ttu-id="6c270-135">Das folgende Beispiel gibt ein Dienstzertifikat für den Client an, das bei der Kommunikation über das HTTP-Protokoll mit Endpunkten, deren Domänenname http://www.contoso.com ist, verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c270-135">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is http://www.contoso.com over the HTTP protocol.</span></span>  
  
```xml  
<serviceCertificate>  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
</serviceCertificate>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c270-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c270-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>  
 [<span data-ttu-id="6c270-137">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="6c270-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="6c270-138">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="6c270-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="6c270-139">\<add></span><span class="sxs-lookup"><span data-stu-id="6c270-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)  
 [<span data-ttu-id="6c270-140">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="6c270-140">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="6c270-141">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="6c270-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
