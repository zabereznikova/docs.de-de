---
title: <gcAllowVeryLargeObjects>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: b6230833808ec45d702502e36f929db4e03173e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116790"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="e2579-102">\<gcallowverylargeobjects > Element</span><span class="sxs-lookup"><span data-stu-id="e2579-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="e2579-103">Ermöglicht auf 64-Bit-Plattformen Arrays mit einer Gesamtgröße von mehr als 2 Gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="e2579-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
<span data-ttu-id="e2579-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e2579-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e2579-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="e2579-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="e2579-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<gcallowverylargeobjects >**</span><span class="sxs-lookup"><span data-stu-id="e2579-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2579-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2579-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2579-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e2579-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e2579-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e2579-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2579-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e2579-110">Attributes</span></span>  
  
|<span data-ttu-id="e2579-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="e2579-111">Attribute</span></span>|<span data-ttu-id="e2579-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2579-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e2579-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="e2579-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e2579-114">Gibt an, ob Arrays mit einer Gesamtgröße von mehr als 2 GB auf 64-Bit-Plattformen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e2579-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e2579-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="e2579-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="e2579-116">Wert</span><span class="sxs-lookup"><span data-stu-id="e2579-116">Value</span></span>|<span data-ttu-id="e2579-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2579-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="e2579-118">Arrays mit einer Gesamtgröße von mehr als 2 GB sind nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e2579-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="e2579-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="e2579-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="e2579-120">Arrays mit einer Gesamtgröße von mehr als 2 GB werden auf 64-Bit-Plattformen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e2579-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2579-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e2579-121">Child Elements</span></span>  
 <span data-ttu-id="e2579-122">Keine</span><span class="sxs-lookup"><span data-stu-id="e2579-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2579-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e2579-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e2579-124">Element</span><span class="sxs-lookup"><span data-stu-id="e2579-124">Element</span></span>|<span data-ttu-id="e2579-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2579-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e2579-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e2579-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e2579-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="e2579-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2579-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2579-128">Remarks</span></span>  
 <span data-ttu-id="e2579-129">Dieses Element in der Anwendungskonfigurationsdatei ermöglicht Arrays, die größer als 2 GB sind, es werden jedoch keine anderen Beschränkungen der Objekt- oder Arraygröße geändert:</span><span class="sxs-lookup"><span data-stu-id="e2579-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="e2579-130">Die maximale Anzahl der Elemente in einem Array ist <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e2579-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="e2579-131">Der maximale Index in jeder einzelnen Dimension ist 2.147.483.591 (0x7FFFFFC7) für Bytearrays und Arrays von Einzelbytestrukturen sowie 2.146.435.071 (0X7FEFFFFF) für andere Typen.</span><span class="sxs-lookup"><span data-stu-id="e2579-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="e2579-132">Die maximale Größe für Zeichenfolgen und andere Nichtarrayobjekte ist unverändert.</span><span class="sxs-lookup"><span data-stu-id="e2579-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="e2579-133">Bevor Sie diese Funktion aktivieren, stellen Sie sicher, dass Ihre Anwendung keinen unsicheren Code enthält, der davon ausgeht, dass alle Arrays weniger als 2 GB groß sind.</span><span class="sxs-lookup"><span data-stu-id="e2579-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="e2579-134">Beispielsweise könnte unsicherer Code, der Arrays als Puffer verwendet, für Pufferüberläufe anfällig sein, wenn dieser ausgehend davon geschrieben wurde, dass Arrays 2 GB nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="e2579-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2579-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2579-135">Example</span></span>  
 <span data-ttu-id="e2579-136">Das folgende Beispiel zeigt, wie diese Funktion für eine Anwendung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="e2579-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="e2579-137">Unterstützt in</span><span class="sxs-lookup"><span data-stu-id="e2579-137">Supported in</span></span>

<span data-ttu-id="e2579-138">.NET Framework 4,5 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="e2579-138">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="e2579-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2579-139">See also</span></span>

- [<span data-ttu-id="e2579-140">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="e2579-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e2579-141">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="e2579-141">Configuration File Schema</span></span>](../index.md)
