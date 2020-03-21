---
title: <appDomainManagerType>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154424"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="306ff-102">\<appDomainManagerType> Element</span><span class="sxs-lookup"><span data-stu-id="306ff-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="306ff-103">Gibt den Typ an, der als Anwendungsdomänen-Manager für die Standardanwendungsdomäne dient.</span><span class="sxs-lookup"><span data-stu-id="306ff-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
<span data-ttu-id="306ff-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="306ff-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="306ff-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="306ff-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="306ff-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**</span><span class="sxs-lookup"><span data-stu-id="306ff-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="306ff-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="306ff-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="306ff-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="306ff-108">Attributes and Elements</span></span>  
 <span data-ttu-id="306ff-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="306ff-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="306ff-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="306ff-110">Attributes</span></span>  
  
|<span data-ttu-id="306ff-111">attribute</span><span class="sxs-lookup"><span data-stu-id="306ff-111">Attribute</span></span>|<span data-ttu-id="306ff-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="306ff-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="306ff-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="306ff-113">Required attribute.</span></span> <span data-ttu-id="306ff-114">Gibt den Namen des Typs an, einschließlich des Namespace, der als Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess dient.</span><span class="sxs-lookup"><span data-stu-id="306ff-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="306ff-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="306ff-115">Child Elements</span></span>  
 <span data-ttu-id="306ff-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="306ff-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="306ff-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="306ff-117">Parent Elements</span></span>  
  
|<span data-ttu-id="306ff-118">Element</span><span class="sxs-lookup"><span data-stu-id="306ff-118">Element</span></span>|<span data-ttu-id="306ff-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="306ff-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="306ff-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="306ff-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="306ff-121">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="306ff-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="306ff-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="306ff-122">Remarks</span></span>  
 <span data-ttu-id="306ff-123">Um den Typ des Anwendungsdomänen-Managers anzugeben, müssen Sie sowohl dieses Element als auch das [ \<appDomainManagerAssembly->-Element](appdomainmanagerassembly-element.md) angeben.</span><span class="sxs-lookup"><span data-stu-id="306ff-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="306ff-124">Wenn eines dieser Elemente nicht angegeben ist, wird das andere ignoriert.</span><span class="sxs-lookup"><span data-stu-id="306ff-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="306ff-125">Wenn die Standardanwendungsdomäne <xref:System.TypeLoadException> geladen wird, wird ausgelöst, wenn der angegebene Typ nicht in der Assembly vorhanden ist, die [ \<vom appDomainManagerAssembly->-Element](appdomainmanagerassembly-element.md) angegeben wird. und der Prozess kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="306ff-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="306ff-126">Wenn Sie den Anwendungsdomänen-Managertyp für die Standardanwendungsdomäne angeben, erben andere Anwendungsdomänen, die von der Standardanwendungsdomäne erstellt wurden, den Anwendungsdomänen-Managertyp.</span><span class="sxs-lookup"><span data-stu-id="306ff-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="306ff-127">Verwenden <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> Sie <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> die und Eigenschaften, um einen anderen Anwendungsdomänen-Managertyp für eine neue Anwendungsdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="306ff-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="306ff-128">Das Angeben des Anwendungsdomänen-Managertyps erfordert, dass die Anwendung voll vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="306ff-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="306ff-129">(Eine Anwendung, die auf dem Desktop ausgeführt wird, hat z. B. volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht über <xref:System.TypeLoadException> die volle Vertrauenswürdigkeit verfügt, wird eine ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="306ff-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="306ff-130">Das Format des Typs und namespace ist das <xref:System.Type.FullName%2A?displayProperty=nameWithType> gleiche Format, das für die Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="306ff-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="306ff-131">Dieses Konfigurationselement ist nur in .NET Framework 4 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="306ff-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="306ff-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="306ff-132">Example</span></span>  
 <span data-ttu-id="306ff-133">Im folgenden Beispiel wird gezeigt, wie Sie angeben, dass der `MyMgr` Anwendungsdomänen-Manager für die Standardanwendungsdomäne eines Prozesses der Typ in der `AdMgrExample` Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="306ff-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="306ff-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="306ff-134">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="306ff-135">\<appDomainManagerAssembly> Element</span><span class="sxs-lookup"><span data-stu-id="306ff-135">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="306ff-136">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="306ff-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="306ff-137">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="306ff-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="306ff-138">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="306ff-138">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
