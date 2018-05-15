---
title: '&lt;AppDomainManagerAssembly&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7656f4819e8ed6d8c1c87eabcbd5862929d47cdc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltappdomainmanagerassemblygt-element"></a><span data-ttu-id="6c931-102">&lt;AppDomainManagerAssembly&gt; Element</span><span class="sxs-lookup"><span data-stu-id="6c931-102">&lt;appDomainManagerAssembly&gt; Element</span></span>
<span data-ttu-id="6c931-103">Gibt die Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6c931-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
 <span data-ttu-id="6c931-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6c931-104">\<configuration></span></span>  
<span data-ttu-id="6c931-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="6c931-105">\<runtime></span></span>  
<span data-ttu-id="6c931-106">\<AppDomainManagerAssembly ></span><span class="sxs-lookup"><span data-stu-id="6c931-106">\<appDomainManagerAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c931-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c931-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c931-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6c931-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6c931-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c931-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c931-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="6c931-110">Attributes</span></span>  
  
|<span data-ttu-id="6c931-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="6c931-111">Attribute</span></span>|<span data-ttu-id="6c931-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c931-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="6c931-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="6c931-113">Required attribute.</span></span> <span data-ttu-id="6c931-114">Gibt den Anzeigenamen der Assembly, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6c931-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c931-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c931-115">Child Elements</span></span>  
 <span data-ttu-id="6c931-116">Keine</span><span class="sxs-lookup"><span data-stu-id="6c931-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c931-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c931-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6c931-118">Element</span><span class="sxs-lookup"><span data-stu-id="6c931-118">Element</span></span>|<span data-ttu-id="6c931-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c931-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6c931-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6c931-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6c931-121">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6c931-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c931-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c931-122">Remarks</span></span>  
 <span data-ttu-id="6c931-123">Um den Typ des Anwendungsdomänen-Managers anzugeben, müssen Sie dieses Element angeben und die [ \<AppDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="6c931-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="6c931-124">Wenn eines dieser Elemente nicht angegeben ist, wird die andere ignoriert.</span><span class="sxs-lookup"><span data-stu-id="6c931-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="6c931-125">Wenn die Standardanwendungsdomäne geladen wird, <xref:System.TypeLoadException> wird ausgelöst, wenn die angegebene Assembly nicht vorhanden ist oder wenn die Assembly nicht mit den vom angegebenen Typ enthält die [ \<AppDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) -Element ist; und der Prozess nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="6c931-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="6c931-126">Wenn die Assembly gefunden wird, aber die Versionsinformationen nicht überein stimmt, eine <xref:System.IO.FileLoadException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="6c931-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="6c931-127">Wenn Sie die Anwendung Manager Domänentyp für die Standardanwendungsdomäne angeben, erben andere Anwendungsdomänen, die von der Standardanwendungsdomäne erstellt Managertyp die Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="6c931-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="6c931-128">Verwenden der <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> und <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> Eigenschaften zur Angabe einer anderen Anwendung Manager Domänentyp für eine neue Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="6c931-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="6c931-129">Die Anwendungsdomänen-Managertyp angeben, muss die Anwendung volle Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="6c931-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="6c931-130">(Z. B. weist eine Anwendung, die auf dem Desktop ausgeführte volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht über die volle Vertrauenswürdigkeit verfügt eine <xref:System.TypeLoadException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="6c931-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="6c931-131">Das Format des Assemblyanzeigenamens, finden Sie unter der <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6c931-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="6c931-132">Dieses Konfigurationselement steht nur in der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] und höher.</span><span class="sxs-lookup"><span data-stu-id="6c931-132">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c931-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c931-133">Example</span></span>  
 <span data-ttu-id="6c931-134">Das folgende Beispiel zeigt, wie Sie angeben, dass die Anwendungsdomänen-Manager für die Standardanwendungsdomäne eines Prozesses ist die `MyMgr` Geben Sie in der `AdMgrExample` Assembly.</span><span class="sxs-lookup"><span data-stu-id="6c931-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c931-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c931-135">See Also</span></span>  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="6c931-136">\<AppDomainManagerType >-Element</span><span class="sxs-lookup"><span data-stu-id="6c931-136">\<appDomainManagerType> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)  
 [<span data-ttu-id="6c931-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="6c931-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="6c931-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="6c931-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="6c931-139">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="6c931-139">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
