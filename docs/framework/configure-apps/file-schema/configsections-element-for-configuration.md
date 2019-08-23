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
ms.openlocfilehash: 31b53837e24029fc7ff0b576d95c0213041a434e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927670"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="fce6f-102">\<configabschnitts > Element für \<Konfigurations ></span><span class="sxs-lookup"><span data-stu-id="fce6f-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="fce6f-103">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="fce6f-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="fce6f-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="fce6f-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="fce6f-105">&nbsp;&nbsp; **\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="fce6f-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="fce6f-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="fce6f-106">Attributes</span></span>

<span data-ttu-id="fce6f-107">None</span><span class="sxs-lookup"><span data-stu-id="fce6f-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="fce6f-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="fce6f-108">Parent element</span></span>

|     | <span data-ttu-id="fce6f-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fce6f-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fce6f-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="fce6f-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="fce6f-111">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fce6f-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="fce6f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fce6f-112">Child elements</span></span>

|     | <span data-ttu-id="fce6f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fce6f-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fce6f-114"> **\<Abschnitts >** </span><span class="sxs-lookup"><span data-stu-id="fce6f-114">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="fce6f-115">Enthält eine Konfigurations Abschnitts Deklaration.</span><span class="sxs-lookup"><span data-stu-id="fce6f-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="fce6f-116"> **\<sectionGroup>** </span><span class="sxs-lookup"><span data-stu-id="fce6f-116">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="fce6f-117">Definiert einen Namespace für Konfigurations Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="fce6f-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="fce6f-118"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="fce6f-118">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="fce6f-119">Entfernt eine vordefinierte Abschnitts-oder Abschnitts Gruppe.</span><span class="sxs-lookup"><span data-stu-id="fce6f-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="fce6f-120"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="fce6f-120">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="fce6f-121">Löscht alle zuvor definierten Abschnitte und Abschnitts Gruppen.</span><span class="sxs-lookup"><span data-stu-id="fce6f-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="fce6f-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fce6f-122">Remarks</span></span>

<span data-ttu-id="fce6f-123">Wenn dieses Element in einer Konfigurationsdatei gespeichert ist, muss es das erste untergeordnete Element des  **\<Configuration >** -Elements sein.</span><span class="sxs-lookup"><span data-stu-id="fce6f-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="fce6f-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fce6f-124">Example</span></span>

<span data-ttu-id="fce6f-125">Im folgenden Beispiel wird gezeigt, wie ein Konfigurations Abschnitt definiert und Einstellungen für diesen Abschnitt definiert werden:</span><span class="sxs-lookup"><span data-stu-id="fce6f-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="fce6f-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="fce6f-126">Configuration file</span></span>

<span data-ttu-id="fce6f-127">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="fce6f-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="fce6f-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fce6f-128">See also</span></span>

- [<span data-ttu-id="fce6f-129">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fce6f-129">Configuration file schema for the .NET Framework</span></span>](index.md)
