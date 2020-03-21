---
title: <clear>Element <listeners> für für<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153541"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="749ea-102">\<klares> \<Element für \<Hörer> für Trace-></span><span class="sxs-lookup"><span data-stu-id="749ea-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="749ea-103">Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="749ea-103">Clears the `Listeners` collection for trace.</span></span>  

<span data-ttu-id="749ea-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="749ea-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="749ea-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="749ea-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="749ea-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Spur>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="749ea-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="749ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Hörer>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="749ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="749ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<klare>**</span><span class="sxs-lookup"><span data-stu-id="749ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="749ea-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="749ea-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="749ea-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="749ea-110">Attributes and Elements</span></span>  
 <span data-ttu-id="749ea-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="749ea-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="749ea-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="749ea-112">Attributes</span></span>  
 <span data-ttu-id="749ea-113">Keine.</span><span class="sxs-lookup"><span data-stu-id="749ea-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="749ea-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="749ea-114">Child Elements</span></span>  
 <span data-ttu-id="749ea-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="749ea-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="749ea-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="749ea-116">Parent Elements</span></span>  
  
|<span data-ttu-id="749ea-117">Element</span><span class="sxs-lookup"><span data-stu-id="749ea-117">Element</span></span>|<span data-ttu-id="749ea-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="749ea-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="749ea-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="749ea-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="749ea-120">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="749ea-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="749ea-121">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="749ea-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="749ea-122">Enthält Listener, die Nachrichten sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="749ea-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="749ea-123">Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="749ea-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="749ea-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="749ea-124">Remarks</span></span>  
 <span data-ttu-id="749ea-125">Das `<clear>` Element entfernt alle `Listeners` Listener aus der Auflistung für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="749ea-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="749ea-126">Sie können `<clear>` das Element `<add>` verwenden, bevor Sie das Element verwenden, um sicher zu sein, dass sich keine anderen aktiven Listener in der Auflistung befinden.</span><span class="sxs-lookup"><span data-stu-id="749ea-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="749ea-127">Sie können `Listeners` die Auflistung programmgesteuert <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> löschen, <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> indem`System.Diagnostics.Trace.Listeners.Clear()`Sie die Methode für die Eigenschaft ( ) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="749ea-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="749ea-128">Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="749ea-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="749ea-129">Das `<clear>` Element entfernt <xref:System.Diagnostics.DefaultTraceListener> die `Listeners` aus der Auflistung, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>wodurch <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>das <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> Verhalten der , <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, und Methoden geändert wird.</span><span class="sxs-lookup"><span data-stu-id="749ea-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="749ea-130">Das `Assert` Aufrufen `Fail` einer oder Methode führt normalerweise zur Anzeige eines Meldungsfelds.</span><span class="sxs-lookup"><span data-stu-id="749ea-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="749ea-131">Das Meldungsfeld wird jedoch <xref:System.Diagnostics.DefaultTraceListener> nicht angezeigt, `Listeners` wenn sich der nicht in der Auflistung befindet.</span><span class="sxs-lookup"><span data-stu-id="749ea-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="749ea-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="749ea-132">Example</span></span>  
 <span data-ttu-id="749ea-133">Das folgende Beispiel zeigt, `<clear>` wie sie `<add>` das Element verwenden, bevor Sie das Element verwenden, um den Listener `console` zur `Listeners` Auflistung für die Ablaufverfolgung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="749ea-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="749ea-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="749ea-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="749ea-135">Ablaufverfolgungs- und Debugeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="749ea-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="749ea-136">\<entfernen sie></span><span class="sxs-lookup"><span data-stu-id="749ea-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="749ea-137">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="749ea-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
