---
title: '&lt;Deaktivieren Sie&gt; NameValueSectionHandler und DictionarySectionHandler-Element'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e91c3d9693cf656a8c56c82d1997f74c2b3d64c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="3605d-102">\<Deaktivieren Sie >-Element für NameValueSectionHandler und DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="3605d-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="3605d-103">Löscht alle zuvor definierte Einstellungen in einem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="3605d-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="3605d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="3605d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="3605d-105">&nbsp;&nbsp;[**\<SectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="3605d-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="3605d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Deaktivieren Sie >**</span><span class="sxs-lookup"><span data-stu-id="3605d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3605d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3605d-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="3605d-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="3605d-108">Attributes</span></span>

<span data-ttu-id="3605d-109">Keine</span><span class="sxs-lookup"><span data-stu-id="3605d-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="3605d-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="3605d-110">Parent element</span></span>

|     | <span data-ttu-id="3605d-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3605d-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="3605d-112">**\<SectionName >** Element</span><span class="sxs-lookup"><span data-stu-id="3605d-112">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="3605d-113">Definiert die Einstellungen für benutzerdefinierte Konfigurationsabschnitte, mit denen die <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> Klassen.</span><span class="sxs-lookup"><span data-stu-id="3605d-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="3605d-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3605d-114">Child elements</span></span>

<span data-ttu-id="3605d-115">Keine</span><span class="sxs-lookup"><span data-stu-id="3605d-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="3605d-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3605d-116">Remarks</span></span>

<span data-ttu-id="3605d-117">Sie können die  **\<deaktivieren >** Element So entfernen Sie alle Einstellungen von Ihrer Anwendung, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3605d-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="3605d-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3605d-118">Example</span></span>

<span data-ttu-id="3605d-119">In diesem Beispiel definiert eine Computerkonfigurationsdatei und einer Anwendungskonfigurationsdatei und zeigt, wie die  **\<deaktivieren >** Element in einer Anwendungskonfigurationsdatei gelöscht zuvor definierten Abschnitte der die Computerkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="3605d-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="3605d-120">Der folgende Konfigurationscode Datei Computer deklariert Abschnitt  **\<MySection >**:</span><span class="sxs-lookup"><span data-stu-id="3605d-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="3605d-121">Der folgende Code für eine Anwendungskonfigurationsdatei entfernt alle Einstellungen von  **\<MySection >**.</span><span class="sxs-lookup"><span data-stu-id="3605d-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="3605d-122">Die Anwendung kann nicht abgerufen werden, die Einstellungen, die im deklariert wurden die in der  **\<MySection >** Abschnitt der Konfigurationsdatei des Computers.</span><span class="sxs-lookup"><span data-stu-id="3605d-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="3605d-123">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="3605d-123">Configuration file</span></span>

<span data-ttu-id="3605d-124">Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="3605d-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="3605d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3605d-125">See also</span></span>

[<span data-ttu-id="3605d-126">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3605d-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
