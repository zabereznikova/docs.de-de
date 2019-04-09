---
title: Schema für Compiler- und Sprachanbietereinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- configuration settings [.NET Framework], compilers
- compiler configuration elements, schema
- compiler configuration elements
- language providers
- compiler configuration settings, schema
- configuration schema [.NET Framework], compiler settings
- language providers, settings schema
- compiler configuration settings
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
ms.openlocfilehash: fe08ac5dc0600e0861bb349ce99875af8658eb4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187446"
---
# <a name="compiler-and-language-provider-settings-schema"></a><span data-ttu-id="5c8e7-102">Schema für Compiler- und Sprachanbietereinstellungen</span><span class="sxs-lookup"><span data-stu-id="5c8e7-102">Compiler and Language Provider Settings Schema</span></span>
<span data-ttu-id="5c8e7-103">Die Compiler- und Sprachanbietereinstellungen geben Compilerkonfigurationselemente für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="5c8e7-103">Compiler and language provider settings specify compiler configuration elements for available language providers.</span></span> <span data-ttu-id="5c8e7-104">Jedes Compilerkonfigurationselement gibt den Typnamen des Codeanbieters, Compilerparameter, unterstützte Sprachnamen und unterstützte Dateierweiterungen an.</span><span class="sxs-lookup"><span data-stu-id="5c8e7-104">Each compiler configuration element specifies the code provider type name, compiler parameters, supported language names, and supported file extensions.</span></span>  
  
 <span data-ttu-id="5c8e7-105">.NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5c8e7-105">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="5c8e7-106">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5c8e7-106">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="5c8e7-107">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="5c8e7-107">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
 [<span data-ttu-id="5c8e7-108">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="5c8e7-108">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="5c8e7-109">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="5c8e7-109">\<system.codedom></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)  
  
 [<span data-ttu-id="5c8e7-110">\<compilers></span><span class="sxs-lookup"><span data-stu-id="5c8e7-110">\<compilers></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
  
 [<span data-ttu-id="5c8e7-111">\<compiler></span><span class="sxs-lookup"><span data-stu-id="5c8e7-111">\<compiler></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)  
  
|<span data-ttu-id="5c8e7-112">Element</span><span class="sxs-lookup"><span data-stu-id="5c8e7-112">Element</span></span>|<span data-ttu-id="5c8e7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c8e7-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c8e7-114">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="5c8e7-114">\<system.codedom></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="5c8e7-115">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="5c8e7-115">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="5c8e7-116">\<compilers></span><span class="sxs-lookup"><span data-stu-id="5c8e7-116">\<compilers></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="5c8e7-117">Der Container für Compilerkonfigurationselemente, dieser enthält 0 (null) oder mehr [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="5c8e7-117">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>|  
|[<span data-ttu-id="5c8e7-118">\<compiler></span><span class="sxs-lookup"><span data-stu-id="5c8e7-118">\<compiler></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="5c8e7-119">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="5c8e7-119">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5c8e7-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c8e7-120">Example</span></span>  
 <span data-ttu-id="5c8e7-121">Das folgende Beispiel veranschaulicht ein typisches Compilerkonfigurationselement.</span><span class="sxs-lookup"><span data-stu-id="5c8e7-121">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler  
          language="c#;cs;csharp"  
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""  
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c8e7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c8e7-122">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="5c8e7-123">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="5c8e7-123">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="5c8e7-124">\<Compilerfehler >-Element</span><span class="sxs-lookup"><span data-stu-id="5c8e7-124">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
