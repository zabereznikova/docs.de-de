---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 0e1651f563bdb2b2b24eacacf7bfe387e33a82c7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855042"
---
# <a name="rsa"></a><span data-ttu-id="1d7c7-101">\<rsa></span><span class="sxs-lookup"><span data-stu-id="1d7c7-101">\<rsa></span></span>
<span data-ttu-id="1d7c7-102">Ein sicherer WCF-Client, der mit dieser Identität eine Verbindung zu einem Endpunkt herstellt, stellt sicher, dass die vom Server bereitgestellten Ansprüche einen Anspruch beinhalten, der den zum Erstellen dieser Identität verwendeten öffentlichen RSA-Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="1d7c7-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
<span data-ttu-id="1d7c7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1d7c7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1d7c7-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1d7c7-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1d7c7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="1d7c7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="1d7c7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Endpunkt >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="1d7c7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="1d7c7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Identitäts >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="1d7c7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="1d7c7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<RSA->**</span><span class="sxs-lookup"><span data-stu-id="1d7c7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rsa>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d7c7-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d7c7-109">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d7c7-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1d7c7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1d7c7-111">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1d7c7-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d7c7-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="1d7c7-112">Attributes</span></span>  
  
|<span data-ttu-id="1d7c7-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="1d7c7-113">Attribute</span></span>|<span data-ttu-id="1d7c7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d7c7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d7c7-115">Wert</span><span class="sxs-lookup"><span data-stu-id="1d7c7-115">value</span></span>|<span data-ttu-id="1d7c7-116">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1d7c7-116">Optional String.</span></span> <span data-ttu-id="1d7c7-117">Der Wert des öffentlichen RSA-Schlüssels, der auf dem Client verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1d7c7-117">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d7c7-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1d7c7-118">Child Elements</span></span>  
 <span data-ttu-id="1d7c7-119">None</span><span class="sxs-lookup"><span data-stu-id="1d7c7-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1d7c7-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1d7c7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1d7c7-121">Element</span><span class="sxs-lookup"><span data-stu-id="1d7c7-121">Element</span></span>|<span data-ttu-id="1d7c7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d7c7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d7c7-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="1d7c7-123">\<identity></span></span>](identity.md)|<span data-ttu-id="1d7c7-124">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="1d7c7-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d7c7-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d7c7-125">Remarks</span></span>  
 <span data-ttu-id="1d7c7-126">Eine RSA-Prüfung ermöglicht Ihnen, die Authentifizierung speziell auf den RSA-Schlüssel eines einzigen Zertifikats zu beschränken oder einen eigenen RSA-Schlüsselwert zu generieren.</span><span class="sxs-lookup"><span data-stu-id="1d7c7-126">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="1d7c7-127">Dies ermöglicht eine strengere Authentifizierung eines bestimmten RSA-Schlüssels auf Kosten des Diensts, der nicht mehr mit vorhandenen Clients zusammenarbeitet, wenn sich der RSA-Schlüsselwert ändert.</span><span class="sxs-lookup"><span data-stu-id="1d7c7-127">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="1d7c7-128">Weitere Informationen zum Überprüfen eines Dienstanbieter mithilfe der Identität für einen Client finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="1d7c7-128">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d7c7-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d7c7-129">Example</span></span>  
 <span data-ttu-id="1d7c7-130">Der folgende Konfigurationscode gibt den Wert des öffentlichen Schlüssels eines für die Authentifizierung eines Servers verwendeten X.509-Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="1d7c7-130">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="1d7c7-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d7c7-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="1d7c7-132">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="1d7c7-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="1d7c7-133">\<identity></span><span class="sxs-lookup"><span data-stu-id="1d7c7-133">\<identity></span></span>](identity.md)
