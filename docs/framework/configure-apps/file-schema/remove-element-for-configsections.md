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
ms.openlocfilehash: 7c0173879c692588cc2e15f0b14a5687bb0404fb
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300675"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="bfaca-102">\<Entfernen Sie >-Element für \<ConfigSections ></span><span class="sxs-lookup"><span data-stu-id="bfaca-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="bfaca-103">Entfernt einen vordefinierten Abschnitt oder Abschnittsgruppe.</span><span class="sxs-lookup"><span data-stu-id="bfaca-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="bfaca-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="bfaca-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="bfaca-105">&nbsp;&nbsp;[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="bfaca-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="bfaca-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**</span><span class="sxs-lookup"><span data-stu-id="bfaca-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="bfaca-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="bfaca-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="bfaca-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="bfaca-108">Attribute</span></span>

|           | <span data-ttu-id="bfaca-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bfaca-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="bfaca-110">**name**</span><span class="sxs-lookup"><span data-stu-id="bfaca-110">**name**</span></span>  | <span data-ttu-id="bfaca-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="bfaca-111">Required attribute.</span></span><br><br><span data-ttu-id="bfaca-112">Gibt den Namen des Abschnitts oder des zu entfernenden Abschnittsgruppe.</span><span class="sxs-lookup"><span data-stu-id="bfaca-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="bfaca-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="bfaca-113">Parent element</span></span>

|     | <span data-ttu-id="bfaca-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bfaca-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="bfaca-115"> *\*\<configSections>** Element</span><span class="sxs-lookup"><span data-stu-id="bfaca-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="bfaca-116">Enthält die Konfiguration im Abschnitt und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="bfaca-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="bfaca-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bfaca-117">Child elements</span></span>

<span data-ttu-id="bfaca-118">None</span><span class="sxs-lookup"><span data-stu-id="bfaca-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="bfaca-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bfaca-119">Remarks</span></span>

<span data-ttu-id="bfaca-120">Können Sie die  **\<entfernen >** Elements, Abschnitte und Abschnittsgruppen aus Ihrer Anwendung, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="bfaca-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="bfaca-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bfaca-121">Example</span></span>

<span data-ttu-id="bfaca-122">Das folgende Beispiel zeigt, wie Sie mit der  **\<entfernen >** Element in einer Anwendungskonfigurationsdatei auf einen Abschnitt, der zuvor in der Computerkonfigurationsdatei definiert zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="bfaca-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="bfaca-123">Der folgende Konfigurationscode Datei Computer deklariert Abschnitt  **\<SampleSection >** :</span><span class="sxs-lookup"><span data-stu-id="bfaca-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="bfaca-124">Der folgende Code für eine Anwendungskonfigurationsdatei entfernt die  **\<SampleSection >** Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="bfaca-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="bfaca-125">Nach dem entfernen kann nicht die Anwendung rufen Sie die Einstellungen in  **\<SampleSection >** .</span><span class="sxs-lookup"><span data-stu-id="bfaca-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="bfaca-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="bfaca-126">Configuration file</span></span>

<span data-ttu-id="bfaca-127">Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden ( *"Machine.config"* ), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="bfaca-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfaca-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfaca-128">See also</span></span>

- [<span data-ttu-id="bfaca-129">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bfaca-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
