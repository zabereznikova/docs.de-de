---
title: '&lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41fc4bc7a6a10a6f99752112f951b66f80d493fe
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltnetfx45cultureawarecomparergethashcodelongstringsgt-element"></a><span data-ttu-id="9a9dd-102">&lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt; Element</span><span class="sxs-lookup"><span data-stu-id="9a9dd-102">&lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt; Element</span></span>
<span data-ttu-id="9a9dd-103">Gibt an, ob die Laufzeit eine feste Menge an Arbeitsspeicher zum Berechnen von Hashcodes für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>-Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a9dd-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="9a9dd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9a9dd-104">\<configuration></span></span>  
<span data-ttu-id="9a9dd-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="9a9dd-105">\<runtime></span></span>  
<span data-ttu-id="9a9dd-106">< NetFx45_CultureAwareComparerGetHashCode_LongStrings ></span><span class="sxs-lookup"><span data-stu-id="9a9dd-106"><NetFx45_CultureAwareComparerGetHashCode_LongStrings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a9dd-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a9dd-107">Syntax</span></span>  
  
```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a9dd-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9a9dd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9a9dd-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9a9dd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a9dd-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="9a9dd-110">Attributes</span></span>  
  
|<span data-ttu-id="9a9dd-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="9a9dd-111">Attribute</span></span>|<span data-ttu-id="9a9dd-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a9dd-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9a9dd-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="9a9dd-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9a9dd-114">Gibt an, ob die Common Language Runtime eine feste Menge an Arbeitsspeicher beim Berechnen von Hashcodes belegt.</span><span class="sxs-lookup"><span data-stu-id="9a9dd-114">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9a9dd-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="9a9dd-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9a9dd-116">Wert</span><span class="sxs-lookup"><span data-stu-id="9a9dd-116">Value</span></span>|<span data-ttu-id="9a9dd-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a9dd-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9a9dd-118">0</span><span class="sxs-lookup"><span data-stu-id="9a9dd-118">0</span></span>|<span data-ttu-id="9a9dd-119">Die Common Language Runtime belegt eine variable Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>-Methode, um Hashcodes zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="9a9dd-119">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="9a9dd-120">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="9a9dd-120">This is the default.</span></span>|  
|<span data-ttu-id="9a9dd-121">1</span><span class="sxs-lookup"><span data-stu-id="9a9dd-121">1</span></span>|<span data-ttu-id="9a9dd-122">Die Common Language Runtime belegt eine feste Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>-Methode, um Hashcodes zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="9a9dd-122">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a9dd-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a9dd-123">Child Elements</span></span>  
 <span data-ttu-id="9a9dd-124">Keine</span><span class="sxs-lookup"><span data-stu-id="9a9dd-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a9dd-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a9dd-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9a9dd-126">Element</span><span class="sxs-lookup"><span data-stu-id="9a9dd-126">Element</span></span>|<span data-ttu-id="9a9dd-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a9dd-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9a9dd-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="9a9dd-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9a9dd-129">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="9a9dd-129">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a9dd-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a9dd-130">Remarks</span></span>  
 <span data-ttu-id="9a9dd-131">Standardmäßig belegt die Common Language Runtime eine variable Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>-Methode, und <xref:System.ArgumentException> kann ausgelöst werden, wenn die Methode versucht, den Hashcode sehr großer Zeichenfolgen zu berechnen (über mehrere Millionen Zeichen lang).</span><span class="sxs-lookup"><span data-stu-id="9a9dd-131">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="9a9dd-132">Indem Sie dieses Element einer Anwendungskonfigurationsdatei hinzufügen und das `enabled`-Attribut auf "1 " festlegen, können Sie angeben, dass die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>-Methode einen alternativen Algorithmus verwendet, der eine feste Menge an Arbeitsspeicher für die Berechnung von Hashcodes belegt.</span><span class="sxs-lookup"><span data-stu-id="9a9dd-132">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9a9dd-133">Das `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` -Element wird nicht in [!INCLUDE[win8](../../../../../includes/win8-md.md)] und höheren Versionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a9dd-133">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in [!INCLUDE[win8](../../../../../includes/win8-md.md)] and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a9dd-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a9dd-134">See Also</span></span>  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="9a9dd-135">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="9a9dd-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="9a9dd-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="9a9dd-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
