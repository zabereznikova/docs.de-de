---
title: <add> von <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 80726cc22cb56013c85c7704c28579b1337666c9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850552"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="75edb-102">\<> von \<backuplist hinzufügen ></span><span class="sxs-lookup"><span data-stu-id="75edb-102">\<add> of \<backupList></span></span>
<span data-ttu-id="75edb-103">Stellt ein Konfigurationselement dar, das ein Sicherungsendpunktelement definiert.</span><span class="sxs-lookup"><span data-stu-id="75edb-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
<span data-ttu-id="75edb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="75edb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="75edb-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="75edb-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="75edb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Routing >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="75edb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="75edb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<backuplists->** ](backuplists.md)</span><span class="sxs-lookup"><span data-stu-id="75edb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)</span></span>\
<span data-ttu-id="75edb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<backuplist->** ](backuplist.md)</span><span class="sxs-lookup"><span data-stu-id="75edb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)</span></span>\
<span data-ttu-id="75edb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="75edb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75edb-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="75edb-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75edb-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="75edb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="75edb-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="75edb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75edb-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="75edb-113">Attributes</span></span>  
  
|<span data-ttu-id="75edb-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="75edb-114">Attribute</span></span>|<span data-ttu-id="75edb-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75edb-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75edb-116">NAME</span><span class="sxs-lookup"><span data-stu-id="75edb-116">name</span></span>|<span data-ttu-id="75edb-117">Eine Zeichenfolge, die den Namen des Sicherungsendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="75edb-117">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75edb-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75edb-118">Child Elements</span></span>  
 <span data-ttu-id="75edb-119">Keine</span><span class="sxs-lookup"><span data-stu-id="75edb-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75edb-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75edb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="75edb-121">Element</span><span class="sxs-lookup"><span data-stu-id="75edb-121">Element</span></span>|<span data-ttu-id="75edb-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75edb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75edb-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="75edb-123">\<routing></span></span>](routing.md)|<span data-ttu-id="75edb-124">Enthält eine Liste von Endpunkten, die der Routing Dienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="75edb-124">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75edb-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75edb-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
