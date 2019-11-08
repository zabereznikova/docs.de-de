---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: c5c7ec2b18143ff4d71540a60e24b8225ca4db16
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738596"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="468b6-101">\<sslStreamSecurity-></span><span class="sxs-lookup"><span data-stu-id="468b6-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="468b6-102">Stellt ein benutzerdefiniertes Bindungselement dar, das die Kanalsicherheit mit einem SSL-Stream unterstützt.</span><span class="sxs-lookup"><span data-stu-id="468b6-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
<span data-ttu-id="468b6-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="468b6-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="468b6-104">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="468b6-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="468b6-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="468b6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="468b6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="468b6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="468b6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="468b6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="468b6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<sslStreamSecurity >**</span><span class="sxs-lookup"><span data-stu-id="468b6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="468b6-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="468b6-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="468b6-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="468b6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="468b6-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="468b6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="468b6-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="468b6-112">Attributes</span></span>  
  
|<span data-ttu-id="468b6-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="468b6-113">Attribute</span></span>|<span data-ttu-id="468b6-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="468b6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="468b6-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="468b6-115">requireClientCertificate</span></span>|<span data-ttu-id="468b6-116">Ein boolescher Wert, der angibt, ob ein Clientzertifikat für diese Bindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="468b6-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="468b6-117">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="468b6-117">The default is `false`.</span></span>|  
|<span data-ttu-id="468b6-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="468b6-118">sslProtocols</span></span>|<span data-ttu-id="468b6-119">Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="468b6-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="468b6-120">Der Standardwert ist&#124;Ssl3&#124;TLS&#124;Tls11 Tls12.</span><span class="sxs-lookup"><span data-stu-id="468b6-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="468b6-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="468b6-121">Child Elements</span></span>  
 <span data-ttu-id="468b6-122">Keine</span><span class="sxs-lookup"><span data-stu-id="468b6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="468b6-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="468b6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="468b6-124">Element</span><span class="sxs-lookup"><span data-stu-id="468b6-124">Element</span></span>|<span data-ttu-id="468b6-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="468b6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="468b6-126">\<binding ></span><span class="sxs-lookup"><span data-stu-id="468b6-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="468b6-127">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="468b6-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="468b6-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="468b6-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="468b6-129">Bindungen</span><span class="sxs-lookup"><span data-stu-id="468b6-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="468b6-130">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="468b6-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="468b6-131">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="468b6-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="468b6-132">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="468b6-132">\<customBinding></span></span>](custombinding.md)
