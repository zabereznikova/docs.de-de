---
title: <clear>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155426"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="6f5f7-102">\<clear>-Element für \<configSections></span><span class="sxs-lookup"><span data-stu-id="6f5f7-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="6f5f7-103">Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="6f5f7-104">&nbsp; &nbsp; &nbsp; &nbsp; [\*\* \<Konfiguration>\*\*](configuration-element.md) &nbsp; &nbsp; [\*\* \<configSections\*\*](configsections-element-for-configuration.md) **>\<klare>**</span><span class="sxs-lookup"><span data-stu-id="6f5f7-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6f5f7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f5f7-105">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="6f5f7-106">attribute</span><span class="sxs-lookup"><span data-stu-id="6f5f7-106">Attribute</span></span>

|           | <span data-ttu-id="6f5f7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f5f7-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="6f5f7-108">**Name**</span><span class="sxs-lookup"><span data-stu-id="6f5f7-108">**name**</span></span>  | <span data-ttu-id="6f5f7-109">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-109">Required attribute.</span></span><br><br><span data-ttu-id="6f5f7-110">Gibt den Namen des zu entfernenden Abschnitts oder der Zu entfernenden Abschnittsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-110">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="6f5f7-111">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="6f5f7-111">Parent element</span></span>

|     | <span data-ttu-id="6f5f7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f5f7-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6f5f7-113">\*\* \<configSections>\*\* Element</span><span class="sxs-lookup"><span data-stu-id="6f5f7-113">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="6f5f7-114">Enthält Konfigurationsabschnittund- und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-114">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6f5f7-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6f5f7-115">Child elements</span></span>

<span data-ttu-id="6f5f7-116">Keine</span><span class="sxs-lookup"><span data-stu-id="6f5f7-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="6f5f7-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6f5f7-117">Remarks</span></span>

<span data-ttu-id="6f5f7-118">Das \*\* \<clear>-Element\*\* entfernt alle Abschnitte und Abschnittsgruppen aus der Anwendung, die zuvor in der aktuellen Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationsdateihierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-118">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="6f5f7-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6f5f7-119">Example</span></span>

<span data-ttu-id="6f5f7-120">In diesem Beispiel werden eine Maschinenkonfigurationsdatei und eine Anwendungskonfigurationsdatei definiert und gezeigt, wie das \*\* \<>-Element\*\* in einer Anwendungskonfigurationsdatei zum Löschen von Abschnitten verwendet wird, die zuvor in der Maschinenkonfigurationsdatei definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-120">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="6f5f7-121">Der folgende Computerkonfigurationsdateicode deklariert zwei Abschnitte, \*\* \<sampleSection>\*\* und \*\* \<anotherSampleSection>\*\*, die vor der Anwendungskonfigurationsdatei gelesen werden:</span><span class="sxs-lookup"><span data-stu-id="6f5f7-121">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="6f5f7-122">Der folgende Anwendungskonfigurationsdateicode löscht alle zuvor deklarierten Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-122">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="6f5f7-123">Die Anwendung kann keine Einstellungen in einem der Abschnitte verwenden oder abrufen, die in der Computerkonfigurationsdatei deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-123">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="6f5f7-124">Es können jedoch Einstellungen von \*\* \<einem anderenAbschnitt**>verwendet werden, da es nach dem \*\* \<klaren>-Element** kommt.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-124">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="6f5f7-125">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="6f5f7-125">Configuration file</span></span>

<span data-ttu-id="6f5f7-126">Dieses Element kann in der Anwendungskonfigurationsdatei, der Computerkonfigurationsdatei (*Machine.config*) und *web.config-Dateien* verwendet werden, die sich nicht auf Anwendungsverzeichnisebene befinden.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f5f7-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f5f7-127">See also</span></span>

- [<span data-ttu-id="6f5f7-128">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6f5f7-128">Configuration file schema for the .NET Framework</span></span>](index.md)
