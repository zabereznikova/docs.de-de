---
title: '&lt;dns&gt;'
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 68cbb25b79bbda301c29d72800a125c7a6ba0b6f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616458"
---
# <a name="ltdnsgt"></a><span data-ttu-id="2095a-102">&lt;dns&gt;</span><span class="sxs-lookup"><span data-stu-id="2095a-102">&lt;dns&gt;</span></span>
<span data-ttu-id="2095a-103">Gibt die erwartete Identität des Servers an.</span><span class="sxs-lookup"><span data-stu-id="2095a-103">Specifies the expected identity of the server.</span></span> <span data-ttu-id="2095a-104">Diese Identität ist für den X.509-Zertifikat-Authentifizierungsmodus gültig, wenn das Serverzertifikat eine DNS mit dem gleichen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="2095a-104">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="2095a-105">Sie ist auch für den Windows-Authentifizierungsmodus gültig, wenn der SPN den gleichen Wert hat.</span><span class="sxs-lookup"><span data-stu-id="2095a-105">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="2095a-106">Weitere Informationen zum Festlegen der Elementwerte finden Sie unter [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2095a-106">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="2095a-107">\<identity></span><span class="sxs-lookup"><span data-stu-id="2095a-107">\<identity></span></span>  
<span data-ttu-id="2095a-108">\<dns></span><span class="sxs-lookup"><span data-stu-id="2095a-108">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2095a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="2095a-109">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2095a-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2095a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2095a-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2095a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2095a-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="2095a-112">Attributes</span></span>  
  
|<span data-ttu-id="2095a-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="2095a-113">Attribute</span></span>|<span data-ttu-id="2095a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2095a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2095a-115">Wert</span><span class="sxs-lookup"><span data-stu-id="2095a-115">value</span></span>|<span data-ttu-id="2095a-116">Der DNS des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="2095a-116">The DNS of the certificate.</span></span> <span data-ttu-id="2095a-117">DNS ist ein standardmäßiges Protokoll, das verwendet wird, um Computer in einem IP-basierten Netzwerk zu suchen.</span><span class="sxs-lookup"><span data-stu-id="2095a-117">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="2095a-118">Benutzer können die Anzeigenamen, wie z. B. merken [ https://go.microsoft.com/fwlink/?prd=10929 ](https://go.microsoft.com/fwlink/?prd=10929) oder [ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165), leichter merken als zahlenbasierte Adressen, beispielsweise 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="2095a-118">Users can remember display names, such as [https://go.microsoft.com/fwlink/?prd=10929](https://go.microsoft.com/fwlink/?prd=10929) or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2095a-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2095a-119">Child Elements</span></span>  
 <span data-ttu-id="2095a-120">Keine</span><span class="sxs-lookup"><span data-stu-id="2095a-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2095a-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2095a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2095a-122">Element</span><span class="sxs-lookup"><span data-stu-id="2095a-122">Element</span></span>|<span data-ttu-id="2095a-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2095a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2095a-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="2095a-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="2095a-125">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="2095a-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2095a-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2095a-126">Example</span></span>  
 <span data-ttu-id="2095a-127">Der folgende Konfigurationscode gibt den DNS eines X.509-Zertifikats an, das für die Authentifizierung eines Servers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2095a-127">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="2095a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2095a-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="2095a-129">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2095a-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2095a-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="2095a-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
