---
title: "&lt;Deaktivieren Sie&gt; -Element für &lt;Listener&gt; für &lt;Quelle&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d5e8518f2ca8a04d91f5bfdd9f6389c741d0278e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="02d09-102">&lt;Deaktivieren Sie&gt; -Element für &lt;Listener&gt; für &lt;Quelle&gt;</span><span class="sxs-lookup"><span data-stu-id="02d09-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="02d09-103">Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="02d09-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="02d09-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="02d09-104">\<configuration></span></span>  
<span data-ttu-id="02d09-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="02d09-105">\<system.diagnostics></span></span>  
<span data-ttu-id="02d09-106">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="02d09-106">\<sources></span></span>  
<span data-ttu-id="02d09-107">\<Quelle ></span><span class="sxs-lookup"><span data-stu-id="02d09-107">\<source></span></span>  
<span data-ttu-id="02d09-108">\<Listener ></span><span class="sxs-lookup"><span data-stu-id="02d09-108">\<listeners></span></span>  
<span data-ttu-id="02d09-109">\<Deaktivieren Sie ></span><span class="sxs-lookup"><span data-stu-id="02d09-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d09-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="02d09-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02d09-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="02d09-111">Attributes and Elements</span></span>  
 <span data-ttu-id="02d09-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="02d09-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02d09-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="02d09-113">Attributes</span></span>  
 <span data-ttu-id="02d09-114">Keine.</span><span class="sxs-lookup"><span data-stu-id="02d09-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="02d09-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02d09-115">Child Elements</span></span>  
 <span data-ttu-id="02d09-116">Keine</span><span class="sxs-lookup"><span data-stu-id="02d09-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02d09-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02d09-117">Parent Elements</span></span>  
  
|<span data-ttu-id="02d09-118">Element</span><span class="sxs-lookup"><span data-stu-id="02d09-118">Element</span></span>|<span data-ttu-id="02d09-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02d09-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="02d09-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="02d09-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="02d09-121">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="02d09-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="02d09-122">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="02d09-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="02d09-123">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="02d09-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="02d09-124">Gibt die Listener, mit die sammeln, speichern und Weiterleiten von Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="02d09-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02d09-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02d09-125">Remarks</span></span>  
 <span data-ttu-id="02d09-126">Die `<clear>` Element entfernt alle Listener aus der `Listeners` -Auflistung für eine Ablaufverfolgungsquelle, einschließlich der <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="02d09-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="02d09-127">Können Sie die `<clear>` Element vor dem Verwenden der `<add>` Element, stellen Sie sicher, dass keine weiteren aktiven Listener in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="02d09-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="02d09-128">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="02d09-128">Configuration File</span></span>  
 <span data-ttu-id="02d09-129">Dieses Element kann in der Computerkonfigurationsdatei ("Machine.config") und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02d09-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02d09-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02d09-130">Example</span></span>  
 <span data-ttu-id="02d09-131">Das folgende Beispiel zeigt, wie Sie die `<clear>` Element vor dem Verwenden der `<add>` Elemente, die Listener hinzugefügt `console` und `textListener` auf der `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="02d09-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="02d09-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02d09-132">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="02d09-133">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="02d09-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="02d09-134">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="02d09-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
