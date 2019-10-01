---
title: <remove>-Element für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 56d1e56514aed98d5f3b9f7363e461af6ac68a8c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697216"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="61a46-102">\<remove >-Element für \<listener > für \<trace ></span><span class="sxs-lookup"><span data-stu-id="61a46-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="61a46-103">Entfernt einen Listener aus der **listenerauflistung** .</span><span class="sxs-lookup"><span data-stu-id="61a46-103">Removes a listener from the **Listeners** collection.</span></span>  
  
[<span data-ttu-id="61a46-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="61a46-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="61a46-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="61a46-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="61a46-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="61a46-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="61a46-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listener >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="61a46-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="61a46-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="61a46-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61a46-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="61a46-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61a46-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="61a46-110">Attributes and Elements</span></span>  
 <span data-ttu-id="61a46-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="61a46-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61a46-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="61a46-112">Attributes</span></span>  
  
|<span data-ttu-id="61a46-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="61a46-113">Attribute</span></span>|<span data-ttu-id="61a46-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61a46-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61a46-115">**name**</span><span class="sxs-lookup"><span data-stu-id="61a46-115">**name**</span></span>|<span data-ttu-id="61a46-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="61a46-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="61a46-117">Der Name des Listener, der aus der **listenerauflistung** entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="61a46-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61a46-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61a46-118">Child Elements</span></span>  
 <span data-ttu-id="61a46-119">Keine</span><span class="sxs-lookup"><span data-stu-id="61a46-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61a46-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61a46-120">Parent Elements</span></span>  
  
|<span data-ttu-id="61a46-121">Element</span><span class="sxs-lookup"><span data-stu-id="61a46-121">Element</span></span>|<span data-ttu-id="61a46-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61a46-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="61a46-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="61a46-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="61a46-124">Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="61a46-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="61a46-125">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="61a46-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="61a46-126">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="61a46-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="61a46-127">Konfiguriert den ASP.net-Ablauf Verfolgungs Dienst.</span><span class="sxs-lookup"><span data-stu-id="61a46-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61a46-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="61a46-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="61a46-129">Wenn Sie die <xref:System.Diagnostics.DefaultTraceListener> aus der `Listeners`-Auflistung entfernen, ändert sich das Verhalten der Methoden <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> und <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="61a46-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="61a46-130">Das Aufrufen einer `Assert`-oder `Fail`-Methode führt normalerweise dazu, dass ein Meldungs Feld angezeigt wird. das Meldungs Feld wird jedoch nicht angezeigt, wenn die <xref:System.Diagnostics.DefaultTraceListener> nicht in der `Listeners`-Auflistung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="61a46-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61a46-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61a46-131">Example</span></span>  
 <span data-ttu-id="61a46-132">Im folgenden Beispiel wird gezeigt, wie der Standardablaufverfolgungslistener aus der Auflistung der ablaufverfol</span><span class="sxs-lookup"><span data-stu-id="61a46-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="61a46-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61a46-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="61a46-134">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="61a46-134">Trace and Debug Settings Schema</span></span>](index.md)
