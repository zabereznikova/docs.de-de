---
title: '&lt;DNS&gt;'
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 6125bf157d04a1b0298a183465d11a18ac3786f0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltdnsgt"></a><span data-ttu-id="99b7b-102">&lt;DNS&gt;</span><span class="sxs-lookup"><span data-stu-id="99b7b-102">&lt;dns&gt;</span></span>
<span data-ttu-id="99b7b-103">Gibt die erwartete Identität des Servers an.</span><span class="sxs-lookup"><span data-stu-id="99b7b-103">Specifies the expected identity of the server.</span></span> <span data-ttu-id="99b7b-104">Diese Identität ist für den X.509-Zertifikat-Authentifizierungsmodus gültig, wenn das Serverzertifikat eine DNS mit dem gleichen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="99b7b-104">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="99b7b-105">Sie ist auch für den Windows-Authentifizierungsmodus gültig, wenn der SPN den gleichen Wert hat.</span><span class="sxs-lookup"><span data-stu-id="99b7b-105">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="99b7b-106">Weitere Informationen zum Festlegen des Werts Element finden Sie unter [-Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="99b7b-106">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="99b7b-107">\<identity></span><span class="sxs-lookup"><span data-stu-id="99b7b-107">\<identity></span></span>  
<span data-ttu-id="99b7b-108">\<DNS ></span><span class="sxs-lookup"><span data-stu-id="99b7b-108">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99b7b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="99b7b-109">Syntax</span></span>  
  
```xml  
<dns value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99b7b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="99b7b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="99b7b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="99b7b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99b7b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="99b7b-112">Attributes</span></span>  
  
|<span data-ttu-id="99b7b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="99b7b-113">Attribute</span></span>|<span data-ttu-id="99b7b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99b7b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99b7b-115">Wert</span><span class="sxs-lookup"><span data-stu-id="99b7b-115">value</span></span>|<span data-ttu-id="99b7b-116">Der DNS des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="99b7b-116">The DNS of the certificate.</span></span> <span data-ttu-id="99b7b-117">DNS ist ein standardmäßiges Protokoll, das verwendet wird, um Computer in einem IP-basierten Netzwerk zu suchen.</span><span class="sxs-lookup"><span data-stu-id="99b7b-117">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="99b7b-118">Benutzer können die Anzeigenamen, wie z. B. merken [ http://go.microsoft.com/fwlink/?prd=10929 ](http://go.microsoft.com/fwlink/?prd=10929) oder [ http://go.microsoft.com/fwlink/?LinkID=96165 ](http://go.microsoft.com/fwlink/?LinkID=96165), leichter merken als zahlenbasierte Adressen, beispielsweise 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="99b7b-118">Users can remember display names, such as [http://go.microsoft.com/fwlink/?prd=10929](http://go.microsoft.com/fwlink/?prd=10929) or [http://go.microsoft.com/fwlink/?LinkID=96165](http://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99b7b-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99b7b-119">Child Elements</span></span>  
 <span data-ttu-id="99b7b-120">Keine</span><span class="sxs-lookup"><span data-stu-id="99b7b-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99b7b-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99b7b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="99b7b-122">Element</span><span class="sxs-lookup"><span data-stu-id="99b7b-122">Element</span></span>|<span data-ttu-id="99b7b-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99b7b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99b7b-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="99b7b-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="99b7b-125">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="99b7b-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="99b7b-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="99b7b-126">Example</span></span>  
 <span data-ttu-id="99b7b-127">Der folgende Konfigurationscode gibt den DNS eines X.509-Zertifikats an, das für die Authentifizierung eines Servers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="99b7b-127">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>  
  <dns value = "www.cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99b7b-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99b7b-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.DnsEndpointIdentity>  
 [<span data-ttu-id="99b7b-129">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="99b7b-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="99b7b-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="99b7b-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
