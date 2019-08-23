---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: dd8e5ab11a7c019a8fe967f1c14b88a922a16c33
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934736"
---
# <a name="rsa"></a><span data-ttu-id="be980-101">\<rsa></span><span class="sxs-lookup"><span data-stu-id="be980-101">\<rsa></span></span>
<span data-ttu-id="be980-102">Ein sicherer WCF-Client, der mit dieser Identität eine Verbindung zu einem Endpunkt herstellt, stellt sicher, dass die vom Server bereitgestellten Ansprüche einen Anspruch beinhalten, der den zum Erstellen dieser Identität verwendeten öffentlichen RSA-Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="be980-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="be980-103">\<identity></span><span class="sxs-lookup"><span data-stu-id="be980-103">\<identity></span></span>  
<span data-ttu-id="be980-104">\<rsa></span><span class="sxs-lookup"><span data-stu-id="be980-104">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be980-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="be980-105">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be980-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="be980-106">Attributes and Elements</span></span>  
 <span data-ttu-id="be980-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="be980-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be980-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="be980-108">Attributes</span></span>  
  
|<span data-ttu-id="be980-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="be980-109">Attribute</span></span>|<span data-ttu-id="be980-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be980-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="be980-111">Wert</span><span class="sxs-lookup"><span data-stu-id="be980-111">value</span></span>|<span data-ttu-id="be980-112">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="be980-112">Optional String.</span></span> <span data-ttu-id="be980-113">Der Wert des öffentlichen RSA-Schlüssels, der auf dem Client verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="be980-113">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be980-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="be980-114">Child Elements</span></span>  
 <span data-ttu-id="be980-115">None</span><span class="sxs-lookup"><span data-stu-id="be980-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="be980-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="be980-116">Parent Elements</span></span>  
  
|<span data-ttu-id="be980-117">Element</span><span class="sxs-lookup"><span data-stu-id="be980-117">Element</span></span>|<span data-ttu-id="be980-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be980-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be980-119">\<identity></span><span class="sxs-lookup"><span data-stu-id="be980-119">\<identity></span></span>](identity.md)|<span data-ttu-id="be980-120">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="be980-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be980-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be980-121">Remarks</span></span>  
 <span data-ttu-id="be980-122">Eine RSA-Prüfung ermöglicht Ihnen, die Authentifizierung speziell auf den RSA-Schlüssel eines einzigen Zertifikats zu beschränken oder einen eigenen RSA-Schlüsselwert zu generieren.</span><span class="sxs-lookup"><span data-stu-id="be980-122">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="be980-123">Dies ermöglicht eine strengere Authentifizierung eines bestimmten RSA-Schlüssels auf Kosten des Diensts, der nicht mehr mit vorhandenen Clients zusammenarbeitet, wenn sich der RSA-Schlüsselwert ändert.</span><span class="sxs-lookup"><span data-stu-id="be980-123">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="be980-124">Weitere Informationen zum Überprüfen eines Dienstanbieter mithilfe der Identität für einen Client finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="be980-124">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be980-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be980-125">Example</span></span>  
 <span data-ttu-id="be980-126">Der folgende Konfigurationscode gibt den Wert des öffentlichen Schlüssels eines für die Authentifizierung eines Servers verwendeten X.509-Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="be980-126">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="be980-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be980-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="be980-128">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="be980-128">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="be980-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="be980-129">\<identity></span></span>](identity.md)
