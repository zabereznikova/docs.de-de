---
title: <gcAllowVeryLargeObjects>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 8b2f39a0867228474afdee788474fda11f14ca82
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154126"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="5fb45-102">\<gcAllowVeryLargeObjects>-Element</span><span class="sxs-lookup"><span data-stu-id="5fb45-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="5fb45-103">Ermöglicht auf 64-Bit-Plattformen Arrays mit einer Gesamtgröße von mehr als 2 Gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="5fb45-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a><span data-ttu-id="5fb45-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5fb45-104">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5fb45-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5fb45-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5fb45-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5fb45-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5fb45-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="5fb45-107">Attributes</span></span>  
  
|<span data-ttu-id="5fb45-108">attribute</span><span class="sxs-lookup"><span data-stu-id="5fb45-108">Attribute</span></span>|<span data-ttu-id="5fb45-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5fb45-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="5fb45-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="5fb45-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="5fb45-111">Gibt an, ob Arrays mit einer Gesamtgröße von mehr als 2 GB auf 64-Bit-Plattformen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="5fb45-111">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="5fb45-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="5fb45-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="5fb45-113">Wert</span><span class="sxs-lookup"><span data-stu-id="5fb45-113">Value</span></span>|<span data-ttu-id="5fb45-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5fb45-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="5fb45-115">Arrays mit einer Gesamtgröße von mehr als 2 GB sind nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5fb45-115">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="5fb45-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="5fb45-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="5fb45-117">Arrays mit einer Gesamtgröße von mehr als 2 GB werden auf 64-Bit-Plattformen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5fb45-117">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5fb45-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5fb45-118">Child Elements</span></span>  
 <span data-ttu-id="5fb45-119">Keine</span><span class="sxs-lookup"><span data-stu-id="5fb45-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5fb45-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5fb45-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5fb45-121">Element</span><span class="sxs-lookup"><span data-stu-id="5fb45-121">Element</span></span>|<span data-ttu-id="5fb45-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5fb45-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5fb45-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5fb45-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5fb45-124">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="5fb45-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fb45-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5fb45-125">Remarks</span></span>  
 <span data-ttu-id="5fb45-126">Dieses Element in der Anwendungskonfigurationsdatei ermöglicht Arrays, die größer als 2 GB sind, es werden jedoch keine anderen Beschränkungen der Objekt- oder Arraygröße geändert:</span><span class="sxs-lookup"><span data-stu-id="5fb45-126">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="5fb45-127">Die maximale Anzahl der Elemente in einem Array ist <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5fb45-127">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="5fb45-128">Der maximale Index in jeder einzelnen Dimension ist 2.147.483.591 (0x7FFFFFC7) für Bytearrays und Arrays von Einzelbytestrukturen sowie 2.146.435.071 (0X7FEFFFFF) für andere Typen.</span><span class="sxs-lookup"><span data-stu-id="5fb45-128">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="5fb45-129">Die maximale Größe für Zeichenfolgen und andere Nichtarrayobjekte ist unverändert.</span><span class="sxs-lookup"><span data-stu-id="5fb45-129">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="5fb45-130">Bevor Sie diese Funktion aktivieren, stellen Sie sicher, dass Ihre Anwendung keinen unsicheren Code enthält, der davon ausgeht, dass alle Arrays weniger als 2 GB groß sind.</span><span class="sxs-lookup"><span data-stu-id="5fb45-130">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="5fb45-131">Beispielsweise könnte unsicherer Code, der Arrays als Puffer verwendet, für Pufferüberläufe anfällig sein, wenn dieser ausgehend davon geschrieben wurde, dass Arrays 2 GB nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="5fb45-131">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fb45-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5fb45-132">Example</span></span>  
 <span data-ttu-id="5fb45-133">Das folgende Beispiel zeigt, wie diese Funktion für eine Anwendung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="5fb45-133">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="5fb45-134">Unterstützt in</span><span class="sxs-lookup"><span data-stu-id="5fb45-134">Supported in</span></span>

<span data-ttu-id="5fb45-135">.NET Framework 4,5 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="5fb45-135">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="5fb45-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5fb45-136">See also</span></span>

- [<span data-ttu-id="5fb45-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="5fb45-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5fb45-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="5fb45-138">Configuration File Schema</span></span>](../index.md)
