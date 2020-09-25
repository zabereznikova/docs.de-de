---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: adfd94365ceb0ddc3164a6baef838c16027b4bc3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190137"
---
# \<dns>

<span data-ttu-id="07511-101">Gibt die erwartete Identität des Servers an.</span><span class="sxs-lookup"><span data-stu-id="07511-101">Specifies the expected identity of the server.</span></span> <span data-ttu-id="07511-102">Diese Identität ist für den X.509-Zertifikat-Authentifizierungsmodus gültig, wenn das Serverzertifikat eine DNS mit dem gleichen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="07511-102">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="07511-103">Sie ist auch für den Windows-Authentifizierungsmodus gültig, wenn der SPN den gleichen Wert hat.</span><span class="sxs-lookup"><span data-stu-id="07511-103">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="07511-104">Weitere Informationen zum Festlegen des Element Werts finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="07511-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**  
  
## <a name="syntax"></a><span data-ttu-id="07511-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="07511-105">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07511-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="07511-106">Attributes and Elements</span></span>  

 <span data-ttu-id="07511-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="07511-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07511-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="07511-108">Attributes</span></span>  
  
|<span data-ttu-id="07511-109">attribute</span><span class="sxs-lookup"><span data-stu-id="07511-109">Attribute</span></span>|<span data-ttu-id="07511-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="07511-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07511-111">value</span><span class="sxs-lookup"><span data-stu-id="07511-111">value</span></span>|<span data-ttu-id="07511-112">Der DNS des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="07511-112">The DNS of the certificate.</span></span> <span data-ttu-id="07511-113">DNS ist ein standardmäßiges Protokoll, das verwendet wird, um Computer in einem IP-basierten Netzwerk zu suchen.</span><span class="sxs-lookup"><span data-stu-id="07511-113">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="07511-114">Benutzer können anzeigen Amen wie `https://go.microsoft.com/fwlink/?prd=10929` oder `https://go.microsoft.com/fwlink/?LinkID=96165` einfacher als Zahlen basierte Adressen, wie z. b. 207.46.131.137, merken.</span><span class="sxs-lookup"><span data-stu-id="07511-114">Users can remember display names, such as `https://go.microsoft.com/fwlink/?prd=10929` or `https://go.microsoft.com/fwlink/?LinkID=96165`, easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07511-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07511-115">Child Elements</span></span>  

 <span data-ttu-id="07511-116">Keine</span><span class="sxs-lookup"><span data-stu-id="07511-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07511-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07511-117">Parent Elements</span></span>  
  
|<span data-ttu-id="07511-118">Element</span><span class="sxs-lookup"><span data-stu-id="07511-118">Element</span></span>|<span data-ttu-id="07511-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07511-119">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="07511-120">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="07511-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="07511-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07511-121">Example</span></span>  

 <span data-ttu-id="07511-122">Der folgende Konfigurationscode gibt den DNS eines X.509-Zertifikats an, das für die Authentifizierung eines Servers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07511-122">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="07511-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07511-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="07511-124">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="07511-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
