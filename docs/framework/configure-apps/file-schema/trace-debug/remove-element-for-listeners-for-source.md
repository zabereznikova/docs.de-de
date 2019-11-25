---
title: <remove> Element für <listeners> für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 75db45d4e868ce88e030ec6a43c8bdaf788a1102
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088853"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="00e21-102">\<> Element für \<Listener > für \<Quelle entfernen ></span><span class="sxs-lookup"><span data-stu-id="00e21-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="00e21-103">Entfernt einen Listener aus der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="00e21-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="00e21-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00e21-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00e21-105">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="00e21-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="00e21-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Quellen**](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="00e21-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="00e21-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**Quelle**](source-element.md) ></span><span class="sxs-lookup"><span data-stu-id="00e21-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="00e21-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](listeners-element-for-source.md) Listener ></span><span class="sxs-lookup"><span data-stu-id="00e21-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="00e21-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**</span><span class="sxs-lookup"><span data-stu-id="00e21-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="00e21-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="00e21-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00e21-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="00e21-111">Attributes and Elements</span></span>  
 <span data-ttu-id="00e21-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00e21-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00e21-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="00e21-113">Attributes</span></span>  
  
|<span data-ttu-id="00e21-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="00e21-114">Attribute</span></span>|<span data-ttu-id="00e21-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00e21-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="00e21-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="00e21-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="00e21-117">Der Name des Listener, der aus der `Listeners` Auflistung entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="00e21-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00e21-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00e21-118">Child Elements</span></span>  
 <span data-ttu-id="00e21-119">Keine</span><span class="sxs-lookup"><span data-stu-id="00e21-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00e21-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00e21-120">Parent Elements</span></span>  
  
|<span data-ttu-id="00e21-121">Element</span><span class="sxs-lookup"><span data-stu-id="00e21-121">Element</span></span>|<span data-ttu-id="00e21-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00e21-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="00e21-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="00e21-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="00e21-124">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="00e21-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="00e21-125">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="00e21-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="00e21-126">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="00e21-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="00e21-127">Gibt Listener an, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="00e21-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00e21-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00e21-128">Remarks</span></span>  
 <span data-ttu-id="00e21-129">Das `<remove>`-Element entfernt einen angegebenen Listener aus der `Listeners` Auflistung für eine Ablauf Verfolgungs Quelle.</span><span class="sxs-lookup"><span data-stu-id="00e21-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="00e21-130">Sie können ein Element aus der `Listeners` Auflistung für eine Ablauf Verfolgungs Quelle Programm gesteuert entfernen, indem Sie die <xref:System.Diagnostics.TraceListenerCollection.Remove%2A>-Methode für die <xref:System.Diagnostics.TraceSource.Listeners%2A>-Eigenschaft der <xref:System.Diagnostics.TraceSource> Instanz aufrufen.</span><span class="sxs-lookup"><span data-stu-id="00e21-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="00e21-131">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00e21-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00e21-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00e21-132">Example</span></span>  
 <span data-ttu-id="00e21-133">Im folgenden Beispiel wird gezeigt, wie das `<remove>`-Element verwendet wird, bevor das `<add>`-Element verwendet wird, um der `Listeners` Auflistung für die Ablauf Verfolgungs Quelle `TraceSourceApp`den Listener`console` hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="00e21-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="00e21-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00e21-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="00e21-135">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="00e21-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="00e21-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="00e21-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="00e21-137">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="00e21-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
