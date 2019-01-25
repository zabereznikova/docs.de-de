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
ms.openlocfilehash: 232ad7527e65fd38fa471cccc917752aef766a88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628837"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="70f22-102">Custom Element for SingleTagSectionHandler element</span><span class="sxs-lookup"><span data-stu-id="70f22-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="70f22-103">Definiert die Einstellungen in einem benutzerdefinierten Konfigurationsabschnitt, der durch definiert ist ein</span><span class="sxs-lookup"><span data-stu-id="70f22-103">Defines settings in a custom configuration section that is defined by a</span></span> <section> <span data-ttu-id="70f22-104">Element- und verwendet die <xref:System.Configuration.SingleTagSectionHandler> Klasse.</span><span class="sxs-lookup"><span data-stu-id="70f22-104">element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="70f22-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="70f22-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="70f22-106">&nbsp;&nbsp;*\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="70f22-106">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="70f22-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="70f22-107">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="70f22-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="70f22-108">Attributes</span></span>

<span data-ttu-id="70f22-109">Attribute und Attributwerte sind benutzerdefiniert.</span><span class="sxs-lookup"><span data-stu-id="70f22-109">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="70f22-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="70f22-110">Parent element</span></span>

|     | <span data-ttu-id="70f22-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70f22-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="70f22-112">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="70f22-112">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="70f22-113">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="70f22-113">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="70f22-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="70f22-114">Child elements</span></span>

<span data-ttu-id="70f22-115">Keine</span><span class="sxs-lookup"><span data-stu-id="70f22-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="70f22-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70f22-116">Remarks</span></span>

<span data-ttu-id="70f22-117">Die  **\<SectionName >** Element ist ein benutzerdefiniertes Element, das definiert, indem eine [  **\<Abschnitt >** ](~/docs/framework/configure-apps/file-schema/section-element.md) -Tag in die [  **\<ConfigSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="70f22-117">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="70f22-118">Gibt zurück, das Konfigurationssystem eine <xref:System.Collections.IDictionary> Objekt beim Aufrufen <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="70f22-118">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="70f22-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70f22-119">Example</span></span>

<span data-ttu-id="70f22-120">Das folgende Beispiel deklariert ein benutzerdefiniertes Element namens  **\<SampleSection >** , das Lesen von Einstellungen enthält die <xref:System.Configuration.SingleTagSectionHandler> Klasse:</span><span class="sxs-lookup"><span data-stu-id="70f22-120">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="70f22-121">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="70f22-121">Configuration file</span></span>

<span data-ttu-id="70f22-122">Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="70f22-122">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="70f22-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70f22-123">See also</span></span>

- [<span data-ttu-id="70f22-124">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="70f22-124">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
