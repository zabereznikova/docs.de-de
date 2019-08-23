---
title: <clear>-Element für NameValueSectionHandler und diktarysectionhandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: fbb689db4abc5d59729d9a4d9807a02a0983d40b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927709"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="cf3a8-102">\<> Element für NameValueSectionHandler und "diktarysectionhandler" Löschen</span><span class="sxs-lookup"><span data-stu-id="cf3a8-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="cf3a8-103">Löscht alle zuvor definierten Einstellungen in einem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="cf3a8-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="cf3a8-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="cf3a8-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="cf3a8-105">&nbsp;&nbsp;[ **\<sectionName>** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="cf3a8-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="cf3a8-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Löschen >**</span><span class="sxs-lookup"><span data-stu-id="cf3a8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="cf3a8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf3a8-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="cf3a8-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="cf3a8-108">Attributes</span></span>

<span data-ttu-id="cf3a8-109">None</span><span class="sxs-lookup"><span data-stu-id="cf3a8-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="cf3a8-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="cf3a8-110">Parent element</span></span>

|     | <span data-ttu-id="cf3a8-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf3a8-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="cf3a8-112">sectionName > Element  **\<** </span><span class="sxs-lookup"><span data-stu-id="cf3a8-112">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="cf3a8-113">Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, die <xref:System.Configuration.NameValueSectionHandler> die <xref:System.Configuration.DictionarySectionHandler> -Klasse und die-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="cf3a8-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="cf3a8-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf3a8-114">Child elements</span></span>

<span data-ttu-id="cf3a8-115">None</span><span class="sxs-lookup"><span data-stu-id="cf3a8-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="cf3a8-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf3a8-116">Remarks</span></span>

<span data-ttu-id="cf3a8-117">Sie können das  **\<Clear >** -Element verwenden, um alle Einstellungen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="cf3a8-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="cf3a8-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf3a8-118">Example</span></span>

<span data-ttu-id="cf3a8-119">In diesem Beispiel werden eine Computer Konfigurationsdatei und eine Anwendungs Konfigurationsdatei definiert, und es wird gezeigt, wie das  **\<Clear >** -Element in einer Anwendungs Konfigurationsdatei verwendet wird, um die zuvor in der Computerkonfiguration definierten Abschnitte Datei.</span><span class="sxs-lookup"><span data-stu-id="cf3a8-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="cf3a8-120">Der folgende Code der Computer Konfigurationsdatei deklariert den Abschnitt  **\<mySection->** :</span><span class="sxs-lookup"><span data-stu-id="cf3a8-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="cf3a8-121">Der folgende Anwendungs Konfigurationsdatei-Code entfernt alle Einstellungen aus  **\<dem mySection->** .</span><span class="sxs-lookup"><span data-stu-id="cf3a8-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="cf3a8-122">Die Anwendung kann keine der Einstellungen abrufen, die im  **\<Abschnitt "mySection >** " der Computer Konfigurationsdatei deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="cf3a8-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="cf3a8-123">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="cf3a8-123">Configuration file</span></span>

<span data-ttu-id="cf3a8-124">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="cf3a8-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf3a8-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf3a8-125">See also</span></span>

- [<span data-ttu-id="cf3a8-126">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cf3a8-126">Configuration file schema for the .NET Framework</span></span>](index.md)
