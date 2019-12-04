---
title: <NetFx45_CultureAwareComparerGetHashCode_LongStrings>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
ms.openlocfilehash: 413eb6c6e61b509135601c65cf045eabd849e8b3
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802114"
---
# <a name="netfx45_cultureawarecomparergethashcode_longstrings-element"></a><span data-ttu-id="fa3b9-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings >-Element</span><span class="sxs-lookup"><span data-stu-id="fa3b9-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>

<span data-ttu-id="fa3b9-103">Gibt an, ob die Laufzeit eine feste Menge an Arbeitsspeicher zum Berechnen von Hashcodes für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="fa3b9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa3b9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fa3b9-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa3b9-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="fa3b9-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<** NetFx45_CultureAwareComparerGetHashCode_LongStrings ></span><span class="sxs-lookup"><span data-stu-id="fa3b9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="fa3b9-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa3b9-107">Syntax</span></span>

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fa3b9-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fa3b9-108">Attributes and Elements</span></span>

<span data-ttu-id="fa3b9-109">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fa3b9-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="fa3b9-110">Attributes</span></span>

|<span data-ttu-id="fa3b9-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="fa3b9-111">Attribute</span></span>|<span data-ttu-id="fa3b9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa3b9-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="fa3b9-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="fa3b9-114">Gibt an, ob die Common Language Runtime eine feste Menge an Arbeitsspeicher beim Berechnen von Hashcodes belegt.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-114">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="fa3b9-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="fa3b9-115">enabled Attribute</span></span>

|<span data-ttu-id="fa3b9-116">{2&gt;Wert&lt;2}</span><span class="sxs-lookup"><span data-stu-id="fa3b9-116">Value</span></span>|<span data-ttu-id="fa3b9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa3b9-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="fa3b9-118">0</span><span class="sxs-lookup"><span data-stu-id="fa3b9-118">0</span></span>|<span data-ttu-id="fa3b9-119">Die Common Language Runtime belegt eine variable Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode, um Hashcodes zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-119">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="fa3b9-120">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-120">This is the default.</span></span>|
|<span data-ttu-id="fa3b9-121">1</span><span class="sxs-lookup"><span data-stu-id="fa3b9-121">1</span></span>|<span data-ttu-id="fa3b9-122">Die Common Language Runtime belegt eine feste Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode, um Hashcodes zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-122">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="fa3b9-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa3b9-123">Child Elements</span></span>

<span data-ttu-id="fa3b9-124">Keine</span><span class="sxs-lookup"><span data-stu-id="fa3b9-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fa3b9-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa3b9-125">Parent Elements</span></span>

|<span data-ttu-id="fa3b9-126">Element</span><span class="sxs-lookup"><span data-stu-id="fa3b9-126">Element</span></span>|<span data-ttu-id="fa3b9-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa3b9-127">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="fa3b9-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="fa3b9-129">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-129">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fa3b9-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa3b9-130">Remarks</span></span>

<span data-ttu-id="fa3b9-131">Standardmäßig belegt die Common Language Runtime eine variable Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode, und <xref:System.ArgumentException> kann ausgelöst werden, wenn die Methode versucht, den Hashcode sehr großer Zeichenfolgen zu berechnen (über mehrere Millionen Zeichen lang).</span><span class="sxs-lookup"><span data-stu-id="fa3b9-131">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="fa3b9-132">Indem Sie dieses Element einer Anwendungskonfigurationsdatei hinzufügen und das `enabled` -Attribut auf "1 " festlegen, können Sie angeben, dass die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode einen alternativen Algorithmus verwendet, der eine feste Menge an Arbeitsspeicher für die Berechnung von Hashcodes belegt.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-132">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa3b9-133">Das `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>`-Element wird in Windows 8 und höheren Versionen nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa3b9-133">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in Windows 8 and later versions.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa3b9-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa3b9-134">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fa3b9-135">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="fa3b9-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fa3b9-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="fa3b9-136">Configuration File Schema</span></span>](../index.md)
