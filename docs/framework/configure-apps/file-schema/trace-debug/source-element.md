---
title: '&lt;Quelle&gt; Element'
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b7c2a71b129a0ad7d1c2a72b18b8a69a111f9495
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752571"
---
# <a name="ltsourcegt-element"></a><span data-ttu-id="bb3bb-102">&lt;Quelle&gt; Element</span><span class="sxs-lookup"><span data-stu-id="bb3bb-102">&lt;source&gt; Element</span></span>
<span data-ttu-id="bb3bb-103">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-103">Specifies a trace source that initiates tracing messages.</span></span>  
  
 <span data-ttu-id="bb3bb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bb3bb-104">\<configuration></span></span>  
<span data-ttu-id="bb3bb-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="bb3bb-105">\<system.diagnostics></span></span>  
<span data-ttu-id="bb3bb-106">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="bb3bb-106">\<sources></span></span>  
<span data-ttu-id="bb3bb-107">\<Quelle ></span><span class="sxs-lookup"><span data-stu-id="bb3bb-107">\<source></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb3bb-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb3bb-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb3bb-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bb3bb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bb3bb-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb3bb-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="bb3bb-111">Attributes</span></span>  
  
|<span data-ttu-id="bb3bb-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="bb3bb-112">Attribute</span></span>|<span data-ttu-id="bb3bb-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb3bb-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="bb3bb-114">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bb3bb-115">Gibt den Namen der Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="bb3bb-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bb3bb-117">Gibt den Namen der Instanz ein Trace-Schalter in der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="bb3bb-118">Wenn der Schalter nicht, in identifiziert wurde einem `<switches>` Element, der Wert gibt die Ebene für den Switch.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="bb3bb-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bb3bb-120">Gibt den Typ der Trace-Schalter.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="bb3bb-121">Falls vorhanden, wird der Typ muss ein gültiger Klassenname sein und darf keine leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="bb3bb-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bb3bb-123">Gibt den Wert für ein Trace-datenquellenspezifische-Attribut identifiziert, indem die <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> Methode für die Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb3bb-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb3bb-124">Child Elements</span></span>  
  
|<span data-ttu-id="bb3bb-125">Element</span><span class="sxs-lookup"><span data-stu-id="bb3bb-125">Element</span></span>|<span data-ttu-id="bb3bb-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb3bb-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb3bb-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="bb3bb-127">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|<span data-ttu-id="bb3bb-128">Enthält die Listener, mit die sammeln, speichern und Weiterleiten von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb3bb-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb3bb-129">Parent Elements</span></span>  
  
|<span data-ttu-id="bb3bb-130">Element</span><span class="sxs-lookup"><span data-stu-id="bb3bb-130">Element</span></span>|<span data-ttu-id="bb3bb-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb3bb-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bb3bb-132">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="bb3bb-133">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="bb3bb-134">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb3bb-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb3bb-135">Remarks</span></span>  
 <span data-ttu-id="bb3bb-136">Dieses Element kann in der Computerkonfigurationsdatei ("Machine.config") und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb3bb-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb3bb-137">Example</span></span>  
 <span data-ttu-id="bb3bb-138">Das folgende Beispiel zeigt, wie Sie die `<source>` Elemente für die Ablaufverfolgungsquelle `mySource` und zum Festlegen der Ebene für den Quellschalter mit dem Namen `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="bb3bb-139">Ein Konsolen-Ablaufverfolgungslistener hinzugefügt wird, die Ablaufverfolgungsinformationen in die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="bb3bb-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb3bb-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb3bb-140">See Also</span></span>  
 [<span data-ttu-id="bb3bb-141">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="bb3bb-141">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="bb3bb-142">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="bb3bb-142">Trace Switches</span></span>](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
