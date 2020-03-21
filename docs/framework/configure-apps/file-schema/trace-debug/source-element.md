---
title: <source>-Element
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 417722ce2f3865350158413307495e3ab435d386
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153294"
---
# <a name="source-element"></a><span data-ttu-id="89b7f-102">\<Quelle> Element</span><span class="sxs-lookup"><span data-stu-id="89b7f-102">\<source> Element</span></span>
<span data-ttu-id="89b7f-103">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="89b7f-103">Specifies a trace source that initiates tracing messages.</span></span>  

<span data-ttu-id="89b7f-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="89b7f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="89b7f-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="89b7f-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="89b7f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Quellen>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="89b7f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="89b7f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Quelle>**</span><span class="sxs-lookup"><span data-stu-id="89b7f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**</span></span>

## <a name="syntax"></a><span data-ttu-id="89b7f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="89b7f-108">Syntax</span></span>  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89b7f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="89b7f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="89b7f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="89b7f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89b7f-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="89b7f-111">Attributes</span></span>  
  
|<span data-ttu-id="89b7f-112">attribute</span><span class="sxs-lookup"><span data-stu-id="89b7f-112">Attribute</span></span>|<span data-ttu-id="89b7f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89b7f-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="89b7f-114">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="89b7f-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="89b7f-115">Gibt den Namen der Ablaufverfolgungsquelle an.</span><span class="sxs-lookup"><span data-stu-id="89b7f-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="89b7f-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="89b7f-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="89b7f-117">Gibt den Namen einer Ablaufverfolgungsschalterinstanz in der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="89b7f-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="89b7f-118">Wenn der Schalter nicht `<switches>` in einem Element identifiziert wird, gibt der Wert die Ebene für den Switch an.</span><span class="sxs-lookup"><span data-stu-id="89b7f-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="89b7f-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="89b7f-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="89b7f-120">Gibt den Typ des Ablaufverfolgungsschalters an.</span><span class="sxs-lookup"><span data-stu-id="89b7f-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="89b7f-121">Wenn vorhanden, muss der Typ ein gültiger Klassenname sein und darf keine leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="89b7f-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="89b7f-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="89b7f-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="89b7f-123">Gibt den Wert für ein Trace-Source-spezifisches Attribut an, das von der <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> Methode für diese Ablaufverfolgungsquelle identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="89b7f-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89b7f-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89b7f-124">Child Elements</span></span>  
  
|<span data-ttu-id="89b7f-125">Element</span><span class="sxs-lookup"><span data-stu-id="89b7f-125">Element</span></span>|<span data-ttu-id="89b7f-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89b7f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89b7f-127">\<Hörer></span><span class="sxs-lookup"><span data-stu-id="89b7f-127">\<listeners></span></span>](listeners-element-for-source.md)|<span data-ttu-id="89b7f-128">Enthält Listener, die Nachrichten sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="89b7f-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89b7f-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89b7f-129">Parent Elements</span></span>  
  
|<span data-ttu-id="89b7f-130">Element</span><span class="sxs-lookup"><span data-stu-id="89b7f-130">Element</span></span>|<span data-ttu-id="89b7f-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89b7f-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="89b7f-132">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="89b7f-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="89b7f-133">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="89b7f-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="89b7f-134">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="89b7f-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89b7f-135">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="89b7f-135">Remarks</span></span>  
 <span data-ttu-id="89b7f-136">Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89b7f-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89b7f-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89b7f-137">Example</span></span>  
 <span data-ttu-id="89b7f-138">Das folgende Beispiel zeigt, `<source>` wie sie das `mySource` Element verwenden, um die `sourceSwitch`Ablaufverfolgungsquelle hinzuzufügen und die Ebene für den Quellschalter mit dem Namen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="89b7f-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="89b7f-139">Ein Konsolenablaufverfolgungslistener wird hinzugefügt, der Ablaufverfolgungsinformationen in die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="89b7f-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="89b7f-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89b7f-140">See also</span></span>

- [<span data-ttu-id="89b7f-141">Ablaufverfolgungs- und Debugeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="89b7f-141">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="89b7f-142">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="89b7f-142">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
