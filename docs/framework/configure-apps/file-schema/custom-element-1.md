---
title: Benutzerdefiniertes Element für SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: a40f35838655f6021af0b2e966335803ec8c16b4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "80635401"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="381f8-102">Benutzerdefiniertes Element für SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="381f8-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="381f8-103">Definiert die Einstellungen in einem benutzerdefinierten Konfigurations Abschnitt, der von einem-Element definiert wird, \<section> und verwendet die- <xref:System.Configuration.SingleTagSectionHandler> Klasse.</span><span class="sxs-lookup"><span data-stu-id="381f8-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="381f8-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="381f8-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="381f8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="381f8-105">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a><span data-ttu-id="381f8-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="381f8-106">Attributes</span></span>

<span data-ttu-id="381f8-107">Attribute und Attributwerte sind Benutzer definiert.</span><span class="sxs-lookup"><span data-stu-id="381f8-107">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="381f8-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="381f8-108">Parent element</span></span>

|     | <span data-ttu-id="381f8-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="381f8-109">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="381f8-110">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="381f8-110">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="381f8-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="381f8-111">Child elements</span></span>

<span data-ttu-id="381f8-112">Keine</span><span class="sxs-lookup"><span data-stu-id="381f8-112">None</span></span>

## <a name="remarks"></a><span data-ttu-id="381f8-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="381f8-113">Remarks</span></span>

<span data-ttu-id="381f8-114">Das- **\<sectionName>** Element ist ein benutzerdefiniertes Element, das durch ein- [**\<section>**](section-element.md) Tag im-Element definiert wird [**\<configSections>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="381f8-114">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="381f8-115">Das Konfigurationssystem gibt ein-Objekt zurück, <xref:System.Collections.IDictionary> Wenn aufgerufen wird <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="381f8-115">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="381f8-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="381f8-116">Example</span></span>

<span data-ttu-id="381f8-117">Im folgenden Beispiel wird ein benutzerdefiniertes Element namens deklariert **\<sampleSection>** , das von der-Klasse gelesene Einstellungen enthält <xref:System.Configuration.SingleTagSectionHandler> :</span><span class="sxs-lookup"><span data-stu-id="381f8-117">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="381f8-118">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="381f8-118">Configuration file</span></span>

<span data-ttu-id="381f8-119">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="381f8-119">This element can be used in the application configuration file, the machine configuration file (*Machine.config*), and *Web.config* files that aren't at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="381f8-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="381f8-120">See also</span></span>

- [<span data-ttu-id="381f8-121">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="381f8-121">Configuration file schema for the .NET Framework</span></span>](index.md)
