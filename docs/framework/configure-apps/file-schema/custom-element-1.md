---
title: Benutzerdefiniertes Element für SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: a40f35838655f6021af0b2e966335803ec8c16b4
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635401"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="bd0f5-102">Benutzerdefiniertes Element für SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="bd0f5-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="bd0f5-103">Definiert Einstellungen in einem benutzerdefinierten Konfigurationsabschnitt, der durch \< <xref:System.Configuration.SingleTagSectionHandler> einen Abschnitt>-Elements definiert wird und die Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="bd0f5-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="bd0f5-104">Konfiguration &nbsp; &nbsp;>[\*\* \<\*\*](configuration-element.md) \* \<AbschnittName>\*</span><span class="sxs-lookup"><span data-stu-id="bd0f5-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="bd0f5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd0f5-105">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a><span data-ttu-id="bd0f5-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="bd0f5-106">Attributes</span></span>

<span data-ttu-id="bd0f5-107">Attribute und Attributwerte sind benutzerdefinierte.</span><span class="sxs-lookup"><span data-stu-id="bd0f5-107">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="bd0f5-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="bd0f5-108">Parent element</span></span>

|     | <span data-ttu-id="bd0f5-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd0f5-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="bd0f5-110">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="bd0f5-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="bd0f5-111">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="bd0f5-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="bd0f5-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bd0f5-112">Child elements</span></span>

<span data-ttu-id="bd0f5-113">Keine</span><span class="sxs-lookup"><span data-stu-id="bd0f5-113">None</span></span>

## <a name="remarks"></a><span data-ttu-id="bd0f5-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd0f5-114">Remarks</span></span>

<span data-ttu-id="bd0f5-115">Das \*\* \<sectionName>-Element\*\* ist ein benutzerdefiniertes Element, das [\*\* \<\*\*](section-element.md) [\*\* \<\*\*](configsections-element-for-configuration.md) durch ein>-Tag im configSections->-Element definiert wird.</span><span class="sxs-lookup"><span data-stu-id="bd0f5-115">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="bd0f5-116">Das Konfigurationssystem <xref:System.Collections.IDictionary> gibt ein <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>Objekt zurück, wenn Sie aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bd0f5-116">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="bd0f5-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd0f5-117">Example</span></span>

<span data-ttu-id="bd0f5-118">Im folgenden Beispiel wird ein benutzerdefiniertes Element namens <xref:System.Configuration.SingleTagSectionHandler> \*\* \<sampleSection>\*\* deklariert, das Einstellungen enthält, die von der Klasse gelesen werden:</span><span class="sxs-lookup"><span data-stu-id="bd0f5-118">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="bd0f5-119">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="bd0f5-119">Configuration file</span></span>

<span data-ttu-id="bd0f5-120">Dieses Element kann in der Anwendungskonfigurationsdatei, der Computerkonfigurationsdatei (*Machine.config*) und *Web.config-Dateien* verwendet werden, die sich nicht auf Anwendungsverzeichnisebene befinden.</span><span class="sxs-lookup"><span data-stu-id="bd0f5-120">This element can be used in the application configuration file, the machine configuration file (*Machine.config*), and *Web.config* files that aren't at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd0f5-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd0f5-121">See also</span></span>

- [<span data-ttu-id="bd0f5-122">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bd0f5-122">Configuration file schema for the .NET Framework</span></span>](index.md)
