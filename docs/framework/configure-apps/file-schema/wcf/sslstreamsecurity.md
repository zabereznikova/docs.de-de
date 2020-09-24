---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: aa6bc7f5a94afc8a190d3d9d2d71ea8b38d8c25b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153572"
---
# \<sslStreamSecurity>

<span data-ttu-id="80036-101">Stellt ein benutzerdefiniertes Bindungselement dar, das die Kanalsicherheit mit einem SSL-Stream unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80036-101">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="80036-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="80036-102">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80036-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="80036-103">Attributes and Elements</span></span>  

 <span data-ttu-id="80036-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="80036-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80036-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="80036-105">Attributes</span></span>  
  
|<span data-ttu-id="80036-106">attribute</span><span class="sxs-lookup"><span data-stu-id="80036-106">Attribute</span></span>|<span data-ttu-id="80036-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80036-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80036-108">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="80036-108">requireClientCertificate</span></span>|<span data-ttu-id="80036-109">Ein boolescher Wert, der angibt, ob ein Clientzertifikat für diese Bindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="80036-109">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="80036-110">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="80036-110">The default is `false`.</span></span>|  
|<span data-ttu-id="80036-111">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="80036-111">sslProtocols</span></span>|<span data-ttu-id="80036-112">Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="80036-112">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="80036-113">Der Standardwert ist Ssl3&#124;TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="80036-113">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80036-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="80036-114">Child Elements</span></span>  

 <span data-ttu-id="80036-115">Keine</span><span class="sxs-lookup"><span data-stu-id="80036-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80036-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="80036-116">Parent Elements</span></span>  
  
|<span data-ttu-id="80036-117">Element</span><span class="sxs-lookup"><span data-stu-id="80036-117">Element</span></span>|<span data-ttu-id="80036-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80036-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="80036-119">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="80036-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80036-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80036-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="80036-121">Bindungen</span><span class="sxs-lookup"><span data-stu-id="80036-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="80036-122">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="80036-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="80036-123">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="80036-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
