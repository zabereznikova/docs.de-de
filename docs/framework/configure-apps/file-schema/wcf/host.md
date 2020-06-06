---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: b764bc21e9c4555b39c3d096212b6e6bcabb62ff
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855212"
---
# \<host>
<span data-ttu-id="e9a94-101">Gibt die Einstellungen für einen Diensthost an.</span><span class="sxs-lookup"><span data-stu-id="e9a94-101">Specifies settings for a service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**  
  
## <a name="syntax"></a><span data-ttu-id="e9a94-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9a94-102">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="e9a94-103">type</span><span class="sxs-lookup"><span data-stu-id="e9a94-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9a94-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e9a94-104">Attributes and Elements</span></span>  
 <span data-ttu-id="e9a94-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9a94-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9a94-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="e9a94-106">Attributes</span></span>  
 <span data-ttu-id="e9a94-107">Keine</span><span class="sxs-lookup"><span data-stu-id="e9a94-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e9a94-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9a94-108">Child Elements</span></span>  
  
|<span data-ttu-id="e9a94-109">Element</span><span class="sxs-lookup"><span data-stu-id="e9a94-109">Element</span></span>|<span data-ttu-id="e9a94-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e9a94-110">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="e9a94-111">Eine Auflistung an `baseAddress`-Elementen, die die vom Diensthost verwendeten Basisadressen angeben.</span><span class="sxs-lookup"><span data-stu-id="e9a94-111">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[\<timeOuts>](timeouts.md)|<span data-ttu-id="e9a94-112">Ein Konfigurationselement, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="e9a94-112">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9a94-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9a94-113">Parent Elements</span></span>  
  
|<span data-ttu-id="e9a94-114">Element</span><span class="sxs-lookup"><span data-stu-id="e9a94-114">Element</span></span>|<span data-ttu-id="e9a94-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e9a94-115">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="e9a94-116">Gibt die Einstellungen für einen Windows Communication Foundation (WCF)-Dienst an.</span><span class="sxs-lookup"><span data-stu-id="e9a94-116">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9a94-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9a94-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="e9a94-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="e9a94-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
