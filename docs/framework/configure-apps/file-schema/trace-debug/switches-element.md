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
ms.openlocfilehash: 4aeb3cb0cd75f0fb27e3b359b86da61a77b491c7
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088807"
---
# <a name="switches-element"></a><span data-ttu-id="091c8-102">\<schaltet > Element</span><span class="sxs-lookup"><span data-stu-id="091c8-102">\<switches> Element</span></span>
<span data-ttu-id="091c8-103">Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="091c8-103">Contains trace switches and the level where the trace switches are set.</span></span>  

<span data-ttu-id="091c8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="091c8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="091c8-105">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="091c8-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="091c8-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Switches >**</span><span class="sxs-lookup"><span data-stu-id="091c8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>

## <a name="syntax"></a><span data-ttu-id="091c8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="091c8-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="091c8-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="091c8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="091c8-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="091c8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="091c8-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="091c8-110">Attributes</span></span>  
 <span data-ttu-id="091c8-111">Keine</span><span class="sxs-lookup"><span data-stu-id="091c8-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="091c8-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="091c8-112">Child Elements</span></span>  
  
|<span data-ttu-id="091c8-113">Element</span><span class="sxs-lookup"><span data-stu-id="091c8-113">Element</span></span>|<span data-ttu-id="091c8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="091c8-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="091c8-115">\<add></span><span class="sxs-lookup"><span data-stu-id="091c8-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="091c8-116">Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="091c8-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="091c8-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="091c8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="091c8-118">Element</span><span class="sxs-lookup"><span data-stu-id="091c8-118">Element</span></span>|<span data-ttu-id="091c8-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="091c8-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="091c8-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="091c8-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="091c8-121">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="091c8-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="091c8-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="091c8-122">Remarks</span></span>  
 <span data-ttu-id="091c8-123">Sie können die Ebene eines Ablauf Verfolgungs Schalters ändern, indem Sie ihn in eine Konfigurationsdatei einfügen.</span><span class="sxs-lookup"><span data-stu-id="091c8-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="091c8-124">Wenn der Schalter ein <xref:System.Diagnostics.BooleanSwitch>ist, können Sie ihn aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="091c8-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="091c8-125">Wenn der Schalter ein <xref:System.Diagnostics.TraceSwitch>ist, können Sie ihm verschiedene Ebenen zuweisen, um die Typen der von der Anwendung ausgegebenen Ablauf Verfolgungs-oder Debugmeldungen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="091c8-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="091c8-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="091c8-126">Example</span></span>  
 <span data-ttu-id="091c8-127">Im folgenden Beispiel wird gezeigt, wie Sie die **\<Switch->** -Element verwenden, um den `General` Trace-Schalter auf die <xref:System.Diagnostics.TraceLevel> Ebene festzulegen und den `Data` booleschen Ablauf Verfolgungs Schalter zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="091c8-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="091c8-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="091c8-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="091c8-129">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="091c8-129">Trace and Debug Settings Schema</span></span>](index.md)
