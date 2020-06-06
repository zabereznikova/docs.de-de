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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74802114"
---
# <a name="netfx45_cultureawarecomparergethashcode_longstrings-element"></a><span data-ttu-id="83982-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>-Element</span><span class="sxs-lookup"><span data-stu-id="83982-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>

<span data-ttu-id="83982-103">Gibt an, ob die Laufzeit eine feste Menge an Arbeitsspeicher zum Berechnen von Hashcodes für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="83982-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>**  

## <a name="syntax"></a><span data-ttu-id="83982-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83982-104">Syntax</span></span>

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a><span data-ttu-id="83982-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="83982-105">Attributes and Elements</span></span>

<span data-ttu-id="83982-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="83982-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="83982-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="83982-107">Attributes</span></span>

|<span data-ttu-id="83982-108">attribute</span><span class="sxs-lookup"><span data-stu-id="83982-108">Attribute</span></span>|<span data-ttu-id="83982-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="83982-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="83982-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="83982-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="83982-111">Gibt an, ob die Common Language Runtime eine feste Menge an Arbeitsspeicher beim Berechnen von Hashcodes belegt.</span><span class="sxs-lookup"><span data-stu-id="83982-111">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="83982-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="83982-112">enabled Attribute</span></span>

|<span data-ttu-id="83982-113">Wert</span><span class="sxs-lookup"><span data-stu-id="83982-113">Value</span></span>|<span data-ttu-id="83982-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="83982-114">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="83982-115">0</span><span class="sxs-lookup"><span data-stu-id="83982-115">0</span></span>|<span data-ttu-id="83982-116">Die Common Language Runtime belegt eine variable Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode, um Hashcodes zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="83982-116">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="83982-117">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="83982-117">This is the default.</span></span>|
|<span data-ttu-id="83982-118">1</span><span class="sxs-lookup"><span data-stu-id="83982-118">1</span></span>|<span data-ttu-id="83982-119">Die Common Language Runtime belegt eine feste Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode, um Hashcodes zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="83982-119">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="83982-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="83982-120">Child Elements</span></span>

<span data-ttu-id="83982-121">Keine</span><span class="sxs-lookup"><span data-stu-id="83982-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="83982-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="83982-122">Parent Elements</span></span>

|<span data-ttu-id="83982-123">Element</span><span class="sxs-lookup"><span data-stu-id="83982-123">Element</span></span>|<span data-ttu-id="83982-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83982-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="83982-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="83982-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="83982-126">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="83982-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="83982-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="83982-127">Remarks</span></span>

<span data-ttu-id="83982-128">Standardmäßig belegt die Common Language Runtime eine variable Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode, und <xref:System.ArgumentException> kann ausgelöst werden, wenn die Methode versucht, den Hashcode sehr großer Zeichenfolgen zu berechnen (über mehrere Millionen Zeichen lang).</span><span class="sxs-lookup"><span data-stu-id="83982-128">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="83982-129">Indem Sie dieses Element einer Anwendungskonfigurationsdatei hinzufügen und das `enabled` -Attribut auf "1 " festlegen, können Sie angeben, dass die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode einen alternativen Algorithmus verwendet, der eine feste Menge an Arbeitsspeicher für die Berechnung von Hashcodes belegt.</span><span class="sxs-lookup"><span data-stu-id="83982-129">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83982-130">Das `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` -Element wird in Windows 8 und höheren Versionen nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="83982-130">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in Windows 8 and later versions.</span></span>

## <a name="see-also"></a><span data-ttu-id="83982-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="83982-131">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="83982-132">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="83982-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="83982-133">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="83982-133">Configuration File Schema</span></span>](../index.md)
