---
title: '&lt;add&gt; von &lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 2cc7cce62082317bb86218d68bd2881b74649771
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670185"
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="f28c5-102">&lt;add&gt; von &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="f28c5-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="f28c5-103">Stellt ein Konfigurationselement dar, das ein Sicherungsendpunktelement definiert.</span><span class="sxs-lookup"><span data-stu-id="f28c5-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="f28c5-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f28c5-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f28c5-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="f28c5-105">\<routing></span></span>  
<span data-ttu-id="f28c5-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="f28c5-106">\<backupLists></span></span>  
<span data-ttu-id="f28c5-107">\<backupList></span><span class="sxs-lookup"><span data-stu-id="f28c5-107">\<backupList></span></span>  
<span data-ttu-id="f28c5-108">\<add></span><span class="sxs-lookup"><span data-stu-id="f28c5-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f28c5-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f28c5-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f28c5-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f28c5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f28c5-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f28c5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f28c5-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f28c5-112">Attributes</span></span>  
  
|<span data-ttu-id="f28c5-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="f28c5-113">Attribute</span></span>|<span data-ttu-id="f28c5-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f28c5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f28c5-115">Name</span><span class="sxs-lookup"><span data-stu-id="f28c5-115">name</span></span>|<span data-ttu-id="f28c5-116">Eine Zeichenfolge, die den Namen des Sicherungsendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="f28c5-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f28c5-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f28c5-117">Child Elements</span></span>  
 <span data-ttu-id="f28c5-118">Keine</span><span class="sxs-lookup"><span data-stu-id="f28c5-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f28c5-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f28c5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f28c5-120">Element</span><span class="sxs-lookup"><span data-stu-id="f28c5-120">Element</span></span>|<span data-ttu-id="f28c5-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f28c5-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f28c5-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="f28c5-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="f28c5-123">Enthält eine Liste der Endpunkte, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="f28c5-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f28c5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f28c5-124">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
