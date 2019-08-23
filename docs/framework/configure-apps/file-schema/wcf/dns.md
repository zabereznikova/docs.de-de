---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 35d33fd4d174c8e4ccdaaf1ac33884663340e16a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919126"
---
# <a name="dns"></a><span data-ttu-id="4f00a-101">\<dns></span><span class="sxs-lookup"><span data-stu-id="4f00a-101">\<dns></span></span>
<span data-ttu-id="4f00a-102">Gibt die erwartete Identität des Servers an.</span><span class="sxs-lookup"><span data-stu-id="4f00a-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="4f00a-103">Diese Identität ist für den X.509-Zertifikat-Authentifizierungsmodus gültig, wenn das Serverzertifikat eine DNS mit dem gleichen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="4f00a-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="4f00a-104">Sie ist auch für den Windows-Authentifizierungsmodus gültig, wenn der SPN den gleichen Wert hat.</span><span class="sxs-lookup"><span data-stu-id="4f00a-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="4f00a-105">Weitere Informationen zum Festlegen des Element Werts finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="4f00a-105">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="4f00a-106">\<identity></span><span class="sxs-lookup"><span data-stu-id="4f00a-106">\<identity></span></span>  
<span data-ttu-id="4f00a-107">\<dns></span><span class="sxs-lookup"><span data-stu-id="4f00a-107">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f00a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f00a-108">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f00a-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4f00a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4f00a-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4f00a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f00a-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="4f00a-111">Attributes</span></span>  
  
|<span data-ttu-id="4f00a-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="4f00a-112">Attribute</span></span>|<span data-ttu-id="4f00a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f00a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f00a-114">Wert</span><span class="sxs-lookup"><span data-stu-id="4f00a-114">value</span></span>|<span data-ttu-id="4f00a-115">Der DNS des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="4f00a-115">The DNS of the certificate.</span></span> <span data-ttu-id="4f00a-116">DNS ist ein standardmäßiges Protokoll, das verwendet wird, um Computer in einem IP-basierten Netzwerk zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4f00a-116">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="4f00a-117">Benutzer können anzeigen Amen <https://go.microsoft.com/fwlink/?prd=10929> wie oder [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165)einfacher als Zahlen basierte Adressen, wie z. b. 207.46.131.137, merken.</span><span class="sxs-lookup"><span data-stu-id="4f00a-117">Users can remember display names, such as <https://go.microsoft.com/fwlink/?prd=10929> or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f00a-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f00a-118">Child Elements</span></span>  
 <span data-ttu-id="4f00a-119">Keine</span><span class="sxs-lookup"><span data-stu-id="4f00a-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f00a-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f00a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4f00a-121">Element</span><span class="sxs-lookup"><span data-stu-id="4f00a-121">Element</span></span>|<span data-ttu-id="4f00a-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f00a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f00a-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="4f00a-123">\<identity></span></span>](identity.md)|<span data-ttu-id="4f00a-124">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="4f00a-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4f00a-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f00a-125">Example</span></span>  
 <span data-ttu-id="4f00a-126">Der folgende Konfigurationscode gibt den DNS eines X.509-Zertifikats an, das für die Authentifizierung eines Servers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4f00a-126">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="4f00a-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f00a-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="4f00a-128">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4f00a-128">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="4f00a-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="4f00a-129">\<identity></span></span>](identity.md)
