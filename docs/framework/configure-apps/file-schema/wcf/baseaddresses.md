---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 3b6cebd178ac5cd30fa034bd961d2d08075771d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201537"
---
# \<baseAddresses>

<span data-ttu-id="bc677-101">Stellt eine Auflistung von `baseAddress`-Elementen dar, bei denen es sich um Basisadressen für einen Diensthost in einer selbst gehosteten Umgebung handelt.</span><span class="sxs-lookup"><span data-stu-id="bc677-101">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="bc677-102">Wenn eine Basisadresse vorhanden ist, können Endpunkte mit Adressen relativ zur Basisadresse konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="bc677-102">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**  
  
## <a name="syntax"></a><span data-ttu-id="bc677-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc677-103">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="bc677-104">Typ</span><span class="sxs-lookup"><span data-stu-id="bc677-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc677-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bc677-105">Attributes and Elements</span></span>  

 <span data-ttu-id="bc677-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc677-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc677-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="bc677-107">Attributes</span></span>  

 <span data-ttu-id="bc677-108">Keine</span><span class="sxs-lookup"><span data-stu-id="bc677-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bc677-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bc677-109">Child Elements</span></span>  
  
|<span data-ttu-id="bc677-110">Element</span><span class="sxs-lookup"><span data-stu-id="bc677-110">Element</span></span>|<span data-ttu-id="bc677-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc677-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddresses.md)|<span data-ttu-id="bc677-112">Ein Konfigurationselement, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="bc677-112">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bc677-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bc677-113">Parent Elements</span></span>  
  
|<span data-ttu-id="bc677-114">Element</span><span class="sxs-lookup"><span data-stu-id="bc677-114">Element</span></span>|<span data-ttu-id="bc677-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc677-115">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="bc677-116">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="bc677-116">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc677-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc677-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="bc677-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="bc677-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
