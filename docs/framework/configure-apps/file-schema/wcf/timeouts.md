---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b9c67ac03f0eb73a2a4cdd43ab48fe12871a1cc3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854966"
---
# \<timeOuts>
<span data-ttu-id="23596-101">Stellt ein Konfigurationselement dar, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="23596-101">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="23596-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="23596-102">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23596-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="23596-103">Attributes and Elements</span></span>  
 <span data-ttu-id="23596-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="23596-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23596-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="23596-105">Attributes</span></span>  
  
|<span data-ttu-id="23596-106">attribute</span><span class="sxs-lookup"><span data-stu-id="23596-106">Attribute</span></span>|<span data-ttu-id="23596-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="23596-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="23596-108">Ein <xref:System.TimeSpan>-Wert, der das für das Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="23596-108">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="23596-109">Ein <xref:System.TimeSpan>-Wert, der das für das Öffnen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="23596-109">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23596-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="23596-110">Child Elements</span></span>  
 <span data-ttu-id="23596-111">Keine</span><span class="sxs-lookup"><span data-stu-id="23596-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="23596-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="23596-112">Parent Elements</span></span>  
  
|<span data-ttu-id="23596-113">Element</span><span class="sxs-lookup"><span data-stu-id="23596-113">Element</span></span>|<span data-ttu-id="23596-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23596-114">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="23596-115">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="23596-115">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23596-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23596-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="23596-117">Hosting</span><span class="sxs-lookup"><span data-stu-id="23596-117">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
