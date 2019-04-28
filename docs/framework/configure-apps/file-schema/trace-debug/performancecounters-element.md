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
ms.openlocfilehash: 6144bcbda69b2ba799e87c3e7fa2118fbe4d9bf6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673733"
---
# <a name="performancecounters-element"></a><span data-ttu-id="ebd9f-102">\<PerformanceCounters >-Element</span><span class="sxs-lookup"><span data-stu-id="ebd9f-102">\<performanceCounters> Element</span></span>

<span data-ttu-id="ebd9f-103">Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-103">Specifies the size of the global memory shared by performance counters.</span></span>

 <span data-ttu-id="ebd9f-104">\<configuration>\\</span><span class="sxs-lookup"><span data-stu-id="ebd9f-104">\<configuration>\\</span></span>
<span data-ttu-id="ebd9f-105">\<system.diagnostics>\\</span><span class="sxs-lookup"><span data-stu-id="ebd9f-105">\<system.diagnostics>\\</span></span>
<span data-ttu-id="ebd9f-106">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="ebd9f-106">\<performanceCounters></span></span>

## <a name="syntax"></a><span data-ttu-id="ebd9f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebd9f-107">Syntax</span></span>

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ebd9f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ebd9f-108">Attributes and Elements</span></span>

<span data-ttu-id="ebd9f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ebd9f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ebd9f-110">Attributes</span></span>

|<span data-ttu-id="ebd9f-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ebd9f-111">Attribute</span></span>|<span data-ttu-id="ebd9f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebd9f-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="ebd9f-113">FileMappingSize</span><span class="sxs-lookup"><span data-stu-id="ebd9f-113">filemappingsize</span></span>|<span data-ttu-id="ebd9f-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="ebd9f-115">Gibt die Größe in Bytes, der dem globalen Arbeitsspeicher-Leistungsindikatoren gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="ebd9f-116">Der Standard ist 524288.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-116">The default is 524288.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ebd9f-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebd9f-117">Child Elements</span></span>

<span data-ttu-id="ebd9f-118">Keine</span><span class="sxs-lookup"><span data-stu-id="ebd9f-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ebd9f-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebd9f-119">Parent Elements</span></span>

|<span data-ttu-id="ebd9f-120">Element</span><span class="sxs-lookup"><span data-stu-id="ebd9f-120">Element</span></span>|<span data-ttu-id="ebd9f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebd9f-121">Description</span></span>|
|-------------|-----------------|
|`Configuration`|<span data-ttu-id="ebd9f-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`system.diagnostics`|<span data-ttu-id="ebd9f-123">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-123">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ebd9f-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ebd9f-124">Remarks</span></span>

<span data-ttu-id="ebd9f-125">Leistungsindikatoren werden im Speicher abgebildete Datei oder gemeinsam genutzten Speicher verwenden, um Leistungsdaten zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="ebd9f-126">Die Größe des freigegebenen Speichers wird bestimmt, wie viele Instanzen gleichzeitig verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="ebd9f-127">Es gibt zwei Arten von freigegebenem Arbeitsspeicher: globale freigegebene Speicher und separater freigegebener Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="ebd9f-128">Der globale freigegebene Speicher wird von allen Leistungsindikatorkategorien, die mit .NET Framework, Version 1.0 oder 1.1 installiert verwendet.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="ebd9f-129">Leistungsindikatorkategorien, die mit .NET Framework, Version 2.0 installiert verwenden separaten freigegebenen Arbeitsspeicher mit jeder Leistungsindikatorkategorie, die über einen eigenen Speicherbereich.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>

<span data-ttu-id="ebd9f-130">Die Größe der globale freigegebene Speicher kann nur mit einer Konfigurationsdatei festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="ebd9f-131">Die Standardgröße ist 524.288, die maximale Größe beträgt 33.554.432 Byte und die minimale Größe beträgt 32.768 Byte.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="ebd9f-132">Da der globale freigegebene Speicher von allen Prozessen und Kategorien gemeinsam verwendet wird, gibt der erste Ersteller die Größe an.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="ebd9f-133">Wenn Sie die Größe in der Konfigurationsdatei Ihrer Anwendung definieren, wird diese Größe nur dann verwendet, wenn Ihre Anwendung die erste Anwendung, die bewirkt, die Leistungsindikatoren ist dass ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="ebd9f-134">Aus diesem Grund den richtigen Speicherort zum Angeben der `filemappingsize` Wert ist die Datei "Machine.config".</span><span class="sxs-lookup"><span data-stu-id="ebd9f-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="ebd9f-135">Speicher, in der globale freigegebene Speicher kann nicht von einzelnen Leistungsindikatoren, sodass freigegeben werden, die globaler freigegebener Speicher ausgeschöpft ist, wenn eine große Anzahl von Leistungsindikatorinstanzen mit unterschiedlichen Namen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>

<span data-ttu-id="ebd9f-136">Der DWORD-Wert FileMappingSize in der Registrierung Schlüssel für die Größe der separater freigegebener Arbeitsspeicher, HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<Kategorienamen >* \Performance verwiesen wird zuerst dann, den Wert für die globale freigegebene Speicher in der Konfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="ebd9f-137">Wenn der FileMappingSize-Wert ist nicht vorhanden, und klicken Sie dann auf ein Viertel die Größe separater freigegebener Arbeitsspeicher festgelegt ist (1/4) die globale Einstellung in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ebd9f-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebd9f-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebd9f-138">See also</span></span>

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
