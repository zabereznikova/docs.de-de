---
title: <source>-Element
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 55120e292ac2a2c822c5510563d1aa167ca921e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920457"
---
# <a name="source-element"></a><span data-ttu-id="54f9d-102">\<Quell > Element</span><span class="sxs-lookup"><span data-stu-id="54f9d-102">\<source> Element</span></span>
<span data-ttu-id="54f9d-103">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="54f9d-103">Specifies a trace source that initiates tracing messages.</span></span>  
  
 <span data-ttu-id="54f9d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="54f9d-104">\<configuration></span></span>  
<span data-ttu-id="54f9d-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="54f9d-105">\<system.diagnostics></span></span>  
<span data-ttu-id="54f9d-106">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="54f9d-106">\<sources></span></span>  
<span data-ttu-id="54f9d-107">\<Quell ></span><span class="sxs-lookup"><span data-stu-id="54f9d-107">\<source></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54f9d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="54f9d-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54f9d-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="54f9d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="54f9d-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="54f9d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54f9d-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="54f9d-111">Attributes</span></span>  
  
|<span data-ttu-id="54f9d-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="54f9d-112">Attribute</span></span>|<span data-ttu-id="54f9d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54f9d-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="54f9d-114">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="54f9d-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="54f9d-115">Gibt den Namen der Ablauf Verfolgungs Quelle an.</span><span class="sxs-lookup"><span data-stu-id="54f9d-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="54f9d-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="54f9d-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="54f9d-117">Gibt den Namen einer Instanz eines Ablauf Verfolgungs Switchs in der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="54f9d-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="54f9d-118">Wenn der Schalter nicht in einem `<switches>` -Element identifiziert wird, gibt der Wert die Ebene für den Schalter an.</span><span class="sxs-lookup"><span data-stu-id="54f9d-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="54f9d-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="54f9d-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="54f9d-120">Gibt den Typ des Ablauf Verfolgungs Schalters an.</span><span class="sxs-lookup"><span data-stu-id="54f9d-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="54f9d-121">Wenn der Typ vorhanden ist, muss er ein gültiger Klassenname sein und darf keine leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="54f9d-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="54f9d-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="54f9d-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="54f9d-123">Gibt den Wert für ein Attribut für eine Ablauf Verfolgungs Quelle an, <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> das durch die-Methode für diese Ablauf Verfolgungs Quelle identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="54f9d-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54f9d-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54f9d-124">Child Elements</span></span>  
  
|<span data-ttu-id="54f9d-125">Element</span><span class="sxs-lookup"><span data-stu-id="54f9d-125">Element</span></span>|<span data-ttu-id="54f9d-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54f9d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54f9d-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="54f9d-127">\<listeners></span></span>](listeners-element-for-source.md)|<span data-ttu-id="54f9d-128">Enthält Listener, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="54f9d-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="54f9d-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54f9d-129">Parent Elements</span></span>  
  
|<span data-ttu-id="54f9d-130">Element</span><span class="sxs-lookup"><span data-stu-id="54f9d-130">Element</span></span>|<span data-ttu-id="54f9d-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54f9d-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="54f9d-132">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="54f9d-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="54f9d-133">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="54f9d-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="54f9d-134">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="54f9d-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54f9d-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="54f9d-135">Remarks</span></span>  
 <span data-ttu-id="54f9d-136">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="54f9d-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54f9d-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="54f9d-137">Example</span></span>  
 <span data-ttu-id="54f9d-138">Im folgenden Beispiel wird gezeigt, wie das `<source>` -Element verwendet wird, um `mySource` die Ablauf Verfolgungs Quelle hinzuzufügen und die Ebene für `sourceSwitch`den Quell Switch mit dem Namen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="54f9d-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="54f9d-139">Ein Konsolen Ablaufverfolgungslistener wird hinzugefügt, der Ablauf Verfolgungs Informationen in die Konsole</span><span class="sxs-lookup"><span data-stu-id="54f9d-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="54f9d-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54f9d-140">See also</span></span>

- [<span data-ttu-id="54f9d-141">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="54f9d-141">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="54f9d-142">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="54f9d-142">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
