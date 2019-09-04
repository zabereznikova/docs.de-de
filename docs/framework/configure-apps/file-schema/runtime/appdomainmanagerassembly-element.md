---
title: <appDomainManagerAssembly>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 083e3ba21dcd196eacfe3d9fd649c211da9dc125
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252852"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="09d8c-102">\<AppDomainManagerAssembly-> Element</span><span class="sxs-lookup"><span data-stu-id="09d8c-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="09d8c-103">Gibt die Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="09d8c-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
<span data-ttu-id="09d8c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="09d8c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="09d8c-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="09d8c-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="09d8c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<appDomainManagerAssembly>**</span><span class="sxs-lookup"><span data-stu-id="09d8c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d8c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="09d8c-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09d8c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="09d8c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="09d8c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="09d8c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09d8c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="09d8c-110">Attributes</span></span>  
  
|<span data-ttu-id="09d8c-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="09d8c-111">Attribute</span></span>|<span data-ttu-id="09d8c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09d8c-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="09d8c-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="09d8c-113">Required attribute.</span></span> <span data-ttu-id="09d8c-114">Gibt den anzeigen amen der Assembly an, die den Anwendungs Domänen-Manager für die Standard Anwendungsdomäne im Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="09d8c-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09d8c-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="09d8c-115">Child Elements</span></span>  
 <span data-ttu-id="09d8c-116">Keine</span><span class="sxs-lookup"><span data-stu-id="09d8c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="09d8c-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="09d8c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="09d8c-118">Element</span><span class="sxs-lookup"><span data-stu-id="09d8c-118">Element</span></span>|<span data-ttu-id="09d8c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09d8c-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="09d8c-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="09d8c-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="09d8c-121">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="09d8c-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09d8c-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="09d8c-122">Remarks</span></span>  
 <span data-ttu-id="09d8c-123">Um den Typ des Anwendungs Domänen-Managers anzugeben, müssen Sie sowohl dieses Element als auch das [ \<AppDomainManagerType->](appdomainmanagertype-element.md) Element angeben.</span><span class="sxs-lookup"><span data-stu-id="09d8c-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="09d8c-124">Wenn keines dieser Elemente angegeben ist, wird das andere ignoriert.</span><span class="sxs-lookup"><span data-stu-id="09d8c-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="09d8c-125">Wenn die Standard Anwendungsdomäne geladen wird, <xref:System.TypeLoadException> wird ausgelöst, wenn die angegebene Assembly nicht vorhanden ist oder wenn die Assembly nicht den Typ enthält, der [ \<vom AppDomainManagerType->](appdomainmanagertype-element.md) Element angegeben wird, und der Prozess fehlschlägt. begonnen.</span><span class="sxs-lookup"><span data-stu-id="09d8c-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="09d8c-126">Wenn die Assembly gefunden wird, die Versionsinformationen aber nicht stimmen, wird <xref:System.IO.FileLoadException> eine ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="09d8c-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="09d8c-127">Wenn Sie den Anwendungs Domänen-Manager für die Standard Anwendungsdomäne angeben, erben andere Anwendungs Domänen, die aus der Standard Anwendungsdomäne erstellt wurden, den Typ des Anwendungs Domänen-Managers.</span><span class="sxs-lookup"><span data-stu-id="09d8c-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="09d8c-128">Verwenden Sie <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> die <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> Eigenschaften und, um einen anderen Anwendungs Domänen-Manager-Typ für eine neue Anwendungsdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="09d8c-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="09d8c-129">Die Angabe des Anwendungs Domänen-Manager-Typs erfordert, dass die Anwendung volle Vertrauenswürdigkeit besitzt.</span><span class="sxs-lookup"><span data-stu-id="09d8c-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="09d8c-130">(Eine Anwendung, die auf dem Desktop ausgeführt wird, hat beispielsweise volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht über volle Vertrauenswürdigkeit verfügt, <xref:System.TypeLoadException> wird eine ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="09d8c-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="09d8c-131">Das Format des Assemblyanzeigenamen finden Sie <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> unter der-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="09d8c-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="09d8c-132">Dieses Konfigurationselement ist nur in den .NET Framework 4 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="09d8c-132">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09d8c-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="09d8c-133">Example</span></span>  
 <span data-ttu-id="09d8c-134">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass der Anwendungs Domänen-Manager für die Standard Anwendungsdomäne `MyMgr` eines Prozesses der `AdMgrExample` Typ in der Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="09d8c-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="09d8c-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09d8c-135">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="09d8c-136">\<AppDomainManagerType >-Element</span><span class="sxs-lookup"><span data-stu-id="09d8c-136">\<appDomainManagerType> Element</span></span>](appdomainmanagertype-element.md)
- [<span data-ttu-id="09d8c-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="09d8c-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="09d8c-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="09d8c-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="09d8c-139">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="09d8c-139">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
