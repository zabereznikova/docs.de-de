---
title: '&lt;add&gt; von &lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 7e7361b24c0444b5f3d51a6f5bf079d5eb2dee18
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745551"
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="3a803-102">&lt;add&gt; von &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="3a803-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="3a803-103">Stellt ein Konfigurationselement dar, das ein Sicherungsendpunktelement definiert.</span><span class="sxs-lookup"><span data-stu-id="3a803-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="3a803-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3a803-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3a803-105">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="3a803-105">\<routing></span></span>  
<span data-ttu-id="3a803-106">\<BackupLists ></span><span class="sxs-lookup"><span data-stu-id="3a803-106">\<backupLists></span></span>  
<span data-ttu-id="3a803-107">\<BackupList ></span><span class="sxs-lookup"><span data-stu-id="3a803-107">\<backupList></span></span>  
<span data-ttu-id="3a803-108">\<add></span><span class="sxs-lookup"><span data-stu-id="3a803-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a803-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a803-109">Syntax</span></span>  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a803-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3a803-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3a803-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a803-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a803-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3a803-112">Attributes</span></span>  
  
|<span data-ttu-id="3a803-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="3a803-113">Attribute</span></span>|<span data-ttu-id="3a803-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a803-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a803-115">Name</span><span class="sxs-lookup"><span data-stu-id="3a803-115">name</span></span>|<span data-ttu-id="3a803-116">Eine Zeichenfolge, die den Namen des Sicherungsendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="3a803-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a803-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a803-117">Child Elements</span></span>  
 <span data-ttu-id="3a803-118">Keine</span><span class="sxs-lookup"><span data-stu-id="3a803-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a803-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a803-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3a803-120">Element</span><span class="sxs-lookup"><span data-stu-id="3a803-120">Element</span></span>|<span data-ttu-id="3a803-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a803-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a803-122">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="3a803-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="3a803-123">Enthält eine Liste der Endpunkte, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="3a803-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a803-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a803-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
