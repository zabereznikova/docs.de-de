---
title: <trace>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: fd90d271591a47849b3f70aea50cbe909b6fd613
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920400"
---
# <a name="trace-element"></a><span data-ttu-id="74fe5-102">\<Trace > Element</span><span class="sxs-lookup"><span data-stu-id="74fe5-102">\<trace> Element</span></span>
<span data-ttu-id="74fe5-103">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="74fe5-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="74fe5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="74fe5-104">\<configuration></span></span>  
<span data-ttu-id="74fe5-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="74fe5-105">\<system.diagnostics></span></span>  
<span data-ttu-id="74fe5-106">\<Ablauf Verfolgungs ></span><span class="sxs-lookup"><span data-stu-id="74fe5-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74fe5-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="74fe5-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74fe5-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="74fe5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="74fe5-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74fe5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74fe5-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="74fe5-110">Attributes</span></span>  
  
|<span data-ttu-id="74fe5-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="74fe5-111">Attribute</span></span>|<span data-ttu-id="74fe5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74fe5-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="74fe5-113">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="74fe5-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="74fe5-114">Gibt an, ob die Ablaufverfolgungslistener den Ausgabepuffer nach jedem Schreibvorgang automatisch leeren.</span><span class="sxs-lookup"><span data-stu-id="74fe5-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="74fe5-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="74fe5-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="74fe5-116">Gibt die Anzahl der Leerzeichen für den Einzug an.</span><span class="sxs-lookup"><span data-stu-id="74fe5-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="74fe5-117">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="74fe5-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="74fe5-118">Gibt an, ob die globale Sperre verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="74fe5-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="74fe5-119">AutoFlush-Attribut</span><span class="sxs-lookup"><span data-stu-id="74fe5-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="74fe5-120">Wert</span><span class="sxs-lookup"><span data-stu-id="74fe5-120">Value</span></span>|<span data-ttu-id="74fe5-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74fe5-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="74fe5-122">Der Ausgabepuffer wird nicht automatisch geleert.</span><span class="sxs-lookup"><span data-stu-id="74fe5-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="74fe5-123">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="74fe5-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="74fe5-124">Leert den Ausgabepuffer automatisch.</span><span class="sxs-lookup"><span data-stu-id="74fe5-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="74fe5-125">UseGlobalLock-Attribut</span><span class="sxs-lookup"><span data-stu-id="74fe5-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="74fe5-126">Wert</span><span class="sxs-lookup"><span data-stu-id="74fe5-126">Value</span></span>|<span data-ttu-id="74fe5-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74fe5-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="74fe5-128">Verwendet nicht die globale Sperre, wenn der Listener Thread sicher ist. Andernfalls verwendet die globale Sperre.</span><span class="sxs-lookup"><span data-stu-id="74fe5-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="74fe5-129">Verwendet die globale Sperre, unabhängig davon, ob der Listener Thread sicher ist.</span><span class="sxs-lookup"><span data-stu-id="74fe5-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="74fe5-130">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="74fe5-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74fe5-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74fe5-131">Child Elements</span></span>  
  
|<span data-ttu-id="74fe5-132">Element</span><span class="sxs-lookup"><span data-stu-id="74fe5-132">Element</span></span>|<span data-ttu-id="74fe5-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74fe5-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74fe5-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="74fe5-134">\<listeners></span></span>](listeners-element-for-trace.md)|<span data-ttu-id="74fe5-135">Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="74fe5-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="74fe5-136">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74fe5-136">Parent Elements</span></span>  
  
|<span data-ttu-id="74fe5-137">Element</span><span class="sxs-lookup"><span data-stu-id="74fe5-137">Element</span></span>|<span data-ttu-id="74fe5-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74fe5-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="74fe5-139">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="74fe5-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="74fe5-140">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="74fe5-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="74fe5-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74fe5-141">Example</span></span>  
 <span data-ttu-id="74fe5-142">Im folgenden Beispiel wird gezeigt, wie das `<trace>` -Element verwendet wird, `MyListener` um den `Listeners` Listener der Auflistung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="74fe5-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="74fe5-143">`MyListener`erstellt eine Datei mit dem Namen `MyListener.log` und schreibt die Ausgabe in die Datei.</span><span class="sxs-lookup"><span data-stu-id="74fe5-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="74fe5-144">Das `useGlobalLock` -Attribut ist auf `false`festgelegt. Dies bewirkt, dass die globale Sperre nicht verwendet wird, wenn der Ablaufverfolgungslistener Thread sicher ist.</span><span class="sxs-lookup"><span data-stu-id="74fe5-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="74fe5-145">Das `autoflush` -Attribut ist auf `true`festgelegt, wodurch der Ablaufverfolgungslistener in die Datei <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> schreibt, unabhängig davon, ob die-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="74fe5-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="74fe5-146">Das `indentsize` -Attribut wird auf 0 (null) festgelegt, was bewirkt, dass der Listener beim Aufrufen der <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> -Methode NULL-Leerzeichen eingibt.</span><span class="sxs-lookup"><span data-stu-id="74fe5-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="74fe5-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74fe5-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="74fe5-148">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="74fe5-148">Trace and Debug Settings Schema</span></span>](index.md)
