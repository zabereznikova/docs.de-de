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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155426"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="19186-102">\<clear>-Element für \<configSections></span><span class="sxs-lookup"><span data-stu-id="19186-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="19186-103">Löscht alle zuvor definierten Abschnitte und Abschnitts Gruppen.</span><span class="sxs-lookup"><span data-stu-id="19186-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="19186-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="19186-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="19186-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="19186-105">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="19186-106">attribute</span><span class="sxs-lookup"><span data-stu-id="19186-106">Attribute</span></span>

|           | <span data-ttu-id="19186-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="19186-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="19186-108">**name**</span><span class="sxs-lookup"><span data-stu-id="19186-108">**name**</span></span>  | <span data-ttu-id="19186-109">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="19186-109">Required attribute.</span></span><br><br><span data-ttu-id="19186-110">Gibt den Namen des Abschnitts oder der Abschnitts Gruppe an, der entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="19186-110">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="19186-111">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="19186-111">Parent element</span></span>

|     | <span data-ttu-id="19186-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="19186-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="19186-113">**\<configSections>** Gewisses</span><span class="sxs-lookup"><span data-stu-id="19186-113">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="19186-114">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="19186-114">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="19186-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="19186-115">Child elements</span></span>

<span data-ttu-id="19186-116">Keine</span><span class="sxs-lookup"><span data-stu-id="19186-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="19186-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="19186-117">Remarks</span></span>

<span data-ttu-id="19186-118">Das **\<clear>** -Element entfernt alle Abschnitte und Abschnitts Gruppen aus der Anwendung, die zuvor in der aktuellen Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationsdatei Hierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="19186-118">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="19186-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19186-119">Example</span></span>

<span data-ttu-id="19186-120">In diesem Beispiel werden eine Computer Konfigurationsdatei und eine Anwendungs Konfigurationsdatei definiert. Außerdem wird gezeigt, wie Sie mit dem- **\<clear>** Element in einer Anwendungs Konfigurationsdatei Abschnitte löschen, die zuvor in der Computer Konfigurationsdatei definiert wurden</span><span class="sxs-lookup"><span data-stu-id="19186-120">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="19186-121">Der folgende Computer Konfigurationsdatei-Code deklariert zwei **\<sampleSection>** Abschnitte **\<anotherSampleSection>** : und, die vor der Anwendungs Konfigurationsdatei gelesen werden:</span><span class="sxs-lookup"><span data-stu-id="19186-121">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

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

<span data-ttu-id="19186-122">Der folgende Anwendungs Konfigurationsdatei-Code löscht alle zuvor deklarierten Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="19186-122">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="19186-123">Die Anwendung kann in keinem der Abschnitte, die in der Computer Konfigurationsdatei deklariert wurden, Einstellungen verwenden oder abrufen.</span><span class="sxs-lookup"><span data-stu-id="19186-123">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="19186-124">Es können jedoch Einstellungen von verwendet werden, **\<anotherSection>** da es hinter dem- **\<clear>** Element liegt.</span><span class="sxs-lookup"><span data-stu-id="19186-124">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="19186-125">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="19186-125">Configuration file</span></span>

<span data-ttu-id="19186-126">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="19186-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="19186-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19186-127">See also</span></span>

- [<span data-ttu-id="19186-128">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="19186-128">Configuration file schema for the .NET Framework</span></span>](index.md)
