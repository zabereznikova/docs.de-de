---
title: <add>-Element für "NameValueSectionHandler" und "diktarysectionhandler"
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac07fc9ba6f030209a5e0d0160689fab95bc1b4a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088764"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="6a420-102">\<> Element für NameValueSectionHandler und "diktarysectionhandler" hinzufügen</span><span class="sxs-lookup"><span data-stu-id="6a420-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="6a420-103">Fügt benutzerdefinierte Anwendungseinstellungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="6a420-103">Adds custom application settings.</span></span> <span data-ttu-id="6a420-104">Jede **\<Add >** -Tags enthält ein Schlüssel-Wert-Paar.</span><span class="sxs-lookup"><span data-stu-id="6a420-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="6a420-105">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6a420-105">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="6a420-106">&nbsp;&nbsp;[ **\<sectionName->** ](custom-element-2.md)</span><span class="sxs-lookup"><span data-stu-id="6a420-106">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)</span></span>\
<span data-ttu-id="6a420-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<hinzufügen >**</span><span class="sxs-lookup"><span data-stu-id="6a420-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6a420-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a420-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="6a420-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="6a420-109">Attributes</span></span>

| <span data-ttu-id="6a420-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="6a420-110">Attribute</span></span> | <span data-ttu-id="6a420-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a420-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="6a420-112">**key**</span><span class="sxs-lookup"><span data-stu-id="6a420-112">**key**</span></span>   | <span data-ttu-id="6a420-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="6a420-113">Required attribute.</span></span><br><br><span data-ttu-id="6a420-114">Gibt den Namen der Einstellung an.</span><span class="sxs-lookup"><span data-stu-id="6a420-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="6a420-115">**Wert**</span><span class="sxs-lookup"><span data-stu-id="6a420-115">**value**</span></span> | <span data-ttu-id="6a420-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="6a420-116">Required attribute.</span></span><br><br><span data-ttu-id="6a420-117">Gibt den Wert der Einstellung an.</span><span class="sxs-lookup"><span data-stu-id="6a420-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="6a420-118">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="6a420-118">Parent element</span></span>

| <span data-ttu-id="6a420-119">Element</span><span class="sxs-lookup"><span data-stu-id="6a420-119">Element</span></span> | <span data-ttu-id="6a420-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a420-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="6a420-121"> **\<sectionName >** Gewisses</span><span class="sxs-lookup"><span data-stu-id="6a420-121">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="6a420-122">Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, in denen die Klassen <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6a420-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6a420-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6a420-123">Child elements</span></span>

<span data-ttu-id="6a420-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="6a420-124">None</span></span>

## <a name="example"></a><span data-ttu-id="6a420-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6a420-125">Example</span></span>

<span data-ttu-id="6a420-126">Im folgenden Beispiel wird gezeigt, wie ein benutzerdefinierter Konfigurations Abschnitt definiert wird und wie das **\<Add >** -Element verwendet wird, um Einstellungen im-Abschnitt zu platzieren:</span><span class="sxs-lookup"><span data-stu-id="6a420-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="6a420-127">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="6a420-127">Configuration file</span></span>

<span data-ttu-id="6a420-128">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="6a420-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a420-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a420-129">See also</span></span>

- [<span data-ttu-id="6a420-130">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6a420-130">Configuration file schema for the .NET Framework</span></span>](index.md)
