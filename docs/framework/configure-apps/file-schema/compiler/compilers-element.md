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
ms.openlocfilehash: 09b1efe321c39402c9280eda0e9def9112462470
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155413"
---
# <a name="compilers-element"></a><span data-ttu-id="527e4-102">\<Compiler> Element</span><span class="sxs-lookup"><span data-stu-id="527e4-102">\<compilers> Element</span></span>
<span data-ttu-id="527e4-103">Container für Compilerkonfigurationselemente; enthält null oder mehr [ \<Compiler>](compiler-element.md) Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="527e4-103">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  

<span data-ttu-id="527e4-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="527e4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="527e4-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="527e4-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="527e4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Compiler>**</span><span class="sxs-lookup"><span data-stu-id="527e4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**</span></span>

## <a name="syntax"></a><span data-ttu-id="527e4-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="527e4-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="527e4-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="527e4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="527e4-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="527e4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="527e4-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="527e4-110">Attributes</span></span>  
 <span data-ttu-id="527e4-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="527e4-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="527e4-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="527e4-112">Child Elements</span></span>  
  
|<span data-ttu-id="527e4-113">Element</span><span class="sxs-lookup"><span data-stu-id="527e4-113">Element</span></span>|<span data-ttu-id="527e4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="527e4-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="527e4-115">\<Compiler> Element</span><span class="sxs-lookup"><span data-stu-id="527e4-115">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="527e4-116">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="527e4-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="527e4-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="527e4-117">Parent Elements</span></span>  
  
|<span data-ttu-id="527e4-118">Element</span><span class="sxs-lookup"><span data-stu-id="527e4-118">Element</span></span>|<span data-ttu-id="527e4-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="527e4-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="527e4-120">\<Konfiguration> Element</span><span class="sxs-lookup"><span data-stu-id="527e4-120">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="527e4-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="527e4-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="527e4-122">\<system.codedom> Element</span><span class="sxs-lookup"><span data-stu-id="527e4-122">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="527e4-123">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="527e4-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="527e4-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="527e4-124">Remarks</span></span>  
 <span data-ttu-id="527e4-125">Die [ \<Compiler>](compilers-element.md) Element die Compilerkonfigurationseinstellungen für Sprachanbieter auf einem Computer enthält.</span><span class="sxs-lookup"><span data-stu-id="527e4-125">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="527e4-126">Jeder [ \<Compiler>-Element](compiler-element.md) die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter angibt.</span><span class="sxs-lookup"><span data-stu-id="527e4-126">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="527e4-127">.NET Framework definiert die anfänglichen Compiler- und Sprachanbietereinstellungen in der Computerkonfigurationsdatei (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="527e4-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="527e4-128">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="527e4-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="527e4-129">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="527e4-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="527e4-130">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="527e4-130">Configuration File</span></span>  
 <span data-ttu-id="527e4-131">Dieses Element kann in der Maschinenkonfigurationsdatei und in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="527e4-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="527e4-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="527e4-132">Example</span></span>  
 <span data-ttu-id="527e4-133">Das folgende Beispiel veranschaulicht ein typisches Compilerkonfigurationselement.</span><span class="sxs-lookup"><span data-stu-id="527e4-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="527e4-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="527e4-134">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="527e4-135">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="527e4-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="527e4-136">Compiler- und Sprachanbietereinstellungen Schema</span><span class="sxs-lookup"><span data-stu-id="527e4-136">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="527e4-137">\<Compiler> Element</span><span class="sxs-lookup"><span data-stu-id="527e4-137">\<compiler> Element</span></span>](compiler-element.md)
