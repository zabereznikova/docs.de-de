---
title: <remove>-Element <listeners> für für<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 0c5c9efb8a22d26ea5d4467f9628af5935d6dbad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920478"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="c129c-102">\<Entfernen Sie > Element \<für Listener > \<für die Ablauf Verfolgung ></span><span class="sxs-lookup"><span data-stu-id="c129c-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="c129c-103">Entfernt einen Listener aus der listenerauflistung.</span><span class="sxs-lookup"><span data-stu-id="c129c-103">Removes a listener from the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="c129c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c129c-104">\<configuration></span></span>  
<span data-ttu-id="c129c-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="c129c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="c129c-106">\<Ablauf Verfolgungs ></span><span class="sxs-lookup"><span data-stu-id="c129c-106">\<trace></span></span>  
<span data-ttu-id="c129c-107">\<Listener ></span><span class="sxs-lookup"><span data-stu-id="c129c-107">\<listeners></span></span>  
<span data-ttu-id="c129c-108">\<remove></span><span class="sxs-lookup"><span data-stu-id="c129c-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c129c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c129c-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c129c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c129c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c129c-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c129c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c129c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c129c-112">Attributes</span></span>  
  
|<span data-ttu-id="c129c-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="c129c-113">Attribute</span></span>|<span data-ttu-id="c129c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c129c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c129c-115">**name**</span><span class="sxs-lookup"><span data-stu-id="c129c-115">**name**</span></span>|<span data-ttu-id="c129c-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="c129c-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="c129c-117">Der Name des Listener, der aus der listenerauflistung entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c129c-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c129c-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c129c-118">Child Elements</span></span>  
 <span data-ttu-id="c129c-119">Keine</span><span class="sxs-lookup"><span data-stu-id="c129c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c129c-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c129c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c129c-121">Element</span><span class="sxs-lookup"><span data-stu-id="c129c-121">Element</span></span>|<span data-ttu-id="c129c-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c129c-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c129c-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c129c-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="c129c-124">Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="c129c-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="c129c-125">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="c129c-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c129c-126">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c129c-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="c129c-127">Konfiguriert den ASP.net-Ablauf Verfolgungs Dienst.</span><span class="sxs-lookup"><span data-stu-id="c129c-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c129c-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c129c-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c129c-129">`Listeners` <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>Wenn Sie ausderAuflistungentfernen,ändertsichdasVerhaltenderMethoden,,und.<xref:System.Diagnostics.DefaultTraceListener></span><span class="sxs-lookup"><span data-stu-id="c129c-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="c129c-130">Wenn Sie `Assert` eine `Fail` -oder-Methode aufrufen, <xref:System.Diagnostics.DefaultTraceListener> wird normalerweise die Anzeige eines Meldungs Felds angezeigt, das Meldungs Feld wird jedoch nicht `Listeners` angezeigt, wenn sich nicht in der Auflistung befindet.</span><span class="sxs-lookup"><span data-stu-id="c129c-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c129c-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c129c-131">Example</span></span>  
 <span data-ttu-id="c129c-132">Im folgenden Beispiel wird gezeigt, wie der Standardablaufverfolgungslistener aus der Auflistung der ablaufverfol</span><span class="sxs-lookup"><span data-stu-id="c129c-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c129c-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c129c-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="c129c-134">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c129c-134">Trace and Debug Settings Schema</span></span>](index.md)
