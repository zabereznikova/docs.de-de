---
title: <add> von <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 80726cc22cb56013c85c7704c28579b1337666c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850552"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="fbe8e-102">\<add> von \<backupList></span><span class="sxs-lookup"><span data-stu-id="fbe8e-102">\<add> of \<backupList></span></span>
<span data-ttu-id="fbe8e-103">Stellt ein Konfigurationselement dar, das ein Sicherungsendpunktelement definiert.</span><span class="sxs-lookup"><span data-stu-id="fbe8e-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="fbe8e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fbe8e-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbe8e-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fbe8e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="fbe8e-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fbe8e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbe8e-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="fbe8e-107">Attributes</span></span>  
  
|<span data-ttu-id="fbe8e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="fbe8e-108">Attribute</span></span>|<span data-ttu-id="fbe8e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fbe8e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fbe8e-110">name</span><span class="sxs-lookup"><span data-stu-id="fbe8e-110">name</span></span>|<span data-ttu-id="fbe8e-111">Eine Zeichenfolge, die den Namen des Sicherungsendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="fbe8e-111">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbe8e-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fbe8e-112">Child Elements</span></span>  
 <span data-ttu-id="fbe8e-113">Keine</span><span class="sxs-lookup"><span data-stu-id="fbe8e-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fbe8e-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fbe8e-114">Parent Elements</span></span>  
  
|<span data-ttu-id="fbe8e-115">Element</span><span class="sxs-lookup"><span data-stu-id="fbe8e-115">Element</span></span>|<span data-ttu-id="fbe8e-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbe8e-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="fbe8e-117">Enthält eine Reihe von Endpunkten, die der Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann. </span><span class="sxs-lookup"><span data-stu-id="fbe8e-117">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fbe8e-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fbe8e-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
