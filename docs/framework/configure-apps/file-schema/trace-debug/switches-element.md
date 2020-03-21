---
title: <switches>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: 15cc9680d7a20341eb5d1d1df302c1e034e70e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153229"
---
# <a name="switches-element"></a><span data-ttu-id="7d3af-102">\<Schalter> Element</span><span class="sxs-lookup"><span data-stu-id="7d3af-102">\<switches> Element</span></span>
<span data-ttu-id="7d3af-103">Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="7d3af-103">Contains trace switches and the level where the trace switches are set.</span></span>  

<span data-ttu-id="7d3af-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d3af-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7d3af-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d3af-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="7d3af-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Switches>**</span><span class="sxs-lookup"><span data-stu-id="7d3af-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7d3af-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d3af-107">Syntax</span></span>  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d3af-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7d3af-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7d3af-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7d3af-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d3af-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="7d3af-110">Attributes</span></span>  
 <span data-ttu-id="7d3af-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="7d3af-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7d3af-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7d3af-112">Child Elements</span></span>  
  
|<span data-ttu-id="7d3af-113">Element</span><span class="sxs-lookup"><span data-stu-id="7d3af-113">Element</span></span>|<span data-ttu-id="7d3af-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d3af-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d3af-115">\<hinzufügen></span><span class="sxs-lookup"><span data-stu-id="7d3af-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="7d3af-116">Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7d3af-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d3af-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7d3af-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7d3af-118">Element</span><span class="sxs-lookup"><span data-stu-id="7d3af-118">Element</span></span>|<span data-ttu-id="7d3af-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d3af-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7d3af-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7d3af-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="7d3af-121">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7d3af-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d3af-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7d3af-122">Remarks</span></span>  
 <span data-ttu-id="7d3af-123">Sie können die Ebene eines Ablaufverfolgungsschalters ändern, indem Sie ihn in eine Konfigurationsdatei einteilen.</span><span class="sxs-lookup"><span data-stu-id="7d3af-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="7d3af-124">Wenn es sich <xref:System.Diagnostics.BooleanSwitch>bei dem Schalter um einen handelt, können Sie ihn ein- und ausschalten.</span><span class="sxs-lookup"><span data-stu-id="7d3af-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="7d3af-125">Wenn es sich <xref:System.Diagnostics.TraceSwitch>bei dem Switch um einen handelt, können Sie ihm verschiedene Ebenen zuweisen, um die Typen von Ablaufverfolgungs- oder Debugmeldungen anzugeben, die die Anwendung ausgibt.</span><span class="sxs-lookup"><span data-stu-id="7d3af-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d3af-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d3af-126">Example</span></span>  
 <span data-ttu-id="7d3af-127">Das folgende Beispiel zeigt, wie Sie den `General` <xref:System.Diagnostics.TraceLevel> \*\* \<Switch>-Element\*\* verwenden, `Data` um den Ablaufverfolgungsschalter auf die Ebene zu setzen, und den booleschen Ablaufverfolgungsschalter aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7d3af-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d3af-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d3af-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="7d3af-129">Ablaufverfolgungs- und Debugeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="7d3af-129">Trace and Debug Settings Schema</span></span>](index.md)
