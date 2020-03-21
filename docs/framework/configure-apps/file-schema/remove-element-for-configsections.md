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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154529"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="37cb4-102">\<Entfernen>-Elements für \<configSections></span><span class="sxs-lookup"><span data-stu-id="37cb4-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="37cb4-103">Entfernt einen vordefinierten Abschnitt oder eine Vorschnittgruppe.</span><span class="sxs-lookup"><span data-stu-id="37cb4-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="37cb4-104">[**\<Konfiguration>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="37cb4-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="37cb4-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="37cb4-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="37cb4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<entfernen sie>**</span><span class="sxs-lookup"><span data-stu-id="37cb4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="37cb4-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="37cb4-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="37cb4-108">attribute</span><span class="sxs-lookup"><span data-stu-id="37cb4-108">Attribute</span></span>

|           | <span data-ttu-id="37cb4-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37cb4-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="37cb4-110">**Name**</span><span class="sxs-lookup"><span data-stu-id="37cb4-110">**name**</span></span>  | <span data-ttu-id="37cb4-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="37cb4-111">Required attribute.</span></span><br><br><span data-ttu-id="37cb4-112">Gibt den Namen des zu entfernenden Abschnitts oder der Zu entfernenden Abschnittsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="37cb4-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="37cb4-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="37cb4-113">Parent element</span></span>

|     | <span data-ttu-id="37cb4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37cb4-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="37cb4-115">\*\* \<configSections>\*\* Element</span><span class="sxs-lookup"><span data-stu-id="37cb4-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="37cb4-116">Enthält Konfigurationsabschnittund- und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="37cb4-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="37cb4-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="37cb4-117">Child elements</span></span>

<span data-ttu-id="37cb4-118">Keine</span><span class="sxs-lookup"><span data-stu-id="37cb4-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="37cb4-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="37cb4-119">Remarks</span></span>

<span data-ttu-id="37cb4-120">Sie können das \*\* \<>-Element entfernen\*\* verwenden, um Abschnitte und Abschnittsgruppen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Konfigurationsdateihierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="37cb4-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="37cb4-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37cb4-121">Example</span></span>

<span data-ttu-id="37cb4-122">Im folgenden Beispiel wird gezeigt, wie Sie das \*\* \<>-Element\*\* in einer Anwendungskonfigurationsdatei verwenden, um einen zuvor in der Maschinenkonfigurationsdatei definierten Abschnitt zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="37cb4-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="37cb4-123">Der folgende Computerkonfigurationsdateicode deklariert den Abschnitt \*\* \<sampleSection>: \*\*</span><span class="sxs-lookup"><span data-stu-id="37cb4-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="37cb4-124">Der folgende Anwendungskonfigurationsdateicode entfernt den \*\* \<Abschnitt "beispielAbschnitt>.\*\*</span><span class="sxs-lookup"><span data-stu-id="37cb4-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="37cb4-125">Nach dem Entfernen kann die Anwendung die Einstellungen in \*\* \<sampleSection>\*\* nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="37cb4-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="37cb4-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="37cb4-126">Configuration file</span></span>

<span data-ttu-id="37cb4-127">Dieses Element kann in der Anwendungskonfigurationsdatei, der Computerkonfigurationsdatei (*Machine.config*) und *web.config-Dateien* verwendet werden, die sich nicht auf Anwendungsverzeichnisebene befinden.</span><span class="sxs-lookup"><span data-stu-id="37cb4-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="37cb4-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37cb4-128">See also</span></span>

- [<span data-ttu-id="37cb4-129">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="37cb4-129">Configuration file schema for the .NET Framework</span></span>](index.md)
