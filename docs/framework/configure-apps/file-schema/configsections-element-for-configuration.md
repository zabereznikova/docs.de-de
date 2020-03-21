---
title: <configSections>-Element für <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 55116f1fe6fdffffea8f26d8a4de783c7305ada3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155348"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="95876-102">\<configSections>-Element für \<die Konfiguration></span><span class="sxs-lookup"><span data-stu-id="95876-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="95876-103">Enthält Konfigurationsabschnittund- und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="95876-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="95876-104">Konfiguration &nbsp; &nbsp;>[\*\* \<\*\*](configuration-element.md) **configSections \<>**</span><span class="sxs-lookup"><span data-stu-id="95876-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="95876-105">Attributes</span><span class="sxs-lookup"><span data-stu-id="95876-105">Attributes</span></span>

<span data-ttu-id="95876-106">Keine</span><span class="sxs-lookup"><span data-stu-id="95876-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="95876-107">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="95876-107">Parent element</span></span>

|     | <span data-ttu-id="95876-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95876-108">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="95876-109">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="95876-109">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="95876-110">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="95876-110">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="95876-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="95876-111">Child elements</span></span>

|     | <span data-ttu-id="95876-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95876-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="95876-113">**\<Abschnitt>**</span><span class="sxs-lookup"><span data-stu-id="95876-113">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="95876-114">Enthält eine Konfigurationsabschnittsdeklaration.</span><span class="sxs-lookup"><span data-stu-id="95876-114">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="95876-115">**\<sectionGruppe>**</span><span class="sxs-lookup"><span data-stu-id="95876-115">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="95876-116">Definiert einen Namespace für Konfigurationsabschnitte.</span><span class="sxs-lookup"><span data-stu-id="95876-116">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="95876-117">**\<entfernen sie>**</span><span class="sxs-lookup"><span data-stu-id="95876-117">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="95876-118">Entfernt einen vordefinierten Abschnitt oder eine Vorschnittgruppe.</span><span class="sxs-lookup"><span data-stu-id="95876-118">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="95876-119">**\<klare>**</span><span class="sxs-lookup"><span data-stu-id="95876-119">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="95876-120">Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen.</span><span class="sxs-lookup"><span data-stu-id="95876-120">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="95876-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="95876-121">Remarks</span></span>

<span data-ttu-id="95876-122">Wenn sich dieses Element in einer Konfigurationsdatei befindet, \*\* \<\*\* muss es das erste untergeordnete Element der Konfiguration>-Elements sein.</span><span class="sxs-lookup"><span data-stu-id="95876-122">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="95876-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="95876-123">Example</span></span>

<span data-ttu-id="95876-124">Das folgende Beispiel zeigt, wie Sie einen Konfigurationsabschnitt definieren und Einstellungen für diesen Abschnitt definieren:</span><span class="sxs-lookup"><span data-stu-id="95876-124">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="95876-125">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="95876-125">Configuration file</span></span>

<span data-ttu-id="95876-126">Dieses Element kann in der Anwendungskonfigurationsdatei, der Computerkonfigurationsdatei (*Machine.config*) und *web.config-Dateien* verwendet werden, die sich nicht auf Anwendungsverzeichnisebene befinden.</span><span class="sxs-lookup"><span data-stu-id="95876-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="95876-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95876-127">See also</span></span>

- [<span data-ttu-id="95876-128">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="95876-128">Configuration file schema for the .NET Framework</span></span>](index.md)
