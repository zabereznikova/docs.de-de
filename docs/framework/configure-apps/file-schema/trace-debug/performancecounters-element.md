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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697154"
---
# <a name="performancecounters-element"></a><span data-ttu-id="96b34-102">\<performanceCounters>-Element</span><span class="sxs-lookup"><span data-stu-id="96b34-102">\<performanceCounters> Element</span></span>

<span data-ttu-id="96b34-103">Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="96b34-103">Specifies the size of the global memory shared by performance counters.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**  

## <a name="syntax"></a><span data-ttu-id="96b34-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="96b34-104">Syntax</span></span>

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="96b34-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="96b34-105">Attributes and Elements</span></span>

<span data-ttu-id="96b34-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="96b34-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="96b34-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="96b34-107">Attributes</span></span>

|<span data-ttu-id="96b34-108">attribute</span><span class="sxs-lookup"><span data-stu-id="96b34-108">Attribute</span></span>|<span data-ttu-id="96b34-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="96b34-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="96b34-110">FileMappingSize</span><span class="sxs-lookup"><span data-stu-id="96b34-110">filemappingsize</span></span>|<span data-ttu-id="96b34-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="96b34-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="96b34-112">Gibt die Größe des globalen Speichers (in Bytes) an, der von den Leistungsindikatoren gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="96b34-112">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="96b34-113">Der Standard ist 524288.</span><span class="sxs-lookup"><span data-stu-id="96b34-113">The default is 524288.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="96b34-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="96b34-114">Child Elements</span></span>

<span data-ttu-id="96b34-115">Keine</span><span class="sxs-lookup"><span data-stu-id="96b34-115">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="96b34-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="96b34-116">Parent Elements</span></span>

|<span data-ttu-id="96b34-117">Element</span><span class="sxs-lookup"><span data-stu-id="96b34-117">Element</span></span>|<span data-ttu-id="96b34-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96b34-118">Description</span></span>|
|-------------|-----------------|
|`Configuration`|<span data-ttu-id="96b34-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="96b34-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`system.diagnostics`|<span data-ttu-id="96b34-120">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="96b34-120">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="96b34-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="96b34-121">Remarks</span></span>

<span data-ttu-id="96b34-122">Leistungsindikatoren verwenden eine Speicher Abbild Datei oder freigegebenen Arbeitsspeicher, um Leistungsdaten zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="96b34-122">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="96b34-123">Die Größe des freigegebenen Speichers bestimmt, wie viele Instanzen gleichzeitig verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="96b34-123">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="96b34-124">Es gibt zwei Arten von gemeinsam genutzten Arbeitsspeicher: globaler gemeinsam genutzter Speicher und separater frei gegebener Speicher.</span><span class="sxs-lookup"><span data-stu-id="96b34-124">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="96b34-125">Der globale freigegebene Speicher wird von allen Leistungs Indikatorenkategorien verwendet, die mit den .NET Framework Version 1,0 oder 1,1 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="96b34-125">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="96b34-126">Die mit der .NET Framework Version 2,0 installierten Leistungs Indikatorenkategorien verwenden separaten freigegebenen Arbeitsspeicher, wobei jede Leistungs Indikatorenkategorie über einen eigenen Arbeitsspeicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="96b34-126">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>

<span data-ttu-id="96b34-127">Die Größe des globalen freigegebenen Speichers kann nur mit einer Konfigurationsdatei festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="96b34-127">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="96b34-128">Die Standardgröße beträgt 524.288 Byte, die maximale Größe beträgt 33.554.432 bytes, und die Mindestgröße beträgt 32.768 Bytes.</span><span class="sxs-lookup"><span data-stu-id="96b34-128">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="96b34-129">Da der globale freigegebene Speicher von allen Prozessen und Kategorien gemeinsam genutzt wird, gibt der erste Ersteller die Größe an.</span><span class="sxs-lookup"><span data-stu-id="96b34-129">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="96b34-130">Wenn Sie die Größe in der Anwendungs Konfigurationsdatei definieren, wird diese Größe nur verwendet, wenn die Anwendung die erste Anwendung ist, die die Ausführung der Leistungsindikatoren bewirkt.</span><span class="sxs-lookup"><span data-stu-id="96b34-130">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="96b34-131">Daher `filemappingsize` ist die Datei Machine. config der richtige Speicherort, um den Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="96b34-131">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="96b34-132">Der Arbeitsspeicher im globalen gemeinsam genutzten Arbeitsspeicher kann nicht von einzelnen Leistungsindikatoren freigegeben werden. Folglich ist der globale freigegebene Speicher erschöpft, wenn eine große Anzahl von Leistungsindikator Instanzen mit unterschiedlichen Namen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="96b34-132">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>

<span data-ttu-id="96b34-133">Bei der Größe des separaten freigegebenen Speichers wird zuerst auf den DWORD-dateimappingsize-Wert im Registrierungsschlüssel HKEY_LOCAL_MACHINE \system\currentcontrolset\services \\ *\<category name>* \Performance verwiesen, gefolgt von dem Wert, der für den globalen gemeinsam genutzten Speicher in der Konfigurationsdatei angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="96b34-133">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="96b34-134">Wenn der FileMappingSize-Wert nicht vorhanden ist, wird die separate Größe des freigegebenen Speichers auf ein viertes (1/4) die globale Einstellung in der Konfigurationsdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="96b34-134">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="96b34-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96b34-135">See also</span></span>

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
