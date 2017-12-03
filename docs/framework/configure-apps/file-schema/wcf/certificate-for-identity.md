---
title: "&lt;certificate&gt; für &lt;identity&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8d847def6268881cbd288fe9b3ba89de9403b41d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltcertificategt-for-ltidentitygt"></a><span data-ttu-id="6b052-102">&lt;certificate&gt; für &lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="6b052-102">&lt;certificate&gt; for &lt;identity&gt;</span></span>
<span data-ttu-id="6b052-103">Gibt ein zum Überprüfen eines Servers an einem Client verwendetes X.509-Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="6b052-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="6b052-104">Weitere Informationen zum Festlegen des Werts Element finden Sie unter [-Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="6b052-104">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="6b052-105">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="6b052-105">\<identity></span></span>  
<span data-ttu-id="6b052-106">\<Zertifikat ></span><span class="sxs-lookup"><span data-stu-id="6b052-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b052-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b052-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b052-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6b052-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6b052-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b052-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b052-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="6b052-110">Attributes</span></span>  
  
|<span data-ttu-id="6b052-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="6b052-111">Attribute</span></span>|<span data-ttu-id="6b052-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b052-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b052-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="6b052-113">encodedValue</span></span>|<span data-ttu-id="6b052-114">Eine Base64-Codierung des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="6b052-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b052-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b052-115">Child Elements</span></span>  
 <span data-ttu-id="6b052-116">Keine</span><span class="sxs-lookup"><span data-stu-id="6b052-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b052-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b052-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6b052-118">Element</span><span class="sxs-lookup"><span data-stu-id="6b052-118">Element</span></span>|<span data-ttu-id="6b052-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b052-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b052-120">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="6b052-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="6b052-121">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="6b052-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6b052-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b052-122">Example</span></span>  
 <span data-ttu-id="6b052-123">Im folgenden Code wird die codierte Darstellung eines Zertifikats dargestellt, das zum Überprüfen eines Servers an einem Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6b052-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>  
  <certificate encodedValue = " MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b052-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b052-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.EndpointIdentity>  
 [<span data-ttu-id="6b052-125">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="6b052-125">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="6b052-126">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="6b052-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
