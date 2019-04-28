---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 67ec30b2bf3c322b949700789ce942e4281b77a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757988"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="7ee11-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="7ee11-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="7ee11-102">Stellt ein benutzerdefiniertes Bindungselement dar, das die Kanalsicherheit mit einem SSL-Stream unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7ee11-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="7ee11-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7ee11-103">\<system.serviceModel></span></span>  
<span data-ttu-id="7ee11-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7ee11-104">\<bindings></span></span>  
<span data-ttu-id="7ee11-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7ee11-105">\<customBinding></span></span>  
<span data-ttu-id="7ee11-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="7ee11-106">\<binding></span></span>  
<span data-ttu-id="7ee11-107">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="7ee11-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ee11-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ee11-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ee11-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7ee11-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7ee11-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7ee11-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ee11-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="7ee11-111">Attributes</span></span>  
  
|<span data-ttu-id="7ee11-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="7ee11-112">Attribute</span></span>|<span data-ttu-id="7ee11-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ee11-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7ee11-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="7ee11-114">requireClientCertificate</span></span>|<span data-ttu-id="7ee11-115">Ein boolescher Wert, der angibt, ob ein Clientzertifikat für diese Bindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7ee11-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="7ee11-116">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="7ee11-116">The default is `false`.</span></span>|  
|<span data-ttu-id="7ee11-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="7ee11-117">sslProtocols</span></span>|<span data-ttu-id="7ee11-118">Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7ee11-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="7ee11-119">Der Standardwert ist Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="7ee11-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ee11-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ee11-120">Child Elements</span></span>  
 <span data-ttu-id="7ee11-121">Keine</span><span class="sxs-lookup"><span data-stu-id="7ee11-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ee11-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ee11-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7ee11-123">Element</span><span class="sxs-lookup"><span data-stu-id="7ee11-123">Element</span></span>|<span data-ttu-id="7ee11-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ee11-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ee11-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="7ee11-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="7ee11-126">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="7ee11-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ee11-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ee11-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="7ee11-128">Bindungen</span><span class="sxs-lookup"><span data-stu-id="7ee11-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="7ee11-129">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="7ee11-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7ee11-130">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="7ee11-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="7ee11-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7ee11-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
