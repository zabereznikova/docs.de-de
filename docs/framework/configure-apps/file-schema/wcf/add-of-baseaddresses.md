---
title: <add> von <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: cd0ef5cc5f0f809bdafa23bd312e7e30fcdccc21
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181608"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="2d6db-102">\<add> von \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="2d6db-102">\<add> of \<baseAddresses></span></span>

<span data-ttu-id="2d6db-103">Stellt ein Konfigurationselement dar, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="2d6db-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="2d6db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d6db-104">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="2d6db-105">Typ</span><span class="sxs-lookup"><span data-stu-id="2d6db-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d6db-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2d6db-106">Attributes and Elements</span></span>  

 <span data-ttu-id="2d6db-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2d6db-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d6db-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="2d6db-108">Attributes</span></span>  
  
|<span data-ttu-id="2d6db-109">attribute</span><span class="sxs-lookup"><span data-stu-id="2d6db-109">Attribute</span></span>|<span data-ttu-id="2d6db-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d6db-110">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="2d6db-111">Eine Zeichenfolge, welche die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="2d6db-111">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d6db-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d6db-112">Child Elements</span></span>  

 <span data-ttu-id="2d6db-113">Keine</span><span class="sxs-lookup"><span data-stu-id="2d6db-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d6db-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d6db-114">Parent Elements</span></span>  
  
|<span data-ttu-id="2d6db-115">Element</span><span class="sxs-lookup"><span data-stu-id="2d6db-115">Element</span></span>|<span data-ttu-id="2d6db-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d6db-116">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="2d6db-117">Eine Auflistung von `baseAddress`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="2d6db-117">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d6db-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d6db-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="2d6db-119">Hosting</span><span class="sxs-lookup"><span data-stu-id="2d6db-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
