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
ms.openlocfilehash: b93b442d21d34eea5031cea565bdcf62139abc81
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="558df-102">&lt;add&gt; von &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="558df-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="558df-103">Stellt ein Konfigurationselement dar, das ein Sicherungsendpunktelement definiert.</span><span class="sxs-lookup"><span data-stu-id="558df-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="558df-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="558df-104">\<system.serviceModel></span></span>  
<span data-ttu-id="558df-105">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="558df-105">\<routing></span></span>  
<span data-ttu-id="558df-106">\<BackupLists ></span><span class="sxs-lookup"><span data-stu-id="558df-106">\<backupLists></span></span>  
<span data-ttu-id="558df-107">\<BackupList ></span><span class="sxs-lookup"><span data-stu-id="558df-107">\<backupList></span></span>  
<span data-ttu-id="558df-108">\<add></span><span class="sxs-lookup"><span data-stu-id="558df-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="558df-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="558df-109">Syntax</span></span>  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="558df-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="558df-110">Attributes and Elements</span></span>  
 <span data-ttu-id="558df-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="558df-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="558df-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="558df-112">Attributes</span></span>  
  
|<span data-ttu-id="558df-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="558df-113">Attribute</span></span>|<span data-ttu-id="558df-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="558df-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="558df-115">Name</span><span class="sxs-lookup"><span data-stu-id="558df-115">name</span></span>|<span data-ttu-id="558df-116">Eine Zeichenfolge, die den Namen des Sicherungsendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="558df-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="558df-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="558df-117">Child Elements</span></span>  
 <span data-ttu-id="558df-118">Keine</span><span class="sxs-lookup"><span data-stu-id="558df-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="558df-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="558df-119">Parent Elements</span></span>  
  
|<span data-ttu-id="558df-120">Element</span><span class="sxs-lookup"><span data-stu-id="558df-120">Element</span></span>|<span data-ttu-id="558df-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="558df-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="558df-122">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="558df-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="558df-123">Enthält eine Liste der Endpunkte, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="558df-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="558df-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="558df-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
