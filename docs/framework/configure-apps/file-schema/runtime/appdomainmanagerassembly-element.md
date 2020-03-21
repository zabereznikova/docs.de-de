---
title: <appDomainManagerAssembly>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 4c4ea35bff17a0e5188f26884e93cf77173a7df8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154425"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="a2c30-102">\<appDomainManagerAssembly> Element</span><span class="sxs-lookup"><span data-stu-id="a2c30-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="a2c30-103">Gibt die Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a2c30-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
<span data-ttu-id="a2c30-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a2c30-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a2c30-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="a2c30-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="a2c30-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**</span><span class="sxs-lookup"><span data-stu-id="a2c30-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2c30-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2c30-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2c30-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a2c30-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a2c30-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2c30-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2c30-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="a2c30-110">Attributes</span></span>  
  
|<span data-ttu-id="a2c30-111">attribute</span><span class="sxs-lookup"><span data-stu-id="a2c30-111">Attribute</span></span>|<span data-ttu-id="a2c30-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2c30-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="a2c30-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a2c30-113">Required attribute.</span></span> <span data-ttu-id="a2c30-114">Gibt den Anzeigenamen der Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a2c30-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2c30-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2c30-115">Child Elements</span></span>  
 <span data-ttu-id="a2c30-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="a2c30-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2c30-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2c30-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a2c30-118">Element</span><span class="sxs-lookup"><span data-stu-id="a2c30-118">Element</span></span>|<span data-ttu-id="a2c30-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2c30-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a2c30-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a2c30-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a2c30-121">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a2c30-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2c30-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a2c30-122">Remarks</span></span>  
 <span data-ttu-id="a2c30-123">Um den Typ des Anwendungsdomänen-Managers anzugeben, müssen Sie sowohl dieses Element als auch [ \<dasDomainManagerType-element>](appdomainmanagertype-element.md) angeben.</span><span class="sxs-lookup"><span data-stu-id="a2c30-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="a2c30-124">Wenn eines dieser Elemente nicht angegeben ist, wird das andere ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a2c30-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="a2c30-125">Wenn die Standardanwendungsdomäne <xref:System.TypeLoadException> geladen wird, wird ausgelöst, wenn die angegebene Assembly nicht vorhanden ist oder wenn die Assembly nicht den vom [ \<appDomainManagerType>-Element](appdomainmanagertype-element.md) angegebenen Typ enthält. und der Prozess kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="a2c30-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="a2c30-126">Wenn die Assembly gefunden wird, die Versionsinformationen jedoch nicht übereinstimmen, wird eine <xref:System.IO.FileLoadException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a2c30-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="a2c30-127">Wenn Sie den Anwendungsdomänen-Managertyp für die Standardanwendungsdomäne angeben, erben andere Anwendungsdomänen, die von der Standardanwendungsdomäne erstellt wurden, den Anwendungsdomänen-Managertyp.</span><span class="sxs-lookup"><span data-stu-id="a2c30-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="a2c30-128">Verwenden <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> Sie <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> die und Eigenschaften, um einen anderen Anwendungsdomänen-Managertyp für eine neue Anwendungsdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a2c30-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="a2c30-129">Das Angeben des Anwendungsdomänen-Managertyps erfordert, dass die Anwendung voll vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="a2c30-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="a2c30-130">(Eine Anwendung, die auf dem Desktop ausgeführt wird, hat z. B. volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht über <xref:System.TypeLoadException> die volle Vertrauenswürdigkeit verfügt, wird eine ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a2c30-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="a2c30-131">Das Format des Assemblyanzeigenamens finden <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> Sie in der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a2c30-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="a2c30-132">Dieses Konfigurationselement ist nur in .NET Framework 4 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a2c30-132">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2c30-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2c30-133">Example</span></span>  
 <span data-ttu-id="a2c30-134">Im folgenden Beispiel wird gezeigt, wie Sie angeben, dass der `MyMgr` Anwendungsdomänen-Manager für die Standardanwendungsdomäne eines Prozesses der Typ in der `AdMgrExample` Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="a2c30-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2c30-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2c30-135">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a2c30-136">\<appDomainManagerType> Element</span><span class="sxs-lookup"><span data-stu-id="a2c30-136">\<appDomainManagerType> Element</span></span>](appdomainmanagertype-element.md)
- [<span data-ttu-id="a2c30-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="a2c30-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a2c30-138">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="a2c30-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a2c30-139">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="a2c30-139">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
