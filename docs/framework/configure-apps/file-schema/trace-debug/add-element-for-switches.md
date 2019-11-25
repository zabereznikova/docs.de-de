---
title: <add>-Element für <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: db2de681227dfdb7420808963219b9f52381f8fe
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088960"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="f0e5a-102">\<> Element für \<Switches hinzufügen ></span><span class="sxs-lookup"><span data-stu-id="f0e5a-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="f0e5a-103">Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-103">Specifies the level where a trace switch is set.</span></span>  

<span data-ttu-id="f0e5a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f0e5a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f0e5a-105">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="f0e5a-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="f0e5a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Switches**](switches-element.md) ></span><span class="sxs-lookup"><span data-stu-id="f0e5a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<switches>**](switches-element.md)</span></span>\
<span data-ttu-id="f0e5a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Hinzufügen >**</span><span class="sxs-lookup"><span data-stu-id="f0e5a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f0e5a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0e5a-108">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0e5a-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f0e5a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f0e5a-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0e5a-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="f0e5a-111">Attributes</span></span>  
  
|<span data-ttu-id="f0e5a-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="f0e5a-112">Attribute</span></span>|<span data-ttu-id="f0e5a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0e5a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0e5a-114">**name**</span><span class="sxs-lookup"><span data-stu-id="f0e5a-114">**name**</span></span>|<span data-ttu-id="f0e5a-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="f0e5a-116">Gibt den Namen des Schalters an.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-116">Specifies the name of the switch.</span></span> <span data-ttu-id="f0e5a-117">Der Wert dieses Attributs entspricht dem *DisplayName* -Parameter, der an den Switch-Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-117">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="f0e5a-118">**Wert**</span><span class="sxs-lookup"><span data-stu-id="f0e5a-118">**value**</span></span>|<span data-ttu-id="f0e5a-119">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="f0e5a-120">Gibt die Ebene des Schalters an.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-120">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0e5a-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0e5a-121">Child Elements</span></span>  
 <span data-ttu-id="f0e5a-122">Keine</span><span class="sxs-lookup"><span data-stu-id="f0e5a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0e5a-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0e5a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f0e5a-124">Element</span><span class="sxs-lookup"><span data-stu-id="f0e5a-124">Element</span></span>|<span data-ttu-id="f0e5a-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0e5a-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f0e5a-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="f0e5a-127">Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-127">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f0e5a-128">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0e5a-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0e5a-129">Remarks</span></span>  
 <span data-ttu-id="f0e5a-130">Sie können die Ebene eines Ablauf Verfolgungs Schalters ändern, indem Sie ihn in eine Konfigurationsdatei einfügen.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-130">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="f0e5a-131">Wenn der Schalter ein <xref:System.Diagnostics.BooleanSwitch>ist, können Sie ihn aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-131">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="f0e5a-132">Wenn der Schalter ein <xref:System.Diagnostics.TraceSwitch>ist, können Sie ihm verschiedene Ebenen zuweisen, um die Typen der von der Anwendung ausgegebenen Ablauf Verfolgungs-oder Debugmeldungen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-132">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0e5a-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0e5a-133">Example</span></span>  
 <span data-ttu-id="f0e5a-134">Im folgenden Beispiel wird gezeigt, wie das **\<Add >** -Elements verwendet wird, um den `General` Trace-Schalter auf die <xref:System.Diagnostics.TraceLevel> Ebene festzulegen und den `Data` booleschen Ablauf Verfolgungs Schalter zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f0e5a-134">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f0e5a-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0e5a-135">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="f0e5a-136">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f0e5a-136">Trace and Debug Settings Schema</span></span>](index.md)
