---
title: '&lt;AppDomainManagerType&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 56d68efe176540ba82ec7b86f35678905ebc970b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltappdomainmanagertypegt-element"></a><span data-ttu-id="58058-102">&lt;AppDomainManagerType&gt; Element</span><span class="sxs-lookup"><span data-stu-id="58058-102">&lt;appDomainManagerType&gt; Element</span></span>
<span data-ttu-id="58058-103">Gibt den Typ an, der als Anwendungsdomänen-Manager für die Standardanwendungsdomäne dient.</span><span class="sxs-lookup"><span data-stu-id="58058-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
 <span data-ttu-id="58058-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="58058-104">\<configuration></span></span>  
<span data-ttu-id="58058-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="58058-105">\<runtime></span></span>  
<span data-ttu-id="58058-106">\<AppDomainManagerType ></span><span class="sxs-lookup"><span data-stu-id="58058-106">\<appDomainManagerType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58058-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="58058-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58058-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="58058-108">Attributes and Elements</span></span>  
 <span data-ttu-id="58058-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58058-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58058-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="58058-110">Attributes</span></span>  
  
|<span data-ttu-id="58058-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="58058-111">Attribute</span></span>|<span data-ttu-id="58058-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58058-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="58058-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="58058-113">Required attribute.</span></span> <span data-ttu-id="58058-114">Gibt den Namen des Typs, einschließlich des Namespace, der als Anwendungsdomänen-Managers für die Standardanwendungsdomäne im Prozess dient.</span><span class="sxs-lookup"><span data-stu-id="58058-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58058-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58058-115">Child Elements</span></span>  
 <span data-ttu-id="58058-116">Keine</span><span class="sxs-lookup"><span data-stu-id="58058-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58058-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58058-117">Parent Elements</span></span>  
  
|<span data-ttu-id="58058-118">Element</span><span class="sxs-lookup"><span data-stu-id="58058-118">Element</span></span>|<span data-ttu-id="58058-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58058-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="58058-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="58058-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="58058-121">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="58058-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58058-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58058-122">Remarks</span></span>  
 <span data-ttu-id="58058-123">Um den Typ des Anwendungsdomänen-Managers anzugeben, müssen Sie dieses Element angeben und die [ \<AppDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="58058-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="58058-124">Wenn eines dieser Elemente nicht angegeben ist, wird die andere ignoriert.</span><span class="sxs-lookup"><span data-stu-id="58058-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="58058-125">Wenn die Standardanwendungsdomäne geladen wird, <xref:System.TypeLoadException> wird ausgelöst, wenn der angegebene Typ nicht in der Assembly vorhanden ist, die von angegeben wird die [ \<AppDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) Element und der Prozess kann nicht Starten.</span><span class="sxs-lookup"><span data-stu-id="58058-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="58058-126">Wenn Sie die Anwendung Manager Domänentyp für die Standardanwendungsdomäne angeben, erben andere Anwendungsdomänen, die von der Standardanwendungsdomäne erstellt Managertyp die Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="58058-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="58058-127">Verwenden der <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> und <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> Eigenschaften zur Angabe einer anderen Anwendung Manager Domänentyp für eine neue Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="58058-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="58058-128">Die Anwendungsdomänen-Managertyp angeben, muss die Anwendung volle Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="58058-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="58058-129">(Z. B. weist eine Anwendung, die auf dem Desktop ausgeführte volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht über die volle Vertrauenswürdigkeit verfügt eine <xref:System.TypeLoadException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="58058-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="58058-130">Das Format des Typs und des Namespace ist das gleiche Format für die verwendeten die <xref:System.Type.FullName%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="58058-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="58058-131">Dieses Konfigurationselement steht nur in der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] und höher.</span><span class="sxs-lookup"><span data-stu-id="58058-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58058-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58058-132">Example</span></span>  
 <span data-ttu-id="58058-133">Das folgende Beispiel zeigt, wie Sie angeben, dass die Anwendungsdomänen-Manager für die Standardanwendungsdomäne eines Prozesses ist die `MyMgr` Geben Sie in der `AdMgrExample` Assembly.</span><span class="sxs-lookup"><span data-stu-id="58058-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="58058-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58058-134">See Also</span></span>  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="58058-135">\<AppDomainManagerAssembly >-Element</span><span class="sxs-lookup"><span data-stu-id="58058-135">\<appDomainManagerAssembly> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
 [<span data-ttu-id="58058-136">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="58058-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="58058-137">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="58058-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="58058-138">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="58058-138">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
