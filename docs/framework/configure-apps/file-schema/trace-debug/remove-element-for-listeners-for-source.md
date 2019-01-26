---
title: '&lt;Entfernen Sie&gt; -Element für &lt;Listener&gt; für &lt;Quelle&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 9f3d8eefdf74f0960f3fe530f77a67c0706e4585
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083482"
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="ef6ea-102">&lt;Entfernen Sie&gt; -Element für &lt;Listener&gt; für &lt;Quelle&gt;</span><span class="sxs-lookup"><span data-stu-id="ef6ea-102">&lt;remove&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="ef6ea-103">Entfernt einen Listener aus der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="ef6ea-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="ef6ea-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ef6ea-104">\<configuration></span></span>  
<span data-ttu-id="ef6ea-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="ef6ea-105">\<system.diagnostics></span></span>  
<span data-ttu-id="ef6ea-106">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="ef6ea-106">\<sources></span></span>  
<span data-ttu-id="ef6ea-107">\<Quelle ></span><span class="sxs-lookup"><span data-stu-id="ef6ea-107">\<source></span></span>  
<span data-ttu-id="ef6ea-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="ef6ea-108">\<listeners></span></span>  
<span data-ttu-id="ef6ea-109">\<remove></span><span class="sxs-lookup"><span data-stu-id="ef6ea-109">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef6ea-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef6ea-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef6ea-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ef6ea-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ef6ea-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ef6ea-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef6ea-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ef6ea-113">Attributes</span></span>  
  
|<span data-ttu-id="ef6ea-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="ef6ea-114">Attribute</span></span>|<span data-ttu-id="ef6ea-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef6ea-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="ef6ea-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ef6ea-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="ef6ea-117">Der Name des Listeners, Aufheben der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="ef6ea-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef6ea-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef6ea-118">Child Elements</span></span>  
 <span data-ttu-id="ef6ea-119">Keine</span><span class="sxs-lookup"><span data-stu-id="ef6ea-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef6ea-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef6ea-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ef6ea-121">Element</span><span class="sxs-lookup"><span data-stu-id="ef6ea-121">Element</span></span>|<span data-ttu-id="ef6ea-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef6ea-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ef6ea-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ef6ea-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ef6ea-124">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ef6ea-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="ef6ea-125">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="ef6ea-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="ef6ea-126">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="ef6ea-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="ef6ea-127">Gibt die Listener, die sammeln, speichern und Weiterleiten von Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="ef6ea-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef6ea-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef6ea-128">Remarks</span></span>  
 <span data-ttu-id="ef6ea-129">Die `<remove>` Element entfernt einen angegebenen Listener aus der `Listeners` -Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="ef6ea-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="ef6ea-130">Können Sie ein Element Entfernen der `Listeners` Sammlung für eine Ablaufverfolgungsquelle programmgesteuert durch Aufrufen der <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> Methode für die <xref:System.Diagnostics.TraceSource.Listeners%2A> Eigenschaft der <xref:System.Diagnostics.TraceSource> Instanz.</span><span class="sxs-lookup"><span data-stu-id="ef6ea-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="ef6ea-131">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef6ea-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef6ea-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef6ea-132">Example</span></span>  
 <span data-ttu-id="ef6ea-133">Das folgende Beispiel zeigt, wie Sie mit der `<remove>` Element vor der Verwendung der `<add>` Element, um den Listener hinzuzufügen `console` auf die `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="ef6ea-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ef6ea-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef6ea-134">See also</span></span>
- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="ef6ea-135">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ef6ea-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="ef6ea-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="ef6ea-136">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="ef6ea-137">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="ef6ea-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
