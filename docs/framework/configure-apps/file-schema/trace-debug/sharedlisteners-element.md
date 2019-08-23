---
title: <sharedListeners>-Element
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
ms.openlocfilehash: 41cabcbce13409b0842cbbd625028b51d32d59d0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926985"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="438a5-102">\<sharedlistener-> Element</span><span class="sxs-lookup"><span data-stu-id="438a5-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="438a5-103">Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="438a5-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="438a5-104">Diese Listener empfangen standardmäßig keine Ablauf Verfolgungen, und es ist nicht möglich, diese Listener zur Laufzeit abzurufen.</span><span class="sxs-lookup"><span data-stu-id="438a5-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="438a5-105">Listener, die als freigegebene Listener identifiziert werden, können Quellen oder Ablauf Verfolgungen anhand des Namens hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="438a5-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
 <span data-ttu-id="438a5-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="438a5-106">\<configuration></span></span>  
<span data-ttu-id="438a5-107">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="438a5-107">\<system.diagnostics></span></span>  
<span data-ttu-id="438a5-108">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="438a5-108">\<sharedListeners></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="438a5-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="438a5-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="438a5-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="438a5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="438a5-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="438a5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="438a5-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="438a5-112">Attributes</span></span>  
 <span data-ttu-id="438a5-113">Keine</span><span class="sxs-lookup"><span data-stu-id="438a5-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="438a5-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="438a5-114">Child Elements</span></span>  
  
|<span data-ttu-id="438a5-115">Element</span><span class="sxs-lookup"><span data-stu-id="438a5-115">Element</span></span>|<span data-ttu-id="438a5-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="438a5-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="438a5-117">\<add></span><span class="sxs-lookup"><span data-stu-id="438a5-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="438a5-118">Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="438a5-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="438a5-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="438a5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="438a5-120">Element</span><span class="sxs-lookup"><span data-stu-id="438a5-120">Element</span></span>|<span data-ttu-id="438a5-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="438a5-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="438a5-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="438a5-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="438a5-123">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="438a5-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="438a5-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="438a5-124">Remarks</span></span>  
 <span data-ttu-id="438a5-125">Durch das Hinzufügen eines Listener zur Auflistung der freigegebenen Listener wird er nicht zu einem aktiven Listener.</span><span class="sxs-lookup"><span data-stu-id="438a5-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="438a5-126">Es muss dennoch einer Ablauf Verfolgungs Quelle oder einer Ablauf Verfolgung hinzugefügt werden, indem es `Listeners` der-Auflistung für dieses Trace-Element hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="438a5-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="438a5-127">Die Listenerklassen in der .NET Framework von der <xref:System.Diagnostics.TraceListener> -Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="438a5-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="438a5-128">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="438a5-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="438a5-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="438a5-129">Example</span></span>  
 <span data-ttu-id="438a5-130">Im folgenden Beispiel wird gezeigt, wie das `<sharedListeners>` -Element verwendet wird, `console` um den `Listeners` Listener der-Auflistung <xref:System.Diagnostics.TraceSource> für <xref:System.Diagnostics.Trace> die-Klasse und die-Klasse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="438a5-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="438a5-131">Der Ablaufverfolgungslistener der Konsole schreibt Ablauf Verfolgungs Informationen <xref:System.Diagnostics.TraceSource> über <xref:System.Diagnostics.Trace>Aufrufe von oder in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="438a5-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
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
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="438a5-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="438a5-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="438a5-133">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="438a5-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="438a5-134">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="438a5-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
