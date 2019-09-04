---
title: <appDomainManagerType>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ffb297cc38f20917e720b216607e9ccfc966866
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252829"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="7b9e3-102">\<AppDomainManagerType >-Element</span><span class="sxs-lookup"><span data-stu-id="7b9e3-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="7b9e3-103">Gibt den Typ an, der als Anwendungsdomänen-Manager für die Standardanwendungsdomäne dient.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
<span data-ttu-id="7b9e3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7b9e3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7b9e3-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="7b9e3-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="7b9e3-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<appDomainManagerType>**</span><span class="sxs-lookup"><span data-stu-id="7b9e3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b9e3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b9e3-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b9e3-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7b9e3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7b9e3-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b9e3-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="7b9e3-110">Attributes</span></span>  
  
|<span data-ttu-id="7b9e3-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="7b9e3-111">Attribute</span></span>|<span data-ttu-id="7b9e3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b9e3-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="7b9e3-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-113">Required attribute.</span></span> <span data-ttu-id="7b9e3-114">Gibt den Namen des Typs einschließlich des Namespace an, der als Anwendungs Domänen-Manager für die Standard Anwendungsdomäne im Prozess dient.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b9e3-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b9e3-115">Child Elements</span></span>  
 <span data-ttu-id="7b9e3-116">Keine</span><span class="sxs-lookup"><span data-stu-id="7b9e3-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b9e3-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b9e3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7b9e3-118">Element</span><span class="sxs-lookup"><span data-stu-id="7b9e3-118">Element</span></span>|<span data-ttu-id="7b9e3-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b9e3-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7b9e3-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7b9e3-121">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b9e3-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b9e3-122">Remarks</span></span>  
 <span data-ttu-id="7b9e3-123">Um den Typ des Anwendungs Domänen-Managers anzugeben, müssen Sie sowohl dieses Element als auch das [ \<AppDomainManagerAssembly->](appdomainmanagerassembly-element.md) Element angeben.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="7b9e3-124">Wenn keines dieser Elemente angegeben ist, wird das andere ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="7b9e3-125">Wenn die Standard Anwendungsdomäne geladen wird, <xref:System.TypeLoadException> wird ausgelöst, wenn der angegebene Typ nicht in der Assembly vorhanden ist, die durch das [ \<> Element AppDomainManagerAssembly](appdomainmanagerassembly-element.md) angegeben wird. der Prozess kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="7b9e3-126">Wenn Sie den Anwendungs Domänen-Manager für die Standard Anwendungsdomäne angeben, erben andere Anwendungs Domänen, die aus der Standard Anwendungsdomäne erstellt wurden, den Typ des Anwendungs Domänen-Managers.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="7b9e3-127">Verwenden Sie <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> die <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> Eigenschaften und, um einen anderen Anwendungs Domänen-Manager-Typ für eine neue Anwendungsdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="7b9e3-128">Die Angabe des Anwendungs Domänen-Manager-Typs erfordert, dass die Anwendung volle Vertrauenswürdigkeit besitzt.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="7b9e3-129">(Eine Anwendung, die auf dem Desktop ausgeführt wird, hat beispielsweise volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht über volle Vertrauenswürdigkeit verfügt, <xref:System.TypeLoadException> wird eine ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="7b9e3-130">Das Format des Typs und Namespace entspricht dem Format, das für die <xref:System.Type.FullName%2A?displayProperty=nameWithType> Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="7b9e3-131">Dieses Konfigurationselement ist nur in den .NET Framework 4 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b9e3-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b9e3-132">Example</span></span>  
 <span data-ttu-id="7b9e3-133">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass der Anwendungs Domänen-Manager für die Standard Anwendungsdomäne `MyMgr` eines Prozesses der `AdMgrExample` Typ in der Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="7b9e3-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b9e3-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b9e3-134">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7b9e3-135">\<AppDomainManagerAssembly-> Element</span><span class="sxs-lookup"><span data-stu-id="7b9e3-135">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="7b9e3-136">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="7b9e3-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7b9e3-137">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="7b9e3-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7b9e3-138">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="7b9e3-138">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
