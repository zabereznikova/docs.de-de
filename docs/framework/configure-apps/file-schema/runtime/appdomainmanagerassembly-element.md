---
title: <appDomainManagerAssembly>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff8c91680a0c3049fa9bc2f7e9c1bf3f654a19b9
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487775"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="ac635-102">\<appDomainManagerAssembly> Element</span><span class="sxs-lookup"><span data-stu-id="ac635-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="ac635-103">Gibt die Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ac635-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
 <span data-ttu-id="ac635-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ac635-104">\<configuration></span></span>  
<span data-ttu-id="ac635-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="ac635-105">\<runtime></span></span>  
<span data-ttu-id="ac635-106">\<appDomainManagerAssembly></span><span class="sxs-lookup"><span data-stu-id="ac635-106">\<appDomainManagerAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac635-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac635-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac635-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ac635-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ac635-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ac635-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac635-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ac635-110">Attributes</span></span>  
  
|<span data-ttu-id="ac635-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ac635-111">Attribute</span></span>|<span data-ttu-id="ac635-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac635-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="ac635-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ac635-113">Required attribute.</span></span> <span data-ttu-id="ac635-114">Gibt den Anzeigenamen der Assembly, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ac635-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac635-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ac635-115">Child Elements</span></span>  
 <span data-ttu-id="ac635-116">Keine</span><span class="sxs-lookup"><span data-stu-id="ac635-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac635-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ac635-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ac635-118">Element</span><span class="sxs-lookup"><span data-stu-id="ac635-118">Element</span></span>|<span data-ttu-id="ac635-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac635-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ac635-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ac635-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ac635-121">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ac635-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac635-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac635-122">Remarks</span></span>  
 <span data-ttu-id="ac635-123">Um den Typ des Anwendungsdomänen-Managers angeben zu können, müssen Sie dieses Element angeben und die [ \<AppDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="ac635-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="ac635-124">Wenn eines der beiden Elemente nicht angegeben ist, wird das andere ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac635-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="ac635-125">Wenn die Standardanwendungsdomäne geladen wird, <xref:System.TypeLoadException> wird ausgelöst, wenn die angegebene Assembly nicht vorhanden ist oder wenn die Assembly nicht mit den vom angegebenen Typ enthält die [ \<AppDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) -Element; und der Prozess nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="ac635-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="ac635-126">Wenn die Assembly gefunden wird, aber die Versionsinformationen nicht überein stimmt, ein <xref:System.IO.FileLoadException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ac635-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="ac635-127">Bei der Angabe des Anwendung Manager Domänentyp für die Standardanwendungsdomäne erben anderen Anwendungsdomänen, die von der Standardanwendungsdomäne erstellt die Anwendungsdomänen-Managertyp.</span><span class="sxs-lookup"><span data-stu-id="ac635-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="ac635-128">Verwenden der <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> und <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> Eigenschaften an eine andere Anwendung Manager Domänentyp für eine neue Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="ac635-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="ac635-129">Der Anwendungstyp für Domänen-Manager angeben, muss die Anwendung volle Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="ac635-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="ac635-130">(Z. B. hat eine Anwendung ausgeführt wird, auf dem Desktop volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht mit voller Vertrauenswürdigkeit, verfügt eine <xref:System.TypeLoadException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ac635-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="ac635-131">Das Format des Anzeigenamens der Assembly finden Sie unter den <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ac635-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="ac635-132">Dieses Element ist nur in .NET Framework 4 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ac635-132">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac635-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac635-133">Example</span></span>  
 <span data-ttu-id="ac635-134">Das folgende Beispiel zeigt, wie Sie angeben, dass die Anwendungsdomänen-Manager für die Standardanwendungsdomäne eines Prozesses ist die `MyMgr` Geben Sie in der `AdMgrExample` Assembly.</span><span class="sxs-lookup"><span data-stu-id="ac635-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac635-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac635-135">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ac635-136">\<AppDomainManagerType >-Element</span><span class="sxs-lookup"><span data-stu-id="ac635-136">\<appDomainManagerType> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)
- [<span data-ttu-id="ac635-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="ac635-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="ac635-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ac635-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ac635-139">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="ac635-139">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
