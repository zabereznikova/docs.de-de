---
title: gcAllowVeryLargeObjects-Element
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 1e54b0780ffb5bbe81ab1be2b376ff7a038ee05c
ms.sourcegitcommit: 0273f8845eb1ea8de64086bef2271b4f22182c91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "98058128"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="cabd0-102">\<gcAllowVeryLargeObjects>-Element</span><span class="sxs-lookup"><span data-stu-id="cabd0-102">\<gcAllowVeryLargeObjects> element</span></span>

<span data-ttu-id="cabd0-103">Ermöglicht auf 64-Bit-Plattformen Arrays mit einer Gesamtgröße von mehr als 2 Gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="cabd0-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a><span data-ttu-id="cabd0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cabd0-104">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects enabled="true|false" />  
```  
  
## <a name="attributes"></a><span data-ttu-id="cabd0-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="cabd0-105">Attributes</span></span>
  
|<span data-ttu-id="cabd0-106">attribute</span><span class="sxs-lookup"><span data-stu-id="cabd0-106">Attribute</span></span>|<span data-ttu-id="cabd0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cabd0-107">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="cabd0-108">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="cabd0-108">Required attribute.</span></span><br /><br /> <span data-ttu-id="cabd0-109">Gibt an, ob Arrays mit einer Gesamtgröße von mehr als 2 GB auf 64-Bit-Plattformen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="cabd0-109">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="cabd0-110">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="cabd0-110">enabled attribute</span></span>  
  
|<span data-ttu-id="cabd0-111">Wert</span><span class="sxs-lookup"><span data-stu-id="cabd0-111">Value</span></span>|<span data-ttu-id="cabd0-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cabd0-112">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="cabd0-113">Arrays mit einer Gesamtgröße von mehr als 2 GB sind nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cabd0-113">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="cabd0-114">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="cabd0-114">This is the default.</span></span>|  
|`true`|<span data-ttu-id="cabd0-115">Arrays mit einer Gesamtgröße von mehr als 2 GB werden auf 64-Bit-Plattformen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cabd0-115">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="cabd0-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cabd0-116">Child elements</span></span>  

<span data-ttu-id="cabd0-117">Keine</span><span class="sxs-lookup"><span data-stu-id="cabd0-117">None.</span></span>  
  
## <a name="parent-elements"></a><span data-ttu-id="cabd0-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cabd0-118">Parent elements</span></span>
  
|<span data-ttu-id="cabd0-119">Element</span><span class="sxs-lookup"><span data-stu-id="cabd0-119">Element</span></span>|<span data-ttu-id="cabd0-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cabd0-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cabd0-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="cabd0-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cabd0-122">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="cabd0-122">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cabd0-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cabd0-123">Remarks</span></span>  

 <span data-ttu-id="cabd0-124">Dieses Element in der Anwendungskonfigurationsdatei ermöglicht Arrays, die größer als 2 GB sind, es werden jedoch keine anderen Beschränkungen der Objekt- oder Arraygröße geändert:</span><span class="sxs-lookup"><span data-stu-id="cabd0-124">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="cabd0-125">Die maximale Anzahl der Elemente in einem Array ist <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cabd0-125">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="cabd0-126">Die maximale Größe in einer einzelnen Dimension beträgt 2.147.483.591 (0x7fffffc7) für Byte Arrays und Arrays von Einzel Byte Strukturen und 2.146.435.071 (0x7fefffff) für Arrays, die andere Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="cabd0-126">The maximum size in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for arrays containing other types.</span></span>  
  
- <span data-ttu-id="cabd0-127">Die maximale Größe für Zeichenfolgen und andere Nichtarrayobjekte ist unverändert.</span><span class="sxs-lookup"><span data-stu-id="cabd0-127">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="cabd0-128">Bevor Sie diese Funktion aktivieren, stellen Sie sicher, dass Ihre Anwendung keinen unsicheren Code enthält, der davon ausgeht, dass alle Arrays weniger als 2 GB groß sind.</span><span class="sxs-lookup"><span data-stu-id="cabd0-128">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="cabd0-129">Beispielsweise ist unsicherer Code, der Arrays als Puffer verwendet, möglicherweise anfällig für Pufferüberläufe, wenn er unter der Annahme geschrieben wird, dass Arrays 2 GB nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="cabd0-129">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it's written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cabd0-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cabd0-130">Example</span></span>  

 <span data-ttu-id="cabd0-131">Das folgende Beispiel zeigt, wie diese Funktion für eine Anwendung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="cabd0-131">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="cabd0-132">Unterstützt in </span><span class="sxs-lookup"><span data-stu-id="cabd0-132">Supported in</span></span>

<span data-ttu-id="cabd0-133">.NET Framework 4,5 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="cabd0-133">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="cabd0-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cabd0-134">See also</span></span>

- [<span data-ttu-id="cabd0-135">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="cabd0-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cabd0-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="cabd0-136">Configuration File Schema</span></span>](../index.md)
