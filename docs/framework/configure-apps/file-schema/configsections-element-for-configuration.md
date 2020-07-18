---
title: <configSections>-Element für <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 1e4bb7a7cfb0b140ca6d13c162708c3c30bd496d
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441686"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="d2574-102">\<configSections>-Element für \<configuration></span><span class="sxs-lookup"><span data-stu-id="d2574-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="d2574-103">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="d2574-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="d2574-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="d2574-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="d2574-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="d2574-105">Attributes</span></span>

<span data-ttu-id="d2574-106">Keine</span><span class="sxs-lookup"><span data-stu-id="d2574-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="d2574-107">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="d2574-107">Parent element</span></span>

|     | <span data-ttu-id="d2574-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2574-108">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="d2574-109">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d2574-109">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d2574-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d2574-110">Child elements</span></span>

|     | <span data-ttu-id="d2574-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2574-111">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="d2574-112">Enthält eine Konfigurations Abschnitts Deklaration.</span><span class="sxs-lookup"><span data-stu-id="d2574-112">Contains a configuration section declaration.</span></span> |
| [**\<sectionGroup>**](sectiongroup-element-for-configsections.md) | <span data-ttu-id="d2574-113">Definiert einen Namespace für Konfigurations Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="d2574-113">Defines a namespace for configuration sections.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d2574-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d2574-114">Remarks</span></span>

<span data-ttu-id="d2574-115">Wenn dieses Element in einer Konfigurationsdatei gespeichert ist, muss es das erste untergeordnete Element des- **\<configuration>** Elements sein.</span><span class="sxs-lookup"><span data-stu-id="d2574-115">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="d2574-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d2574-116">Example</span></span>

<span data-ttu-id="d2574-117">Im folgenden Beispiel wird gezeigt, wie ein Konfigurations Abschnitt definiert und Einstellungen für diesen Abschnitt definiert werden:</span><span class="sxs-lookup"><span data-stu-id="d2574-117">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="d2574-118">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="d2574-118">Configuration file</span></span>

<span data-ttu-id="d2574-119">Dieses Element kann in der Anwendungs Konfigurationsdatei, der Computer Konfigurationsdatei (*Machine.config*) und *Web.config* Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="d2574-119">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2574-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2574-120">See also</span></span>

- [<span data-ttu-id="d2574-121">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d2574-121">Configuration file schema for the .NET Framework</span></span>](index.md)
