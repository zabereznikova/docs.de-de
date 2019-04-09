---
title: <appDomainManagerAssembly> Element
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4fe1dfbd62a6967ae51031fa12f80e9c5563dc44
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182350"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="6b6d1-102">\<appDomainManagerAssembly> Element</span><span class="sxs-lookup"><span data-stu-id="6b6d1-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="6b6d1-103">Gibt die Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
 <span data-ttu-id="6b6d1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6b6d1-104">\<configuration></span></span>  
<span data-ttu-id="6b6d1-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="6b6d1-105">\<runtime></span></span>  
<span data-ttu-id="6b6d1-106">\<appDomainManagerAssembly></span><span class="sxs-lookup"><span data-stu-id="6b6d1-106">\<appDomainManagerAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b6d1-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b6d1-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b6d1-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6b6d1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6b6d1-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b6d1-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="6b6d1-110">Attributes</span></span>  
  
|<span data-ttu-id="6b6d1-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="6b6d1-111">Attribute</span></span>|<span data-ttu-id="6b6d1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b6d1-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="6b6d1-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-113">Required attribute.</span></span> <span data-ttu-id="6b6d1-114">Gibt den Anzeigenamen der Assembly, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b6d1-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b6d1-115">Child Elements</span></span>  
 <span data-ttu-id="6b6d1-116">Keine</span><span class="sxs-lookup"><span data-stu-id="6b6d1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b6d1-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b6d1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6b6d1-118">Element</span><span class="sxs-lookup"><span data-stu-id="6b6d1-118">Element</span></span>|<span data-ttu-id="6b6d1-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b6d1-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6b6d1-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6b6d1-121">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b6d1-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b6d1-122">Remarks</span></span>  
 <span data-ttu-id="6b6d1-123">Um den Typ des Anwendungsdomänen-Managers angeben zu können, müssen Sie dieses Element angeben und die [ \<AppDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="6b6d1-124">Wenn eines der beiden Elemente nicht angegeben ist, wird das andere ignoriert.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="6b6d1-125">Wenn die Standardanwendungsdomäne geladen wird, <xref:System.TypeLoadException> wird ausgelöst, wenn die angegebene Assembly nicht vorhanden ist oder wenn die Assembly nicht mit den vom angegebenen Typ enthält die [ \<AppDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) -Element; und der Prozess nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="6b6d1-126">Wenn die Assembly gefunden wird, aber die Versionsinformationen nicht überein stimmt, ein <xref:System.IO.FileLoadException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="6b6d1-127">Bei der Angabe des Anwendung Manager Domänentyp für die Standardanwendungsdomäne erben anderen Anwendungsdomänen, die von der Standardanwendungsdomäne erstellt die Anwendungsdomänen-Managertyp.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="6b6d1-128">Verwenden der <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> und <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> Eigenschaften an eine andere Anwendung Manager Domänentyp für eine neue Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="6b6d1-129">Der Anwendungstyp für Domänen-Manager angeben, muss die Anwendung volle Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="6b6d1-130">(Z. B. hat eine Anwendung ausgeführt wird, auf dem Desktop volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht mit voller Vertrauenswürdigkeit, verfügt eine <xref:System.TypeLoadException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="6b6d1-131">Das Format des Anzeigenamens der Assembly finden Sie unter den <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="6b6d1-132">Dieses Konfigurationselement steht nur in der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] und höher.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-132">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b6d1-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b6d1-133">Example</span></span>  
 <span data-ttu-id="6b6d1-134">Das folgende Beispiel zeigt, wie Sie angeben, dass die Anwendungsdomänen-Manager für die Standardanwendungsdomäne eines Prozesses ist die `MyMgr` Geben Sie in der `AdMgrExample` Assembly.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b6d1-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b6d1-135">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6b6d1-136">\<AppDomainManagerType >-Element</span><span class="sxs-lookup"><span data-stu-id="6b6d1-136">\<appDomainManagerType> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)
- [<span data-ttu-id="6b6d1-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="6b6d1-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="6b6d1-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="6b6d1-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="6b6d1-139">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="6b6d1-139">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
