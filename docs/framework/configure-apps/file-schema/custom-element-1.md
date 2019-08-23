---
title: Benutzerdefiniertes Element für SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 8fae3673fe72d036802cb1a8366aaa2430c38884
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927501"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="2aaa5-102">Benutzerdefiniertes Element für SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="2aaa5-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="2aaa5-103">Definiert Einstellungen in einem benutzerdefinierten Konfigurations Abschnitt, der von einem \<Abschnitt >-Elements definiert wird <xref:System.Configuration.SingleTagSectionHandler> und die-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="2aaa5-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="2aaa5-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="2aaa5-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="2aaa5-105">&nbsp;&nbsp; *\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="2aaa5-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="2aaa5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2aaa5-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="2aaa5-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="2aaa5-107">Attributes</span></span>

<span data-ttu-id="2aaa5-108">Attribute und Attributwerte sind Benutzer definiert.</span><span class="sxs-lookup"><span data-stu-id="2aaa5-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="2aaa5-109">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="2aaa5-109">Parent element</span></span>

|     | <span data-ttu-id="2aaa5-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2aaa5-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2aaa5-111"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="2aaa5-111">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="2aaa5-112">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2aaa5-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="2aaa5-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2aaa5-113">Child elements</span></span>

<span data-ttu-id="2aaa5-114">None</span><span class="sxs-lookup"><span data-stu-id="2aaa5-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="2aaa5-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2aaa5-115">Remarks</span></span>

<span data-ttu-id="2aaa5-116">**Das\<Element sectionName >** ist ein benutzerdefiniertes Element, das durch einen [ **\<Abschnitt >** ](section-element.md) -Tag im [ **\<>** ](configsections-element-for-configuration.md) -Element von configabschnitts definiert wird.</span><span class="sxs-lookup"><span data-stu-id="2aaa5-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="2aaa5-117">Das Konfigurationssystem gibt ein <xref:System.Collections.IDictionary> -Objekt zurück, <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>wenn aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2aaa5-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="2aaa5-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2aaa5-118">Example</span></span>

<span data-ttu-id="2aaa5-119">Im folgenden Beispiel wird ein benutzerdefiniertes Element namens  **\<sampleSection >** deklariert, das die <xref:System.Configuration.SingleTagSectionHandler> von der-Klasse gelesenen Einstellungen enthält:</span><span class="sxs-lookup"><span data-stu-id="2aaa5-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="2aaa5-120">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="2aaa5-120">Configuration file</span></span>

<span data-ttu-id="2aaa5-121">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="2aaa5-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="2aaa5-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2aaa5-122">See also</span></span>

- [<span data-ttu-id="2aaa5-123">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2aaa5-123">Configuration file schema for the .NET Framework</span></span>](index.md)
