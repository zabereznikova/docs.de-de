---
title: <remove> -Element für <listeners> für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 53ba773ea1cb31955e59c1f57e1c0cc807227402
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173872"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="138d4-102">\<remove> -Element für \<listeners> für \<source></span><span class="sxs-lookup"><span data-stu-id="138d4-102">\<remove> Element for \<listeners> for \<source></span></span>

<span data-ttu-id="138d4-103">Entfernt einen Listener aus der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="138d4-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="138d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="138d4-104">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="138d4-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="138d4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="138d4-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="138d4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="138d4-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="138d4-107">Attributes</span></span>  
  
|<span data-ttu-id="138d4-108">attribute</span><span class="sxs-lookup"><span data-stu-id="138d4-108">Attribute</span></span>|<span data-ttu-id="138d4-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="138d4-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="138d4-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="138d4-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="138d4-111">Der Name des Listener, der aus der Auflistung entfernt werden soll `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="138d4-111">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="138d4-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="138d4-112">Child Elements</span></span>  

 <span data-ttu-id="138d4-113">Keine</span><span class="sxs-lookup"><span data-stu-id="138d4-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="138d4-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="138d4-114">Parent Elements</span></span>  
  
|<span data-ttu-id="138d4-115">Element</span><span class="sxs-lookup"><span data-stu-id="138d4-115">Element</span></span>|<span data-ttu-id="138d4-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="138d4-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="138d4-117">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="138d4-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="138d4-118">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="138d4-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="138d4-119">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="138d4-119">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="138d4-120">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="138d4-120">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="138d4-121">Gibt Listener an, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="138d4-121">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="138d4-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="138d4-122">Remarks</span></span>  

 <span data-ttu-id="138d4-123">Das- `<remove>` Element entfernt einen angegebenen Listener aus der-Auflistung `Listeners` für eine Ablauf Verfolgungs Quelle.</span><span class="sxs-lookup"><span data-stu-id="138d4-123">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="138d4-124">Sie können ein Element aus der-Auflistung `Listeners` für eine Ablauf Verfolgungs Quelle Programm gesteuert entfernen, indem Sie die- <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> Methode für die- <xref:System.Diagnostics.TraceSource.Listeners%2A> Eigenschaft der-Instanz aufrufen <xref:System.Diagnostics.TraceSource> .</span><span class="sxs-lookup"><span data-stu-id="138d4-124">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="138d4-125">Dieses Element kann in der Computer Konfigurationsdatei (Machine.config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="138d4-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="138d4-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="138d4-126">Example</span></span>  

 <span data-ttu-id="138d4-127">Im folgenden Beispiel wird gezeigt, wie das-Element verwendet wird, bevor das-Element verwendet wird, um der-Auflistung `<remove>` `<add>` `console` `Listeners` für die Ablauf Verfolgungs Quelle den Listener hinzuzufügen `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="138d4-127">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="138d4-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="138d4-128">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="138d4-129">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="138d4-129">Trace and Debug Settings Schema</span></span>](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="138d4-130">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="138d4-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
