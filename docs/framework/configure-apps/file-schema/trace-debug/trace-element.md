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
ms.openlocfilehash: 7d8a989219d84e8604e767456c84c0092bc73b22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153165"
---
# <a name="trace-element"></a><span data-ttu-id="23705-102">\<Ablaufverfolgung> Element</span><span class="sxs-lookup"><span data-stu-id="23705-102">\<trace> Element</span></span>
<span data-ttu-id="23705-103">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="23705-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[<span data-ttu-id="23705-104">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="23705-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="23705-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="23705-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="23705-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Spur>**</span><span class="sxs-lookup"><span data-stu-id="23705-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23705-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="23705-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23705-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="23705-108">Attributes and Elements</span></span>  
 <span data-ttu-id="23705-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="23705-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23705-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="23705-110">Attributes</span></span>  
  
|<span data-ttu-id="23705-111">attribute</span><span class="sxs-lookup"><span data-stu-id="23705-111">Attribute</span></span>|<span data-ttu-id="23705-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23705-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="23705-113">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="23705-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="23705-114">Gibt an, ob die Ablaufverfolgungslistener den Ausgabepuffer nach jedem Schreibvorgang automatisch leeren.</span><span class="sxs-lookup"><span data-stu-id="23705-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="23705-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="23705-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="23705-116">Gibt die Anzahl der einrückenden Leerzeichen an.</span><span class="sxs-lookup"><span data-stu-id="23705-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="23705-117">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="23705-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="23705-118">Gibt an, ob die globale Sperre verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="23705-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="23705-119">autoflush-Attribut</span><span class="sxs-lookup"><span data-stu-id="23705-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="23705-120">value</span><span class="sxs-lookup"><span data-stu-id="23705-120">Value</span></span>|<span data-ttu-id="23705-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23705-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="23705-122">Spült den Ausgabepuffer nicht automatisch.</span><span class="sxs-lookup"><span data-stu-id="23705-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="23705-123">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="23705-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="23705-124">Spült den Ausgabepuffer automatisch.</span><span class="sxs-lookup"><span data-stu-id="23705-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="23705-125">VerwendenDesGlobalLock-Attribut</span><span class="sxs-lookup"><span data-stu-id="23705-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="23705-126">value</span><span class="sxs-lookup"><span data-stu-id="23705-126">Value</span></span>|<span data-ttu-id="23705-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23705-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="23705-128">Verwendet die globale Sperre nicht, wenn der Listener threadsicher ist. Andernfalls wird die globale Sperre verwendet.</span><span class="sxs-lookup"><span data-stu-id="23705-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="23705-129">Verwendet die globale Sperre unabhängig davon, ob der Listener threadsicher ist.</span><span class="sxs-lookup"><span data-stu-id="23705-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="23705-130">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="23705-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23705-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="23705-131">Child Elements</span></span>  
  
|<span data-ttu-id="23705-132">Element</span><span class="sxs-lookup"><span data-stu-id="23705-132">Element</span></span>|<span data-ttu-id="23705-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23705-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23705-134">\<Hörer></span><span class="sxs-lookup"><span data-stu-id="23705-134">\<listeners></span></span>](listeners-element-for-trace.md)|<span data-ttu-id="23705-135">Gibt einen Listener an, der Nachrichten sammelt, speichert und leitet.</span><span class="sxs-lookup"><span data-stu-id="23705-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23705-136">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="23705-136">Parent Elements</span></span>  
  
|<span data-ttu-id="23705-137">Element</span><span class="sxs-lookup"><span data-stu-id="23705-137">Element</span></span>|<span data-ttu-id="23705-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23705-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="23705-139">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="23705-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="23705-140">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="23705-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="23705-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="23705-141">Example</span></span>  
 <span data-ttu-id="23705-142">Das folgende Beispiel zeigt, `<trace>` wie sie das `MyListener` Element `Listeners` zum Hinzufügen des Listeners zur Auflistung verwenden.</span><span class="sxs-lookup"><span data-stu-id="23705-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="23705-143">`MyListener`erstellt eine Datei `MyListener.log` mit dem Namen und schreibt die Ausgabe in die Datei.</span><span class="sxs-lookup"><span data-stu-id="23705-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="23705-144">Das `useGlobalLock` Attribut ist `false`auf festgelegt, wodurch die globale Sperre nicht verwendet wird, wenn der Ablaufverfolgungslistener threadsicher ist.</span><span class="sxs-lookup"><span data-stu-id="23705-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="23705-145">Das `autoflush` Attribut ist `true`auf festgelegt, wodurch der Ablaufverfolgungslistener <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> unabhängig davon, ob die Methode aufgerufen wird, in die Datei geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="23705-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="23705-146">Das `indentsize` Attribut wird auf 0 (Null) gesetzt, wodurch der <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> Listener beim Aufruf der Methode Leerzeichen einrücken lässt.</span><span class="sxs-lookup"><span data-stu-id="23705-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="23705-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23705-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="23705-148">Ablaufverfolgungs- und Debugeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="23705-148">Trace and Debug Settings Schema</span></span>](index.md)
