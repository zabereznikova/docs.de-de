---
title: <scopedCertificates>-Element
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: 3c06159709df0afe2a475de1e186b0114af32bc2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399956"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="7f3c3-102">\<scopedCertificates>-Element</span><span class="sxs-lookup"><span data-stu-id="7f3c3-102">\<scopedCertificates> Element</span></span>
<span data-ttu-id="7f3c3-103">Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7f3c3-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="7f3c3-104">Diese Auflistung wird normalerweise verwendet, um die Dienstzertifikate für Sicherheitstokendienste in einem Verbundsszenario anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7f3c3-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopedCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="7f3c3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f3c3-105">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f3c3-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7f3c3-106">Attributes and Elements</span></span>  
 <span data-ttu-id="7f3c3-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7f3c3-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f3c3-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="7f3c3-108">Attributes</span></span>  
 <span data-ttu-id="7f3c3-109">Keine</span><span class="sxs-lookup"><span data-stu-id="7f3c3-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7f3c3-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7f3c3-110">Child Elements</span></span>  
  
|<span data-ttu-id="7f3c3-111">Element</span><span class="sxs-lookup"><span data-stu-id="7f3c3-111">Element</span></span>|<span data-ttu-id="7f3c3-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7f3c3-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-scopedcertificates-element.md)|<span data-ttu-id="7f3c3-113">Fügt ein X.509-Zertifikat zur Auflistung der Zertifikate mit Gültigkeitsbereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="7f3c3-113">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f3c3-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7f3c3-114">Parent Elements</span></span>  
  
|<span data-ttu-id="7f3c3-115">Element</span><span class="sxs-lookup"><span data-stu-id="7f3c3-115">Element</span></span>|<span data-ttu-id="7f3c3-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7f3c3-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="7f3c3-117">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7f3c3-117">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f3c3-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7f3c3-118">Remarks</span></span>  
 <span data-ttu-id="7f3c3-119">Diese Auflistung ermöglicht dem Client, die zu verwendenden Dienstzertifikate basierend auf der URL des Diensts, mit dem er kommuniziert, zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7f3c3-119">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="7f3c3-120">Dies ist vor allem hilfreich bei Szenarien mit ausgestellten Token, in denen ein Client mit verschiedenen Diensten kommuniziert (dem Endservice und den zwischengeschalteten Sicherheitstokendiensten).</span><span class="sxs-lookup"><span data-stu-id="7f3c3-120">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="7f3c3-121">Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird dieses Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f3c3-121">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="7f3c3-122">Wenn eine Bindung ein Zertifikat für den Dienst erfordert und kein bestimmtes Zertifikat für die Dienst-URL in ScopedCertificates gefunden wird, wird das Standardzertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f3c3-122">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="7f3c3-123">Weitere Informationen finden Sie im Abschnitt "Bereichs bezogene Zertifikate" unter Gewusst [wie: Erstellen eines Verbund Clients](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="7f3c3-123">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f3c3-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f3c3-124">Example</span></span>  
 <span data-ttu-id="7f3c3-125">Im folgenden Beispiel wird ein Dienst Zertifikat angegeben, das der Client bei der Kommunikation mit Endpunkten, deren Domänen Name über dem HTTP-Protokoll ist, verwendet werden soll `http://www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="7f3c3-125">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7f3c3-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f3c3-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="7f3c3-127">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="7f3c3-127">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="7f3c3-128">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="7f3c3-128">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [\<add>](add-of-scopedcertificates-element.md)
- [<span data-ttu-id="7f3c3-129">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="7f3c3-129">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="7f3c3-130">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="7f3c3-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
