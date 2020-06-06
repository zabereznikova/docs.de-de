---
title: <remove>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154529"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="30d36-102">\<remove>-Element für \<configSections></span><span class="sxs-lookup"><span data-stu-id="30d36-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="30d36-103">Entfernt eine vordefinierte Abschnitts-oder Abschnitts Gruppe.</span><span class="sxs-lookup"><span data-stu-id="30d36-103">Removes a predefined section or section group.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="30d36-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30d36-104">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="30d36-105">attribute</span><span class="sxs-lookup"><span data-stu-id="30d36-105">Attribute</span></span>

|           | <span data-ttu-id="30d36-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="30d36-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="30d36-107">**name**</span><span class="sxs-lookup"><span data-stu-id="30d36-107">**name**</span></span>  | <span data-ttu-id="30d36-108">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="30d36-108">Required attribute.</span></span><br><br><span data-ttu-id="30d36-109">Gibt den Namen des Abschnitts oder der Abschnitts Gruppe an, der entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="30d36-109">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="30d36-110">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="30d36-110">Parent element</span></span>

|     | <span data-ttu-id="30d36-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="30d36-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="30d36-112">**\<configSections>** Gewisses</span><span class="sxs-lookup"><span data-stu-id="30d36-112">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="30d36-113">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="30d36-113">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="30d36-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30d36-114">Child elements</span></span>

<span data-ttu-id="30d36-115">Keine</span><span class="sxs-lookup"><span data-stu-id="30d36-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="30d36-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="30d36-116">Remarks</span></span>

<span data-ttu-id="30d36-117">Sie können das **\<remove>** -Element verwenden, um Abschnitts-und Abschnitts Gruppen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdateien definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="30d36-117">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="30d36-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30d36-118">Example</span></span>

<span data-ttu-id="30d36-119">Das folgende Beispiel zeigt, wie das- **\<remove>** Element in einer Anwendungs Konfigurationsdatei verwendet wird, um einen Abschnitt zu entfernen, der zuvor in der Computer Konfigurationsdatei definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="30d36-119">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="30d36-120">Der folgende Code der Computer Konfigurationsdatei deklariert den Abschnitt **\<sampleSection>** :</span><span class="sxs-lookup"><span data-stu-id="30d36-120">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

```xml
<!-- Machine.config file -->
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

<span data-ttu-id="30d36-121">Der folgende Anwendungs Konfigurationsdatei-Code entfernt den- **\<sampleSection>** Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="30d36-121">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="30d36-122">Nach dem Entfernen kann die Anwendung die Einstellungen in nicht abrufen **\<sampleSection>** .</span><span class="sxs-lookup"><span data-stu-id="30d36-122">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="30d36-123">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="30d36-123">Configuration file</span></span>

<span data-ttu-id="30d36-124">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="30d36-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="30d36-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30d36-125">See also</span></span>

- [<span data-ttu-id="30d36-126">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="30d36-126">Configuration file schema for the .NET Framework</span></span>](index.md)
