---
title: <clear>-Element für NameValueSectionHandler und diktarysectionhandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
ms.openlocfilehash: f6d860f35d22002030ffa3d09dd0d8a96116bf5e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214744"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="310e8-102">\<clear>-Element für NameValueSectionHandler und diktarysectionhandler</span><span class="sxs-lookup"><span data-stu-id="310e8-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="310e8-103">Löscht alle zuvor definierten Einstellungen in einem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="310e8-103">Clears all previously defined settings in a section.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="310e8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="310e8-104">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="310e8-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="310e8-105">Attributes</span></span>

<span data-ttu-id="310e8-106">Keine</span><span class="sxs-lookup"><span data-stu-id="310e8-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="310e8-107">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="310e8-107">Parent element</span></span>

|     | <span data-ttu-id="310e8-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="310e8-108">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="310e8-109">**\<sectionName>** Gewisses</span><span class="sxs-lookup"><span data-stu-id="310e8-109">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="310e8-110">Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, die die <xref:System.Configuration.NameValueSectionHandler> -Klasse und die- <xref:System.Configuration.DictionarySectionHandler> Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="310e8-110">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="310e8-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="310e8-111">Child elements</span></span>

<span data-ttu-id="310e8-112">Keine</span><span class="sxs-lookup"><span data-stu-id="310e8-112">None</span></span>

## <a name="remarks"></a><span data-ttu-id="310e8-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="310e8-113">Remarks</span></span>

<span data-ttu-id="310e8-114">Sie können das- **\<clear>** Element verwenden, um alle Einstellungen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdateien definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="310e8-114">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="310e8-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="310e8-115">Example</span></span>

<span data-ttu-id="310e8-116">In diesem Beispiel werden eine Computer Konfigurationsdatei und eine Anwendungs Konfigurationsdatei definiert. Außerdem wird gezeigt, wie Sie mit dem- **\<clear>** Element in einer Anwendungs Konfigurationsdatei Abschnitte löschen, die zuvor in der Computer Konfigurationsdatei definiert wurden</span><span class="sxs-lookup"><span data-stu-id="310e8-116">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="310e8-117">Der folgende Code der Computer Konfigurationsdatei deklariert den Abschnitt **\<mySection>** :</span><span class="sxs-lookup"><span data-stu-id="310e8-117">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="310e8-118">Mit dem folgenden Anwendungs Konfigurationsdatei-Code werden alle Einstellungen aus entfernt **\<mySection>** .</span><span class="sxs-lookup"><span data-stu-id="310e8-118">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="310e8-119">Die Anwendung kann keine der im- **\<mySection>** Abschnitt der Computer Konfigurationsdatei deklarierten Einstellungen abrufen.</span><span class="sxs-lookup"><span data-stu-id="310e8-119">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="310e8-120">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="310e8-120">Configuration file</span></span>

<span data-ttu-id="310e8-121">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="310e8-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="310e8-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="310e8-122">See also</span></span>

- [<span data-ttu-id="310e8-123">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="310e8-123">Configuration file schema for the .NET Framework</span></span>](index.md)
