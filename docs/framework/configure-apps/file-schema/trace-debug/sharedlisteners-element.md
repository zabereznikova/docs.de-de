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
ms.openlocfilehash: b419ecf451b79808e545525c7b8761175f390200
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699300"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="bea8c-102">\<sharedlistener-> Element</span><span class="sxs-lookup"><span data-stu-id="bea8c-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="bea8c-103">Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="bea8c-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="bea8c-104">Diese Listener empfangen standardmäßig keine Ablauf Verfolgungen, und es ist nicht möglich, diese Listener zur Laufzeit abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bea8c-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="bea8c-105">Listener, die als freigegebene Listener identifiziert werden, können Quellen oder Ablauf Verfolgungen anhand des Namens hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bea8c-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[<span data-ttu-id="bea8c-106"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="bea8c-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="bea8c-107">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="bea8c-107">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="bea8c-108">&nbsp;&nbsp;&nbsp;&nbsp; **\<sharedlistener >**</span><span class="sxs-lookup"><span data-stu-id="bea8c-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bea8c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="bea8c-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bea8c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bea8c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bea8c-111">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bea8c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bea8c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="bea8c-112">Attributes</span></span>  
 <span data-ttu-id="bea8c-113">None.</span><span class="sxs-lookup"><span data-stu-id="bea8c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bea8c-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bea8c-114">Child Elements</span></span>  
  
|<span data-ttu-id="bea8c-115">Element</span><span class="sxs-lookup"><span data-stu-id="bea8c-115">Element</span></span>|<span data-ttu-id="bea8c-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bea8c-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bea8c-117">\<add></span><span class="sxs-lookup"><span data-stu-id="bea8c-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="bea8c-118">Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="bea8c-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bea8c-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bea8c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="bea8c-120">Element</span><span class="sxs-lookup"><span data-stu-id="bea8c-120">Element</span></span>|<span data-ttu-id="bea8c-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bea8c-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="bea8c-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="bea8c-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="bea8c-123">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="bea8c-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bea8c-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bea8c-124">Remarks</span></span>  
 <span data-ttu-id="bea8c-125">Durch das Hinzufügen eines Listener zur Auflistung der freigegebenen Listener wird er nicht zu einem aktiven Listener.</span><span class="sxs-lookup"><span data-stu-id="bea8c-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="bea8c-126">Es muss dennoch einer Ablauf Verfolgungs Quelle oder einer Ablauf Verfolgung hinzugefügt werden, indem es der `Listeners`-Auflistung für dieses Trace-Element hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="bea8c-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="bea8c-127">Die Listenerklassen in der .NET Framework von der <xref:System.Diagnostics.TraceListener>-Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="bea8c-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="bea8c-128">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bea8c-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bea8c-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bea8c-129">Example</span></span>  
 <span data-ttu-id="bea8c-130">Im folgenden Beispiel wird gezeigt, wie das `<sharedListeners>`-Element verwendet wird, um der `Listeners`-Auflistung für die Klassen <xref:System.Diagnostics.TraceSource> und <xref:System.Diagnostics.Trace> die Listener`console` hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bea8c-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="bea8c-131">Der Ablaufverfolgungslistener der Konsole schreibt Ablauf Verfolgungs Informationen über Aufrufe von <xref:System.Diagnostics.TraceSource> oder <xref:System.Diagnostics.Trace>in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="bea8c-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bea8c-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bea8c-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="bea8c-133">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="bea8c-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bea8c-134">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="bea8c-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
