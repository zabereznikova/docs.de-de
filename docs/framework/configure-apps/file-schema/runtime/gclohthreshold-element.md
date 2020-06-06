---
title: Gclohthreshold-Element
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74451323"
---
# <a name="gclohthreshold-element"></a><span data-ttu-id="d2048-102">Gclohthreshold-Element</span><span class="sxs-lookup"><span data-stu-id="d2048-102">GCLOHThreshold element</span></span>

<span data-ttu-id="d2048-103">Gibt die Schwellenwert Größe in Bytes an, die bewirkt, dass der Garbage Collector Objekte auf dem großen Objekt Heap (Loh) platziert.</span><span class="sxs-lookup"><span data-stu-id="d2048-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold>

## <a name="syntax"></a><span data-ttu-id="d2048-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2048-104">Syntax</span></span>

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a><span data-ttu-id="d2048-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="d2048-105">Attributes</span></span>

|<span data-ttu-id="d2048-106">attribute</span><span class="sxs-lookup"><span data-stu-id="d2048-106">Attribute</span></span>|<span data-ttu-id="d2048-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d2048-107">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="d2048-108">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="d2048-108">Required attribute.</span></span><br /><br /><span data-ttu-id="d2048-109">Gibt den Schwellenwert an, der bewirkt, dass Objekte im großen Objekt Heap angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d2048-109">Specifies the threshold size that causes objects to go on the large object heap.</span></span>|

### <a name="enabled-attribute"></a><span data-ttu-id="d2048-110">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="d2048-110">enabled attribute</span></span>

|<span data-ttu-id="d2048-111">Wert</span><span class="sxs-lookup"><span data-stu-id="d2048-111">Value</span></span>|<span data-ttu-id="d2048-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d2048-112">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="d2048-113">Die Schwellenwert Größe in Byte, die bewirkt, dass Objekte auf dem großen Objekt Heap laufen.</span><span class="sxs-lookup"><span data-stu-id="d2048-113">The threshold size, in bytes, that causes objects to go on the large object heap.</span></span>|

## <a name="child-elements"></a><span data-ttu-id="d2048-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d2048-114">Child elements</span></span>

<span data-ttu-id="d2048-115">Keine</span><span class="sxs-lookup"><span data-stu-id="d2048-115">None.</span></span>

## <a name="parent-elements"></a><span data-ttu-id="d2048-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d2048-116">Parent elements</span></span>

|<span data-ttu-id="d2048-117">Element</span><span class="sxs-lookup"><span data-stu-id="d2048-117">Element</span></span>|<span data-ttu-id="d2048-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2048-118">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="d2048-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d2048-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="d2048-120">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d2048-120">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d2048-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d2048-121">Remarks</span></span>

<span data-ttu-id="d2048-122">Diese Einstellung wurde in .NET Framework 4,8 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d2048-122">This setting was introduced in .NET Framework 4.8.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2048-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2048-123">See also</span></span>

- [<span data-ttu-id="d2048-124">Schema für Lauf Zeit Einstellungen</span><span class="sxs-lookup"><span data-stu-id="d2048-124">Run-time settings schema</span></span>](index.md)
- [<span data-ttu-id="d2048-125">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="d2048-125">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="d2048-126">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="d2048-126">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="d2048-127">Optionen für die .net Core-Laufzeitkonfiguration für GC</span><span class="sxs-lookup"><span data-stu-id="d2048-127">NET Core run-time config options for GC</span></span>](../../../../core/run-time-config/garbage-collector.md)
