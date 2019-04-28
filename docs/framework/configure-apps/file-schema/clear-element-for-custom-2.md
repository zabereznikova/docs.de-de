---
title: <clear> Element für NameValueSectionHandler und DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: ad3ac93b2a7f92cd33787620fc0caa2b632aa072
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705362"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="b3a0e-102">\<Deaktivieren Sie >-Element für NameValueSectionHandler und DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="b3a0e-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="b3a0e-103">Löscht alle zuvor definierte Einstellungen in einem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b3a0e-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="b3a0e-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="b3a0e-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="b3a0e-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="b3a0e-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="b3a0e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="b3a0e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b3a0e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3a0e-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="b3a0e-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="b3a0e-108">Attributes</span></span>

<span data-ttu-id="b3a0e-109">Keiner</span><span class="sxs-lookup"><span data-stu-id="b3a0e-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="b3a0e-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="b3a0e-110">Parent element</span></span>

|     | <span data-ttu-id="b3a0e-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3a0e-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="b3a0e-112">**\<sectionName>** Element</span><span class="sxs-lookup"><span data-stu-id="b3a0e-112">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="b3a0e-113">Definiert die Einstellungen für die benutzerdefinierten Konfigurationsabschnitte, mit denen die <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> Klassen.</span><span class="sxs-lookup"><span data-stu-id="b3a0e-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b3a0e-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b3a0e-114">Child elements</span></span>

<span data-ttu-id="b3a0e-115">Keiner</span><span class="sxs-lookup"><span data-stu-id="b3a0e-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="b3a0e-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b3a0e-116">Remarks</span></span>

<span data-ttu-id="b3a0e-117">Können Sie die  **\<Löschen >** Element So entfernen Sie alle Einstellungen aus Ihrer Anwendung, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b3a0e-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="b3a0e-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3a0e-118">Example</span></span>

<span data-ttu-id="b3a0e-119">In diesem Beispiel definiert eine Computer-Konfigurationsdatei und eine Anwendungskonfigurationsdatei und zeigt, wie die  **\<Löschen >** Element in der Konfigurationsdatei einer Anwendung zum Entfernen von Abschnitten, die zuvor definiert, der die Computerkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b3a0e-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="b3a0e-120">Der folgende Konfigurationscode Datei Computer deklariert Abschnitt  **\<MySection >**:</span><span class="sxs-lookup"><span data-stu-id="b3a0e-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="b3a0e-121">Der folgende Code für eine Anwendungskonfigurationsdatei entfernt alle Einstellungen von  **\<MySection >**.</span><span class="sxs-lookup"><span data-stu-id="b3a0e-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="b3a0e-122">Die Anwendung kann nicht abgerufen werden, die Einstellungen, die in deklariert wurden die in der  **\<MySection >** Abschnitt der Konfigurationsdatei des Computers.</span><span class="sxs-lookup"><span data-stu-id="b3a0e-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="b3a0e-123">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="b3a0e-123">Configuration file</span></span>

<span data-ttu-id="b3a0e-124">Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="b3a0e-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3a0e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3a0e-125">See also</span></span>

- [<span data-ttu-id="b3a0e-126">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b3a0e-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
