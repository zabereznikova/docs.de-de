---
title: <clear>Element <listeners> für für<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 7f9ddd93d27c3619119702c82c9e8752dab1af7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153580"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="af9cf-102">\<clear> \<Element für \<Listener> für Quell-></span><span class="sxs-lookup"><span data-stu-id="af9cf-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="af9cf-103">Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="af9cf-103">Clears the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="af9cf-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="af9cf-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="af9cf-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="af9cf-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="af9cf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Quellen>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="af9cf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="af9cf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Quelle>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="af9cf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="af9cf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Hörer>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="af9cf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="af9cf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<klare>**</span><span class="sxs-lookup"><span data-stu-id="af9cf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="af9cf-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="af9cf-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af9cf-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="af9cf-111">Attributes and Elements</span></span>  
 <span data-ttu-id="af9cf-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="af9cf-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af9cf-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="af9cf-113">Attributes</span></span>  
 <span data-ttu-id="af9cf-114">Keine.</span><span class="sxs-lookup"><span data-stu-id="af9cf-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="af9cf-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af9cf-115">Child Elements</span></span>  
 <span data-ttu-id="af9cf-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="af9cf-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af9cf-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af9cf-117">Parent Elements</span></span>  
  
|<span data-ttu-id="af9cf-118">Element</span><span class="sxs-lookup"><span data-stu-id="af9cf-118">Element</span></span>|<span data-ttu-id="af9cf-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af9cf-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="af9cf-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="af9cf-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="af9cf-121">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="af9cf-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="af9cf-122">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="af9cf-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="af9cf-123">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="af9cf-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="af9cf-124">Gibt Listener an, die Nachrichten sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="af9cf-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af9cf-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="af9cf-125">Remarks</span></span>  
 <span data-ttu-id="af9cf-126">Das `<clear>` Element entfernt alle `Listeners` Listener aus der Auflistung <xref:System.Diagnostics.DefaultTraceListener>für eine Ablaufverfolgungsquelle, einschließlich der .</span><span class="sxs-lookup"><span data-stu-id="af9cf-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="af9cf-127">Sie können `<clear>` das Element `<add>` verwenden, bevor Sie das Element verwenden, um sicher zu sein, dass sich keine anderen aktiven Listener in der Auflistung befinden.</span><span class="sxs-lookup"><span data-stu-id="af9cf-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="af9cf-128">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="af9cf-128">Configuration File</span></span>  
 <span data-ttu-id="af9cf-129">Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="af9cf-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af9cf-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af9cf-130">Example</span></span>  
 <span data-ttu-id="af9cf-131">Das folgende Beispiel zeigt, `<clear>` wie Sie `<add>` das Element `console` verwenden, bevor Sie die Elemente zum Hinzufügen der Listener und `textListener` zur `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`verwenden.</span><span class="sxs-lookup"><span data-stu-id="af9cf-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="af9cf-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af9cf-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="af9cf-133">Ablaufverfolgungs- und Debugeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="af9cf-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="af9cf-134">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="af9cf-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
