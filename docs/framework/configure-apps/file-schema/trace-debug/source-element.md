---
title: <source>-Element
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 8860f5d3ed7ee0c04d1e8afd7614f3f73b470808
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673705"
---
# <a name="source-element"></a><span data-ttu-id="0a72e-102">\<Quelle >-Element</span><span class="sxs-lookup"><span data-stu-id="0a72e-102">\<source> Element</span></span>
<span data-ttu-id="0a72e-103">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="0a72e-103">Specifies a trace source that initiates tracing messages.</span></span>  
  
 <span data-ttu-id="0a72e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0a72e-104">\<configuration></span></span>  
<span data-ttu-id="0a72e-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="0a72e-105">\<system.diagnostics></span></span>  
<span data-ttu-id="0a72e-106">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="0a72e-106">\<sources></span></span>  
<span data-ttu-id="0a72e-107">\<Quelle ></span><span class="sxs-lookup"><span data-stu-id="0a72e-107">\<source></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a72e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a72e-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a72e-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0a72e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0a72e-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a72e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a72e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="0a72e-111">Attributes</span></span>  
  
|<span data-ttu-id="0a72e-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="0a72e-112">Attribute</span></span>|<span data-ttu-id="0a72e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a72e-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="0a72e-114">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0a72e-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0a72e-115">Gibt den Namen der Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="0a72e-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="0a72e-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0a72e-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0a72e-117">Gibt den Namen einer Instanz der Trace-Schalter in der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="0a72e-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="0a72e-118">Wenn der Schalter nicht, in erkannt wird einem `<switches>` -Element wird der Wert gibt die Ebene für den Switch.</span><span class="sxs-lookup"><span data-stu-id="0a72e-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="0a72e-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0a72e-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0a72e-120">Gibt den Typ, der den Ablaufverfolgungsschalter.</span><span class="sxs-lookup"><span data-stu-id="0a72e-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="0a72e-121">Falls vorhanden, wird der Typ muss ein gültiger Klassenname sein und darf keine leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="0a72e-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="0a72e-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0a72e-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0a72e-123">Gibt den Wert für eine Ablaufverfolgung datenquellenspezifische Attributs, identifiziert durch den <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> Methode für die Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="0a72e-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a72e-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a72e-124">Child Elements</span></span>  
  
|<span data-ttu-id="0a72e-125">Element</span><span class="sxs-lookup"><span data-stu-id="0a72e-125">Element</span></span>|<span data-ttu-id="0a72e-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a72e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a72e-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="0a72e-127">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|<span data-ttu-id="0a72e-128">Enthält Listener, die sammeln, speichern und Weiterleiten von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="0a72e-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a72e-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a72e-129">Parent Elements</span></span>  
  
|<span data-ttu-id="0a72e-130">Element</span><span class="sxs-lookup"><span data-stu-id="0a72e-130">Element</span></span>|<span data-ttu-id="0a72e-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a72e-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0a72e-132">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0a72e-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="0a72e-133">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0a72e-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="0a72e-134">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="0a72e-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a72e-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0a72e-135">Remarks</span></span>  
 <span data-ttu-id="0a72e-136">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a72e-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a72e-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a72e-137">Example</span></span>  
 <span data-ttu-id="0a72e-138">Das folgende Beispiel zeigt, wie Sie mit der `<source>` Ablaufverfolgungsquelle hinzuzufügenden Elements `mySource` und legen Sie die Ebene für den Quellschalter namens `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="0a72e-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="0a72e-139">Dass, die Ablaufverfolgungsinformationen in die Konsole schreibt, wird ein Konsolen-Ablaufverfolgungslistener hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0a72e-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0a72e-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a72e-140">See also</span></span>

- [<span data-ttu-id="0a72e-141">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0a72e-141">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="0a72e-142">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="0a72e-142">Trace Switches</span></span>](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
