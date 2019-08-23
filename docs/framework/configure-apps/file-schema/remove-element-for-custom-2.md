---
title: <remove>-Element für NameValueSectionHandler und diktarysectionhandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: cd338ff2d613be31ab1524f6baed6107f803a688
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920949"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="f8a25-102">\<Entfernen Sie > Element für NameValueSectionHandler und "diktarysectionhandler".</span><span class="sxs-lookup"><span data-stu-id="f8a25-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="f8a25-103">Entfernt eine zuvor definierte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="f8a25-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="f8a25-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="f8a25-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="f8a25-105">&nbsp;&nbsp;[ **\<sectionName>** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="f8a25-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="f8a25-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**</span><span class="sxs-lookup"><span data-stu-id="f8a25-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f8a25-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8a25-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="f8a25-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="f8a25-108">Attribute</span></span>

|           | <span data-ttu-id="f8a25-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8a25-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f8a25-110">**key**</span><span class="sxs-lookup"><span data-stu-id="f8a25-110">**key**</span></span>   | <span data-ttu-id="f8a25-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f8a25-111">Required attribute.</span></span><br><br><span data-ttu-id="f8a25-112">Gibt den Namen der zu entfernenden Einstellung an.</span><span class="sxs-lookup"><span data-stu-id="f8a25-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f8a25-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="f8a25-113">Parent element</span></span>

| <span data-ttu-id="f8a25-114">Element</span><span class="sxs-lookup"><span data-stu-id="f8a25-114">Element</span></span> | <span data-ttu-id="f8a25-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8a25-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="f8a25-116">sectionName > Element  **\<** </span><span class="sxs-lookup"><span data-stu-id="f8a25-116">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="f8a25-117">Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, die <xref:System.Configuration.NameValueSectionHandler> die <xref:System.Configuration.DictionarySectionHandler> -Klasse und die-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8a25-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f8a25-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f8a25-118">Child elements</span></span>

<span data-ttu-id="f8a25-119">None</span><span class="sxs-lookup"><span data-stu-id="f8a25-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="f8a25-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8a25-120">Remarks</span></span>

<span data-ttu-id="f8a25-121">Sie können das  **\<remove >** -Element verwenden, um Einstellungen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f8a25-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="f8a25-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8a25-122">Example</span></span>

<span data-ttu-id="f8a25-123">Im folgenden Beispiel wird gezeigt, wie das  **\<remove >** -Element in einer Anwendungs Konfigurationsdatei verwendet wird, um zuvor in der Computer Konfigurationsdatei definierte Einstellungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f8a25-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="f8a25-124">Der folgende Code der Computer Konfigurationsdatei deklariert den Abschnitt  **\<mySection >** und `key1` fügt ihm `key2`zwei Einstellungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="f8a25-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="f8a25-125">Der folgende Anwendungs Konfigurationsdatei-Code `key2` entfernt die Einstellung aus  **\<dem mySection->** :</span><span class="sxs-lookup"><span data-stu-id="f8a25-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="f8a25-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="f8a25-126">Configuration file</span></span>

<span data-ttu-id="f8a25-127">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="f8a25-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8a25-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8a25-128">See also</span></span>

- [<span data-ttu-id="f8a25-129">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f8a25-129">Configuration file schema for the .NET Framework</span></span>](index.md)
