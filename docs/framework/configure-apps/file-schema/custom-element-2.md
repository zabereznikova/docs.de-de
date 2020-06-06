---
title: Benutzerdefiniertes Element für NameValueSectionHandler und diktarysectionhandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: e5c5c6cf5744aa385e6f6700cad623751a4d7427
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215472"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="66113-102">Benutzerdefiniertes Element für NameValueSectionHandler und diktarysectionhandler</span><span class="sxs-lookup"><span data-stu-id="66113-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="66113-103">Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, die die <xref:System.Configuration.NameValueSectionHandler> -Klasse und die- <xref:System.Configuration.DictionarySectionHandler> Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="66113-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;**\<sectionName>**

## <a name="attributes"></a><span data-ttu-id="66113-104">Attribute</span><span class="sxs-lookup"><span data-stu-id="66113-104">Attributes</span></span>

<span data-ttu-id="66113-105">Keine</span><span class="sxs-lookup"><span data-stu-id="66113-105">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="66113-106">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="66113-106">Parent element</span></span>

|     | <span data-ttu-id="66113-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66113-107">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="66113-108">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="66113-108">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="66113-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="66113-109">Child elements</span></span>

|     | <span data-ttu-id="66113-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="66113-110">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="66113-111">[**\<add>**](add-element-for-custom-2.md)für <xref:System.Configuration.NameValueSectionHandler> und<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="66113-111">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="66113-112">Fügt benutzerdefinierte Anwendungseinstellungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="66113-112">Adds custom application settings.</span></span> |
| <span data-ttu-id="66113-113">[**\<remove>**](remove-element-for-custom-2.md)für <xref:System.Configuration.NameValueSectionHandler> und<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="66113-113">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="66113-114">Entfernt eine zuvor definierte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="66113-114">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="66113-115">[**\<clear>**](clear-element-for-custom-2.md)für <xref:System.Configuration.NameValueSectionHandler> und<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="66113-115">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="66113-116">Löscht alle zuvor definierten Einstellungen in einem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="66113-116">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="66113-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="66113-117">Remarks</span></span>

<span data-ttu-id="66113-118">Das- **\<sectionName>** Element ist ein benutzerdefiniertes Element, das durch ein- **\<section>** Tag im-Element definiert wird **\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="66113-118">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="66113-119">In der folgenden Tabelle wird der Objekttyp angezeigt, der von der ConfigurationSettings. GetConfig-Methode für jeden Konfigurations Abschnitts Handler zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="66113-119">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="66113-120">Konfigurations Abschnitts Handler</span><span class="sxs-lookup"><span data-stu-id="66113-120">Configuration section handler</span></span>                        | <span data-ttu-id="66113-121">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="66113-121">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="66113-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="66113-122">Example</span></span>

<span data-ttu-id="66113-123">Im folgenden Beispiel wird gezeigt, wie Sie Abschnitte deklarieren, die die <xref:System.Configuration.DictionarySectionHandler> Klassen und verwenden <xref:System.Configuration.NameValueSectionHandler> .</span><span class="sxs-lookup"><span data-stu-id="66113-123">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="66113-124">Das erste benutzerdefinierte Element ist **\<dictionarySample>** , das die von der- <xref:System.Configuration.DictionarySectionHandler> Klasse in der Assembly gelesenen Einstellungen enthält `System.dll` .</span><span class="sxs-lookup"><span data-stu-id="66113-124">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="66113-125">Das zweite benutzerdefinierte Element ist **\<mySection>** , das die von der- <xref:System.Configuration.NameValueSectionHandler> Klasse in der Assembly gelesenen Einstellungen enthält `System.dll` .</span><span class="sxs-lookup"><span data-stu-id="66113-125">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="66113-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="66113-126">Configuration file</span></span>

<span data-ttu-id="66113-127">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="66113-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="66113-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66113-128">See also</span></span>

- [<span data-ttu-id="66113-129">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="66113-129">Configuration file schema for the .NET Framework</span></span>](index.md)
