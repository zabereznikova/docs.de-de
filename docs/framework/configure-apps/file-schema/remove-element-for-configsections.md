---
title: <remove>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 99d67bd621390789993caa4862e5ce379135eb92
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215389"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="73ff5-102">\<> Element für \<configabschnitts entfernen ></span><span class="sxs-lookup"><span data-stu-id="73ff5-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="73ff5-103">Entfernt eine vordefinierte Abschnitts-oder Abschnitts Gruppe.</span><span class="sxs-lookup"><span data-stu-id="73ff5-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="73ff5-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="73ff5-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="73ff5-105">&nbsp;&nbsp;[ **\<configabschnitts >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="73ff5-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="73ff5-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**</span><span class="sxs-lookup"><span data-stu-id="73ff5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="73ff5-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="73ff5-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="73ff5-108">attribute</span><span class="sxs-lookup"><span data-stu-id="73ff5-108">Attribute</span></span>

|           | <span data-ttu-id="73ff5-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="73ff5-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="73ff5-110">**name**</span><span class="sxs-lookup"><span data-stu-id="73ff5-110">**name**</span></span>  | <span data-ttu-id="73ff5-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="73ff5-111">Required attribute.</span></span><br><br><span data-ttu-id="73ff5-112">Gibt den Namen des Abschnitts oder der Abschnitts Gruppe an, der entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="73ff5-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="73ff5-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="73ff5-113">Parent element</span></span>

|     | <span data-ttu-id="73ff5-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="73ff5-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="73ff5-115"> **\<configabschnitts >** Gewisses</span><span class="sxs-lookup"><span data-stu-id="73ff5-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="73ff5-116">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="73ff5-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="73ff5-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="73ff5-117">Child elements</span></span>

<span data-ttu-id="73ff5-118">Keine</span><span class="sxs-lookup"><span data-stu-id="73ff5-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="73ff5-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="73ff5-119">Remarks</span></span>

<span data-ttu-id="73ff5-120">Sie können das **\<remove >** -Element verwenden, um Abschnitts-und Abschnitts Gruppen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="73ff5-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="73ff5-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="73ff5-121">Example</span></span>

<span data-ttu-id="73ff5-122">Im folgenden Beispiel wird gezeigt, wie das **\<remove >** -Elements in einer Anwendungs Konfigurationsdatei verwendet wird, um einen Abschnitt zu entfernen, der zuvor in der Computer Konfigurationsdatei definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="73ff5-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="73ff5-123">Der folgende Code der Computer Konfigurationsdatei deklariert den Abschnitt **\<sampleSection->** :</span><span class="sxs-lookup"><span data-stu-id="73ff5-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="73ff5-124">Der folgende Anwendungs Konfigurationsdatei-Code entfernt den Abschnitt **\<Sample section >** .</span><span class="sxs-lookup"><span data-stu-id="73ff5-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="73ff5-125">Nach dem Entfernen kann die Anwendung die Einstellungen nicht mehr in **\<sampleSection->** abrufen.</span><span class="sxs-lookup"><span data-stu-id="73ff5-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="73ff5-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="73ff5-126">Configuration file</span></span>

<span data-ttu-id="73ff5-127">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="73ff5-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="73ff5-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="73ff5-128">See also</span></span>

- [<span data-ttu-id="73ff5-129">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="73ff5-129">Configuration file schema for the .NET Framework</span></span>](index.md)
