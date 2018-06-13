---
title: '&lt;sslStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: a86e1aae7ddd5389f098e532ae2c2cc67f4085e3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752402"
---
# <a name="ltsslstreamsecuritygt"></a><span data-ttu-id="99a4c-102">&lt;sslStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="99a4c-102">&lt;sslStreamSecurity&gt;</span></span>
<span data-ttu-id="99a4c-103">Stellt ein benutzerdefiniertes binding-Element dar, das die Kanalsicherheit unter Verwendung eines SSL-Datenstroms unterstützt.</span><span class="sxs-lookup"><span data-stu-id="99a4c-103">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="99a4c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="99a4c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="99a4c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="99a4c-105">\<bindings></span></span>  
<span data-ttu-id="99a4c-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="99a4c-106">\<customBinding></span></span>  
<span data-ttu-id="99a4c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="99a4c-107">\<binding></span></span>  
<span data-ttu-id="99a4c-108">\<SslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="99a4c-108">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99a4c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="99a4c-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"      sslProtocols="Ssl3|Tls|Tls11|Tls12" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99a4c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="99a4c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="99a4c-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="99a4c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99a4c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="99a4c-112">Attributes</span></span>  
  
|<span data-ttu-id="99a4c-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="99a4c-113">Attribute</span></span>|<span data-ttu-id="99a4c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99a4c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99a4c-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="99a4c-115">requireClientCertificate</span></span>|<span data-ttu-id="99a4c-116">Ein boolescher Wert, der angibt, ob ein Clientzertifikat für diese Bindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="99a4c-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="99a4c-117">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="99a4c-117">The default is `false`.</span></span>|  
|<span data-ttu-id="99a4c-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="99a4c-118">sslProtocols</span></span>|<span data-ttu-id="99a4c-119">Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="99a4c-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="99a4c-120">Der Standardwert ist Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="99a4c-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99a4c-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99a4c-121">Child Elements</span></span>  
 <span data-ttu-id="99a4c-122">Keine</span><span class="sxs-lookup"><span data-stu-id="99a4c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99a4c-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99a4c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="99a4c-124">Element</span><span class="sxs-lookup"><span data-stu-id="99a4c-124">Element</span></span>|<span data-ttu-id="99a4c-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99a4c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99a4c-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="99a4c-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="99a4c-127">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="99a4c-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99a4c-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99a4c-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 [<span data-ttu-id="99a4c-129">Bindungen</span><span class="sxs-lookup"><span data-stu-id="99a4c-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="99a4c-130">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="99a4c-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="99a4c-131">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="99a4c-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="99a4c-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="99a4c-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
