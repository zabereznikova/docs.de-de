---
title: <add> von <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: d75142209ad8706d0cad5ce188d9d991a5e881bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850587"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="7be55-102">\<add> von \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="7be55-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="7be55-103">Stellt ein Konfigurationselement dar, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="7be55-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="7be55-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7be55-104">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="7be55-105">type</span><span class="sxs-lookup"><span data-stu-id="7be55-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7be55-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7be55-106">Attributes and Elements</span></span>  
 <span data-ttu-id="7be55-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7be55-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7be55-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="7be55-108">Attributes</span></span>  
  
|<span data-ttu-id="7be55-109">attribute</span><span class="sxs-lookup"><span data-stu-id="7be55-109">Attribute</span></span>|<span data-ttu-id="7be55-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7be55-110">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="7be55-111">Eine Zeichenfolge, welche die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="7be55-111">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7be55-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7be55-112">Child Elements</span></span>  
 <span data-ttu-id="7be55-113">Keine</span><span class="sxs-lookup"><span data-stu-id="7be55-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7be55-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7be55-114">Parent Elements</span></span>  
  
|<span data-ttu-id="7be55-115">Element</span><span class="sxs-lookup"><span data-stu-id="7be55-115">Element</span></span>|<span data-ttu-id="7be55-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7be55-116">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="7be55-117">Eine Auflistung von `baseAddress`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="7be55-117">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7be55-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7be55-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="7be55-119">Hosting</span><span class="sxs-lookup"><span data-stu-id="7be55-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
