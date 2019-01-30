---
title: <gcAllowVeryLargeObjects>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6af994284a56c573d70f3688ccec16459b8eed59
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273373"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="7da1f-102">\<gcAllowVeryLargeObjects> Element</span><span class="sxs-lookup"><span data-stu-id="7da1f-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="7da1f-103">Ermöglicht auf 64-Bit-Plattformen Arrays mit einer Gesamtgröße von mehr als 2 Gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="7da1f-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
 <span data-ttu-id="7da1f-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="7da1f-104">\<configuration> Element</span></span>  
<span data-ttu-id="7da1f-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="7da1f-105">\<runtime> Element</span></span>  
<span data-ttu-id="7da1f-106">\<gcAllowVeryLargeObjects> Element</span><span class="sxs-lookup"><span data-stu-id="7da1f-106">\<gcAllowVeryLargeObjects> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7da1f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7da1f-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7da1f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7da1f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7da1f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7da1f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7da1f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="7da1f-110">Attributes</span></span>  
  
|<span data-ttu-id="7da1f-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="7da1f-111">Attribute</span></span>|<span data-ttu-id="7da1f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7da1f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="7da1f-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="7da1f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="7da1f-114">Gibt an, ob Arrays mit einer Gesamtgröße von mehr als 2 GB auf 64-Bit-Plattformen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="7da1f-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7da1f-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="7da1f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="7da1f-116">Wert</span><span class="sxs-lookup"><span data-stu-id="7da1f-116">Value</span></span>|<span data-ttu-id="7da1f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7da1f-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="7da1f-118">Arrays mit einer Gesamtgröße von mehr als 2 GB sind nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7da1f-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="7da1f-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="7da1f-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="7da1f-120">Arrays mit einer Gesamtgröße von mehr als 2 GB werden auf 64-Bit-Plattformen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7da1f-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7da1f-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7da1f-121">Child Elements</span></span>  
 <span data-ttu-id="7da1f-122">Keine</span><span class="sxs-lookup"><span data-stu-id="7da1f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7da1f-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7da1f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7da1f-124">Element</span><span class="sxs-lookup"><span data-stu-id="7da1f-124">Element</span></span>|<span data-ttu-id="7da1f-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7da1f-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7da1f-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7da1f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7da1f-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="7da1f-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7da1f-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7da1f-128">Remarks</span></span>  
 <span data-ttu-id="7da1f-129">Dieses Element in der Anwendungskonfigurationsdatei ermöglicht Arrays, die größer als 2 GB sind, es werden jedoch keine anderen Beschränkungen der Objekt- oder Arraygröße geändert:</span><span class="sxs-lookup"><span data-stu-id="7da1f-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
-   <span data-ttu-id="7da1f-130">Die maximale Anzahl der Elemente in einem Array ist <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7da1f-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="7da1f-131">Der maximale Index in jeder einzelnen Dimension ist 2.147.483.591 (0x7FFFFFC7) für Bytearrays und Arrays von Einzelbytestrukturen sowie 2.146.435.071 (0X7FEFFFFF) für andere Typen.</span><span class="sxs-lookup"><span data-stu-id="7da1f-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
-   <span data-ttu-id="7da1f-132">Die maximale Größe für Zeichenfolgen und andere Nichtarrayobjekte ist unverändert.</span><span class="sxs-lookup"><span data-stu-id="7da1f-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7da1f-133">Bevor Sie diese Funktion aktivieren, stellen Sie sicher, dass Ihre Anwendung keinen unsicheren Code enthält, der davon ausgeht, dass alle Arrays weniger als 2 GB groß sind.</span><span class="sxs-lookup"><span data-stu-id="7da1f-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="7da1f-134">Beispielsweise könnte unsicherer Code, der Arrays als Puffer verwendet, für Pufferüberläufe anfällig sein, wenn dieser ausgehend davon geschrieben wurde, dass Arrays 2 GB nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="7da1f-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7da1f-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7da1f-135">Example</span></span>  
 <span data-ttu-id="7da1f-136">Das folgende Beispiel zeigt, wie diese Funktion für eine Anwendung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="7da1f-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7da1f-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7da1f-137">See also</span></span>
- [<span data-ttu-id="7da1f-138">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="7da1f-138">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="7da1f-139">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="7da1f-139">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
