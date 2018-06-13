---
title: '&lt;SharedListeners&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 57927d09f10e84e73c3da424c283846bd79b5044
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745574"
---
# <a name="ltsharedlistenersgt-element"></a><span data-ttu-id="ba34d-102">&lt;SharedListeners&gt; Element</span><span class="sxs-lookup"><span data-stu-id="ba34d-102">&lt;sharedListeners&gt; Element</span></span>
<span data-ttu-id="ba34d-103">Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="ba34d-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="ba34d-104">Diese Listener ablaufverfolgungen in der Standardeinstellung nicht gesendet, und es ist nicht möglich, diese Listener zur Laufzeit abrufen.</span><span class="sxs-lookup"><span data-stu-id="ba34d-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="ba34d-105">Listener als freigegebene Listener Quellen oder ablaufverfolgungen namentlich hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="ba34d-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
 <span data-ttu-id="ba34d-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ba34d-106">\<configuration></span></span>  
<span data-ttu-id="ba34d-107">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="ba34d-107">\<system.diagnostics></span></span>  
<span data-ttu-id="ba34d-108">\<SharedListeners ></span><span class="sxs-lookup"><span data-stu-id="ba34d-108">\<sharedListeners></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba34d-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba34d-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba34d-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ba34d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ba34d-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba34d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba34d-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="ba34d-112">Attributes</span></span>  
 <span data-ttu-id="ba34d-113">Keine</span><span class="sxs-lookup"><span data-stu-id="ba34d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ba34d-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba34d-114">Child Elements</span></span>  
  
|<span data-ttu-id="ba34d-115">Element</span><span class="sxs-lookup"><span data-stu-id="ba34d-115">Element</span></span>|<span data-ttu-id="ba34d-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba34d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba34d-117">\<add></span><span class="sxs-lookup"><span data-stu-id="ba34d-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="ba34d-118">Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="ba34d-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba34d-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba34d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ba34d-120">Element</span><span class="sxs-lookup"><span data-stu-id="ba34d-120">Element</span></span>|<span data-ttu-id="ba34d-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba34d-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="ba34d-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ba34d-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ba34d-123">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="ba34d-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba34d-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba34d-124">Remarks</span></span>  
 <span data-ttu-id="ba34d-125">Hinzufügen eines Listeners zur gemeinsam genutzten Auflistung ist keinen aktiven Listener erleichtern.</span><span class="sxs-lookup"><span data-stu-id="ba34d-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="ba34d-126">Es muss immer noch eine Ablaufverfolgungsquelle oder einer Ablaufverfolgung hinzugefügt werden, durch Hinzufügen zu der `Listeners` Auflistung für das Trace-Element.</span><span class="sxs-lookup"><span data-stu-id="ba34d-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="ba34d-127">Die Listenerklassen in .NET Framework abgeleitet werden, aus der <xref:System.Diagnostics.TraceListener> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ba34d-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="ba34d-128">Dieses Element kann in der Computerkonfigurationsdatei ("Machine.config") und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba34d-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba34d-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba34d-129">Example</span></span>  
 <span data-ttu-id="ba34d-130">Das folgende Beispiel zeigt, wie Sie die `<sharedListeners>` Element an den Listener hinzufügen `console` auf die `Listeners` Auflistung für beide die <xref:System.Diagnostics.TraceSource> und <xref:System.Diagnostics.Trace> Klassen.</span><span class="sxs-lookup"><span data-stu-id="ba34d-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="ba34d-131">Die Konsolen-Ablaufverfolgungslistener Schreibt Ablaufverfolgungsinformationen in die Konsole durch Aufrufe von <xref:System.Diagnostics.TraceSource> oder <xref:System.Diagnostics.Trace>.</span><span class="sxs-lookup"><span data-stu-id="ba34d-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration></system.diagnostics>   
```  
  
## <a name="see-also"></a><span data-ttu-id="ba34d-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba34d-132">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="ba34d-133">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ba34d-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="ba34d-134">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="ba34d-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
