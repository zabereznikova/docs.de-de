---
title: <compilers>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
ms.openlocfilehash: 15beb15d7927d616cc09c7e318ef26a6627926af
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260605"
---
# <a name="compilers-element"></a><span data-ttu-id="b5e32-102">\<Compiler > Element</span><span class="sxs-lookup"><span data-stu-id="b5e32-102">\<compilers> Element</span></span>
<span data-ttu-id="b5e32-103">Der Container für Compilerkonfigurationselemente, dieser enthält 0 (null) oder mehr [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="b5e32-103">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>  
  
 <span data-ttu-id="b5e32-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b5e32-104">\<configuration></span></span>  
<span data-ttu-id="b5e32-105">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="b5e32-105">\<system.codedom></span></span>  
<span data-ttu-id="b5e32-106">\<Compiler > Element</span><span class="sxs-lookup"><span data-stu-id="b5e32-106">\<compilers> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5e32-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5e32-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5e32-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b5e32-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b5e32-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5e32-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5e32-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b5e32-110">Attributes</span></span>  
 <span data-ttu-id="b5e32-111">Keine</span><span class="sxs-lookup"><span data-stu-id="b5e32-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b5e32-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b5e32-112">Child Elements</span></span>  
  
|<span data-ttu-id="b5e32-113">Element</span><span class="sxs-lookup"><span data-stu-id="b5e32-113">Element</span></span>|<span data-ttu-id="b5e32-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5e32-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5e32-115">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="b5e32-115">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="b5e32-116">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="b5e32-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5e32-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b5e32-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b5e32-118">Element</span><span class="sxs-lookup"><span data-stu-id="b5e32-118">Element</span></span>|<span data-ttu-id="b5e32-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5e32-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5e32-120">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="b5e32-120">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="b5e32-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b5e32-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="b5e32-122">\<System.CodeDom >-Element</span><span class="sxs-lookup"><span data-stu-id="b5e32-122">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="b5e32-123">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="b5e32-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5e32-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5e32-124">Remarks</span></span>  
 <span data-ttu-id="b5e32-125">Die [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) Element enthält die compilerkonfigurationseinstellungen für Sprachanbieter auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="b5e32-125">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="b5e32-126">Jede [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) Element gibt die compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="b5e32-126">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="b5e32-127">.NET Framework definiert die anfänglichen Compiler und sprachanbietereinstellungen in der Computerkonfigurationsdatei (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b5e32-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="b5e32-128">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b5e32-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="b5e32-129">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="b5e32-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="b5e32-130">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="b5e32-130">Configuration File</span></span>  
 <span data-ttu-id="b5e32-131">Dieses Element kann in der Konfigurationsdatei des Computers und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5e32-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5e32-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5e32-132">Example</span></span>  
 <span data-ttu-id="b5e32-133">Das folgende Beispiel veranschaulicht ein typisches Compilerkonfigurationselement.</span><span class="sxs-lookup"><span data-stu-id="b5e32-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b5e32-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5e32-134">See also</span></span>
- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="b5e32-135">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b5e32-135">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="b5e32-136">Compiler and Language Provider Settings Schema (Schema für Compiler- und Sprachanbietereinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b5e32-136">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)
- [<span data-ttu-id="b5e32-137">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="b5e32-137">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
