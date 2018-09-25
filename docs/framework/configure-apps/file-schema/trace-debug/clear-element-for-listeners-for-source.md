---
title: '&lt;Deaktivieren Sie&gt; -Element für &lt;Listener&gt; für &lt;Quelle&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 3674b5e8f54735010da901c76b77bd617218891e
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47071752"
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="cf2a2-102">&lt;Deaktivieren Sie&gt; -Element für &lt;Listener&gt; für &lt;Quelle&gt;</span><span class="sxs-lookup"><span data-stu-id="cf2a2-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="cf2a2-103">Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="cf2a2-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="cf2a2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cf2a2-104">\<configuration></span></span>  
<span data-ttu-id="cf2a2-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="cf2a2-105">\<system.diagnostics></span></span>  
<span data-ttu-id="cf2a2-106">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="cf2a2-106">\<sources></span></span>  
<span data-ttu-id="cf2a2-107">\<Quelle ></span><span class="sxs-lookup"><span data-stu-id="cf2a2-107">\<source></span></span>  
<span data-ttu-id="cf2a2-108">\<Listener ></span><span class="sxs-lookup"><span data-stu-id="cf2a2-108">\<listeners></span></span>  
<span data-ttu-id="cf2a2-109">\<Deaktivieren Sie ></span><span class="sxs-lookup"><span data-stu-id="cf2a2-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf2a2-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf2a2-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf2a2-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cf2a2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cf2a2-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cf2a2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf2a2-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="cf2a2-113">Attributes</span></span>  
 <span data-ttu-id="cf2a2-114">Keine</span><span class="sxs-lookup"><span data-stu-id="cf2a2-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cf2a2-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf2a2-115">Child Elements</span></span>  
 <span data-ttu-id="cf2a2-116">Keine</span><span class="sxs-lookup"><span data-stu-id="cf2a2-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cf2a2-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf2a2-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cf2a2-118">Element</span><span class="sxs-lookup"><span data-stu-id="cf2a2-118">Element</span></span>|<span data-ttu-id="cf2a2-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf2a2-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cf2a2-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="cf2a2-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="cf2a2-121">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cf2a2-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="cf2a2-122">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="cf2a2-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="cf2a2-123">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="cf2a2-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="cf2a2-124">Gibt die Listener, die sammeln, speichern und Weiterleiten von Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="cf2a2-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf2a2-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf2a2-125">Remarks</span></span>  
 <span data-ttu-id="cf2a2-126">Die `<clear>` -Element entfernt alle Listener aus der `Listeners` Sammlung für eine Ablaufverfolgungsquelle, einschließlich der <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="cf2a2-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="cf2a2-127">Können Sie die `<clear>` Element vor der Verwendung der `<add>` Element, stellen Sie sicher, dass keine anderen aktiven Listener in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cf2a2-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="cf2a2-128">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="cf2a2-128">Configuration File</span></span>  
 <span data-ttu-id="cf2a2-129">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf2a2-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf2a2-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf2a2-130">Example</span></span>  
 <span data-ttu-id="cf2a2-131">Das folgende Beispiel zeigt, wie Sie mit der `<clear>` Element vor der Verwendung der `<add>` Elemente, die Listener hinzugefügt werden `console` und `textListener` auf die `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="cf2a2-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="cf2a2-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf2a2-132">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="cf2a2-133">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="cf2a2-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="cf2a2-134">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="cf2a2-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
