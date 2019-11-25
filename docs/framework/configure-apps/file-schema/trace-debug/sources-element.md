---
title: <sources>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
ms.openlocfilehash: a903d009f2056e65414c1792494fbbd20e224413
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088813"
---
# <a name="sources-element"></a><span data-ttu-id="790e1-102">\<Quellen >-Element</span><span class="sxs-lookup"><span data-stu-id="790e1-102">\<sources> Element</span></span>
<span data-ttu-id="790e1-103">Gibt Ablauf Verfolgungs Quellen an, die Ablauf Verfolgungs Meldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="790e1-103">Specifies trace sources that initiate tracing messages.</span></span>  

<span data-ttu-id="790e1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="790e1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="790e1-105">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="790e1-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="790e1-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Quellen >**</span><span class="sxs-lookup"><span data-stu-id="790e1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**</span></span>

## <a name="syntax"></a><span data-ttu-id="790e1-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="790e1-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="790e1-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="790e1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="790e1-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="790e1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="790e1-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="790e1-110">Attributes</span></span>  
 <span data-ttu-id="790e1-111">Keine</span><span class="sxs-lookup"><span data-stu-id="790e1-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="790e1-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="790e1-112">Child Elements</span></span>  
  
|<span data-ttu-id="790e1-113">Element</span><span class="sxs-lookup"><span data-stu-id="790e1-113">Element</span></span>|<span data-ttu-id="790e1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="790e1-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="790e1-115">\<source></span><span class="sxs-lookup"><span data-stu-id="790e1-115">\<source></span></span>](source-element.md)|<span data-ttu-id="790e1-116">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="790e1-116">Required element.</span></span><br /><br /> <span data-ttu-id="790e1-117">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="790e1-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="790e1-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="790e1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="790e1-119">Element</span><span class="sxs-lookup"><span data-stu-id="790e1-119">Element</span></span>|<span data-ttu-id="790e1-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="790e1-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="790e1-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="790e1-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="790e1-122">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="790e1-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="790e1-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="790e1-123">Remarks</span></span>  
 <span data-ttu-id="790e1-124">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="790e1-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="790e1-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="790e1-125">Example</span></span>  
 <span data-ttu-id="790e1-126">Im folgenden Beispiel wird gezeigt, wie das `<sources>`-Element verwendet wird, um die Ablauf Verfolgungs Quelle `mySource` hinzuzufügen und die Ebene für den Quell Switch mit dem Namen `sourceSwitch`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="790e1-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="790e1-127">Ein Konsolen Ablaufverfolgungslistener wird hinzugefügt, der Ablauf Verfolgungs Informationen in die Konsole</span><span class="sxs-lookup"><span data-stu-id="790e1-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="790e1-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="790e1-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="790e1-129">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="790e1-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="790e1-130">\<source></span><span class="sxs-lookup"><span data-stu-id="790e1-130">\<source></span></span>](source-element.md)
