---
title: '&lt;Entfernen Sie&gt; NameValueSectionHandler und DictionarySectionHandler-Element'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: decf0ca5f9f743a2a2884c06777b7ee9d6d6a8ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="967d1-102">\<Entfernen Sie >-Element für NameValueSectionHandler und DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="967d1-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="967d1-103">Entfernt eine zuvor definierte Einstellung an.</span><span class="sxs-lookup"><span data-stu-id="967d1-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="967d1-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="967d1-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="967d1-105">&nbsp;&nbsp;[**\<SectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="967d1-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="967d1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Entfernen >**</span><span class="sxs-lookup"><span data-stu-id="967d1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="967d1-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="967d1-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="967d1-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="967d1-108">Attribute</span></span>

|           | <span data-ttu-id="967d1-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="967d1-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="967d1-110">**key**</span><span class="sxs-lookup"><span data-stu-id="967d1-110">**key**</span></span>   | <span data-ttu-id="967d1-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="967d1-111">Required attribute.</span></span><br><br><span data-ttu-id="967d1-112">Gibt den Namen der Einstellung entfernen.</span><span class="sxs-lookup"><span data-stu-id="967d1-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="967d1-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="967d1-113">Parent element</span></span>

| <span data-ttu-id="967d1-114">Element</span><span class="sxs-lookup"><span data-stu-id="967d1-114">Element</span></span> | <span data-ttu-id="967d1-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="967d1-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="967d1-116">**\<SectionName >** Element</span><span class="sxs-lookup"><span data-stu-id="967d1-116">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="967d1-117">Definiert die Einstellungen für benutzerdefinierte Konfigurationsabschnitte, mit denen die <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> Klassen.</span><span class="sxs-lookup"><span data-stu-id="967d1-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="967d1-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="967d1-118">Child elements</span></span>

<span data-ttu-id="967d1-119">Keine</span><span class="sxs-lookup"><span data-stu-id="967d1-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="967d1-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="967d1-120">Remarks</span></span>

<span data-ttu-id="967d1-121">Sie können die  **\<entfernen >** Element So entfernen Sie die Einstellungen aus Ihrer Anwendung, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="967d1-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="967d1-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="967d1-122">Example</span></span>

<span data-ttu-id="967d1-123">Das folgende Beispiel zeigt, wie Sie die  **\<entfernen >** Element in einer Anwendungskonfigurationsdatei So entfernen Sie die Einstellungen, die zuvor in der Computerkonfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="967d1-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="967d1-124">Der folgende Konfigurationscode Datei Computer deklariert Abschnitt  **\<MySection >** und fügt zwei Einstellungen `key1` und `key2`, darauf:</span><span class="sxs-lookup"><span data-stu-id="967d1-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="967d1-125">Der folgende Code für eine Anwendungskonfigurationsdatei entfernt die `key2` Festlegen von  **\<MySection >**:</span><span class="sxs-lookup"><span data-stu-id="967d1-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="967d1-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="967d1-126">Configuration file</span></span>

<span data-ttu-id="967d1-127">Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="967d1-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="967d1-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="967d1-128">See also</span></span>

[<span data-ttu-id="967d1-129">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="967d1-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
