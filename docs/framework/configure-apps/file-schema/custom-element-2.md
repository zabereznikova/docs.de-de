---
title: Benutzerdefiniertes Element für NameValueSectionHandler und diktarysectionhandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d73c07d58bb226346cb99a1fe50b12bb0e7e746e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118542"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="29e07-102">Benutzerdefiniertes Element für NameValueSectionHandler und diktarysectionhandler</span><span class="sxs-lookup"><span data-stu-id="29e07-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="29e07-103">Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, in denen die Klassen <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29e07-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="29e07-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="29e07-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="29e07-105">&nbsp;&nbsp; **\<sectionName >**</span><span class="sxs-lookup"><span data-stu-id="29e07-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="29e07-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="29e07-106">Attributes</span></span>

<span data-ttu-id="29e07-107">Keiner</span><span class="sxs-lookup"><span data-stu-id="29e07-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="29e07-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="29e07-108">Parent element</span></span>

|     | <span data-ttu-id="29e07-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29e07-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="29e07-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="29e07-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="29e07-111">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="29e07-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="29e07-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="29e07-112">Child elements</span></span>

|     | <span data-ttu-id="29e07-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29e07-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="29e07-114">[ **\<** ](add-element-for-custom-2.md) für <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> hinzufügen</span><span class="sxs-lookup"><span data-stu-id="29e07-114">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="29e07-115">Fügt benutzerdefinierte Anwendungseinstellungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="29e07-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="29e07-116">[ **\<** ](remove-element-for-custom-2.md) für <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> entfernen.</span><span class="sxs-lookup"><span data-stu-id="29e07-116">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="29e07-117">Entfernt eine zuvor definierte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="29e07-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="29e07-118">[ **\<** ](clear-element-for-custom-2.md) für <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> löschen.</span><span class="sxs-lookup"><span data-stu-id="29e07-118">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="29e07-119">Löscht alle zuvor definierten Einstellungen in einem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="29e07-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="29e07-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="29e07-120">Remarks</span></span>

<span data-ttu-id="29e07-121">Das **\<sectionName >** -Element ist ein benutzerdefiniertes Element, das durch einen **\<Abschnitt >** -Tag im\<Element > **configabschnitts** definiert wird.</span><span class="sxs-lookup"><span data-stu-id="29e07-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="29e07-122">In der folgenden Tabelle wird der Objekttyp angezeigt, der von der ConfigurationSettings. GetConfig-Methode für jeden Konfigurations Abschnitts Handler zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="29e07-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="29e07-123">Konfigurations Abschnitts Handler</span><span class="sxs-lookup"><span data-stu-id="29e07-123">Configuration section handler</span></span>                        | <span data-ttu-id="29e07-124">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="29e07-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="29e07-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="29e07-125">Example</span></span>

<span data-ttu-id="29e07-126">Im folgenden Beispiel wird gezeigt, wie Sie Abschnitte deklarieren, in denen die Klassen <xref:System.Configuration.DictionarySectionHandler> und <xref:System.Configuration.NameValueSectionHandler> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29e07-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="29e07-127">Das erste benutzerdefinierte Element ist **\<"ditaarysample" >** , das die von der <xref:System.Configuration.DictionarySectionHandler>-Klasse in der `System.dll` Assembly gelesenen Einstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="29e07-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="29e07-128">Das zweite benutzerdefinierte Element ist **\<mySection >** , das die von der <xref:System.Configuration.NameValueSectionHandler>-Klasse in der `System.dll` Assembly gelesenen Einstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="29e07-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="29e07-129">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="29e07-129">Configuration file</span></span>

<span data-ttu-id="29e07-130">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="29e07-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="29e07-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29e07-131">See also</span></span>

- [<span data-ttu-id="29e07-132">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="29e07-132">Configuration file schema for the .NET Framework</span></span>](index.md)
