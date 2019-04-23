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
ms.openlocfilehash: 29932eb27bcd13876ea6982982e67341edb8e0de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076288"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="a305e-102">\<PublisherPolicy >-Element</span><span class="sxs-lookup"><span data-stu-id="a305e-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="a305e-103">Gibt an, ob die Common Language Runtime die Herausgeberrichtlinie anwendet.</span><span class="sxs-lookup"><span data-stu-id="a305e-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
 <span data-ttu-id="a305e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a305e-104">\<configuration></span></span>  
<span data-ttu-id="a305e-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="a305e-105">\<runtime></span></span>  
<span data-ttu-id="a305e-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="a305e-106">\<assemblyBinding></span></span>  
<span data-ttu-id="a305e-107">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="a305e-107">\<dependentAssembly></span></span>  
<span data-ttu-id="a305e-108">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="a305e-108">\<publisherPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a305e-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a305e-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a305e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a305e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a305e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a305e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a305e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a305e-112">Attributes</span></span>  
  
|<span data-ttu-id="a305e-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="a305e-113">Attribute</span></span>|<span data-ttu-id="a305e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a305e-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="a305e-115">Gibt an, ob die Herausgeberrichtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a305e-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="a305e-116">Attribut anwenden</span><span class="sxs-lookup"><span data-stu-id="a305e-116">apply Attribute</span></span>  
  
|<span data-ttu-id="a305e-117">Wert</span><span class="sxs-lookup"><span data-stu-id="a305e-117">Value</span></span>|<span data-ttu-id="a305e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a305e-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="a305e-119">Wendet die Verleger-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="a305e-119">Applies publisher policy.</span></span> <span data-ttu-id="a305e-120">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="a305e-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="a305e-121">Herausgeberrichtlinie wird nicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a305e-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a305e-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a305e-122">Child Elements</span></span>  
 <span data-ttu-id="a305e-123">Keine</span><span class="sxs-lookup"><span data-stu-id="a305e-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a305e-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a305e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a305e-125">Element</span><span class="sxs-lookup"><span data-stu-id="a305e-125">Element</span></span>|<span data-ttu-id="a305e-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a305e-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a305e-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a305e-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a305e-128">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a305e-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a305e-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a305e-129">Remarks</span></span>  
 <span data-ttu-id="a305e-130">Bei einem Komponentenanbieter eine neue Version einer Assembly der Veröffentlichung kann der Anbieter eine Herausgeberrichtlinie enthalten, sodass Anwendungen, die die alte Version nun verwenden die neue Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="a305e-130">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="a305e-131">Um anzugeben, ob Herausgeberrichtlinie für eine bestimmte Assembly anzuwenden, fügen die  **\<PublisherPolicy >** Element in der  **\<DependentAssembly >** Element.</span><span class="sxs-lookup"><span data-stu-id="a305e-131">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="a305e-132">Die Standardeinstellung für die **anwenden** Attribut **Ja**.</span><span class="sxs-lookup"><span data-stu-id="a305e-132">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="a305e-133">Festlegen der **anwenden** Attribut **keine** überschreibt alle vorherigen **Ja** Einstellungen für eine Assembly.</span><span class="sxs-lookup"><span data-stu-id="a305e-133">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="a305e-134">Berechtigung ist erforderlich, damit eine Anwendung explizit ignoriert Herausgeberrichtlinie mithilfe der [ \<PublisherPolicy anwenden = "no" / >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) Element in der Konfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a305e-134">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="a305e-135">Die Berechtigung wird erteilt, indem die <xref:System.Security.Permissions.SecurityPermissionFlag> flag für die <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="a305e-135">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="a305e-136">Weitere Informationen finden Sie unter [Sicherheitsberechtigung für die Umleitung der Assemblybindung](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="a305e-136">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a305e-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a305e-137">Example</span></span>  
 <span data-ttu-id="a305e-138">Das folgende Beispiel deaktiviert die Herausgeberrichtlinie für die Assembly `myAssembly`.</span><span class="sxs-lookup"><span data-stu-id="a305e-138">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a305e-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a305e-139">See also</span></span>

- [<span data-ttu-id="a305e-140">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="a305e-140">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="a305e-141">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="a305e-141">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="a305e-142">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="a305e-142">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="a305e-143">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="a305e-143">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
