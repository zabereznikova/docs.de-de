---
title: <sectionGroup>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9113811557ded3a580a0bbacb24f2fe7e8d05ccf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114782"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="393d1-102">\<sectionGroup-> Element für \<configabschnitts-></span><span class="sxs-lookup"><span data-stu-id="393d1-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="393d1-103">Definiert einen Namespace für Konfigurations Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="393d1-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="393d1-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="393d1-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="393d1-105">&nbsp;&nbsp;[ **\<configabschnitts >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="393d1-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="393d1-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="393d1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="393d1-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="393d1-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="393d1-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="393d1-108">Attribute</span></span>

|           | <span data-ttu-id="393d1-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="393d1-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="393d1-110">**name**</span><span class="sxs-lookup"><span data-stu-id="393d1-110">**name**</span></span>  | <span data-ttu-id="393d1-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="393d1-111">Required attribute.</span></span><br><br><span data-ttu-id="393d1-112">Gibt den Namen der Abschnitts Gruppe an, die Sie definieren.</span><span class="sxs-lookup"><span data-stu-id="393d1-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="393d1-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="393d1-113">Parent element</span></span>

|     | <span data-ttu-id="393d1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="393d1-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="393d1-115"> **\<configabschnitts >** Gewisses</span><span class="sxs-lookup"><span data-stu-id="393d1-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="393d1-116">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="393d1-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="393d1-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="393d1-117">Child elements</span></span>

|     | <span data-ttu-id="393d1-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="393d1-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="393d1-119"> **\<Abschnitt >** </span><span class="sxs-lookup"><span data-stu-id="393d1-119">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="393d1-120">Enthält eine Konfigurations Abschnitts Deklaration.</span><span class="sxs-lookup"><span data-stu-id="393d1-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="393d1-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="393d1-121">Remarks</span></span>

<span data-ttu-id="393d1-122">Beim Deklarieren einer Abschnitts Gruppe wird ein containertag für Konfigurations Abschnitte erstellt, und es wird sichergestellt, dass keine Namenskonflikte mit von einer anderen Person definierten Konfigurations Abschnitten bestehen.</span><span class="sxs-lookup"><span data-stu-id="393d1-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="393d1-123">Sie können **\<sectionGroup->** Elemente in einander Schachteln.</span><span class="sxs-lookup"><span data-stu-id="393d1-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="393d1-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="393d1-124">Example</span></span>

<span data-ttu-id="393d1-125">Im folgenden Beispiel wird gezeigt, wie Sie eine Abschnitts Gruppe deklarieren und Abschnitte innerhalb einer Abschnitts Gruppe deklarieren:</span><span class="sxs-lookup"><span data-stu-id="393d1-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="393d1-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="393d1-126">Configuration file</span></span>

<span data-ttu-id="393d1-127">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="393d1-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="393d1-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="393d1-128">See also</span></span>

- [<span data-ttu-id="393d1-129">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="393d1-129">Configuration file schema for the .NET Framework</span></span>](index.md)
