---
title: "&lt;Entfernen Sie&gt; -Element für &lt;Listener&gt; für &lt;Quelle&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6170c02296859d9c47e5288f287a4371d7cb0c56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="1dd23-102">&lt;Entfernen Sie&gt; -Element für &lt;Listener&gt; für &lt;Quelle&gt;</span><span class="sxs-lookup"><span data-stu-id="1dd23-102">&lt;remove&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="1dd23-103">Entfernt einen Listener aus der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="1dd23-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="1dd23-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1dd23-104">\<configuration></span></span>  
<span data-ttu-id="1dd23-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="1dd23-105">\<system.diagnostics></span></span>  
<span data-ttu-id="1dd23-106">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="1dd23-106">\<sources></span></span>  
<span data-ttu-id="1dd23-107">\<Quelle ></span><span class="sxs-lookup"><span data-stu-id="1dd23-107">\<source></span></span>  
<span data-ttu-id="1dd23-108">\<Listener ></span><span class="sxs-lookup"><span data-stu-id="1dd23-108">\<listeners></span></span>  
<span data-ttu-id="1dd23-109">\<Entfernen ></span><span class="sxs-lookup"><span data-stu-id="1dd23-109">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dd23-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="1dd23-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dd23-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1dd23-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1dd23-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1dd23-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dd23-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="1dd23-113">Attributes</span></span>  
  
|<span data-ttu-id="1dd23-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="1dd23-114">Attribute</span></span>|<span data-ttu-id="1dd23-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dd23-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="1dd23-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="1dd23-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="1dd23-117">Der Name des Listeners, Aufheben der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="1dd23-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1dd23-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1dd23-118">Child Elements</span></span>  
 <span data-ttu-id="1dd23-119">Keine</span><span class="sxs-lookup"><span data-stu-id="1dd23-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1dd23-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1dd23-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1dd23-121">Element</span><span class="sxs-lookup"><span data-stu-id="1dd23-121">Element</span></span>|<span data-ttu-id="1dd23-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dd23-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1dd23-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="1dd23-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1dd23-124">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1dd23-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="1dd23-125">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="1dd23-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="1dd23-126">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="1dd23-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="1dd23-127">Gibt die Listener, mit die sammeln, speichern und Weiterleiten von Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="1dd23-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dd23-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1dd23-128">Remarks</span></span>  
 <span data-ttu-id="1dd23-129">Die `<remove>` Element entfernt einen angegebenen Listener aus der `Listeners` -Auflistung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="1dd23-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="1dd23-130">Können, entfernen Sie ein Element aus der `Listeners` -Auflistung für eine Ablaufverfolgungsquelle programmgesteuert durch Aufrufen der <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> Methode für die <xref:System.Diagnostics.TraceSource.Listeners%2A> Eigenschaft der <xref:System.Diagnostics.TraceSource> Instanz.</span><span class="sxs-lookup"><span data-stu-id="1dd23-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="1dd23-131">Dieses Element kann in der Computerkonfigurationsdatei ("Machine.config") und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1dd23-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1dd23-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1dd23-132">Example</span></span>  
 <span data-ttu-id="1dd23-133">Das folgende Beispiel zeigt, wie Sie die `<remove>` Element vor dem Verwenden der `<add>` Element an den Listener hinzufügen `console` auf die `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="1dd23-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="1dd23-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1dd23-134">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource.Listeners%2A>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="1dd23-135">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1dd23-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="1dd23-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="1dd23-136">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)  
 [<span data-ttu-id="1dd23-137">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="1dd23-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
