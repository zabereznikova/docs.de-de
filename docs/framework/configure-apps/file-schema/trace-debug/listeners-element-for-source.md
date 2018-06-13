---
title: '&lt;Listener&gt; -Element für &lt;Quelle&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a711b8d6bfd5b6d73d3240cb84810841bdc5a2b6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746838"
---
# <a name="ltlistenersgt-element-for-ltsourcegt"></a><span data-ttu-id="2c7cb-102">&lt;Listener&gt; -Element für &lt;Quelle&gt;</span><span class="sxs-lookup"><span data-stu-id="2c7cb-102">&lt;listeners&gt; Element for &lt;source&gt;</span></span>
<span data-ttu-id="2c7cb-103">Hinzufügt oder entfernt Listener in der <xref:System.Diagnostics.TraceSource.Listeners%2A> Auflistung für einen <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="2c7cb-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="2c7cb-104">Ein Listener leitet die Ablaufverfolgungsausgabe an ein entsprechendes Ziel, z. B. ein Protokoll, Fenster oder Textdatei.</span><span class="sxs-lookup"><span data-stu-id="2c7cb-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="2c7cb-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2c7cb-105">\<configuration></span></span>  
<span data-ttu-id="2c7cb-106">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="2c7cb-106">\<system.diagnostics></span></span>  
<span data-ttu-id="2c7cb-107">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="2c7cb-107">\<sources></span></span>  
<span data-ttu-id="2c7cb-108">\<Quelle ></span><span class="sxs-lookup"><span data-stu-id="2c7cb-108">\<source></span></span>  
<span data-ttu-id="2c7cb-109">\<Listener >-Element</span><span class="sxs-lookup"><span data-stu-id="2c7cb-109">\<listeners> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c7cb-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c7cb-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c7cb-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2c7cb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2c7cb-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2c7cb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c7cb-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="2c7cb-113">Attributes</span></span>  
 <span data-ttu-id="2c7cb-114">Keine</span><span class="sxs-lookup"><span data-stu-id="2c7cb-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2c7cb-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2c7cb-115">Child Elements</span></span>  
  
|<span data-ttu-id="2c7cb-116">Element</span><span class="sxs-lookup"><span data-stu-id="2c7cb-116">Element</span></span>|<span data-ttu-id="2c7cb-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c7cb-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c7cb-118">\<add></span><span class="sxs-lookup"><span data-stu-id="2c7cb-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|<span data-ttu-id="2c7cb-119">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="2c7cb-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="2c7cb-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="2c7cb-120">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|<span data-ttu-id="2c7cb-121">Entfernt einen Listener aus der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="2c7cb-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="2c7cb-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="2c7cb-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|<span data-ttu-id="2c7cb-123">Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="2c7cb-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c7cb-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2c7cb-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2c7cb-125">Element</span><span class="sxs-lookup"><span data-stu-id="2c7cb-125">Element</span></span>|<span data-ttu-id="2c7cb-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c7cb-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2c7cb-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2c7cb-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2c7cb-128">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2c7cb-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="2c7cb-129">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="2c7cb-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="2c7cb-130">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="2c7cb-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c7cb-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c7cb-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="2c7cb-132">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="2c7cb-132">Configuration File</span></span>  
 <span data-ttu-id="2c7cb-133">Dieses Element kann in der Computerkonfigurationsdatei ("Machine.config") und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c7cb-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c7cb-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c7cb-134">Example</span></span>  
 <span data-ttu-id="2c7cb-135">Das folgende Beispiel zeigt, wie Sie die `<listeners>` einen Konsolen-Ablaufverfolgungslistener zum hinzuzufügenden Elements der `mySource` Quelle und den Standard-Ablaufverfolgungslistener zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2c7cb-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2c7cb-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c7cb-136">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="2c7cb-137">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2c7cb-137">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="2c7cb-138">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="2c7cb-138">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
