---
title: Benutzerdefiniertes Element für NameValueSectionHandler und diktarysectionhandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 890269857aaa00ce62195ccb2f4cb184b363b61e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921044"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="c3495-102">Benutzerdefiniertes Element für NameValueSectionHandler und diktarysectionhandler</span><span class="sxs-lookup"><span data-stu-id="c3495-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="c3495-103">Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, die <xref:System.Configuration.NameValueSectionHandler> die <xref:System.Configuration.DictionarySectionHandler> -Klasse und die-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3495-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="c3495-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c3495-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="c3495-105">&nbsp;&nbsp; **\<sectionName>**</span><span class="sxs-lookup"><span data-stu-id="c3495-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="c3495-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="c3495-106">Attributes</span></span>

<span data-ttu-id="c3495-107">None</span><span class="sxs-lookup"><span data-stu-id="c3495-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="c3495-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="c3495-108">Parent element</span></span>

|     | <span data-ttu-id="c3495-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3495-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c3495-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c3495-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="c3495-111">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c3495-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="c3495-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3495-112">Child elements</span></span>

|     | <span data-ttu-id="c3495-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3495-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="c3495-114">Hinzufügen von <xref:System.Configuration.NameValueSectionHandler> > für und [ **\<** ](add-element-for-custom-2.md)<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="c3495-114">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="c3495-115">Fügt benutzerdefinierte Anwendungseinstellungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="c3495-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="c3495-116">Entfernen Sie <xref:System.Configuration.NameValueSectionHandler> > für und. [ **\<** ](remove-element-for-custom-2.md)<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="c3495-116">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="c3495-117">Entfernt eine zuvor definierte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="c3495-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="c3495-118">Löschen von <xref:System.Configuration.NameValueSectionHandler> > für und [ **\<** ](clear-element-for-custom-2.md)<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="c3495-118">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="c3495-119">Löscht alle zuvor definierten Einstellungen in einem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c3495-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c3495-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3495-120">Remarks</span></span>

<span data-ttu-id="c3495-121">**Das\<Element sectionName >** ist ein benutzerdefiniertes Element, das durch einen  **\<Abschnitt >** -Tag im  **\<>** -Element von configabschnitts definiert wird.</span><span class="sxs-lookup"><span data-stu-id="c3495-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="c3495-122">In der folgenden Tabelle wird der Objekttyp angezeigt, der von der ConfigurationSettings. GetConfig-Methode für jeden Konfigurations Abschnitts Handler zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="c3495-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="c3495-123">Konfigurations Abschnitts Handler</span><span class="sxs-lookup"><span data-stu-id="c3495-123">Configuration section handler</span></span>                        | <span data-ttu-id="c3495-124">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="c3495-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="c3495-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3495-125">Example</span></span>

<span data-ttu-id="c3495-126">Im folgenden Beispiel wird gezeigt, wie Sie Abschnitte deklarieren <xref:System.Configuration.DictionarySectionHandler> , <xref:System.Configuration.NameValueSectionHandler> die die Klassen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3495-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="c3495-127">Das erste benutzerdefinierte Element ist <xref:System.Configuration.DictionarySectionHandler> `System.dll`  **\<eine "ditionarysample >** ", die die von der-Klasse in der Assembly gelesenen Einstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="c3495-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="c3495-128">Das zweite benutzerdefinierte Element ist  **\<mySection >** , das die von der <xref:System.Configuration.NameValueSectionHandler> -Klasse in der `System.dll` Assembly gelesenen Einstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="c3495-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="c3495-129">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="c3495-129">Configuration file</span></span>

<span data-ttu-id="c3495-130">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="c3495-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3495-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3495-131">See also</span></span>

- [<span data-ttu-id="c3495-132">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c3495-132">Configuration file schema for the .NET Framework</span></span>](index.md)
