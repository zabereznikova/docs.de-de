---
title: <listeners>-Element für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 0eee325e01b41a15a19e4f40f479596f9d70f73b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153411"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="2485b-102">\<Listener> \<Element für Quell-></span><span class="sxs-lookup"><span data-stu-id="2485b-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="2485b-103">Fügt Listener in <xref:System.Diagnostics.TraceSource.Listeners%2A> der Auflistung <xref:System.Diagnostics.TraceSource>für eine hinzu oder entfernt sie.</span><span class="sxs-lookup"><span data-stu-id="2485b-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="2485b-104">Ein Listener leitet die Ablaufverfolgungsausgabe an ein geeignetes Ziel weiter, z. B. ein Protokoll, ein Fenster oder eine Textdatei.</span><span class="sxs-lookup"><span data-stu-id="2485b-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="2485b-105">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="2485b-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="2485b-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="2485b-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="2485b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Quellen>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="2485b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="2485b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Quelle>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="2485b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="2485b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Hörer>**</span><span class="sxs-lookup"><span data-stu-id="2485b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2485b-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="2485b-110">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2485b-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2485b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2485b-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2485b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2485b-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="2485b-113">Attributes</span></span>  
 <span data-ttu-id="2485b-114">Keine.</span><span class="sxs-lookup"><span data-stu-id="2485b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2485b-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2485b-115">Child Elements</span></span>  
  
|<span data-ttu-id="2485b-116">Element</span><span class="sxs-lookup"><span data-stu-id="2485b-116">Element</span></span>|<span data-ttu-id="2485b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2485b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2485b-118">\<hinzufügen></span><span class="sxs-lookup"><span data-stu-id="2485b-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="2485b-119">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="2485b-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="2485b-120">\<entfernen sie></span><span class="sxs-lookup"><span data-stu-id="2485b-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="2485b-121">Entfernt einen Listener `Listeners` aus der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="2485b-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="2485b-122">\<klare></span><span class="sxs-lookup"><span data-stu-id="2485b-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="2485b-123">Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="2485b-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2485b-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2485b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2485b-125">Element</span><span class="sxs-lookup"><span data-stu-id="2485b-125">Element</span></span>|<span data-ttu-id="2485b-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2485b-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2485b-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2485b-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2485b-128">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2485b-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="2485b-129">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="2485b-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="2485b-130">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="2485b-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2485b-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2485b-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="2485b-132">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="2485b-132">Configuration File</span></span>  
 <span data-ttu-id="2485b-133">Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2485b-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2485b-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2485b-134">Example</span></span>  
 <span data-ttu-id="2485b-135">Das folgende Beispiel zeigt, `<listeners>` wie Sie das Element verwenden, um der `mySource` Quelle einen Konsolenablaufverfolgungslistener hinzuzufügen und den standardmäßigen Ablaufverfolgungslistener zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2485b-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2485b-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2485b-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="2485b-137">Ablaufverfolgungs- und Debugeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="2485b-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2485b-138">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="2485b-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
