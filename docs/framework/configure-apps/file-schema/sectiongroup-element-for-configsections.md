---
title: <sectionGroup>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
ms.openlocfilehash: eb221027470fe6e485f8fcc4b939b71e4f219712
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215266"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="1c20f-102">\<sectionGroup>-Element für \<configSections></span><span class="sxs-lookup"><span data-stu-id="1c20f-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="1c20f-103">Definiert einen Namespace für Konfigurations Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="1c20f-103">Defines a namespace for configuration sections.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**

## <a name="syntax"></a><span data-ttu-id="1c20f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c20f-104">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="1c20f-105">attribute</span><span class="sxs-lookup"><span data-stu-id="1c20f-105">Attribute</span></span>

|           | <span data-ttu-id="1c20f-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1c20f-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="1c20f-107">**name**</span><span class="sxs-lookup"><span data-stu-id="1c20f-107">**name**</span></span>  | <span data-ttu-id="1c20f-108">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="1c20f-108">Required attribute.</span></span><br><br><span data-ttu-id="1c20f-109">Gibt den Namen der Abschnitts Gruppe an, die Sie definieren.</span><span class="sxs-lookup"><span data-stu-id="1c20f-109">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="1c20f-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="1c20f-110">Parent element</span></span>

|     | <span data-ttu-id="1c20f-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1c20f-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1c20f-112">**\<configSections>** Gewisses</span><span class="sxs-lookup"><span data-stu-id="1c20f-112">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="1c20f-113">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="1c20f-113">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="1c20f-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1c20f-114">Child elements</span></span>

|     | <span data-ttu-id="1c20f-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1c20f-115">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="1c20f-116">Enthält eine Konfigurations Abschnitts Deklaration.</span><span class="sxs-lookup"><span data-stu-id="1c20f-116">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1c20f-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1c20f-117">Remarks</span></span>

<span data-ttu-id="1c20f-118">Beim Deklarieren einer Abschnitts Gruppe wird ein containertag für Konfigurations Abschnitte erstellt, und es wird sichergestellt, dass keine Namenskonflikte mit von einer anderen Person definierten Konfigurations Abschnitten bestehen.</span><span class="sxs-lookup"><span data-stu-id="1c20f-118">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="1c20f-119">Sie können **\<sectionGroup>** Elemente in einander Schachteln.</span><span class="sxs-lookup"><span data-stu-id="1c20f-119">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="1c20f-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c20f-120">Example</span></span>

<span data-ttu-id="1c20f-121">Im folgenden Beispiel wird gezeigt, wie Sie eine Abschnitts Gruppe deklarieren und Abschnitte innerhalb einer Abschnitts Gruppe deklarieren:</span><span class="sxs-lookup"><span data-stu-id="1c20f-121">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="1c20f-122">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="1c20f-122">Configuration file</span></span>

<span data-ttu-id="1c20f-123">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="1c20f-123">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c20f-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1c20f-124">See also</span></span>

- [<span data-ttu-id="1c20f-125">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1c20f-125">Configuration file schema for the .NET Framework</span></span>](index.md)
