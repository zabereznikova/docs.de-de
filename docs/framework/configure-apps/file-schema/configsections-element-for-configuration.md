---
title: '&lt;ConfigSections&gt; -Element für &lt;Konfiguration&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: guardrex
ms.author: mairaw
ms.openlocfilehash: f46c84a1674a3e9352d0a4ccda23d44e650a70ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629487"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="2aeab-102">\<ConfigSections >-Element für \<Configuration ></span><span class="sxs-lookup"><span data-stu-id="2aeab-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="2aeab-103">Enthält die Konfiguration im Abschnitt und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="2aeab-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="2aeab-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="2aeab-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="2aeab-105">&nbsp;&nbsp;**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="2aeab-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="2aeab-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="2aeab-106">Attributes</span></span>

<span data-ttu-id="2aeab-107">Keine</span><span class="sxs-lookup"><span data-stu-id="2aeab-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="2aeab-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="2aeab-108">Parent element</span></span>

|     | <span data-ttu-id="2aeab-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2aeab-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2aeab-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="2aeab-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="2aeab-111">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2aeab-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="2aeab-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2aeab-112">Child elements</span></span>

|     | <span data-ttu-id="2aeab-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2aeab-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2aeab-114">**\<section>**</span><span class="sxs-lookup"><span data-stu-id="2aeab-114">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="2aeab-115">Enthält die Deklaration einer Konfigurations-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="2aeab-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="2aeab-116">**\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="2aeab-116">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="2aeab-117">Definiert einen Namespace für Konfigurationsabschnitte.</span><span class="sxs-lookup"><span data-stu-id="2aeab-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="2aeab-118">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="2aeab-118">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="2aeab-119">Entfernt einen vordefinierten Abschnitt oder Abschnittsgruppe.</span><span class="sxs-lookup"><span data-stu-id="2aeab-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="2aeab-120">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="2aeab-120">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="2aeab-121">Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen.</span><span class="sxs-lookup"><span data-stu-id="2aeab-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="2aeab-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2aeab-122">Remarks</span></span>

<span data-ttu-id="2aeab-123">Wenn dieses Element in einer Konfigurationsdatei ist, muss es sein, dass das erste untergeordnete Element von der  **\<Configuration >** Element.</span><span class="sxs-lookup"><span data-stu-id="2aeab-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="2aeab-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2aeab-124">Example</span></span>

<span data-ttu-id="2aeab-125">Das folgende Beispiel zeigt, wie Sie definieren einen Konfigurationsabschnitt aus, und definieren Sie Einstellungen für diesen Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="2aeab-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="2aeab-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="2aeab-126">Configuration file</span></span>

<span data-ttu-id="2aeab-127">Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="2aeab-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="2aeab-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2aeab-128">See also</span></span>

- [<span data-ttu-id="2aeab-129">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2aeab-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
