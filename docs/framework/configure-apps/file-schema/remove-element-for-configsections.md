---
title: <remove>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 4ff9bb537a31e28dbd4b878c1bc04c96262f85ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927456"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="15b76-102">\<Entfernen Sie > Element \<für configabschnitts ></span><span class="sxs-lookup"><span data-stu-id="15b76-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="15b76-103">Entfernt eine vordefinierte Abschnitts-oder Abschnitts Gruppe.</span><span class="sxs-lookup"><span data-stu-id="15b76-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="15b76-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="15b76-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="15b76-105">&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="15b76-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="15b76-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**</span><span class="sxs-lookup"><span data-stu-id="15b76-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="15b76-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="15b76-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="15b76-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="15b76-108">Attribute</span></span>

|           | <span data-ttu-id="15b76-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15b76-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="15b76-110">**name**</span><span class="sxs-lookup"><span data-stu-id="15b76-110">**name**</span></span>  | <span data-ttu-id="15b76-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="15b76-111">Required attribute.</span></span><br><br><span data-ttu-id="15b76-112">Gibt den Namen des Abschnitts oder der Abschnitts Gruppe an, der entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="15b76-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="15b76-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="15b76-113">Parent element</span></span>

|     | <span data-ttu-id="15b76-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15b76-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="15b76-115"> **\<configSections>** Element</span><span class="sxs-lookup"><span data-stu-id="15b76-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="15b76-116">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="15b76-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="15b76-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15b76-117">Child elements</span></span>

<span data-ttu-id="15b76-118">None</span><span class="sxs-lookup"><span data-stu-id="15b76-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="15b76-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15b76-119">Remarks</span></span>

<span data-ttu-id="15b76-120">Sie können das  **\<remove >** -Element verwenden, um Abschnitts-und Abschnitts Gruppen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="15b76-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="15b76-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="15b76-121">Example</span></span>

<span data-ttu-id="15b76-122">Im folgenden Beispiel wird gezeigt, wie das  **\<remove >** -Element in einer Anwendungs Konfigurationsdatei verwendet wird, um einen Abschnitt zu entfernen, der zuvor in der Computer Konfigurationsdatei definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="15b76-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="15b76-123">Der folgende Code der Computer Konfigurationsdatei deklariert den Abschnitt  **\<sampleSection->** :</span><span class="sxs-lookup"><span data-stu-id="15b76-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="15b76-124">Der folgende Anwendungs Konfigurationsdatei-Code entfernt den  **\<Abschnitt "Sample section >** ".</span><span class="sxs-lookup"><span data-stu-id="15b76-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="15b76-125">Nach dem Entfernen kann die Anwendung die Einstellungen nicht mehr in  **\<sampleSection >** abrufen.</span><span class="sxs-lookup"><span data-stu-id="15b76-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="15b76-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="15b76-126">Configuration file</span></span>

<span data-ttu-id="15b76-127">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="15b76-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="15b76-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15b76-128">See also</span></span>

- [<span data-ttu-id="15b76-129">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="15b76-129">Configuration file schema for the .NET Framework</span></span>](index.md)
