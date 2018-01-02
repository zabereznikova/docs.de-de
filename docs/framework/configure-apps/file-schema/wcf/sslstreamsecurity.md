---
title: '&lt;sslStreamSecurity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 65233bf416080212a5c1447cffd329eca1b921f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltsslstreamsecuritygt"></a><span data-ttu-id="fb807-102">&lt;sslStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="fb807-102">&lt;sslStreamSecurity&gt;</span></span>
<span data-ttu-id="fb807-103">Stellt ein benutzerdefiniertes binding-Element dar, das die Kanalsicherheit unter Verwendung eines SSL-Datenstroms unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb807-103">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="fb807-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="fb807-104">\<system.serviceModel></span></span>  
<span data-ttu-id="fb807-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="fb807-105">\<bindings></span></span>  
<span data-ttu-id="fb807-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="fb807-106">\<customBinding></span></span>  
<span data-ttu-id="fb807-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="fb807-107">\<binding></span></span>  
<span data-ttu-id="fb807-108">\<SslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="fb807-108">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb807-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb807-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"      sslProtocols="Ssl3|Tls|Tls11|Tls12" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb807-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fb807-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fb807-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fb807-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb807-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="fb807-112">Attributes</span></span>  
  
|<span data-ttu-id="fb807-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="fb807-113">Attribute</span></span>|<span data-ttu-id="fb807-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb807-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb807-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="fb807-115">requireClientCertificate</span></span>|<span data-ttu-id="fb807-116">Ein boolescher Wert, der angibt, ob ein Clientzertifikat für diese Bindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fb807-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="fb807-117">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="fb807-117">The default is `false`.</span></span>|  
|<span data-ttu-id="fb807-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="fb807-118">sslProtocols</span></span>|<span data-ttu-id="fb807-119">Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="fb807-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="fb807-120">Der Standardwert ist Ssl3 &#124; TLS &#124; Tls11 &#124; Tls12.</span><span class="sxs-lookup"><span data-stu-id="fb807-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb807-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb807-121">Child Elements</span></span>  
 <span data-ttu-id="fb807-122">Keine</span><span class="sxs-lookup"><span data-stu-id="fb807-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb807-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb807-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fb807-124">Element</span><span class="sxs-lookup"><span data-stu-id="fb807-124">Element</span></span>|<span data-ttu-id="fb807-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb807-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb807-126">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="fb807-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="fb807-127">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="fb807-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb807-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb807-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 [<span data-ttu-id="fb807-129">Bindungen</span><span class="sxs-lookup"><span data-stu-id="fb807-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fb807-130">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="fb807-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="fb807-131">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="fb807-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="fb807-132">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="fb807-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
