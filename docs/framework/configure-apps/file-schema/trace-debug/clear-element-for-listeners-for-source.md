---
title: <clear> Element für <listeners> für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 4567f236397435e89371ca4c80730ff964fddd21
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088932"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="55e13-102">\<> Element für \<Listener > für \<Quelle löschen ></span><span class="sxs-lookup"><span data-stu-id="55e13-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="55e13-103">Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="55e13-103">Clears the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="55e13-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="55e13-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="55e13-105">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="55e13-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="55e13-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Quellen**](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="55e13-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="55e13-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**Quelle**](source-element.md) ></span><span class="sxs-lookup"><span data-stu-id="55e13-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="55e13-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](listeners-element-for-source.md) Listener ></span><span class="sxs-lookup"><span data-stu-id="55e13-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="55e13-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<löschen** ></span><span class="sxs-lookup"><span data-stu-id="55e13-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="55e13-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="55e13-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55e13-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="55e13-111">Attributes and Elements</span></span>  
 <span data-ttu-id="55e13-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="55e13-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55e13-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="55e13-113">Attributes</span></span>  
 <span data-ttu-id="55e13-114">Keine</span><span class="sxs-lookup"><span data-stu-id="55e13-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="55e13-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55e13-115">Child Elements</span></span>  
 <span data-ttu-id="55e13-116">Keine</span><span class="sxs-lookup"><span data-stu-id="55e13-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55e13-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55e13-117">Parent Elements</span></span>  
  
|<span data-ttu-id="55e13-118">Element</span><span class="sxs-lookup"><span data-stu-id="55e13-118">Element</span></span>|<span data-ttu-id="55e13-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55e13-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="55e13-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="55e13-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="55e13-121">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="55e13-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="55e13-122">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="55e13-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="55e13-123">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="55e13-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="55e13-124">Gibt Listener an, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="55e13-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55e13-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55e13-125">Remarks</span></span>  
 <span data-ttu-id="55e13-126">Das `<clear>`-Element entfernt alle Listener aus der `Listeners` Auflistung für eine Ablauf Verfolgungs Quelle, einschließlich des <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="55e13-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="55e13-127">Sie können das `<clear>`-Element verwenden, bevor Sie das `<add>`-Element verwenden, um sicher zu sein, dass keine anderen aktiven Listener in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="55e13-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="55e13-128">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="55e13-128">Configuration File</span></span>  
 <span data-ttu-id="55e13-129">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="55e13-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55e13-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55e13-130">Example</span></span>  
 <span data-ttu-id="55e13-131">Im folgenden Beispiel wird gezeigt, wie das `<clear>`-Element verwendet wird, bevor die `<add>` Elemente verwendet werden, um die Listener `console` und `textListener` der `Listeners` Auflistung für die Ablauf Verfolgungs Quelle `TraceSourceApp`hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="55e13-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="55e13-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55e13-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="55e13-133">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="55e13-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="55e13-134">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="55e13-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
