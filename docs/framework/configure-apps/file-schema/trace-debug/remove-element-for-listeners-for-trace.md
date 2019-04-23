---
title: <remove> -Element für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: adf00394bc0bfe808836e74214003cd2078204e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164254"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="42017-102">\<Entfernen Sie >-Element für \<Listener > für \<Ablaufverfolgung ></span><span class="sxs-lookup"><span data-stu-id="42017-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="42017-103">Entfernt einen Listener aus der **Listener** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="42017-103">Removes a listener from the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="42017-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="42017-104">\<configuration></span></span>  
<span data-ttu-id="42017-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="42017-105">\<system.diagnostics></span></span>  
<span data-ttu-id="42017-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="42017-106">\<trace></span></span>  
<span data-ttu-id="42017-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="42017-107">\<listeners></span></span>  
<span data-ttu-id="42017-108">\<remove></span><span class="sxs-lookup"><span data-stu-id="42017-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42017-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="42017-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42017-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="42017-110">Attributes and Elements</span></span>  
 <span data-ttu-id="42017-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="42017-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42017-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="42017-112">Attributes</span></span>  
  
|<span data-ttu-id="42017-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="42017-113">Attribute</span></span>|<span data-ttu-id="42017-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42017-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42017-115">**name**</span><span class="sxs-lookup"><span data-stu-id="42017-115">**name**</span></span>|<span data-ttu-id="42017-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="42017-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="42017-117">Der Name des Listeners, Aufheben der **Listener** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="42017-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42017-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42017-118">Child Elements</span></span>  
 <span data-ttu-id="42017-119">Keine</span><span class="sxs-lookup"><span data-stu-id="42017-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42017-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42017-120">Parent Elements</span></span>  
  
|<span data-ttu-id="42017-121">Element</span><span class="sxs-lookup"><span data-stu-id="42017-121">Element</span></span>|<span data-ttu-id="42017-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42017-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="42017-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="42017-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="42017-124">Gibt an, einen Listener, der sammelt, speichert, und leitet Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="42017-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="42017-125">Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.</span><span class="sxs-lookup"><span data-stu-id="42017-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="42017-126">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="42017-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="42017-127">Konfiguriert den ASP.NET-Ablaufverfolgungsdienst.</span><span class="sxs-lookup"><span data-stu-id="42017-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42017-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42017-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42017-129">Entfernen der <xref:System.Diagnostics.DefaultTraceListener> aus der `Listeners` Auflistung ändert das Sitzungsverhalten, sodass die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, und <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> Methoden.</span><span class="sxs-lookup"><span data-stu-id="42017-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="42017-130">Aufrufen einer `Assert` oder `Fail` -Methode führt normalerweise in der Anzeige eines Meldungsfelds, aber das Feld nicht angezeigt wird der <xref:System.Diagnostics.DefaultTraceListener> befindet sich nicht in der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="42017-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42017-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="42017-131">Example</span></span>  
 <span data-ttu-id="42017-132">Das folgende Beispiel zeigt, wie Sie den standardmäßigen Ablaufverfolgungslistener aus der Ablaufverfolgung entfernen **Listener** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="42017-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="42017-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42017-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="42017-134">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="42017-134">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
