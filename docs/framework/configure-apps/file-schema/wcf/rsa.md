---
title: '&lt;RSA&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab07508c4cab32cb2a60d37af368c345a0f12d88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltrsagt"></a><span data-ttu-id="08686-102">&lt;RSA&gt;</span><span class="sxs-lookup"><span data-stu-id="08686-102">&lt;rsa&gt;</span></span>
<span data-ttu-id="08686-103">Ein sicherer WCF-Client, der mit dieser Identität eine Verbindung zu einem Endpunkt herstellt, stellt sicher, dass die vom Server bereitgestellten Ansprüche einen Anspruch beinhalten, der den zum Erstellen dieser Identität verwendeten öffentlichen RSA-Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="08686-103">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="08686-104">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="08686-104">\<identity></span></span>  
<span data-ttu-id="08686-105">\<RSA ></span><span class="sxs-lookup"><span data-stu-id="08686-105">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08686-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="08686-106">Syntax</span></span>  
  
```xml  
<rsa value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08686-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="08686-107">Attributes and Elements</span></span>  
 <span data-ttu-id="08686-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="08686-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08686-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="08686-109">Attributes</span></span>  
  
|<span data-ttu-id="08686-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="08686-110">Attribute</span></span>|<span data-ttu-id="08686-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08686-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08686-112">Wert</span><span class="sxs-lookup"><span data-stu-id="08686-112">value</span></span>|<span data-ttu-id="08686-113">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="08686-113">Optional String.</span></span> <span data-ttu-id="08686-114">Der Wert des öffentlichen RSA-Schlüssels, der auf dem Client verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="08686-114">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08686-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="08686-115">Child Elements</span></span>  
 <span data-ttu-id="08686-116">Keine</span><span class="sxs-lookup"><span data-stu-id="08686-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08686-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="08686-117">Parent Elements</span></span>  
  
|<span data-ttu-id="08686-118">Element</span><span class="sxs-lookup"><span data-stu-id="08686-118">Element</span></span>|<span data-ttu-id="08686-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08686-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08686-120">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="08686-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="08686-121">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="08686-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08686-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08686-122">Remarks</span></span>  
 <span data-ttu-id="08686-123">Eine RSA-Prüfung ermöglicht Ihnen, die Authentifizierung speziell auf den RSA-Schlüssel eines einzigen Zertifikats zu beschränken oder einen eigenen RSA-Schlüsselwert zu generieren.</span><span class="sxs-lookup"><span data-stu-id="08686-123">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="08686-124">Dies ermöglicht eine strengere Authentifizierung eines bestimmten RSA-Schlüssels auf Kosten des Diensts, der nicht mehr mit vorhandenen Clients zusammenarbeitet, wenn sich der RSA-Schlüsselwert ändert.</span><span class="sxs-lookup"><span data-stu-id="08686-124">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="08686-125">Weitere Informationen zur Verwendung von Identität für einen Dienst an einen Client zu überprüfen, finden Sie unter [-Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="08686-125">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="08686-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08686-126">Example</span></span>  
 <span data-ttu-id="08686-127">Der folgende Konfigurationscode gibt den Wert des öffentlichen Schlüssels eines für die Authentifizierung eines Servers verwendeten X.509-Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="08686-127">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>  
  <rsa value = "0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000"/>  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="08686-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08686-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.RsaEndpointIdentity>  
 [<span data-ttu-id="08686-129">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="08686-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="08686-130">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="08686-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
