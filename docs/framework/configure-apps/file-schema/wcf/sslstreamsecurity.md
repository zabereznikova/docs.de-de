---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: f66569f36dc61a063b79a088dcbc405126a074d8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284595"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="002e4-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="002e4-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="002e4-102">Stellt ein benutzerdefiniertes binding-Element dar, das die Kanalsicherheit unter Verwendung eines SSL-Datenstroms unterstützt.</span><span class="sxs-lookup"><span data-stu-id="002e4-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="002e4-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="002e4-103">\<system.serviceModel></span></span>  
<span data-ttu-id="002e4-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="002e4-104">\<bindings></span></span>  
<span data-ttu-id="002e4-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="002e4-105">\<customBinding></span></span>  
<span data-ttu-id="002e4-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="002e4-106">\<binding></span></span>  
<span data-ttu-id="002e4-107">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="002e4-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="002e4-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="002e4-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="002e4-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="002e4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="002e4-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="002e4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="002e4-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="002e4-111">Attributes</span></span>  
  
|<span data-ttu-id="002e4-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="002e4-112">Attribute</span></span>|<span data-ttu-id="002e4-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="002e4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="002e4-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="002e4-114">requireClientCertificate</span></span>|<span data-ttu-id="002e4-115">Ein boolescher Wert, der angibt, ob ein Clientzertifikat für diese Bindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="002e4-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="002e4-116">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="002e4-116">The default is `false`.</span></span>|  
|<span data-ttu-id="002e4-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="002e4-117">sslProtocols</span></span>|<span data-ttu-id="002e4-118">Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="002e4-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="002e4-119">Der Standardwert ist Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="002e4-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="002e4-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="002e4-120">Child Elements</span></span>  
 <span data-ttu-id="002e4-121">Keine</span><span class="sxs-lookup"><span data-stu-id="002e4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="002e4-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="002e4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="002e4-123">Element</span><span class="sxs-lookup"><span data-stu-id="002e4-123">Element</span></span>|<span data-ttu-id="002e4-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="002e4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="002e4-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="002e4-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="002e4-126">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="002e4-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="002e4-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="002e4-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="002e4-128">Bindungen</span><span class="sxs-lookup"><span data-stu-id="002e4-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="002e4-129">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="002e4-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="002e4-130">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="002e4-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="002e4-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="002e4-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
