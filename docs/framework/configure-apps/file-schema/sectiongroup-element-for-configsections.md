---
title: '&lt;SectionGroup&gt; -Element für &lt;"configSections"&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: guardrex
ms.author: mairaw
ms.openlocfilehash: b898c81700e95ec9bc94e04c5a76494b7ac4b0dc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754014"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="f883d-102">\<SectionGroup >-Element für \<ConfigSections ></span><span class="sxs-lookup"><span data-stu-id="f883d-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="f883d-103">Definiert einen Namespace für Konfigurationsabschnitte.</span><span class="sxs-lookup"><span data-stu-id="f883d-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="f883d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="f883d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="f883d-105">&nbsp;&nbsp;[**\<ConfigSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="f883d-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="f883d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<SectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="f883d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f883d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f883d-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="f883d-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="f883d-108">Attribute</span></span>

|           | <span data-ttu-id="f883d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f883d-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f883d-110">**name**</span><span class="sxs-lookup"><span data-stu-id="f883d-110">**name**</span></span>  | <span data-ttu-id="f883d-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f883d-111">Required attribute.</span></span><br><br><span data-ttu-id="f883d-112">Gibt den Namen der Abschnittsgruppe, die Sie definieren.</span><span class="sxs-lookup"><span data-stu-id="f883d-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f883d-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="f883d-113">Parent element</span></span>

|     | <span data-ttu-id="f883d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f883d-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f883d-115">**\<ConfigSections >** Element</span><span class="sxs-lookup"><span data-stu-id="f883d-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="f883d-116">Enthält die Konfiguration im Abschnitt und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="f883d-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f883d-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f883d-117">Child elements</span></span>

|     | <span data-ttu-id="f883d-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f883d-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f883d-119">**\<Abschnitt >**</span><span class="sxs-lookup"><span data-stu-id="f883d-119">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="f883d-120">Enthält eine Deklaration der Konfiguration im Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="f883d-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f883d-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f883d-121">Remarks</span></span>

<span data-ttu-id="f883d-122">Deklarieren eine Abschnittsgruppe erstellt ein Containertag für Konfigurationsabschnitte und stellt sicher, dass keine Namenskonflikte mit Konfigurationsabschnitte, die von einer anderen Person definiert.</span><span class="sxs-lookup"><span data-stu-id="f883d-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="f883d-123">Sie können schachteln  **\<SectionGroup >** Elemente in einem anderen.</span><span class="sxs-lookup"><span data-stu-id="f883d-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="f883d-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f883d-124">Example</span></span>

<span data-ttu-id="f883d-125">Das folgende Beispiel zeigt, wie zum Deklarieren einer Abschnittsgruppe und Abschnitte innerhalb einer Abschnittsgruppe deklarieren:</span><span class="sxs-lookup"><span data-stu-id="f883d-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="f883d-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="f883d-126">Configuration file</span></span>

<span data-ttu-id="f883d-127">Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="f883d-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="f883d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f883d-128">See also</span></span>

[<span data-ttu-id="f883d-129">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f883d-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
