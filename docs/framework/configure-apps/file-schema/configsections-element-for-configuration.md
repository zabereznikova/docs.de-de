---
title: <configSections>-Element für <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: d522d004630dee942e24c39a936feae7dc957bd5
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300792"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="7bad9-102">\<ConfigSections >-Element für \<Configuration ></span><span class="sxs-lookup"><span data-stu-id="7bad9-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="7bad9-103">Enthält die Konfiguration im Abschnitt und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="7bad9-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="7bad9-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="7bad9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="7bad9-105">&nbsp;&nbsp; **\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="7bad9-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="7bad9-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="7bad9-106">Attributes</span></span>

<span data-ttu-id="7bad9-107">Keiner</span><span class="sxs-lookup"><span data-stu-id="7bad9-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="7bad9-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="7bad9-108">Parent element</span></span>

|     | <span data-ttu-id="7bad9-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7bad9-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7bad9-110"> *\*\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="7bad9-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="7bad9-111">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7bad9-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7bad9-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7bad9-112">Child elements</span></span>

|     | <span data-ttu-id="7bad9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7bad9-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7bad9-114"> *\*\<section>** </span><span class="sxs-lookup"><span data-stu-id="7bad9-114">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="7bad9-115">Enthält die Deklaration einer Konfigurations-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="7bad9-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="7bad9-116"> *\*\<sectionGroup>** </span><span class="sxs-lookup"><span data-stu-id="7bad9-116">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="7bad9-117">Definiert einen Namespace für Konfigurationsabschnitte.</span><span class="sxs-lookup"><span data-stu-id="7bad9-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="7bad9-118"> *\*\<remove>** </span><span class="sxs-lookup"><span data-stu-id="7bad9-118">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="7bad9-119">Entfernt einen vordefinierten Abschnitt oder Abschnittsgruppe.</span><span class="sxs-lookup"><span data-stu-id="7bad9-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="7bad9-120"> *\*\<clear>** </span><span class="sxs-lookup"><span data-stu-id="7bad9-120">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="7bad9-121">Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen.</span><span class="sxs-lookup"><span data-stu-id="7bad9-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7bad9-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7bad9-122">Remarks</span></span>

<span data-ttu-id="7bad9-123">Wenn dieses Element in einer Konfigurationsdatei ist, muss es sein, dass das erste untergeordnete Element von der  **\<Configuration >** Element.</span><span class="sxs-lookup"><span data-stu-id="7bad9-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="7bad9-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7bad9-124">Example</span></span>

<span data-ttu-id="7bad9-125">Das folgende Beispiel zeigt, wie Sie definieren einen Konfigurationsabschnitt aus, und definieren Sie Einstellungen für diesen Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="7bad9-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="7bad9-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="7bad9-126">Configuration file</span></span>

<span data-ttu-id="7bad9-127">Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden ( *"Machine.config"* ), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="7bad9-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bad9-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bad9-128">See also</span></span>

- [<span data-ttu-id="7bad9-129">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7bad9-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
