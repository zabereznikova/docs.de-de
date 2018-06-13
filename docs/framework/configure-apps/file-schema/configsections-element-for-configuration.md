---
title: '&lt;"configSections"&gt; -Element für &lt;Konfiguration&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 33406a67389cdf857fa5030e20d8a4dec7662741
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752077"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="0bde2-102">\<ConfigSections >-Element für \<Configuration ></span><span class="sxs-lookup"><span data-stu-id="0bde2-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="0bde2-103">Enthält die Konfiguration im Abschnitt und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="0bde2-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="0bde2-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0bde2-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="0bde2-105">&nbsp;&nbsp;**\<ConfigSections >**</span><span class="sxs-lookup"><span data-stu-id="0bde2-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="0bde2-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="0bde2-106">Attributes</span></span>

<span data-ttu-id="0bde2-107">Keiner</span><span class="sxs-lookup"><span data-stu-id="0bde2-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="0bde2-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="0bde2-108">Parent element</span></span>

|     | <span data-ttu-id="0bde2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bde2-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0bde2-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="0bde2-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="0bde2-111">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0bde2-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0bde2-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0bde2-112">Child elements</span></span>

|     | <span data-ttu-id="0bde2-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bde2-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0bde2-114">**\<Abschnitt >**</span><span class="sxs-lookup"><span data-stu-id="0bde2-114">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="0bde2-115">Enthält eine Deklaration der Konfiguration im Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="0bde2-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="0bde2-116">**\<SectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="0bde2-116">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="0bde2-117">Definiert einen Namespace für Konfigurationsabschnitte.</span><span class="sxs-lookup"><span data-stu-id="0bde2-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="0bde2-118">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="0bde2-118">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="0bde2-119">Entfernt einen vordefinierten Abschnitt oder Abschnittsgruppe.</span><span class="sxs-lookup"><span data-stu-id="0bde2-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="0bde2-120">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="0bde2-120">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="0bde2-121">Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen.</span><span class="sxs-lookup"><span data-stu-id="0bde2-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0bde2-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0bde2-122">Remarks</span></span>

<span data-ttu-id="0bde2-123">Wenn dieses Element in einer Konfigurationsdatei angegeben ist, muss er das erste untergeordnete Element von der  **\<Configuration >** Element.</span><span class="sxs-lookup"><span data-stu-id="0bde2-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="0bde2-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0bde2-124">Example</span></span>

<span data-ttu-id="0bde2-125">Das folgende Beispiel veranschaulicht einen Konfigurationsabschnitt zu definieren, und definieren Sie Einstellungen für diesen Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="0bde2-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="0bde2-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="0bde2-126">Configuration file</span></span>

<span data-ttu-id="0bde2-127">Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="0bde2-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bde2-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bde2-128">See also</span></span>

[<span data-ttu-id="0bde2-129">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0bde2-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
