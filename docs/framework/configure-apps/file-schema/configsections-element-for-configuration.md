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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155348"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="418e6-102">\<configSections>-Element für \<configuration></span><span class="sxs-lookup"><span data-stu-id="418e6-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="418e6-103">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="418e6-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="418e6-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="418e6-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="418e6-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="418e6-105">Attributes</span></span>

<span data-ttu-id="418e6-106">Keine</span><span class="sxs-lookup"><span data-stu-id="418e6-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="418e6-107">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="418e6-107">Parent element</span></span>

|     | <span data-ttu-id="418e6-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="418e6-108">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="418e6-109">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="418e6-109">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="418e6-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="418e6-110">Child elements</span></span>

|     | <span data-ttu-id="418e6-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="418e6-111">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="418e6-112">Enthält eine Konfigurations Abschnitts Deklaration.</span><span class="sxs-lookup"><span data-stu-id="418e6-112">Contains a configuration section declaration.</span></span> |
| [**\<sectionGroup>**](sectiongroup-element-for-configsections.md) | <span data-ttu-id="418e6-113">Definiert einen Namespace für Konfigurations Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="418e6-113">Defines a namespace for configuration sections.</span></span> |
| [**\<remove>**](remove-element-for-configsections.md) | <span data-ttu-id="418e6-114">Entfernt eine vordefinierte Abschnitts-oder Abschnitts Gruppe.</span><span class="sxs-lookup"><span data-stu-id="418e6-114">Removes a predefined section or section group.</span></span> |
| [**\<clear>**](clear-element-for-configsections.md) | <span data-ttu-id="418e6-115">Löscht alle zuvor definierten Abschnitte und Abschnitts Gruppen.</span><span class="sxs-lookup"><span data-stu-id="418e6-115">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="418e6-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="418e6-116">Remarks</span></span>

<span data-ttu-id="418e6-117">Wenn dieses Element in einer Konfigurationsdatei gespeichert ist, muss es das erste untergeordnete Element des- **\<configuration>** Elements sein.</span><span class="sxs-lookup"><span data-stu-id="418e6-117">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="418e6-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="418e6-118">Example</span></span>

<span data-ttu-id="418e6-119">Im folgenden Beispiel wird gezeigt, wie ein Konfigurations Abschnitt definiert und Einstellungen für diesen Abschnitt definiert werden:</span><span class="sxs-lookup"><span data-stu-id="418e6-119">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="418e6-120">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="418e6-120">Configuration file</span></span>

<span data-ttu-id="418e6-121">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="418e6-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="418e6-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="418e6-122">See also</span></span>

- [<span data-ttu-id="418e6-123">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="418e6-123">Configuration file schema for the .NET Framework</span></span>](index.md)
