---
title: '&lt;Quellen&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a9c5c5529e349eca2ba089ed6fb71da4bd48430a
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48033245"
---
# <a name="ltsourcesgt-element"></a><span data-ttu-id="be875-102">&lt;Quellen&gt; Element</span><span class="sxs-lookup"><span data-stu-id="be875-102">&lt;sources&gt; Element</span></span>
<span data-ttu-id="be875-103">Gibt die Ablaufverfolgungsquellen, die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="be875-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="be875-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="be875-104">\<configuration></span></span>  
<span data-ttu-id="be875-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="be875-105">\<system.diagnostics></span></span>  
<span data-ttu-id="be875-106">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="be875-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be875-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="be875-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be875-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="be875-108">Attributes and Elements</span></span>  
 <span data-ttu-id="be875-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="be875-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be875-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="be875-110">Attributes</span></span>  
 <span data-ttu-id="be875-111">Keine</span><span class="sxs-lookup"><span data-stu-id="be875-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="be875-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="be875-112">Child Elements</span></span>  
  
|<span data-ttu-id="be875-113">Element</span><span class="sxs-lookup"><span data-stu-id="be875-113">Element</span></span>|<span data-ttu-id="be875-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be875-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be875-115">\<source></span><span class="sxs-lookup"><span data-stu-id="be875-115">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="be875-116">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="be875-116">Required element.</span></span><br /><br /> <span data-ttu-id="be875-117">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="be875-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="be875-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="be875-118">Parent Elements</span></span>  
  
|<span data-ttu-id="be875-119">Element</span><span class="sxs-lookup"><span data-stu-id="be875-119">Element</span></span>|<span data-ttu-id="be875-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be875-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="be875-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="be875-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="be875-122">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="be875-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be875-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be875-123">Remarks</span></span>  
 <span data-ttu-id="be875-124">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be875-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be875-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be875-125">Example</span></span>  
 <span data-ttu-id="be875-126">Das folgende Beispiel zeigt, wie Sie mit der `<sources>` Ablaufverfolgungsquelle hinzuzufügenden Elements `mySource` und legen Sie die Ebene für den Quellschalter namens `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="be875-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="be875-127">Dass, die Ablaufverfolgungsinformationen in die Konsole schreibt, wird ein Konsolen-Ablaufverfolgungslistener hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be875-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"   
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"   
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"   
                     initializeData="Error" />  
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
  
## <a name="see-also"></a><span data-ttu-id="be875-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be875-128">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 [<span data-ttu-id="be875-129">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="be875-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="be875-130">\<source></span><span class="sxs-lookup"><span data-stu-id="be875-130">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)
