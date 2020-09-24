---
title: <clear> -Element für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 2d301d588e33b0eea4164a6bf62dedd7b0c450ec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149269"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="0f07c-102">\<clear> -Element für \<listeners> für \<trace></span><span class="sxs-lookup"><span data-stu-id="0f07c-102">\<clear> Element for \<listeners> for \<trace></span></span>

<span data-ttu-id="0f07c-103">Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="0f07c-103">Clears the `Listeners` collection for trace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="0f07c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f07c-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f07c-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0f07c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0f07c-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0f07c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f07c-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="0f07c-107">Attributes</span></span>  

 <span data-ttu-id="0f07c-108">Keine</span><span class="sxs-lookup"><span data-stu-id="0f07c-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0f07c-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0f07c-109">Child Elements</span></span>  

 <span data-ttu-id="0f07c-110">Keine</span><span class="sxs-lookup"><span data-stu-id="0f07c-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f07c-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0f07c-111">Parent Elements</span></span>  
  
|<span data-ttu-id="0f07c-112">Element</span><span class="sxs-lookup"><span data-stu-id="0f07c-112">Element</span></span>|<span data-ttu-id="0f07c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f07c-113">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0f07c-114">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0f07c-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="0f07c-115">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0f07c-115">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="0f07c-116">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="0f07c-116">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="0f07c-117">Enthält Listener, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="0f07c-117">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="0f07c-118">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="0f07c-118">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f07c-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0f07c-119">Remarks</span></span>  

 <span data-ttu-id="0f07c-120">Das- `<clear>` Element entfernt alle Listener aus der-Auflistung für die Ablauf `Listeners` Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="0f07c-120">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="0f07c-121">Sie können das- `<clear>` Element verwenden, bevor Sie das- `<add>` Element verwenden, um sicher zu sein, dass keine anderen aktiven Listener in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="0f07c-121">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="0f07c-122">Sie können die Auflistung Programm gesteuert löschen, `Listeners` indem Sie die- <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> Methode für die- <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> Eigenschaft ( `System.Diagnostics.Trace.Listeners.Clear()` ) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0f07c-122">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="0f07c-123">Dieses Element kann in der Computer Konfigurationsdatei (Machine.config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0f07c-123">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f07c-124">Das- `<clear>` Element entfernt das <xref:System.Diagnostics.DefaultTraceListener> -Element aus der-Auflistung `Listeners` und ändert das Verhalten der <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> Methoden,, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> und <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0f07c-124">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="0f07c-125">Wenn eine-Methode oder eine-Methode aufgerufen wird, wird `Assert` `Fail` normalerweise ein Meldungs Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f07c-125">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="0f07c-126">Das Meldungs Feld wird jedoch nicht angezeigt, wenn <xref:System.Diagnostics.DefaultTraceListener> sich nicht in der Auflistung befindet `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="0f07c-126">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f07c-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0f07c-127">Example</span></span>  

 <span data-ttu-id="0f07c-128">Das folgende Beispiel zeigt, wie das-Element verwendet wird, bevor das-Element verwendet wird, um der-Auflistung für die Ablauf `<clear>` `<add>` Verfolgung den Listener hinzuzufügen `console` `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="0f07c-128">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0f07c-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f07c-129">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="0f07c-130">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="0f07c-130">Trace and Debug Settings Schema</span></span>](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="0f07c-131">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="0f07c-131">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
