---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 524226cbb826486def18c1b3b66c5b4a3c456dec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185677"
---
# \<host>

<span data-ttu-id="f089e-101">Gibt die Einstellungen für einen Diensthost an.</span><span class="sxs-lookup"><span data-stu-id="f089e-101">Specifies settings for a service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**  
  
## <a name="syntax"></a><span data-ttu-id="f089e-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="f089e-102">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="f089e-103">Typ</span><span class="sxs-lookup"><span data-stu-id="f089e-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f089e-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f089e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="f089e-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f089e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f089e-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="f089e-106">Attributes</span></span>  

 <span data-ttu-id="f089e-107">Keine</span><span class="sxs-lookup"><span data-stu-id="f089e-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f089e-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f089e-108">Child Elements</span></span>  
  
|<span data-ttu-id="f089e-109">Element</span><span class="sxs-lookup"><span data-stu-id="f089e-109">Element</span></span>|<span data-ttu-id="f089e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f089e-110">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="f089e-111">Eine Auflistung an `baseAddress`-Elementen, die die vom Diensthost verwendeten Basisadressen angeben.</span><span class="sxs-lookup"><span data-stu-id="f089e-111">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[\<timeOuts>](timeouts.md)|<span data-ttu-id="f089e-112">Ein Konfigurationselement, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="f089e-112">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f089e-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f089e-113">Parent Elements</span></span>  
  
|<span data-ttu-id="f089e-114">Element</span><span class="sxs-lookup"><span data-stu-id="f089e-114">Element</span></span>|<span data-ttu-id="f089e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f089e-115">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="f089e-116">Gibt die Einstellungen für einen Windows Communication Foundation (WCF)-Dienst an.</span><span class="sxs-lookup"><span data-stu-id="f089e-116">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f089e-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f089e-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="f089e-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="f089e-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
