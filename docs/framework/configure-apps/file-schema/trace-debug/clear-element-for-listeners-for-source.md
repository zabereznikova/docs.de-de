---
title: <clear> -Element für <listeners> für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 63d3bb272fcdbee2c59b0569c85f8183cdac8666
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158352"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="177b1-102">\<clear >-Element für \<Listener > für \<Quelle ></span><span class="sxs-lookup"><span data-stu-id="177b1-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="177b1-103">Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="177b1-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="177b1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="177b1-104">\<configuration></span></span>  
<span data-ttu-id="177b1-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="177b1-105">\<system.diagnostics></span></span>  
<span data-ttu-id="177b1-106">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="177b1-106">\<sources></span></span>  
<span data-ttu-id="177b1-107">\<Quelle ></span><span class="sxs-lookup"><span data-stu-id="177b1-107">\<source></span></span>  
<span data-ttu-id="177b1-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="177b1-108">\<listeners></span></span>  
<span data-ttu-id="177b1-109">\<clear></span><span class="sxs-lookup"><span data-stu-id="177b1-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="177b1-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="177b1-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="177b1-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="177b1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="177b1-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="177b1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="177b1-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="177b1-113">Attributes</span></span>  
 <span data-ttu-id="177b1-114">Keine</span><span class="sxs-lookup"><span data-stu-id="177b1-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="177b1-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="177b1-115">Child Elements</span></span>  
 <span data-ttu-id="177b1-116">Keine</span><span class="sxs-lookup"><span data-stu-id="177b1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="177b1-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="177b1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="177b1-118">Element</span><span class="sxs-lookup"><span data-stu-id="177b1-118">Element</span></span>|<span data-ttu-id="177b1-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="177b1-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="177b1-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="177b1-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="177b1-121">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="177b1-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="177b1-122">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="177b1-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="177b1-123">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="177b1-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="177b1-124">Gibt die Listener, die sammeln, speichern und Weiterleiten von Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="177b1-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="177b1-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="177b1-125">Remarks</span></span>  
 <span data-ttu-id="177b1-126">Die `<clear>` -Element entfernt alle Listener aus der `Listeners` Sammlung für eine Ablaufverfolgungsquelle, einschließlich der <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="177b1-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="177b1-127">Können Sie die `<clear>` Element vor der Verwendung der `<add>` Element, stellen Sie sicher, dass keine anderen aktiven Listener in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="177b1-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="177b1-128">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="177b1-128">Configuration File</span></span>  
 <span data-ttu-id="177b1-129">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="177b1-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="177b1-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="177b1-130">Example</span></span>  
 <span data-ttu-id="177b1-131">Das folgende Beispiel zeigt, wie Sie mit der `<clear>` Element vor der Verwendung der `<add>` Elemente, die Listener hinzugefügt werden `console` und `textListener` auf die `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="177b1-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="177b1-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="177b1-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="177b1-133">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="177b1-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="177b1-134">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="177b1-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
