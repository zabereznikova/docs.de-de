---
title: <remove>-Element für <listeners> für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 4a11308278f755ec8271477352d91d8797d105c5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699488"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="b0b2d-102">\<remove >-Element für \<listener > für \<source ></span><span class="sxs-lookup"><span data-stu-id="b0b2d-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="b0b2d-103">Entfernt einen Listener aus der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="b0b2d-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="b0b2d-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b0b2d-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b0b2d-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="b0b2d-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="b0b2d-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="b0b2d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="b0b2d-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="b0b2d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="b0b2d-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listener >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="b0b2d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="b0b2d-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1remove >**</span><span class="sxs-lookup"><span data-stu-id="b0b2d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0b2d-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0b2d-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0b2d-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b0b2d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b0b2d-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0b2d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0b2d-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="b0b2d-113">Attributes</span></span>  
  
|<span data-ttu-id="b0b2d-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="b0b2d-114">Attribute</span></span>|<span data-ttu-id="b0b2d-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0b2d-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="b0b2d-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b0b2d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="b0b2d-117">Der Name des Listener, der aus der `Listeners`-Auflistung entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b0b2d-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0b2d-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0b2d-118">Child Elements</span></span>  
 <span data-ttu-id="b0b2d-119">Keine</span><span class="sxs-lookup"><span data-stu-id="b0b2d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0b2d-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0b2d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b0b2d-121">Element</span><span class="sxs-lookup"><span data-stu-id="b0b2d-121">Element</span></span>|<span data-ttu-id="b0b2d-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0b2d-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b0b2d-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b0b2d-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b0b2d-124">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b0b2d-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="b0b2d-125">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="b0b2d-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="b0b2d-126">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="b0b2d-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="b0b2d-127">Gibt Listener an, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="b0b2d-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0b2d-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0b2d-128">Remarks</span></span>  
 <span data-ttu-id="b0b2d-129">Das `<remove>`-Element entfernt einen angegebenen Listener aus der `Listeners`-Auflistung für eine Ablauf Verfolgungs Quelle.</span><span class="sxs-lookup"><span data-stu-id="b0b2d-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="b0b2d-130">Sie können ein Element aus der `Listeners`-Auflistung für eine Ablauf Verfolgungs Quelle Programm gesteuert entfernen, indem Sie die <xref:System.Diagnostics.TraceListenerCollection.Remove%2A>-Methode für die <xref:System.Diagnostics.TraceSource.Listeners%2A>-Eigenschaft der <xref:System.Diagnostics.TraceSource>-Instanz aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b0b2d-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="b0b2d-131">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0b2d-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0b2d-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0b2d-132">Example</span></span>  
 <span data-ttu-id="b0b2d-133">Im folgenden Beispiel wird gezeigt, wie das `<remove>`-Element verwendet wird, bevor das `<add>`-Element verwendet wird, um den Listener `console` der `Listeners`-Auflistung für die Ablauf Verfolgungs Quelle `TraceSourceApp` hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b0b2d-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="b0b2d-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0b2d-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="b0b2d-135">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b0b2d-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b0b2d-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="b0b2d-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="b0b2d-137">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="b0b2d-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
