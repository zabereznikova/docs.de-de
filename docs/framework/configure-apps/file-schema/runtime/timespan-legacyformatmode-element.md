---
title: <TimeSpan_LegacyFormatMode>-Element
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64bf667c5c9bc20db14f08f18fa6f4f84fa12a24
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252248"
---
# <a name="timespan_legacyformatmode-element"></a><span data-ttu-id="9b775-102">\<TimeSpan_LegacyFormatMode >-Element</span><span class="sxs-lookup"><span data-stu-id="9b775-102">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="9b775-103">Bestimmt, ob die Laufzeit Legacy Verhalten bei Formatierungs Vorgängen mit <xref:System.TimeSpan?displayProperty=nameWithType> Werten beibehält.</span><span class="sxs-lookup"><span data-stu-id="9b775-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

<span data-ttu-id="9b775-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b775-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b775-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b775-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="9b775-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<TimeSpan_LegacyFormatMode >**</span><span class="sxs-lookup"><span data-stu-id="9b775-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<TimeSpan_LegacyFormatMode>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="9b775-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b775-107">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9b775-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9b775-108">Attributes and Elements</span></span>

<span data-ttu-id="9b775-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9b775-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9b775-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="9b775-110">Attributes</span></span>

|<span data-ttu-id="9b775-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="9b775-111">Attribute</span></span>|<span data-ttu-id="9b775-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b775-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="9b775-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="9b775-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9b775-114">Gibt an, ob die Laufzeit Legacy Formatierungs <xref:System.TimeSpan?displayProperty=nameWithType> Verhalten mit-Werten verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b775-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="9b775-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="9b775-115">enabled Attribute</span></span>

|<span data-ttu-id="9b775-116">Wert</span><span class="sxs-lookup"><span data-stu-id="9b775-116">Value</span></span>|<span data-ttu-id="9b775-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b775-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="9b775-118">Die Laufzeit stellt das Legacy Formatierungs Verhalten nicht wieder her.</span><span class="sxs-lookup"><span data-stu-id="9b775-118">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="9b775-119">Die Laufzeit stellt das Legacy Formatierungs Verhalten wieder her.</span><span class="sxs-lookup"><span data-stu-id="9b775-119">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9b775-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b775-120">Child Elements</span></span>

<span data-ttu-id="9b775-121">Keine</span><span class="sxs-lookup"><span data-stu-id="9b775-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9b775-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b775-122">Parent Elements</span></span>

|<span data-ttu-id="9b775-123">Element</span><span class="sxs-lookup"><span data-stu-id="9b775-123">Element</span></span>|<span data-ttu-id="9b775-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b775-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="9b775-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="9b775-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="9b775-126">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="9b775-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9b775-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b775-127">Remarks</span></span>

<span data-ttu-id="9b775-128">Beginnend mit dem .NET Framework 4 implementiert die <xref:System.TimeSpan?displayProperty=nameWithType> -Struktur die <xref:System.IFormattable> -Schnittstelle und unterstützt Formatierungs Vorgänge mit standardmäßigen und benutzerdefinierten Format Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="9b775-128">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="9b775-129">Wenn eine Methode für die Methode einen nicht unterstützten Format Bezeichner oder eine Format Zeichenfolge <xref:System.FormatException>erkennt, wird eine ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9b775-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="9b775-130">In früheren Versionen der .NET Framework wurde die <xref:System.TimeSpan> -Struktur nicht implementiert <xref:System.IFormattable> , und es wurden keine Format Zeichenfolgen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9b775-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="9b775-131">Viele Entwickler haben jedoch fälschlicherweise angenommen, <xref:System.TimeSpan> dass eine Reihe von Format Zeichenfolgen unterstützt und Sie in zusammen [gesetzten Formatierungs Vorgängen](../../../../standard/base-types/composite-formatting.md) <xref:System.String.Format%2A?displayProperty=nameWithType>mit Methoden wie verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b775-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9b775-132">Wenn ein Typ eine Format Zeichenfolge implementiert <xref:System.IFormattable> und unterstützt, lösen Aufrufe von Formatierungs Methoden mit nicht unterstützten Format Zeichenfolgen normalerweise einen <xref:System.FormatException>aus.</span><span class="sxs-lookup"><span data-stu-id="9b775-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="9b775-133">Da <xref:System.TimeSpan> jedoch nicht implementiert <xref:System.IFormattable>hat, hat die Laufzeit die Format Zeichenfolge ignoriert und stattdessen <xref:System.TimeSpan.ToString?displayProperty=nameWithType> die-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9b775-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9b775-134">Dies bedeutet, dass die Format Zeichenfolgen zwar keine Auswirkung auf den Formatierungs Vorgang haben, das vorhanden sein aller <xref:System.FormatException>dings nicht zu einer führte.</span><span class="sxs-lookup"><span data-stu-id="9b775-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="9b775-135">In Fällen, in denen Legacy Code eine kombinierte Formatierungs Methode und eine ungültige Format Zeichenfolge übergibt und dieser Code nicht erneut kompiliert werden kann `<TimeSpan_LegacyFormatMode>` , können Sie das Legacy <xref:System.TimeSpan> Verhalten mit dem-Element wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="9b775-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="9b775-136">Wenn Sie `enabled` das-Attribut dieses Elements auf <xref:System.TimeSpan.ToString?displayProperty=nameWithType> `true`festlegen, führt die kombinierte Formatierungs Methode dazu, dass anstelle <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>von aufgerufen wird, <xref:System.FormatException> und wird nicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9b775-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="9b775-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b775-137">Example</span></span>

<span data-ttu-id="9b775-138">Im folgenden Beispiel wird ein <xref:System.TimeSpan> -Objekt instanziiert und versucht, es mit der <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> -Methode zu formatieren, indem eine nicht unterstützte Standardformat Zeichenfolge verwendet wird</span><span class="sxs-lookup"><span data-stu-id="9b775-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="9b775-139">Wenn Sie das Beispiel auf dem .NET Framework 3,5 oder einer früheren Version ausführen, wird die folgende Ausgabe angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9b775-139">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```
12:30:45
```

<span data-ttu-id="9b775-140">Dies unterscheidet sich deutlich von der Ausgabe, wenn Sie das Beispiel auf dem .NET Framework 4 oder einer höheren Version ausführen:</span><span class="sxs-lookup"><span data-stu-id="9b775-140">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```
Invalid Format
```

<span data-ttu-id="9b775-141">Wenn Sie jedoch die folgende Konfigurationsdatei zum Verzeichnis des Beispiels hinzufügen und dann das Beispiel für die Version .NET Framework 4 oder höher ausführen, ist die Ausgabe identisch mit der Ausgabe, die im Beispiel erstellt wird, wenn Sie auf .NET Framework 3,5 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9b775-141">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="9b775-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b775-142">See also</span></span>

- [<span data-ttu-id="9b775-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="9b775-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9b775-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="9b775-144">Configuration File Schema</span></span>](../index.md)
