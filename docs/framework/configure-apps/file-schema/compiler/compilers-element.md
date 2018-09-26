---
title: '&lt;Compiler&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 8ce303d33a83d972247609e5d02d16a4a57669ff
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47202522"
---
# <a name="ltcompilersgt-element"></a><span data-ttu-id="0d800-102">&lt;Compiler&gt; Element</span><span class="sxs-lookup"><span data-stu-id="0d800-102">&lt;compilers&gt; Element</span></span>
<span data-ttu-id="0d800-103">Der Container für Compilerkonfigurationselemente, dieser enthält 0 (null) oder mehr [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="0d800-103">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>  
  
 <span data-ttu-id="0d800-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0d800-104">\<configuration></span></span>  
<span data-ttu-id="0d800-105">\<System.CodeDom ></span><span class="sxs-lookup"><span data-stu-id="0d800-105">\<system.codedom></span></span>  
<span data-ttu-id="0d800-106">\<Compiler > Element</span><span class="sxs-lookup"><span data-stu-id="0d800-106">\<compilers> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d800-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d800-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d800-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0d800-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0d800-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0d800-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d800-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="0d800-110">Attributes</span></span>  
 <span data-ttu-id="0d800-111">Keine</span><span class="sxs-lookup"><span data-stu-id="0d800-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0d800-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0d800-112">Child Elements</span></span>  
  
|<span data-ttu-id="0d800-113">Element</span><span class="sxs-lookup"><span data-stu-id="0d800-113">Element</span></span>|<span data-ttu-id="0d800-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d800-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d800-115">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="0d800-115">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="0d800-116">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="0d800-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d800-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0d800-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0d800-118">Element</span><span class="sxs-lookup"><span data-stu-id="0d800-118">Element</span></span>|<span data-ttu-id="0d800-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d800-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d800-120">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="0d800-120">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="0d800-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0d800-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="0d800-122">\<System.CodeDom >-Element</span><span class="sxs-lookup"><span data-stu-id="0d800-122">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="0d800-123">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="0d800-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d800-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d800-124">Remarks</span></span>  
 <span data-ttu-id="0d800-125">Die [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) Element enthält die compilerkonfigurationseinstellungen für Sprachanbieter auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="0d800-125">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="0d800-126">Jede [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) Element gibt die compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="0d800-126">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="0d800-127">.NET Framework definiert die anfänglichen Compiler und sprachanbietereinstellungen in der Computerkonfigurationsdatei (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="0d800-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="0d800-128">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0d800-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="0d800-129">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="0d800-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="0d800-130">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="0d800-130">Configuration File</span></span>  
 <span data-ttu-id="0d800-131">Dieses Element kann in der Konfigurationsdatei des Computers und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0d800-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d800-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d800-132">Example</span></span>  
 <span data-ttu-id="0d800-133">Das folgende Beispiel veranschaulicht ein typisches Compilerkonfigurationselement.</span><span class="sxs-lookup"><span data-stu-id="0d800-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0d800-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d800-134">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="0d800-135">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="0d800-135">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="0d800-136">Compiler and Language Provider Settings Schema (Schema für Compiler- und Sprachanbietereinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0d800-136">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 [<span data-ttu-id="0d800-137">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="0d800-137">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
