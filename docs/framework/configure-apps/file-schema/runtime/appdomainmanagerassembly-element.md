---
title: <appDomainManagerAssembly>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 1716b11106775bed2c0d6ccb62e8d5b032b6e8be
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176135"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="21593-102">\<appDomainManagerAssembly>-Element</span><span class="sxs-lookup"><span data-stu-id="21593-102">\<appDomainManagerAssembly> Element</span></span>

<span data-ttu-id="21593-103">Gibt die Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="21593-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="21593-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21593-104">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21593-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="21593-105">Attributes and Elements</span></span>  

 <span data-ttu-id="21593-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="21593-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21593-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="21593-107">Attributes</span></span>  
  
|<span data-ttu-id="21593-108">attribute</span><span class="sxs-lookup"><span data-stu-id="21593-108">Attribute</span></span>|<span data-ttu-id="21593-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21593-109">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="21593-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="21593-110">Required attribute.</span></span> <span data-ttu-id="21593-111">Gibt den anzeigen amen der Assembly an, die den Anwendungs Domänen-Manager für die Standard Anwendungsdomäne im Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="21593-111">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21593-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="21593-112">Child Elements</span></span>  

 <span data-ttu-id="21593-113">Keine</span><span class="sxs-lookup"><span data-stu-id="21593-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="21593-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="21593-114">Parent Elements</span></span>  
  
|<span data-ttu-id="21593-115">Element</span><span class="sxs-lookup"><span data-stu-id="21593-115">Element</span></span>|<span data-ttu-id="21593-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21593-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="21593-117">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="21593-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="21593-118">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="21593-118">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21593-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="21593-119">Remarks</span></span>  

 <span data-ttu-id="21593-120">Um den Typ des Anwendungs Domänen-Managers anzugeben, müssen Sie sowohl dieses Element als auch das- [\<appDomainManagerType>](appdomainmanagertype-element.md) Element angeben.</span><span class="sxs-lookup"><span data-stu-id="21593-120">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="21593-121">Wenn keines dieser Elemente angegeben ist, wird das andere ignoriert.</span><span class="sxs-lookup"><span data-stu-id="21593-121">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="21593-122">Wenn die Standard Anwendungsdomäne geladen wird, <xref:System.TypeLoadException> wird ausgelöst, wenn die angegebene Assembly nicht vorhanden ist oder wenn die Assembly nicht den Typ enthält, der vom-Element angegeben wird [\<appDomainManagerType>](appdomainmanagertype-element.md) . der Prozess kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="21593-122">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="21593-123">Wenn die Assembly gefunden wird, die Versionsinformationen aber nicht stimmen, wird eine ausgelöst <xref:System.IO.FileLoadException> .</span><span class="sxs-lookup"><span data-stu-id="21593-123">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="21593-124">Wenn Sie den Anwendungs Domänen-Manager für die Standard Anwendungsdomäne angeben, erben andere Anwendungs Domänen, die aus der Standard Anwendungsdomäne erstellt wurden, den Typ des Anwendungs Domänen-Managers.</span><span class="sxs-lookup"><span data-stu-id="21593-124">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="21593-125">Verwenden <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> Sie die <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> Eigenschaften und, um einen anderen Anwendungs Domänen-Manager-Typ für eine neue Anwendungsdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="21593-125">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="21593-126">Die Angabe des Anwendungs Domänen-Manager-Typs erfordert, dass die Anwendung volle Vertrauenswürdigkeit besitzt.</span><span class="sxs-lookup"><span data-stu-id="21593-126">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="21593-127">(Eine Anwendung, die auf dem Desktop ausgeführt wird, hat beispielsweise volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht über volle Vertrauenswürdigkeit verfügt, <xref:System.TypeLoadException> wird eine ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="21593-127">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="21593-128">Das Format des Assemblyanzeigenamen finden Sie unter der- <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="21593-128">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="21593-129">Dieses Konfigurationselement ist nur in den .NET Framework 4 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="21593-129">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21593-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21593-130">Example</span></span>  

 <span data-ttu-id="21593-131">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass der Anwendungs Domänen-Manager für die Standard Anwendungsdomäne eines Prozesses der `MyMgr` Typ in der `AdMgrExample` Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="21593-131">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="21593-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21593-132">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="21593-133">\<appDomainManagerType>-Element</span><span class="sxs-lookup"><span data-stu-id="21593-133">\<appDomainManagerType> Element</span></span>](appdomainmanagertype-element.md)
- [<span data-ttu-id="21593-134">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="21593-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="21593-135">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="21593-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="21593-136">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="21593-136">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
