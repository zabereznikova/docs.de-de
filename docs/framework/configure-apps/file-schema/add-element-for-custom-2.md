---
title: <add>-Element für NameValueSectionHandler und diktarysectionhandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
ms.openlocfilehash: 57722f3518fad12cb8e6e35d68f40bb8465bdd86
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215442"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="b7ea5-102">\<add>-Element für NameValueSectionHandler und diktarysectionhandler</span><span class="sxs-lookup"><span data-stu-id="b7ea5-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="b7ea5-103">Fügt benutzerdefinierte Anwendungseinstellungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="b7ea5-103">Adds custom application settings.</span></span> <span data-ttu-id="b7ea5-104">Jedes **\<add>** Tag enthält ein Schlüssel-Wert-Paar.</span><span class="sxs-lookup"><span data-stu-id="b7ea5-104">Each **\<add>** tag contains a key/value pair.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="b7ea5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7ea5-105">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="b7ea5-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="b7ea5-106">Attributes</span></span>

| <span data-ttu-id="b7ea5-107">attribute</span><span class="sxs-lookup"><span data-stu-id="b7ea5-107">Attribute</span></span> | <span data-ttu-id="b7ea5-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b7ea5-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b7ea5-109">**key**</span><span class="sxs-lookup"><span data-stu-id="b7ea5-109">**key**</span></span>   | <span data-ttu-id="b7ea5-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b7ea5-110">Required attribute.</span></span><br><br><span data-ttu-id="b7ea5-111">Gibt den Namen der Einstellung an.</span><span class="sxs-lookup"><span data-stu-id="b7ea5-111">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="b7ea5-112">**value**</span><span class="sxs-lookup"><span data-stu-id="b7ea5-112">**value**</span></span> | <span data-ttu-id="b7ea5-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b7ea5-113">Required attribute.</span></span><br><br><span data-ttu-id="b7ea5-114">Gibt den Wert der Einstellung an.</span><span class="sxs-lookup"><span data-stu-id="b7ea5-114">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b7ea5-115">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="b7ea5-115">Parent element</span></span>

| <span data-ttu-id="b7ea5-116">Element</span><span class="sxs-lookup"><span data-stu-id="b7ea5-116">Element</span></span> | <span data-ttu-id="b7ea5-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7ea5-117">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="b7ea5-118">**\<sectionName>** Gewisses</span><span class="sxs-lookup"><span data-stu-id="b7ea5-118">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="b7ea5-119">Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, die die <xref:System.Configuration.NameValueSectionHandler> -Klasse und die- <xref:System.Configuration.DictionarySectionHandler> Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7ea5-119">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b7ea5-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b7ea5-120">Child elements</span></span>

<span data-ttu-id="b7ea5-121">Keine</span><span class="sxs-lookup"><span data-stu-id="b7ea5-121">None</span></span>

## <a name="example"></a><span data-ttu-id="b7ea5-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7ea5-122">Example</span></span>

<span data-ttu-id="b7ea5-123">Im folgenden Beispiel wird gezeigt, wie ein benutzerdefinierter Konfigurations Abschnitt definiert wird und wie mit dem- **\<add>** Element Einstellungen in den-Abschnitt eingefügt werden:</span><span class="sxs-lookup"><span data-stu-id="b7ea5-123">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="b7ea5-124">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="b7ea5-124">Configuration file</span></span>

<span data-ttu-id="b7ea5-125">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="b7ea5-125">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7ea5-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7ea5-126">See also</span></span>

- [<span data-ttu-id="b7ea5-127">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7ea5-127">Configuration file schema for the .NET Framework</span></span>](index.md)
