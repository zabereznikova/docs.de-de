---
title: <clear> Element für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 049b8e7ed17633c0f34b062915afaf719927dad6
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088915"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="a868a-102">\<> Element für \<Listener > für \<Ablauf Verfolgung löschen ></span><span class="sxs-lookup"><span data-stu-id="a868a-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="a868a-103">Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="a868a-103">Clears the `Listeners` collection for trace.</span></span>  

<span data-ttu-id="a868a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a868a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a868a-105">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="a868a-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="a868a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Ablauf Verfolgungs**](trace-element.md) ></span><span class="sxs-lookup"><span data-stu-id="a868a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="a868a-107">&nbsp;&nbsp;&nbsp;&nbsp;[ \**&nbsp;&nbsp;\<Listener >\** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="a868a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\</span></span>
<span data-ttu-id="a868a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Löschen >**</span><span class="sxs-lookup"><span data-stu-id="a868a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a868a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a868a-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a868a-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a868a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a868a-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a868a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a868a-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a868a-112">Attributes</span></span>  
 <span data-ttu-id="a868a-113">Keine</span><span class="sxs-lookup"><span data-stu-id="a868a-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a868a-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a868a-114">Child Elements</span></span>  
 <span data-ttu-id="a868a-115">Keine</span><span class="sxs-lookup"><span data-stu-id="a868a-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a868a-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a868a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a868a-117">Element</span><span class="sxs-lookup"><span data-stu-id="a868a-117">Element</span></span>|<span data-ttu-id="a868a-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a868a-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a868a-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a868a-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a868a-120">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a868a-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="a868a-121">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="a868a-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="a868a-122">Enthält Listener, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="a868a-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="a868a-123">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="a868a-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a868a-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a868a-124">Remarks</span></span>  
 <span data-ttu-id="a868a-125">Das `<clear>`-Element entfernt alle Listener aus der `Listeners` Auflistung für die Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="a868a-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="a868a-126">Sie können das `<clear>`-Element verwenden, bevor Sie das `<add>`-Element verwenden, um sicher zu sein, dass keine anderen aktiven Listener in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a868a-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="a868a-127">Sie können die `Listeners` Auflistung Programm gesteuert löschen, indem Sie die <xref:System.Diagnostics.TraceListenerCollection.Clear%2A>-Methode für die <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>-Eigenschaft (`System.Diagnostics.Trace.Listeners.Clear()`) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a868a-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="a868a-128">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a868a-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a868a-129">Das `<clear>`-Element entfernt die <xref:System.Diagnostics.DefaultTraceListener> aus der `Listeners`-Auflistung und ändert das Verhalten der Methoden <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>und <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a868a-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="a868a-130">Wenn Sie eine `Assert` oder `Fail` Methode aufrufen, wird normalerweise eine Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a868a-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="a868a-131">Das Meldungs Feld wird jedoch nicht angezeigt, wenn die <xref:System.Diagnostics.DefaultTraceListener> nicht in der `Listeners` Auflistung aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="a868a-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a868a-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a868a-132">Example</span></span>  
 <span data-ttu-id="a868a-133">Im folgenden Beispiel wird gezeigt, wie das `<clear>`-Element verwendet wird, bevor das `<add>`-Element verwendet wird, um der `Listeners` Auflistung für die Ablauf Verfolgung den Listener `console` hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a868a-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a868a-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a868a-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="a868a-135">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a868a-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a868a-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="a868a-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="a868a-137">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="a868a-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
