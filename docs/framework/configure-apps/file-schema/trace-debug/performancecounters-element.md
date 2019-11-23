---
title: <performanceCounters>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: f52fdb2d5b0b7911de63f96663e70735d2f2496c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697154"
---
# <a name="performancecounters-element"></a><span data-ttu-id="4cedb-102">\<performanceCounters >-Element</span><span class="sxs-lookup"><span data-stu-id="4cedb-102">\<performanceCounters> Element</span></span>

<span data-ttu-id="4cedb-103">Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4cedb-103">Specifies the size of the global memory shared by performance counters.</span></span>

[<span data-ttu-id="4cedb-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="4cedb-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="4cedb-105">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="4cedb-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="4cedb-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Performance Counters >**</span><span class="sxs-lookup"><span data-stu-id="4cedb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="4cedb-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4cedb-107">Syntax</span></span>

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4cedb-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4cedb-108">Attributes and Elements</span></span>

<span data-ttu-id="4cedb-109">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4cedb-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4cedb-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="4cedb-110">Attributes</span></span>

|<span data-ttu-id="4cedb-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="4cedb-111">Attribute</span></span>|<span data-ttu-id="4cedb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cedb-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="4cedb-113">FileMappingSize</span><span class="sxs-lookup"><span data-stu-id="4cedb-113">filemappingsize</span></span>|<span data-ttu-id="4cedb-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="4cedb-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="4cedb-115">Gibt die Größe des globalen Speichers in Bytes an, der von den Leistungsindikatoren gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="4cedb-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="4cedb-116">Der Standard ist 524288.</span><span class="sxs-lookup"><span data-stu-id="4cedb-116">The default is 524288.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="4cedb-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4cedb-117">Child Elements</span></span>

<span data-ttu-id="4cedb-118">None.</span><span class="sxs-lookup"><span data-stu-id="4cedb-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4cedb-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4cedb-119">Parent Elements</span></span>

|<span data-ttu-id="4cedb-120">Element</span><span class="sxs-lookup"><span data-stu-id="4cedb-120">Element</span></span>|<span data-ttu-id="4cedb-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cedb-121">Description</span></span>|
|-------------|-----------------|
|`Configuration`|<span data-ttu-id="4cedb-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4cedb-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`system.diagnostics`|<span data-ttu-id="4cedb-123">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="4cedb-123">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4cedb-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4cedb-124">Remarks</span></span>

<span data-ttu-id="4cedb-125">Leistungsindikatoren verwenden eine Speicher Abbild Datei oder freigegebenen Arbeitsspeicher, um Leistungsdaten zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4cedb-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="4cedb-126">Die Größe des freigegebenen Speichers bestimmt, wie viele Instanzen gleichzeitig verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4cedb-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="4cedb-127">Es gibt zwei Arten von gemeinsam genutzten Arbeitsspeicher: globaler gemeinsam genutzter Speicher und separater frei gegebener Speicher.</span><span class="sxs-lookup"><span data-stu-id="4cedb-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="4cedb-128">Der globale freigegebene Speicher wird von allen Leistungs Indikatorenkategorien verwendet, die mit den .NET Framework Version 1,0 oder 1,1 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="4cedb-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="4cedb-129">Die mit der .NET Framework Version 2,0 installierten Leistungs Indikatorenkategorien verwenden separaten freigegebenen Arbeitsspeicher, wobei jede Leistungs Indikatorenkategorie über einen eigenen Arbeitsspeicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="4cedb-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>

<span data-ttu-id="4cedb-130">Die Größe des globalen freigegebenen Speichers kann nur mit einer Konfigurationsdatei festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4cedb-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="4cedb-131">Die Standardgröße beträgt 524.288 Byte, die maximale Größe beträgt 33.554.432 bytes, und die Mindestgröße beträgt 32.768 Bytes.</span><span class="sxs-lookup"><span data-stu-id="4cedb-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="4cedb-132">Da der globale freigegebene Speicher von allen Prozessen und Kategorien gemeinsam genutzt wird, gibt der erste Ersteller die Größe an.</span><span class="sxs-lookup"><span data-stu-id="4cedb-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="4cedb-133">Wenn Sie die Größe in der Anwendungs Konfigurationsdatei definieren, wird diese Größe nur verwendet, wenn die Anwendung die erste Anwendung ist, die die Ausführung der Leistungsindikatoren bewirkt.</span><span class="sxs-lookup"><span data-stu-id="4cedb-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="4cedb-134">Daher ist der richtige Speicherort zum Angeben des `filemappingsize` Werts die Datei Machine. config.</span><span class="sxs-lookup"><span data-stu-id="4cedb-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="4cedb-135">Der Arbeitsspeicher im globalen gemeinsam genutzten Arbeitsspeicher kann nicht von einzelnen Leistungsindikatoren freigegeben werden. Folglich ist der globale freigegebene Speicher erschöpft, wenn eine große Anzahl von Leistungsindikator Instanzen mit unterschiedlichen Namen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4cedb-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>

<span data-ttu-id="4cedb-136">Bei der Größe des separaten freigegebenen Speichers wird zuerst auf den DWORD-dateimappingsize-Wert im Registrierungsschlüssel HKEY_LOCAL_MACHINE \system\currentcontrolset\services\\ *\<Kategoriename >* \Performance verwiesen, gefolgt von dem Wert, der für den globalen gemeinsam genutzten Speicher in der Konfigurationsdatei angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="4cedb-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="4cedb-137">Wenn der FileMappingSize-Wert nicht vorhanden ist, wird die separate Größe des freigegebenen Speichers auf ein viertes (1/4) die globale Einstellung in der Konfigurationsdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4cedb-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="4cedb-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cedb-138">See also</span></span>

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
