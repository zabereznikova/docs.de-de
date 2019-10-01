---
title: <clear>-Element für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 0361580724351f8f42d058d5e20354e3335bac2f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699380"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="90739-102">\<clear >-Element für \<listener > für \<trace ></span><span class="sxs-lookup"><span data-stu-id="90739-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="90739-103">Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="90739-103">Clears the `Listeners` collection for trace.</span></span>  
  
[<span data-ttu-id="90739-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="90739-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="90739-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="90739-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="90739-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="90739-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="90739-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listener >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="90739-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="90739-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="90739-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90739-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="90739-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90739-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="90739-110">Attributes and Elements</span></span>  
 <span data-ttu-id="90739-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90739-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90739-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="90739-112">Attributes</span></span>  
 <span data-ttu-id="90739-113">Keine</span><span class="sxs-lookup"><span data-stu-id="90739-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="90739-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90739-114">Child Elements</span></span>  
 <span data-ttu-id="90739-115">Keine</span><span class="sxs-lookup"><span data-stu-id="90739-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90739-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90739-116">Parent Elements</span></span>  
  
|<span data-ttu-id="90739-117">Element</span><span class="sxs-lookup"><span data-stu-id="90739-117">Element</span></span>|<span data-ttu-id="90739-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90739-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="90739-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="90739-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="90739-120">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="90739-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="90739-121">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="90739-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="90739-122">Enthält Listener, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="90739-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="90739-123">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="90739-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90739-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90739-124">Remarks</span></span>  
 <span data-ttu-id="90739-125">Das `<clear>`-Element entfernt alle Listener aus der `Listeners`-Sammlung für die Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="90739-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="90739-126">Sie können das `<clear>`-Element verwenden, bevor Sie das `<add>`-Element verwenden, um sicherzustellen, dass keine anderen aktiven Listener in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90739-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="90739-127">Sie können die `Listeners`-Auflistung Programm gesteuert löschen, indem Sie die <xref:System.Diagnostics.TraceListenerCollection.Clear%2A>-Methode für die <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>-Eigenschaft (`System.Diagnostics.Trace.Listeners.Clear()`) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="90739-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="90739-128">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="90739-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90739-129">Das `<clear>`-Element entfernt das <xref:System.Diagnostics.DefaultTraceListener> aus der `Listeners`-Auflistung und ändert das Verhalten der <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>-, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>-und <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="90739-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="90739-130">Das Aufrufen einer `Assert`-oder `Fail`-Methode führt normalerweise dazu, dass ein Meldungs Feld angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="90739-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="90739-131">Das Meldungs Feld wird jedoch nicht angezeigt, wenn die <xref:System.Diagnostics.DefaultTraceListener> nicht in der `Listeners`-Auflistung aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="90739-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90739-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90739-132">Example</span></span>  
 <span data-ttu-id="90739-133">Im folgenden Beispiel wird gezeigt, wie das `<clear>`-Element verwendet wird, bevor das `<add>`-Element verwendet wird, um der `Listeners`-Auflistung für die Ablauf Verfolgung den Listener `console` hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="90739-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="90739-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90739-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="90739-135">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="90739-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="90739-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="90739-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="90739-137">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="90739-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
