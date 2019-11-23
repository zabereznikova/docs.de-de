---
title: <configSections>-Element für <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6024144b6f12df22369366f04c3cbad02c5011d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119020"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="0d072-102">\<configabschnitts > Element für \<Configuration ></span><span class="sxs-lookup"><span data-stu-id="0d072-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="0d072-103">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="0d072-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="0d072-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0d072-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="0d072-105">&nbsp;&nbsp; **\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="0d072-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="0d072-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="0d072-106">Attributes</span></span>

<span data-ttu-id="0d072-107">Keine</span><span class="sxs-lookup"><span data-stu-id="0d072-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="0d072-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="0d072-108">Parent element</span></span>

|     | <span data-ttu-id="0d072-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d072-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0d072-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="0d072-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="0d072-111">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0d072-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0d072-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0d072-112">Child elements</span></span>

|     | <span data-ttu-id="0d072-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d072-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0d072-114"> **\<Abschnitt >** </span><span class="sxs-lookup"><span data-stu-id="0d072-114">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="0d072-115">Enthält eine Konfigurations Abschnitts Deklaration.</span><span class="sxs-lookup"><span data-stu-id="0d072-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="0d072-116"> **\<sectionGroup>** </span><span class="sxs-lookup"><span data-stu-id="0d072-116">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="0d072-117">Definiert einen Namespace für Konfigurations Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="0d072-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="0d072-118"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="0d072-118">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="0d072-119">Entfernt eine vordefinierte Abschnitts-oder Abschnitts Gruppe.</span><span class="sxs-lookup"><span data-stu-id="0d072-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="0d072-120"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="0d072-120">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="0d072-121">Löscht alle zuvor definierten Abschnitte und Abschnitts Gruppen.</span><span class="sxs-lookup"><span data-stu-id="0d072-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0d072-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d072-122">Remarks</span></span>

<span data-ttu-id="0d072-123">Wenn dieses Element in einer Konfigurationsdatei gespeichert ist, muss es das erste untergeordnete Element des **\<Configuration >** -Elements sein.</span><span class="sxs-lookup"><span data-stu-id="0d072-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="0d072-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d072-124">Example</span></span>

<span data-ttu-id="0d072-125">Im folgenden Beispiel wird gezeigt, wie ein Konfigurations Abschnitt definiert und Einstellungen für diesen Abschnitt definiert werden:</span><span class="sxs-lookup"><span data-stu-id="0d072-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="0d072-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="0d072-126">Configuration file</span></span>

<span data-ttu-id="0d072-127">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="0d072-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d072-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d072-128">See also</span></span>

- [<span data-ttu-id="0d072-129">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0d072-129">Configuration file schema for the .NET Framework</span></span>](index.md)
