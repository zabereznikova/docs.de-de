---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: c5c7ec2b18143ff4d71540a60e24b8225ca4db16
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738596"
---
# \<sslStreamSecurity>
<span data-ttu-id="f50a2-101">Stellt ein benutzerdefiniertes Bindungselement dar, das die Kanalsicherheit mit einem SSL-Stream unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f50a2-101">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="f50a2-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="f50a2-102">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f50a2-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f50a2-103">Attributes and Elements</span></span>  
 <span data-ttu-id="f50a2-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f50a2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f50a2-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="f50a2-105">Attributes</span></span>  
  
|<span data-ttu-id="f50a2-106">attribute</span><span class="sxs-lookup"><span data-stu-id="f50a2-106">Attribute</span></span>|<span data-ttu-id="f50a2-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f50a2-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f50a2-108">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="f50a2-108">requireClientCertificate</span></span>|<span data-ttu-id="f50a2-109">Ein boolescher Wert, der angibt, ob ein Clientzertifikat für diese Bindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f50a2-109">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="f50a2-110">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="f50a2-110">The default is `false`.</span></span>|  
|<span data-ttu-id="f50a2-111">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="f50a2-111">sslProtocols</span></span>|<span data-ttu-id="f50a2-112">Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f50a2-112">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="f50a2-113">Der Standardwert ist Ssl3&#124;TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="f50a2-113">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f50a2-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f50a2-114">Child Elements</span></span>  
 <span data-ttu-id="f50a2-115">Keine</span><span class="sxs-lookup"><span data-stu-id="f50a2-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f50a2-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f50a2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f50a2-117">Element</span><span class="sxs-lookup"><span data-stu-id="f50a2-117">Element</span></span>|<span data-ttu-id="f50a2-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f50a2-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="f50a2-119">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="f50a2-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f50a2-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f50a2-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="f50a2-121">Bindungen</span><span class="sxs-lookup"><span data-stu-id="f50a2-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f50a2-122">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="f50a2-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f50a2-123">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="f50a2-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
