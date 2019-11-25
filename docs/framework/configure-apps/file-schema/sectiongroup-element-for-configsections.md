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
ms.openlocfilehash: 746a997e162b0fd370a249b8d039be623b57d77f
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089007"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="d65a2-102">\<sectionGroup-> Element für \<configabschnitts-></span><span class="sxs-lookup"><span data-stu-id="d65a2-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="d65a2-103">Definiert einen Namespace für Konfigurations Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="d65a2-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="d65a2-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d65a2-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="d65a2-105">&nbsp;&nbsp;[ **\<configabschnitts >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="d65a2-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="d65a2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="d65a2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d65a2-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d65a2-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="d65a2-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="d65a2-108">Attribute</span></span>

|           | <span data-ttu-id="d65a2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d65a2-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="d65a2-110">**name**</span><span class="sxs-lookup"><span data-stu-id="d65a2-110">**name**</span></span>  | <span data-ttu-id="d65a2-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="d65a2-111">Required attribute.</span></span><br><br><span data-ttu-id="d65a2-112">Gibt den Namen der Abschnitts Gruppe an, die Sie definieren.</span><span class="sxs-lookup"><span data-stu-id="d65a2-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="d65a2-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="d65a2-113">Parent element</span></span>

|     | <span data-ttu-id="d65a2-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d65a2-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d65a2-115"> **\<configabschnitts >** Gewisses</span><span class="sxs-lookup"><span data-stu-id="d65a2-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="d65a2-116">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="d65a2-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d65a2-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d65a2-117">Child elements</span></span>

|     | <span data-ttu-id="d65a2-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d65a2-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d65a2-119"> **\<Abschnitt >** </span><span class="sxs-lookup"><span data-stu-id="d65a2-119">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="d65a2-120">Enthält eine Konfigurations Abschnitts Deklaration.</span><span class="sxs-lookup"><span data-stu-id="d65a2-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d65a2-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d65a2-121">Remarks</span></span>

<span data-ttu-id="d65a2-122">Beim Deklarieren einer Abschnitts Gruppe wird ein containertag für Konfigurations Abschnitte erstellt, und es wird sichergestellt, dass keine Namenskonflikte mit von einer anderen Person definierten Konfigurations Abschnitten bestehen.</span><span class="sxs-lookup"><span data-stu-id="d65a2-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="d65a2-123">Sie können **\<sectionGroup->** Elemente in einander Schachteln.</span><span class="sxs-lookup"><span data-stu-id="d65a2-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="d65a2-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d65a2-124">Example</span></span>

<span data-ttu-id="d65a2-125">Im folgenden Beispiel wird gezeigt, wie Sie eine Abschnitts Gruppe deklarieren und Abschnitte innerhalb einer Abschnitts Gruppe deklarieren:</span><span class="sxs-lookup"><span data-stu-id="d65a2-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="d65a2-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="d65a2-126">Configuration file</span></span>

<span data-ttu-id="d65a2-127">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="d65a2-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d65a2-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d65a2-128">See also</span></span>

- [<span data-ttu-id="d65a2-129">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d65a2-129">Configuration file schema for the .NET Framework</span></span>](index.md)
