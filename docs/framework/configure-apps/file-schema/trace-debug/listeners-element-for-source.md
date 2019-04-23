---
title: <listeners>-Element für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: b15a30fb6d356f92312bf33bc1964c7922ba1383
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089652"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="69e72-102">\<Listener >-Element für \<Quelle ></span><span class="sxs-lookup"><span data-stu-id="69e72-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="69e72-103">Fügt Listener hinzu oder entfernt den <xref:System.Diagnostics.TraceSource.Listeners%2A> Sammlung für einen <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="69e72-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="69e72-104">Ein Listener leitet die Ablaufverfolgungsausgabe an ein entsprechendes Ziel, z. B. ein Protokoll, Fenster oder Text-Datei.</span><span class="sxs-lookup"><span data-stu-id="69e72-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="69e72-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="69e72-105">\<configuration></span></span>  
<span data-ttu-id="69e72-106">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="69e72-106">\<system.diagnostics></span></span>  
<span data-ttu-id="69e72-107">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="69e72-107">\<sources></span></span>  
<span data-ttu-id="69e72-108">\<Quelle ></span><span class="sxs-lookup"><span data-stu-id="69e72-108">\<source></span></span>  
<span data-ttu-id="69e72-109">\<Listener >-Element</span><span class="sxs-lookup"><span data-stu-id="69e72-109">\<listeners> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e72-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="69e72-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69e72-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="69e72-111">Attributes and Elements</span></span>  
 <span data-ttu-id="69e72-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69e72-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69e72-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="69e72-113">Attributes</span></span>  
 <span data-ttu-id="69e72-114">Keine</span><span class="sxs-lookup"><span data-stu-id="69e72-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="69e72-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69e72-115">Child Elements</span></span>  
  
|<span data-ttu-id="69e72-116">Element</span><span class="sxs-lookup"><span data-stu-id="69e72-116">Element</span></span>|<span data-ttu-id="69e72-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69e72-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69e72-118">\<add></span><span class="sxs-lookup"><span data-stu-id="69e72-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|<span data-ttu-id="69e72-119">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="69e72-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="69e72-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="69e72-120">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|<span data-ttu-id="69e72-121">Entfernt einen Listener aus der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="69e72-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="69e72-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="69e72-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|<span data-ttu-id="69e72-123">Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="69e72-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="69e72-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69e72-124">Parent Elements</span></span>  
  
|<span data-ttu-id="69e72-125">Element</span><span class="sxs-lookup"><span data-stu-id="69e72-125">Element</span></span>|<span data-ttu-id="69e72-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69e72-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="69e72-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="69e72-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="69e72-128">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="69e72-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="69e72-129">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="69e72-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="69e72-130">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="69e72-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69e72-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="69e72-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="69e72-132">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="69e72-132">Configuration File</span></span>  
 <span data-ttu-id="69e72-133">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69e72-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69e72-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="69e72-134">Example</span></span>  
 <span data-ttu-id="69e72-135">Das folgende Beispiel zeigt, wie Sie mit der `<listeners>` Element, um einen Konsolen-Ablaufverfolgungslistener hinzugefügt werden die `mySource` Quelle und den standardmäßigen Ablaufverfolgungslistener zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="69e72-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="69e72-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69e72-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="69e72-137">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="69e72-137">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="69e72-138">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="69e72-138">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
