---
title: '&lt;add&gt; von &lt;backupList&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 786620b0daf1cd22a95f9d0c94b7fc3d17c1a2c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="a1571-102">&lt;add&gt; von &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="a1571-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="a1571-103">Stellt ein Konfigurationselement dar, das ein Sicherungsendpunktelement definiert.</span><span class="sxs-lookup"><span data-stu-id="a1571-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="a1571-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a1571-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a1571-105">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="a1571-105">\<routing></span></span>  
<span data-ttu-id="a1571-106">\<BackupLists ></span><span class="sxs-lookup"><span data-stu-id="a1571-106">\<backupLists></span></span>  
<span data-ttu-id="a1571-107">\<BackupList ></span><span class="sxs-lookup"><span data-stu-id="a1571-107">\<backupList></span></span>  
<span data-ttu-id="a1571-108">\<add></span><span class="sxs-lookup"><span data-stu-id="a1571-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1571-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1571-109">Syntax</span></span>  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1571-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a1571-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a1571-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1571-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1571-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a1571-112">Attributes</span></span>  
  
|<span data-ttu-id="a1571-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="a1571-113">Attribute</span></span>|<span data-ttu-id="a1571-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1571-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1571-115">Name</span><span class="sxs-lookup"><span data-stu-id="a1571-115">name</span></span>|<span data-ttu-id="a1571-116">Eine Zeichenfolge, die den Namen des Sicherungsendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="a1571-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1571-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1571-117">Child Elements</span></span>  
 <span data-ttu-id="a1571-118">Keine</span><span class="sxs-lookup"><span data-stu-id="a1571-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1571-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1571-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a1571-120">Element</span><span class="sxs-lookup"><span data-stu-id="a1571-120">Element</span></span>|<span data-ttu-id="a1571-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1571-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1571-122">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="a1571-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="a1571-123">Enthält eine Liste der Endpunkte, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="a1571-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1571-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1571-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
