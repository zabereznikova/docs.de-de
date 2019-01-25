---
title: '&lt;Deaktivieren Sie&gt; -Element für &lt;Listener&gt; für &lt;Ablaufverfolgung&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2e0970fe197ecf6e0fbcf94f410364cb59d267e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732608"
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="b2c28-102">&lt;Deaktivieren Sie&gt; -Element für &lt;Listener&gt; für &lt;Ablaufverfolgung&gt;</span><span class="sxs-lookup"><span data-stu-id="b2c28-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="b2c28-103">Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="b2c28-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="b2c28-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b2c28-104">\<configuration></span></span>  
<span data-ttu-id="b2c28-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="b2c28-105">\<system.diagnostics></span></span>  
<span data-ttu-id="b2c28-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="b2c28-106">\<trace></span></span>  
<span data-ttu-id="b2c28-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="b2c28-107">\<listeners></span></span>  
<span data-ttu-id="b2c28-108">\<clear></span><span class="sxs-lookup"><span data-stu-id="b2c28-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2c28-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2c28-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2c28-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b2c28-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b2c28-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b2c28-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2c28-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="b2c28-112">Attributes</span></span>  
 <span data-ttu-id="b2c28-113">Keine</span><span class="sxs-lookup"><span data-stu-id="b2c28-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b2c28-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2c28-114">Child Elements</span></span>  
 <span data-ttu-id="b2c28-115">Keine</span><span class="sxs-lookup"><span data-stu-id="b2c28-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2c28-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2c28-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b2c28-117">Element</span><span class="sxs-lookup"><span data-stu-id="b2c28-117">Element</span></span>|<span data-ttu-id="b2c28-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2c28-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b2c28-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b2c28-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b2c28-120">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b2c28-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="b2c28-121">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="b2c28-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="b2c28-122">Enthält Listener, die sammeln, speichern und Weiterleiten von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b2c28-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="b2c28-123">Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.</span><span class="sxs-lookup"><span data-stu-id="b2c28-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2c28-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b2c28-124">Remarks</span></span>  
 <span data-ttu-id="b2c28-125">Die `<clear>` -Element entfernt alle Listener aus der `Listeners` -Sammlung für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="b2c28-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="b2c28-126">Können Sie die `<clear>` Element vor der Verwendung der `<add>` Element, stellen Sie sicher, dass keine anderen aktiven Listener in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b2c28-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="b2c28-127">Können Sie löschen die `Listeners` Auflistung programmgesteuert durch Aufrufen der <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> Methode für die <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> Eigenschaft (`System.Diagnostics.Trace.Listeners.Clear()`).</span><span class="sxs-lookup"><span data-stu-id="b2c28-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="b2c28-128">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b2c28-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2c28-129">Die `<clear>` -Element entfernt die <xref:System.Diagnostics.DefaultTraceListener> aus der `Listeners` Auflistung, die Änderung des Verhaltens der <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, und <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> Methoden.</span><span class="sxs-lookup"><span data-stu-id="b2c28-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="b2c28-130">Aufrufen einer `Assert` oder `Fail` -Methode führt normalerweise in der Anzeige eines Meldungsfelds.</span><span class="sxs-lookup"><span data-stu-id="b2c28-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="b2c28-131">Allerdings das Meldungsfeld wird nicht angezeigt, wenn die <xref:System.Diagnostics.DefaultTraceListener> befindet sich nicht in der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="b2c28-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2c28-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2c28-132">Example</span></span>  
 <span data-ttu-id="b2c28-133">Das folgende Beispiel zeigt, wie Sie mit der `<clear>` Element vor der Verwendung der `<add>` Element, um den Listener hinzuzufügen `console` auf die `Listeners` -Sammlung für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="b2c28-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="b2c28-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2c28-134">See also</span></span>
- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="b2c28-135">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b2c28-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="b2c28-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="b2c28-136">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="b2c28-137">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="b2c28-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
