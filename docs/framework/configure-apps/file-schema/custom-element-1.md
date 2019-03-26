---
title: Custom Element for SingleTagSectionHandler element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: guardrex
ms.author: mairaw
ms.openlocfilehash: bfc2a916e37ac27d45746eb268912b3752f4d80f
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2019
ms.locfileid: "58464436"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="e7e2a-102">Custom Element for SingleTagSectionHandler element</span><span class="sxs-lookup"><span data-stu-id="e7e2a-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="e7e2a-103">Definiert die Einstellungen in einem benutzerdefinierten Konfigurationsabschnitt, der durch definiert ist eine \<Abschnitt >-Element und verwendet die <xref:System.Configuration.SingleTagSectionHandler> Klasse.</span><span class="sxs-lookup"><span data-stu-id="e7e2a-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="e7e2a-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e7e2a-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="e7e2a-105">&nbsp;&nbsp;*\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="e7e2a-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="e7e2a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7e2a-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="e7e2a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e7e2a-107">Attributes</span></span>

<span data-ttu-id="e7e2a-108">Attribute und Attributwerte sind benutzerdefiniert.</span><span class="sxs-lookup"><span data-stu-id="e7e2a-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="e7e2a-109">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="e7e2a-109">Parent element</span></span>

|     | <span data-ttu-id="e7e2a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7e2a-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e7e2a-111">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="e7e2a-111">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="e7e2a-112">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e7e2a-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e7e2a-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e7e2a-113">Child elements</span></span>

<span data-ttu-id="e7e2a-114">Keiner</span><span class="sxs-lookup"><span data-stu-id="e7e2a-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="e7e2a-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7e2a-115">Remarks</span></span>

<span data-ttu-id="e7e2a-116">Die  **\<SectionName >** Element ist ein benutzerdefiniertes Element, das definiert, indem eine [  **\<Abschnitt >** ](~/docs/framework/configure-apps/file-schema/section-element.md) -Tag in die [  **\<ConfigSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e7e2a-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="e7e2a-117">Gibt zurück, das Konfigurationssystem eine <xref:System.Collections.IDictionary> Objekt beim Aufrufen <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e7e2a-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="e7e2a-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7e2a-118">Example</span></span>

<span data-ttu-id="e7e2a-119">Das folgende Beispiel deklariert ein benutzerdefiniertes Element namens  **\<SampleSection >** , das Lesen von Einstellungen enthält die <xref:System.Configuration.SingleTagSectionHandler> Klasse:</span><span class="sxs-lookup"><span data-stu-id="e7e2a-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection" 
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="e7e2a-120">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="e7e2a-120">Configuration file</span></span>

<span data-ttu-id="e7e2a-121">Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="e7e2a-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7e2a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7e2a-122">See also</span></span>

- [<span data-ttu-id="e7e2a-123">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e7e2a-123">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
