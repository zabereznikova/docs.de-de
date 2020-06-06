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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155413"
---
# <a name="compilers-element"></a><span data-ttu-id="66e91-102">\<compilers>-Element</span><span class="sxs-lookup"><span data-stu-id="66e91-102">\<compilers> Element</span></span>
<span data-ttu-id="66e91-103">Container für Compilerkonfigurationselemente; enthält 0 (null) oder mehr- [\<compiler>](compiler-element.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="66e91-103">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**

## <a name="syntax"></a><span data-ttu-id="66e91-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="66e91-104">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66e91-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="66e91-105">Attributes and Elements</span></span>  
 <span data-ttu-id="66e91-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="66e91-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66e91-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="66e91-107">Attributes</span></span>  
 <span data-ttu-id="66e91-108">Keine</span><span class="sxs-lookup"><span data-stu-id="66e91-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="66e91-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="66e91-109">Child Elements</span></span>  
  
|<span data-ttu-id="66e91-110">Element</span><span class="sxs-lookup"><span data-stu-id="66e91-110">Element</span></span>|<span data-ttu-id="66e91-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="66e91-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66e91-112">\<compiler>Gewisses</span><span class="sxs-lookup"><span data-stu-id="66e91-112">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="66e91-113">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="66e91-113">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="66e91-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="66e91-114">Parent Elements</span></span>  
  
|<span data-ttu-id="66e91-115">Element</span><span class="sxs-lookup"><span data-stu-id="66e91-115">Element</span></span>|<span data-ttu-id="66e91-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="66e91-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66e91-117">\<configuration>Gewisses</span><span class="sxs-lookup"><span data-stu-id="66e91-117">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="66e91-118">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="66e91-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="66e91-119">\<system.codedom>Gewisses</span><span class="sxs-lookup"><span data-stu-id="66e91-119">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="66e91-120">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="66e91-120">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66e91-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="66e91-121">Remarks</span></span>  
 <span data-ttu-id="66e91-122">Das- [\<compilers>](compilers-element.md) Element enthält die Compilerkonfigurationseinstellungen für Sprachanbieter auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="66e91-122">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="66e91-123">Jedes- [\<compiler>](compiler-element.md) Element gibt die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="66e91-123">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="66e91-124">In der-.NET Framework werden die anfänglichen Compiler-und Sprachanbieter Einstellungen in der Computer Konfigurationsdatei (Machine. config) definiert.</span><span class="sxs-lookup"><span data-stu-id="66e91-124">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="66e91-125">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="66e91-125">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="66e91-126">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="66e91-126">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="66e91-127">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="66e91-127">Configuration File</span></span>  
 <span data-ttu-id="66e91-128">Dieses Element kann in der Computer Konfigurationsdatei und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="66e91-128">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66e91-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="66e91-129">Example</span></span>  
 <span data-ttu-id="66e91-130">Das folgende Beispiel veranschaulicht ein typisches Compilerkonfigurationselement.</span><span class="sxs-lookup"><span data-stu-id="66e91-130">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="66e91-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66e91-131">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="66e91-132">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="66e91-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="66e91-133">Schema für Compiler- und Sprachanbietereinstellungen</span><span class="sxs-lookup"><span data-stu-id="66e91-133">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="66e91-134">\<compiler>Gewisses</span><span class="sxs-lookup"><span data-stu-id="66e91-134">\<compiler> Element</span></span>](compiler-element.md)
