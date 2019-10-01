---
title: <clear>-Element für <listeners> für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 05c20040ef59f4dee6b15bbe0b0369281b532754
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697184"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="bba00-102">\<clear >-Element für \<listener > für \<source-></span><span class="sxs-lookup"><span data-stu-id="bba00-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="bba00-103">Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="bba00-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="bba00-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="bba00-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="bba00-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="bba00-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="bba00-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="bba00-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="bba00-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="bba00-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="bba00-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listener >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="bba00-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="bba00-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="bba00-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bba00-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="bba00-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bba00-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bba00-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bba00-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bba00-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bba00-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="bba00-113">Attributes</span></span>  
 <span data-ttu-id="bba00-114">Keine</span><span class="sxs-lookup"><span data-stu-id="bba00-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bba00-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bba00-115">Child Elements</span></span>  
 <span data-ttu-id="bba00-116">Keine</span><span class="sxs-lookup"><span data-stu-id="bba00-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bba00-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bba00-117">Parent Elements</span></span>  
  
|<span data-ttu-id="bba00-118">Element</span><span class="sxs-lookup"><span data-stu-id="bba00-118">Element</span></span>|<span data-ttu-id="bba00-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bba00-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bba00-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="bba00-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="bba00-121">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bba00-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="bba00-122">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="bba00-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="bba00-123">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="bba00-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="bba00-124">Gibt Listener an, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="bba00-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bba00-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bba00-125">Remarks</span></span>  
 <span data-ttu-id="bba00-126">Das `<clear>`-Element entfernt alle Listener aus der `Listeners`-Auflistung für eine Ablauf Verfolgungs Quelle, einschließlich der <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="bba00-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="bba00-127">Sie können das `<clear>`-Element verwenden, bevor Sie das `<add>`-Element verwenden, um sicherzustellen, dass keine anderen aktiven Listener in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="bba00-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="bba00-128">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="bba00-128">Configuration File</span></span>  
 <span data-ttu-id="bba00-129">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bba00-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bba00-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bba00-130">Example</span></span>  
 <span data-ttu-id="bba00-131">Im folgenden Beispiel wird gezeigt, wie das `<clear>`-Element verwendet wird, bevor die `<add>`-Elemente verwendet werden, um die Listener `console` und `textListener` der `Listeners`-Sammlung für die Ablauf Verfolgungs Quelle `TraceSourceApp` hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bba00-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bba00-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bba00-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="bba00-133">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="bba00-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bba00-134">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="bba00-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
