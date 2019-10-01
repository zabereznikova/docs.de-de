---
title: <listeners>-Element für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: d7641611e5d8257b49bc6a6abd0a2fadfde66e91
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697301"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="f259f-102">\<listener >-Element für \<source-></span><span class="sxs-lookup"><span data-stu-id="f259f-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="f259f-103">Fügt Listener in der <xref:System.Diagnostics.TraceSource.Listeners%2A>-Auflistung für einen <xref:System.Diagnostics.TraceSource> hinzu oder entfernt Sie.</span><span class="sxs-lookup"><span data-stu-id="f259f-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="f259f-104">Ein Listener leitet die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel, z. b. ein Protokoll, ein Fenster oder eine Textdatei.</span><span class="sxs-lookup"><span data-stu-id="f259f-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="f259f-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f259f-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f259f-106">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="f259f-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="f259f-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="f259f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="f259f-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="f259f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="f259f-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<listener >**</span><span class="sxs-lookup"><span data-stu-id="f259f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f259f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="f259f-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f259f-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f259f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f259f-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f259f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f259f-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="f259f-113">Attributes</span></span>  
 <span data-ttu-id="f259f-114">Keine</span><span class="sxs-lookup"><span data-stu-id="f259f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f259f-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f259f-115">Child Elements</span></span>  
  
|<span data-ttu-id="f259f-116">Element</span><span class="sxs-lookup"><span data-stu-id="f259f-116">Element</span></span>|<span data-ttu-id="f259f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f259f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f259f-118">\<add></span><span class="sxs-lookup"><span data-stu-id="f259f-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="f259f-119">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="f259f-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="f259f-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="f259f-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="f259f-121">Entfernt einen Listener aus der `Listeners`-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="f259f-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="f259f-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="f259f-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="f259f-123">Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="f259f-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f259f-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f259f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f259f-125">Element</span><span class="sxs-lookup"><span data-stu-id="f259f-125">Element</span></span>|<span data-ttu-id="f259f-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f259f-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f259f-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f259f-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f259f-128">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f259f-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="f259f-129">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="f259f-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="f259f-130">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="f259f-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f259f-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f259f-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="f259f-132">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="f259f-132">Configuration File</span></span>  
 <span data-ttu-id="f259f-133">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f259f-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f259f-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f259f-134">Example</span></span>  
 <span data-ttu-id="f259f-135">Im folgenden Beispiel wird gezeigt, wie das `<listeners>`-Element verwendet wird, um der `mySource`-Quelle einen Ablaufverfolgungslistener hinzuzufügen und um den standardablaufverfolgungsli</span><span class="sxs-lookup"><span data-stu-id="f259f-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f259f-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f259f-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="f259f-137">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f259f-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f259f-138">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="f259f-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
