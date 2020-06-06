---
title: <remove>-Element für NameValueSectionHandler und diktarysectionhandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: d1e4f3478f6afd6a20c01c6b57a137020ee88f5f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214753"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="e1235-102">\<remove>-Element für NameValueSectionHandler und diktarysectionhandler</span><span class="sxs-lookup"><span data-stu-id="e1235-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="e1235-103">Entfernt eine zuvor definierte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="e1235-103">Removes a previously defined setting.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="e1235-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1235-104">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="e1235-105">attribute</span><span class="sxs-lookup"><span data-stu-id="e1235-105">Attribute</span></span>

|           | <span data-ttu-id="e1235-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1235-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="e1235-107">**key**</span><span class="sxs-lookup"><span data-stu-id="e1235-107">**key**</span></span>   | <span data-ttu-id="e1235-108">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="e1235-108">Required attribute.</span></span><br><br><span data-ttu-id="e1235-109">Gibt den Namen der zu entfernenden Einstellung an.</span><span class="sxs-lookup"><span data-stu-id="e1235-109">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="e1235-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="e1235-110">Parent element</span></span>

| <span data-ttu-id="e1235-111">Element</span><span class="sxs-lookup"><span data-stu-id="e1235-111">Element</span></span> | <span data-ttu-id="e1235-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1235-112">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="e1235-113">**\<sectionName>** Gewisses</span><span class="sxs-lookup"><span data-stu-id="e1235-113">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="e1235-114">Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, die die <xref:System.Configuration.NameValueSectionHandler> -Klasse und die- <xref:System.Configuration.DictionarySectionHandler> Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1235-114">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e1235-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1235-115">Child elements</span></span>

<span data-ttu-id="e1235-116">Keine</span><span class="sxs-lookup"><span data-stu-id="e1235-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="e1235-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e1235-117">Remarks</span></span>

<span data-ttu-id="e1235-118">Sie können das- **\<remove>** Element verwenden, um Einstellungen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdateien definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e1235-118">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="e1235-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1235-119">Example</span></span>

<span data-ttu-id="e1235-120">Im folgenden Beispiel wird gezeigt, wie das- **\<remove>** Element in einer Anwendungs Konfigurationsdatei verwendet wird, um zuvor in der Computer Konfigurationsdatei definierte Einstellungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e1235-120">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="e1235-121">Der folgende Computer Konfigurationsdatei-Code deklariert den-Abschnitt **\<mySection>** und fügt ihm zwei Einstellungen hinzu `key1` `key2` :</span><span class="sxs-lookup"><span data-stu-id="e1235-121">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="e1235-122">Mit dem folgenden Anwendungs Konfigurationsdatei-Code wird die `key2` Einstellung aus entfernt **\<mySection>** :</span><span class="sxs-lookup"><span data-stu-id="e1235-122">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="e1235-123">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="e1235-123">Configuration file</span></span>

<span data-ttu-id="e1235-124">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="e1235-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1235-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1235-125">See also</span></span>

- [<span data-ttu-id="e1235-126">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e1235-126">Configuration file schema for the .NET Framework</span></span>](index.md)
