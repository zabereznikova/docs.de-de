---
title: <add> Element für NameValueSectionHandler und DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 3bbe4ad6559e324db5853b95e797f50a7b908dcb
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301431"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="fdf13-102">\<Hinzufügen >-Element für NameValueSectionHandler und DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="fdf13-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="fdf13-103">Fügt benutzerdefinierte Anwendungseinstellungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="fdf13-103">Adds custom application settings.</span></span> <span data-ttu-id="fdf13-104">Jede  **\<hinzufügen >** -Tag enthält ein Schlüssel/Wert-Paar.</span><span class="sxs-lookup"><span data-stu-id="fdf13-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="fdf13-105">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="fdf13-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="fdf13-106">&nbsp;&nbsp;[ **\<sectionName>** ](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="fdf13-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="fdf13-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="fdf13-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fdf13-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdf13-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="fdf13-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="fdf13-109">Attributes</span></span>

| <span data-ttu-id="fdf13-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="fdf13-110">Attribute</span></span> | <span data-ttu-id="fdf13-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fdf13-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="fdf13-112">**key**</span><span class="sxs-lookup"><span data-stu-id="fdf13-112">**key**</span></span>   | <span data-ttu-id="fdf13-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="fdf13-113">Required attribute.</span></span><br><br><span data-ttu-id="fdf13-114">Gibt den Namen der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="fdf13-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="fdf13-115">**value**</span><span class="sxs-lookup"><span data-stu-id="fdf13-115">**value**</span></span> | <span data-ttu-id="fdf13-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="fdf13-116">Required attribute.</span></span><br><br><span data-ttu-id="fdf13-117">Gibt den Wert der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="fdf13-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="fdf13-118">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="fdf13-118">Parent element</span></span>

| <span data-ttu-id="fdf13-119">Element</span><span class="sxs-lookup"><span data-stu-id="fdf13-119">Element</span></span> | <span data-ttu-id="fdf13-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fdf13-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="fdf13-121"> *\*\<sectionName>** Element</span><span class="sxs-lookup"><span data-stu-id="fdf13-121">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="fdf13-122">Definiert die Einstellungen für die benutzerdefinierten Konfigurationsabschnitte, mit denen die <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> Klassen.</span><span class="sxs-lookup"><span data-stu-id="fdf13-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="fdf13-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fdf13-123">Child elements</span></span>

<span data-ttu-id="fdf13-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="fdf13-124">None</span></span>

## <a name="example"></a><span data-ttu-id="fdf13-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fdf13-125">Example</span></span>

<span data-ttu-id="fdf13-126">Das folgende Beispiel zeigt, wie zum Definieren eines benutzerdefinierten Konfigurationsabschnitts und Verwenden der  **\<hinzufügen >** Element, Einstellungen in den Abschnitt zu speichern:</span><span class="sxs-lookup"><span data-stu-id="fdf13-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="fdf13-127">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="fdf13-127">Configuration file</span></span>

<span data-ttu-id="fdf13-128">Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden ( *"Machine.config"* ), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="fdf13-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdf13-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdf13-129">See also</span></span>

- [<span data-ttu-id="fdf13-130">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fdf13-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
