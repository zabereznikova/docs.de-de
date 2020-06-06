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
ms.openlocfilehash: 9d9eedf52f5d711412e4549e39e6ea23abb68ff3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968907"
---
# <a name="timespan_legacyformatmode-element"></a><span data-ttu-id="393dc-102">\<TimeSpan_LegacyFormatMode>-Element</span><span class="sxs-lookup"><span data-stu-id="393dc-102">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="393dc-103">Bestimmt, ob die Laufzeit Legacy Verhalten bei Formatierungs Vorgängen mit Werten beibehält <xref:System.TimeSpan?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="393dc-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<TimeSpan_LegacyFormatMode>**  

## <a name="syntax"></a><span data-ttu-id="393dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="393dc-104">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="393dc-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="393dc-105">Attributes and Elements</span></span>

<span data-ttu-id="393dc-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="393dc-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="393dc-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="393dc-107">Attributes</span></span>

|<span data-ttu-id="393dc-108">attribute</span><span class="sxs-lookup"><span data-stu-id="393dc-108">Attribute</span></span>|<span data-ttu-id="393dc-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="393dc-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="393dc-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="393dc-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="393dc-111">Gibt an, ob die Laufzeit Legacy Formatierungs Verhalten mit- <xref:System.TimeSpan?displayProperty=nameWithType> Werten verwendet.</span><span class="sxs-lookup"><span data-stu-id="393dc-111">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="393dc-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="393dc-112">enabled Attribute</span></span>

|<span data-ttu-id="393dc-113">Wert</span><span class="sxs-lookup"><span data-stu-id="393dc-113">Value</span></span>|<span data-ttu-id="393dc-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="393dc-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="393dc-115">Die Laufzeit stellt das Legacy Formatierungs Verhalten nicht wieder her.</span><span class="sxs-lookup"><span data-stu-id="393dc-115">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="393dc-116">Die Laufzeit stellt das Legacy Formatierungs Verhalten wieder her.</span><span class="sxs-lookup"><span data-stu-id="393dc-116">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="393dc-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="393dc-117">Child Elements</span></span>

<span data-ttu-id="393dc-118">Keine</span><span class="sxs-lookup"><span data-stu-id="393dc-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="393dc-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="393dc-119">Parent Elements</span></span>

|<span data-ttu-id="393dc-120">Element</span><span class="sxs-lookup"><span data-stu-id="393dc-120">Element</span></span>|<span data-ttu-id="393dc-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="393dc-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="393dc-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="393dc-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="393dc-123">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="393dc-123">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="393dc-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="393dc-124">Remarks</span></span>

<span data-ttu-id="393dc-125">Beginnend mit dem .NET Framework 4 implementiert die <xref:System.TimeSpan?displayProperty=nameWithType> -Struktur die <xref:System.IFormattable> -Schnittstelle und unterstützt Formatierungs Vorgänge mit standardmäßigen und benutzerdefinierten Format Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="393dc-125">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="393dc-126">Wenn eine Methode für die Methode einen nicht unterstützten Format Bezeichner oder eine Format Zeichenfolge erkennt, wird eine ausgelöst <xref:System.FormatException> .</span><span class="sxs-lookup"><span data-stu-id="393dc-126">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="393dc-127">In früheren Versionen der .NET Framework wurde die <xref:System.TimeSpan> -Struktur nicht implementiert, <xref:System.IFormattable> und es wurden keine Format Zeichenfolgen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="393dc-127">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="393dc-128">Viele Entwickler haben jedoch fälschlicherweise angenommen, dass <xref:System.TimeSpan> eine Reihe von Format Zeichenfolgen unterstützt und Sie in zusammen [gesetzten Formatierungs Vorgängen](../../../../standard/base-types/composite-formatting.md) mit Methoden wie verwendet <xref:System.String.Format%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="393dc-128">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="393dc-129">Wenn ein Typ eine Format Zeichenfolge implementiert <xref:System.IFormattable> und unterstützt, lösen Aufrufe von Formatierungs Methoden mit nicht unterstützten Format Zeichenfolgen normalerweise einen aus <xref:System.FormatException> .</span><span class="sxs-lookup"><span data-stu-id="393dc-129">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="393dc-130">Da jedoch <xref:System.TimeSpan> nicht implementiert hat <xref:System.IFormattable> , hat die Laufzeit die Format Zeichenfolge ignoriert und stattdessen die- <xref:System.TimeSpan.ToString?displayProperty=nameWithType> Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="393dc-130">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="393dc-131">Dies bedeutet, dass die Format Zeichenfolgen zwar keine Auswirkung auf den Formatierungs Vorgang haben, das vorhanden sein allerdings nicht zu einer führte <xref:System.FormatException> .</span><span class="sxs-lookup"><span data-stu-id="393dc-131">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="393dc-132">In Fällen, in denen Legacy Code eine kombinierte Formatierungs Methode und eine ungültige Format Zeichenfolge übergibt und dieser Code nicht erneut kompiliert werden kann, können Sie das Legacy Verhalten mit dem- `<TimeSpan_LegacyFormatMode>` Element wiederherstellen <xref:System.TimeSpan> .</span><span class="sxs-lookup"><span data-stu-id="393dc-132">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="393dc-133">Wenn Sie das- `enabled` Attribut dieses Elements auf festlegen `true` , führt die kombinierte Formatierungs Methode dazu, dass anstelle von aufgerufen wird <xref:System.TimeSpan.ToString?displayProperty=nameWithType> <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> , und <xref:System.FormatException> wird nicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="393dc-133">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="393dc-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="393dc-134">Example</span></span>

<span data-ttu-id="393dc-135">Im folgenden Beispiel wird ein-Objekt instanziiert <xref:System.TimeSpan> und versucht, es mit der-Methode zu formatieren, <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> indem eine nicht unterstützte Standardformat Zeichenfolge verwendet wird</span><span class="sxs-lookup"><span data-stu-id="393dc-135">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="393dc-136">Wenn Sie das Beispiel auf dem .NET Framework 3,5 oder einer früheren Version ausführen, wird die folgende Ausgabe angezeigt:</span><span class="sxs-lookup"><span data-stu-id="393dc-136">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```console
12:30:45
```

<span data-ttu-id="393dc-137">Dies unterscheidet sich deutlich von der Ausgabe, wenn Sie das Beispiel auf dem .NET Framework 4 oder einer höheren Version ausführen:</span><span class="sxs-lookup"><span data-stu-id="393dc-137">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```console
Invalid Format
```

<span data-ttu-id="393dc-138">Wenn Sie jedoch die folgende Konfigurationsdatei zum Verzeichnis des Beispiels hinzufügen und dann das Beispiel für die Version .NET Framework 4 oder höher ausführen, ist die Ausgabe identisch mit der Ausgabe, die im Beispiel erstellt wird, wenn Sie auf .NET Framework 3,5 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="393dc-138">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="393dc-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="393dc-139">See also</span></span>

- [<span data-ttu-id="393dc-140">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="393dc-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="393dc-141">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="393dc-141">Configuration File Schema</span></span>](../index.md)
