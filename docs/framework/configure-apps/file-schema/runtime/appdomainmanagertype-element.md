---
title: <appDomainManagerType>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: e21384de6ca07c637a79ee54207d1e3ddfbf20e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170310"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="e82f2-102">\<appDomainManagerType>-Element</span><span class="sxs-lookup"><span data-stu-id="e82f2-102">\<appDomainManagerType> Element</span></span>

<span data-ttu-id="e82f2-103">Gibt den Typ an, der als Anwendungsdomänen-Manager für die Standardanwendungsdomäne dient.</span><span class="sxs-lookup"><span data-stu-id="e82f2-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**  
  
## <a name="syntax"></a><span data-ttu-id="e82f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e82f2-104">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e82f2-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e82f2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e82f2-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e82f2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e82f2-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e82f2-107">Attributes</span></span>  
  
|<span data-ttu-id="e82f2-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e82f2-108">Attribute</span></span>|<span data-ttu-id="e82f2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e82f2-109">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="e82f2-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="e82f2-110">Required attribute.</span></span> <span data-ttu-id="e82f2-111">Gibt den Namen des Typs einschließlich des Namespace an, der als Anwendungs Domänen-Manager für die Standard Anwendungsdomäne im Prozess dient.</span><span class="sxs-lookup"><span data-stu-id="e82f2-111">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e82f2-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e82f2-112">Child Elements</span></span>  

 <span data-ttu-id="e82f2-113">Keine</span><span class="sxs-lookup"><span data-stu-id="e82f2-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e82f2-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e82f2-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e82f2-115">Element</span><span class="sxs-lookup"><span data-stu-id="e82f2-115">Element</span></span>|<span data-ttu-id="e82f2-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e82f2-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e82f2-117">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e82f2-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e82f2-118">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e82f2-118">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e82f2-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e82f2-119">Remarks</span></span>  

 <span data-ttu-id="e82f2-120">Um den Typ des Anwendungs Domänen-Managers anzugeben, müssen Sie sowohl dieses Element als auch das- [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) Element angeben.</span><span class="sxs-lookup"><span data-stu-id="e82f2-120">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="e82f2-121">Wenn keines dieser Elemente angegeben ist, wird das andere ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e82f2-121">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="e82f2-122">Wenn die Standard Anwendungsdomäne geladen wird, <xref:System.TypeLoadException> wird ausgelöst, wenn der angegebene Typ in der Assembly, die vom-Element angegeben ist, nicht vorhanden ist [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) . der Prozess kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="e82f2-122">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="e82f2-123">Wenn Sie den Anwendungs Domänen-Manager für die Standard Anwendungsdomäne angeben, erben andere Anwendungs Domänen, die aus der Standard Anwendungsdomäne erstellt wurden, den Typ des Anwendungs Domänen-Managers.</span><span class="sxs-lookup"><span data-stu-id="e82f2-123">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="e82f2-124">Verwenden <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> Sie die <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> Eigenschaften und, um einen anderen Anwendungs Domänen-Manager-Typ für eine neue Anwendungsdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e82f2-124">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="e82f2-125">Die Angabe des Anwendungs Domänen-Manager-Typs erfordert, dass die Anwendung volle Vertrauenswürdigkeit besitzt.</span><span class="sxs-lookup"><span data-stu-id="e82f2-125">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="e82f2-126">(Eine Anwendung, die auf dem Desktop ausgeführt wird, hat beispielsweise volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht über volle Vertrauenswürdigkeit verfügt, <xref:System.TypeLoadException> wird eine ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e82f2-126">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="e82f2-127">Das Format des Typs und Namespace entspricht dem Format, das für die Eigenschaft verwendet wird <xref:System.Type.FullName%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e82f2-127">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="e82f2-128">Dieses Konfigurationselement ist nur in den .NET Framework 4 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e82f2-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e82f2-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e82f2-129">Example</span></span>  

 <span data-ttu-id="e82f2-130">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass der Anwendungs Domänen-Manager für die Standard Anwendungsdomäne eines Prozesses der `MyMgr` Typ in der `AdMgrExample` Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="e82f2-130">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e82f2-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e82f2-131">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e82f2-132">\<appDomainManagerAssembly>-Element</span><span class="sxs-lookup"><span data-stu-id="e82f2-132">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="e82f2-133">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="e82f2-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e82f2-134">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="e82f2-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e82f2-135">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="e82f2-135">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
