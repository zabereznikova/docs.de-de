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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088960"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="4b492-102">\<add>-Element für \<switches></span><span class="sxs-lookup"><span data-stu-id="4b492-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="4b492-103">Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4b492-103">Specifies the level where a trace switch is set.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<switches>**](switches-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="4b492-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b492-104">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b492-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4b492-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4b492-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4b492-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b492-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="4b492-107">Attributes</span></span>  
  
|<span data-ttu-id="4b492-108">attribute</span><span class="sxs-lookup"><span data-stu-id="4b492-108">Attribute</span></span>|<span data-ttu-id="4b492-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4b492-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b492-110">**name**</span><span class="sxs-lookup"><span data-stu-id="4b492-110">**name**</span></span>|<span data-ttu-id="4b492-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="4b492-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="4b492-112">Gibt den Namen des Schalters an.</span><span class="sxs-lookup"><span data-stu-id="4b492-112">Specifies the name of the switch.</span></span> <span data-ttu-id="4b492-113">Der Wert dieses Attributs entspricht dem *DisplayName* -Parameter, der an den Switch-Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="4b492-113">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="4b492-114">**value**</span><span class="sxs-lookup"><span data-stu-id="4b492-114">**value**</span></span>|<span data-ttu-id="4b492-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="4b492-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="4b492-116">Gibt die Ebene des Schalters an.</span><span class="sxs-lookup"><span data-stu-id="4b492-116">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b492-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b492-117">Child Elements</span></span>  
 <span data-ttu-id="4b492-118">Keine</span><span class="sxs-lookup"><span data-stu-id="4b492-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b492-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b492-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4b492-120">Element</span><span class="sxs-lookup"><span data-stu-id="4b492-120">Element</span></span>|<span data-ttu-id="4b492-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b492-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4b492-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4b492-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="4b492-123">Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="4b492-123">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4b492-124">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4b492-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b492-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4b492-125">Remarks</span></span>  
 <span data-ttu-id="4b492-126">Sie können die Ebene eines Ablauf Verfolgungs Schalters ändern, indem Sie ihn in eine Konfigurationsdatei einfügen.</span><span class="sxs-lookup"><span data-stu-id="4b492-126">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="4b492-127">Wenn der Schalter ein ist <xref:System.Diagnostics.BooleanSwitch> , können Sie ihn aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4b492-127">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="4b492-128">Wenn der Schalter ein ist <xref:System.Diagnostics.TraceSwitch> , können Sie ihm verschiedene Ebenen zuweisen, um die Typen der Ablauf Verfolgungs-oder Debugmeldungen anzugeben, die die Anwendung ausgibt.</span><span class="sxs-lookup"><span data-stu-id="4b492-128">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b492-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b492-129">Example</span></span>  
 <span data-ttu-id="4b492-130">Im folgenden Beispiel wird gezeigt, wie das **\<add>** -Element verwendet wird, um den Ablauf `General` Verfolgungs Schalter auf die Ebene festzulegen <xref:System.Diagnostics.TraceLevel> und den `Data` booleschen Ablauf Verfolgungs Schalter zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4b492-130">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4b492-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b492-131">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="4b492-132">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="4b492-132">Trace and Debug Settings Schema</span></span>](index.md)
