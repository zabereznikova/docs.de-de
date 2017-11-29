---
title: "&lt;\"configSections\"&gt; -Element für &lt;Konfiguration&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7bcf425f345a3153a83cc60e76d87b3c32d83dbe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="fbd79-102">\<ConfigSections >-Element für \<Configuration ></span><span class="sxs-lookup"><span data-stu-id="fbd79-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="fbd79-103">Enthält die Konfiguration im Abschnitt und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="fbd79-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="fbd79-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="fbd79-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="fbd79-105">&nbsp;&nbsp;**\<ConfigSections >**</span><span class="sxs-lookup"><span data-stu-id="fbd79-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="fbd79-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="fbd79-106">Attributes</span></span>

<span data-ttu-id="fbd79-107">Keine</span><span class="sxs-lookup"><span data-stu-id="fbd79-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="fbd79-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="fbd79-108">Parent element</span></span>

|     | <span data-ttu-id="fbd79-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbd79-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fbd79-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="fbd79-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="fbd79-111">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fbd79-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="fbd79-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fbd79-112">Child elements</span></span>

|     | <span data-ttu-id="fbd79-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbd79-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fbd79-114">**\<Abschnitt >**</span><span class="sxs-lookup"><span data-stu-id="fbd79-114">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="fbd79-115">Enthält eine Deklaration der Konfiguration im Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="fbd79-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="fbd79-116">**\<SectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="fbd79-116">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="fbd79-117">Definiert einen Namespace für Konfigurationsabschnitte.</span><span class="sxs-lookup"><span data-stu-id="fbd79-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="fbd79-118">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="fbd79-118">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="fbd79-119">Entfernt einen vordefinierten Abschnitt oder Abschnittsgruppe.</span><span class="sxs-lookup"><span data-stu-id="fbd79-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="fbd79-120">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="fbd79-120">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="fbd79-121">Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen.</span><span class="sxs-lookup"><span data-stu-id="fbd79-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="fbd79-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fbd79-122">Remarks</span></span>

<span data-ttu-id="fbd79-123">Wenn dieses Element in einer Konfigurationsdatei angegeben ist, muss er das erste untergeordnete Element von der  **\<Configuration >** Element.</span><span class="sxs-lookup"><span data-stu-id="fbd79-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="fbd79-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fbd79-124">Example</span></span>

<span data-ttu-id="fbd79-125">Das folgende Beispiel veranschaulicht einen Konfigurationsabschnitt zu definieren, und definieren Sie Einstellungen für diesen Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="fbd79-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="fbd79-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="fbd79-126">Configuration file</span></span>

<span data-ttu-id="fbd79-127">Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="fbd79-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbd79-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbd79-128">See also</span></span>

[<span data-ttu-id="fbd79-129">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fbd79-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
