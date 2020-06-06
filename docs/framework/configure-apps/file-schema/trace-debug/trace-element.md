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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153165"
---
# <a name="trace-element"></a><span data-ttu-id="28533-102">\<trace>-Element</span><span class="sxs-lookup"><span data-stu-id="28533-102">\<trace> Element</span></span>
<span data-ttu-id="28533-103">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="28533-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**  
  
## <a name="syntax"></a><span data-ttu-id="28533-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28533-104">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28533-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="28533-105">Attributes and Elements</span></span>  
 <span data-ttu-id="28533-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="28533-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28533-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="28533-107">Attributes</span></span>  
  
|<span data-ttu-id="28533-108">attribute</span><span class="sxs-lookup"><span data-stu-id="28533-108">Attribute</span></span>|<span data-ttu-id="28533-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="28533-109">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="28533-110">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="28533-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="28533-111">Gibt an, ob die Ablaufverfolgungslistener den Ausgabepuffer nach jedem Schreibvorgang automatisch leeren.</span><span class="sxs-lookup"><span data-stu-id="28533-111">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="28533-112">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="28533-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="28533-113">Gibt die Anzahl der Leerzeichen für den Einzug an.</span><span class="sxs-lookup"><span data-stu-id="28533-113">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="28533-114">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="28533-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="28533-115">Gibt an, ob die globale Sperre verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="28533-115">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="28533-116">AutoFlush-Attribut</span><span class="sxs-lookup"><span data-stu-id="28533-116">autoflush Attribute</span></span>  
  
|<span data-ttu-id="28533-117">Wert</span><span class="sxs-lookup"><span data-stu-id="28533-117">Value</span></span>|<span data-ttu-id="28533-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="28533-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="28533-119">Der Ausgabepuffer wird nicht automatisch geleert.</span><span class="sxs-lookup"><span data-stu-id="28533-119">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="28533-120">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="28533-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="28533-121">Leert den Ausgabepuffer automatisch.</span><span class="sxs-lookup"><span data-stu-id="28533-121">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="28533-122">UseGlobalLock-Attribut</span><span class="sxs-lookup"><span data-stu-id="28533-122">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="28533-123">Wert</span><span class="sxs-lookup"><span data-stu-id="28533-123">Value</span></span>|<span data-ttu-id="28533-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="28533-124">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="28533-125">Verwendet nicht die globale Sperre, wenn der Listener Thread sicher ist. Andernfalls verwendet die globale Sperre.</span><span class="sxs-lookup"><span data-stu-id="28533-125">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="28533-126">Verwendet die globale Sperre, unabhängig davon, ob der Listener Thread sicher ist.</span><span class="sxs-lookup"><span data-stu-id="28533-126">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="28533-127">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="28533-127">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28533-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="28533-128">Child Elements</span></span>  
  
|<span data-ttu-id="28533-129">Element</span><span class="sxs-lookup"><span data-stu-id="28533-129">Element</span></span>|<span data-ttu-id="28533-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28533-130">Description</span></span>|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-trace.md)|<span data-ttu-id="28533-131">Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="28533-131">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28533-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="28533-132">Parent Elements</span></span>  
  
|<span data-ttu-id="28533-133">Element</span><span class="sxs-lookup"><span data-stu-id="28533-133">Element</span></span>|<span data-ttu-id="28533-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28533-134">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="28533-135">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="28533-135">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="28533-136">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="28533-136">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="28533-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="28533-137">Example</span></span>  
 <span data-ttu-id="28533-138">Im folgenden Beispiel wird gezeigt, wie das-Element verwendet wird, `<trace>` um den Listener der Auflistung hinzuzufügen `MyListener` `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="28533-138">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="28533-139">`MyListener`erstellt eine Datei `MyListener.log` mit dem Namen und schreibt die Ausgabe in die Datei.</span><span class="sxs-lookup"><span data-stu-id="28533-139">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="28533-140">Das- `useGlobalLock` Attribut ist auf festgelegt `false` . Dies bewirkt, dass die globale Sperre nicht verwendet wird, wenn der Ablaufverfolgungslistener Thread sicher ist.</span><span class="sxs-lookup"><span data-stu-id="28533-140">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="28533-141">Das- `autoflush` Attribut ist auf festgelegt `true` , wodurch der Ablaufverfolgungslistener in die Datei schreibt, unabhängig davon, ob die- <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="28533-141">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="28533-142">Das- `indentsize` Attribut wird auf 0 (null) festgelegt, was bewirkt, dass der Listener beim Aufrufen der-Methode NULL-Leerzeichen <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> eingibt.</span><span class="sxs-lookup"><span data-stu-id="28533-142">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="28533-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28533-143">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="28533-144">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="28533-144">Trace and Debug Settings Schema</span></span>](index.md)
