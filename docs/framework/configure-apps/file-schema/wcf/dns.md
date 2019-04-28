---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 26b45b17ecd7bbd3fffb5d03553834ec22eedc62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700929"
---
# <a name="dns"></a><span data-ttu-id="87a20-101">\<dns></span><span class="sxs-lookup"><span data-stu-id="87a20-101">\<dns></span></span>
<span data-ttu-id="87a20-102">Gibt die erwartete Identität des Servers an.</span><span class="sxs-lookup"><span data-stu-id="87a20-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="87a20-103">Diese Identität ist für den X.509-Zertifikat-Authentifizierungsmodus gültig, wenn das Serverzertifikat eine DNS mit dem gleichen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="87a20-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="87a20-104">Sie ist auch für den Windows-Authentifizierungsmodus gültig, wenn der SPN den gleichen Wert hat.</span><span class="sxs-lookup"><span data-stu-id="87a20-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="87a20-105">Weitere Informationen zum Festlegen der Elementwerte finden Sie unter [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="87a20-105">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="87a20-106">\<identity></span><span class="sxs-lookup"><span data-stu-id="87a20-106">\<identity></span></span>  
<span data-ttu-id="87a20-107">\<dns></span><span class="sxs-lookup"><span data-stu-id="87a20-107">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87a20-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="87a20-108">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87a20-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="87a20-109">Attributes and Elements</span></span>  
 <span data-ttu-id="87a20-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="87a20-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87a20-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="87a20-111">Attributes</span></span>  
  
|<span data-ttu-id="87a20-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="87a20-112">Attribute</span></span>|<span data-ttu-id="87a20-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87a20-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87a20-114">Wert</span><span class="sxs-lookup"><span data-stu-id="87a20-114">value</span></span>|<span data-ttu-id="87a20-115">Der DNS des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="87a20-115">The DNS of the certificate.</span></span> <span data-ttu-id="87a20-116">DNS ist ein standardmäßiges Protokoll, das verwendet wird, um Computer in einem IP-basierten Netzwerk zu suchen.</span><span class="sxs-lookup"><span data-stu-id="87a20-116">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="87a20-117">Benutzer können die Anzeigenamen, wie z. B. merken <https://go.microsoft.com/fwlink/?prd=10929> oder [ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165), leichter merken als zahlenbasierte Adressen, beispielsweise 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="87a20-117">Users can remember display names, such as <https://go.microsoft.com/fwlink/?prd=10929> or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87a20-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87a20-118">Child Elements</span></span>  
 <span data-ttu-id="87a20-119">Keine</span><span class="sxs-lookup"><span data-stu-id="87a20-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87a20-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87a20-120">Parent Elements</span></span>  
  
|<span data-ttu-id="87a20-121">Element</span><span class="sxs-lookup"><span data-stu-id="87a20-121">Element</span></span>|<span data-ttu-id="87a20-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87a20-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87a20-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="87a20-123">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="87a20-124">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="87a20-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="87a20-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87a20-125">Example</span></span>  
 <span data-ttu-id="87a20-126">Der folgende Konfigurationscode gibt den DNS eines X.509-Zertifikats an, das für die Authentifizierung eines Servers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="87a20-126">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="87a20-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87a20-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="87a20-128">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="87a20-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="87a20-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="87a20-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
