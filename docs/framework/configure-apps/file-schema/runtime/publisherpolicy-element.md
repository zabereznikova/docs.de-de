---
title: <publisherPolicy>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc206e584440778858e61fc0bab51fc8ffa2009a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252380"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="229bc-102">\<publisherPolicy-> Element</span><span class="sxs-lookup"><span data-stu-id="229bc-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="229bc-103">Gibt an, ob die Common Language Runtime die Herausgeberrichtlinie anwendet.</span><span class="sxs-lookup"><span data-stu-id="229bc-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
<span data-ttu-id="229bc-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="229bc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="229bc-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="229bc-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="229bc-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding->** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="229bc-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="229bc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly->** ](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="229bc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="229bc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<publisherPolicy->**</span><span class="sxs-lookup"><span data-stu-id="229bc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="229bc-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="229bc-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="229bc-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="229bc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="229bc-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="229bc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="229bc-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="229bc-112">Attributes</span></span>  
  
|<span data-ttu-id="229bc-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="229bc-113">Attribute</span></span>|<span data-ttu-id="229bc-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="229bc-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="229bc-115">Gibt an, ob Herausgeber Richtlinien angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="229bc-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="229bc-116">Attribut anwenden</span><span class="sxs-lookup"><span data-stu-id="229bc-116">apply Attribute</span></span>  
  
|<span data-ttu-id="229bc-117">Wert</span><span class="sxs-lookup"><span data-stu-id="229bc-117">Value</span></span>|<span data-ttu-id="229bc-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="229bc-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="229bc-119">Wendet Herausgeber Richtlinien an.</span><span class="sxs-lookup"><span data-stu-id="229bc-119">Applies publisher policy.</span></span> <span data-ttu-id="229bc-120">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="229bc-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="229bc-121">Die Herausgeber Richtlinie wird nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="229bc-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="229bc-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="229bc-122">Child Elements</span></span>  

<span data-ttu-id="229bc-123">Keine</span><span class="sxs-lookup"><span data-stu-id="229bc-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="229bc-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="229bc-124">Parent Elements</span></span>  
  
|<span data-ttu-id="229bc-125">Element</span><span class="sxs-lookup"><span data-stu-id="229bc-125">Element</span></span>|<span data-ttu-id="229bc-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="229bc-126">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="229bc-127">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="229bc-127">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="229bc-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="229bc-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="229bc-129">Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="229bc-129">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="229bc-130">Verwenden Sie `<dependentAssembly>` ein-Element für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="229bc-130">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="229bc-131">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="229bc-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="229bc-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="229bc-132">Remarks</span></span>  
 <span data-ttu-id="229bc-133">Wenn ein Komponentenhersteller eine neue Version einer Assembly freigibt, kann der Hersteller eine Herausgeber Richtlinie einschließen, damit Anwendungen, die die alte Version verwenden, nun die neue Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="229bc-133">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="229bc-134">Um anzugeben, ob die Herausgeber Richtlinie für eine bestimmte Assembly angewendet werden soll, fügen Sie das  **\<Element publisherPolicy >** in das  **\<> Element dependentAssembly** ein.</span><span class="sxs-lookup"><span data-stu-id="229bc-134">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="229bc-135">Die Standardeinstellung für das **Apply** -Attribut ist " **Yes**".</span><span class="sxs-lookup"><span data-stu-id="229bc-135">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="229bc-136">Wenn Sie das **Apply** -Attribut auf **No** festlegen, werden alle vorherigen **Yes** -Einstellungen für eine Assembly überschrieben.</span><span class="sxs-lookup"><span data-stu-id="229bc-136">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="229bc-137">Die Berechtigung ist erforderlich, damit eine Anwendung die Herausgeber Richtlinie mithilfe des [ \<publisherPolicy Apply = "No"/>-](publisherpolicy-element.md) Elements in der Anwendungs Konfigurationsdatei explizit ignoriert.</span><span class="sxs-lookup"><span data-stu-id="229bc-137">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="229bc-138">Die Berechtigung wird erteilt, indem das <xref:System.Security.Permissions.SecurityPermissionFlag> -Flag <xref:System.Security.Permissions.SecurityPermission>auf festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="229bc-138">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="229bc-139">Weitere Informationen finden Sie unter [Sicherheits Berechtigung für die assemblybindungsumleitung](../../assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="229bc-139">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="229bc-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="229bc-140">Example</span></span>  
 <span data-ttu-id="229bc-141">Im folgenden Beispiel wird die Herausgeber Richtlinie für die `myAssembly`Assembly deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="229bc-141">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="229bc-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="229bc-142">See also</span></span>

- [<span data-ttu-id="229bc-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="229bc-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="229bc-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="229bc-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="229bc-145">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="229bc-145">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="229bc-146">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="229bc-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
