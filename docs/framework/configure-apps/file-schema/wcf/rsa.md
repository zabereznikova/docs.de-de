---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 0e307069bd3a98153cc66147ba7bcf511cf13a8e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091654"
---
# <a name="rsa"></a><span data-ttu-id="3efd2-101">\<rsa></span><span class="sxs-lookup"><span data-stu-id="3efd2-101">\<rsa></span></span>
<span data-ttu-id="3efd2-102">Ein sicherer WCF-Client, der mit dieser Identität eine Verbindung zu einem Endpunkt herstellt, stellt sicher, dass die vom Server bereitgestellten Ansprüche einen Anspruch beinhalten, der den zum Erstellen dieser Identität verwendeten öffentlichen RSA-Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="3efd2-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="3efd2-103">\<identity></span><span class="sxs-lookup"><span data-stu-id="3efd2-103">\<identity></span></span>  
<span data-ttu-id="3efd2-104">\<rsa></span><span class="sxs-lookup"><span data-stu-id="3efd2-104">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3efd2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3efd2-105">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3efd2-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3efd2-106">Attributes and Elements</span></span>  
 <span data-ttu-id="3efd2-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3efd2-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3efd2-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="3efd2-108">Attributes</span></span>  
  
|<span data-ttu-id="3efd2-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="3efd2-109">Attribute</span></span>|<span data-ttu-id="3efd2-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3efd2-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3efd2-111">Wert</span><span class="sxs-lookup"><span data-stu-id="3efd2-111">value</span></span>|<span data-ttu-id="3efd2-112">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3efd2-112">Optional String.</span></span> <span data-ttu-id="3efd2-113">Der Wert des öffentlichen RSA-Schlüssels, der auf dem Client verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="3efd2-113">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3efd2-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3efd2-114">Child Elements</span></span>  
 <span data-ttu-id="3efd2-115">Keiner</span><span class="sxs-lookup"><span data-stu-id="3efd2-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3efd2-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3efd2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3efd2-117">Element</span><span class="sxs-lookup"><span data-stu-id="3efd2-117">Element</span></span>|<span data-ttu-id="3efd2-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3efd2-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3efd2-119">\<identity></span><span class="sxs-lookup"><span data-stu-id="3efd2-119">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="3efd2-120">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="3efd2-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3efd2-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3efd2-121">Remarks</span></span>  
 <span data-ttu-id="3efd2-122">Eine RSA-Prüfung ermöglicht Ihnen, die Authentifizierung speziell auf den RSA-Schlüssel eines einzigen Zertifikats zu beschränken oder einen eigenen RSA-Schlüsselwert zu generieren.</span><span class="sxs-lookup"><span data-stu-id="3efd2-122">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="3efd2-123">Dies ermöglicht eine strengere Authentifizierung eines bestimmten RSA-Schlüssels auf Kosten des Diensts, der nicht mehr mit vorhandenen Clients zusammenarbeitet, wenn sich der RSA-Schlüsselwert ändert.</span><span class="sxs-lookup"><span data-stu-id="3efd2-123">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="3efd2-124">Weitere Informationen zur Verwendung der Identität ein Diensts gegenüber einem Client zu überprüfen, finden Sie unter [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="3efd2-124">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3efd2-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3efd2-125">Example</span></span>  
 <span data-ttu-id="3efd2-126">Der folgende Konfigurationscode gibt den Wert des öffentlichen Schlüssels eines für die Authentifizierung eines Servers verwendeten X.509-Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="3efd2-126">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="3efd2-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3efd2-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="3efd2-128">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="3efd2-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3efd2-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="3efd2-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
