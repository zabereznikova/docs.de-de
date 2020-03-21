---
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153728"
---
# <a name="section-element"></a><span data-ttu-id="e9f25-102">\<Abschnitt>-Element</span><span class="sxs-lookup"><span data-stu-id="e9f25-102">\<section> element</span></span>

<span data-ttu-id="e9f25-103">Enthält eine Konfigurationsabschnittsdeklaration.</span><span class="sxs-lookup"><span data-stu-id="e9f25-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="e9f25-104">[**\<Konfiguration>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9f25-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="e9f25-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="e9f25-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="e9f25-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Abschnitt>**</span><span class="sxs-lookup"><span data-stu-id="e9f25-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="e9f25-107">[**\<Konfiguration>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9f25-107">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="e9f25-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="e9f25-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="e9f25-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGruppe>**](sectiongroup-element-for-configsections.md)</span><span class="sxs-lookup"><span data-stu-id="e9f25-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>\
<span data-ttu-id="e9f25-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Abschnitt>**</span><span class="sxs-lookup"><span data-stu-id="e9f25-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e9f25-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9f25-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="e9f25-112">Erforderliche Attribute</span><span class="sxs-lookup"><span data-stu-id="e9f25-112">Required attributes</span></span>

|           | <span data-ttu-id="e9f25-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9f25-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="e9f25-114">**Name**</span><span class="sxs-lookup"><span data-stu-id="e9f25-114">**name**</span></span>  | <span data-ttu-id="e9f25-115">Gibt den Namen des Konfigurationsabschnitts an.</span><span class="sxs-lookup"><span data-stu-id="e9f25-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="e9f25-116">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e9f25-116">**type**</span></span>  | <span data-ttu-id="e9f25-117">Gibt den Namen der Konfigurationsabschnittshandlerklasse an, die den Abschnitt aus der Konfigurationsdatei liest.</span><span class="sxs-lookup"><span data-stu-id="e9f25-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="e9f25-118">Der Typwert hat die Syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span><span class="sxs-lookup"><span data-stu-id="e9f25-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="e9f25-119">Der einfache Assemblyname ist der Root-Dateiname ohne die *Dateierweiterung .dll.*</span><span class="sxs-lookup"><span data-stu-id="e9f25-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="e9f25-120">Optionale Attribute</span><span class="sxs-lookup"><span data-stu-id="e9f25-120">Optional attributes</span></span>

<span data-ttu-id="e9f25-121">Die folgenden Attribute gelten nur für ASP.NET Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e9f25-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="e9f25-122">Das Konfigurationssystem ignoriert diese Attribute für andere Anwendungstypen.</span><span class="sxs-lookup"><span data-stu-id="e9f25-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="e9f25-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9f25-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="e9f25-124">**Allowdefinition**</span><span class="sxs-lookup"><span data-stu-id="e9f25-124">**allowDefinition**</span></span> | <span data-ttu-id="e9f25-125">Gibt an, in welcher Konfigurationsdatei der Abschnitt verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e9f25-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="e9f25-126">Verwenden Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="e9f25-126">Use one of the following values:</span></span><br><br><span data-ttu-id="e9f25-127">**Überall**</span><span class="sxs-lookup"><span data-stu-id="e9f25-127">**Everywhere**</span></span><br><span data-ttu-id="e9f25-128">Ermöglicht die Verwendung des Abschnitts in jeder Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e9f25-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="e9f25-129">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="e9f25-129">This is the default.</span></span><br><span data-ttu-id="e9f25-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="e9f25-130">**MachineOnly**</span></span><br><span data-ttu-id="e9f25-131">Lässt die Verwendung des Abschnitts nur in der Maschinenkonfigurationsdatei (*Machine.config*) zu.</span><span class="sxs-lookup"><span data-stu-id="e9f25-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="e9f25-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="e9f25-132">**MachineToApplication**</span></span><br><span data-ttu-id="e9f25-133">Ermöglicht die Verwendung des Abschnitts in der Maschinenkonfigurationsdatei oder in der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e9f25-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="e9f25-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="e9f25-134">**allowLocation**</span></span>   | <span data-ttu-id="e9f25-135">Bestimmt, ob der Abschnitt \*\* \<\*\* innerhalb der Position>Elements verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e9f25-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="e9f25-136">Verwenden Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="e9f25-136">Use one of the following values:</span></span><br><br><span data-ttu-id="e9f25-137">**true**</span><span class="sxs-lookup"><span data-stu-id="e9f25-137">**true**</span></span><br><span data-ttu-id="e9f25-138">Ermöglicht die Verwendung des \*\* \<\*\* Abschnitts innerhalb der Position>Elements.</span><span class="sxs-lookup"><span data-stu-id="e9f25-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="e9f25-139">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="e9f25-139">This is the default.</span></span><br><span data-ttu-id="e9f25-140">**false**</span><span class="sxs-lookup"><span data-stu-id="e9f25-140">**false**</span></span><br><span data-ttu-id="e9f25-141">Lässt nicht zu, dass der \*\* \<\*\* Abschnitt innerhalb der Position>Elements verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e9f25-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="e9f25-142">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9f25-142">Parent elements</span></span>

|     | <span data-ttu-id="e9f25-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9f25-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e9f25-144">\*\* \<configSections>\*\* Element</span><span class="sxs-lookup"><span data-stu-id="e9f25-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="e9f25-145">Enthält Konfigurationsabschnittund- und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="e9f25-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="e9f25-146">\*\* \<sectionGruppe>\*\* Element</span><span class="sxs-lookup"><span data-stu-id="e9f25-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="e9f25-147">Definiert einen Namespace für Konfigurationsabschnitte.</span><span class="sxs-lookup"><span data-stu-id="e9f25-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="e9f25-148">Ein \*\* \<Abschnitt>-Element\*\* ist ein untergeordnetes Element von \*\* \<configSections>\*\* oder \*\* \<sectionGroup>\*\* aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="e9f25-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="e9f25-149">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9f25-149">Child elements</span></span>

<span data-ttu-id="e9f25-150">Keine</span><span class="sxs-lookup"><span data-stu-id="e9f25-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="e9f25-151">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e9f25-151">Remarks</span></span>

<span data-ttu-id="e9f25-152">Durch das Deklarieren eines Konfigurationsabschnitts wird im Wesentlichen ein neues Element für die Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="e9f25-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="e9f25-153">Das neue Element enthält Einstellungen, die ein Konfigurationsabschnittshandler <xref:System.Configuration.IConfigurationSectionHandler> (d. h. eine Klasse, die die Schnittstelle implementiert) liest.</span><span class="sxs-lookup"><span data-stu-id="e9f25-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="e9f25-154">Die Attribute und untergeordneten Elemente eines Abschnitts, den Sie definieren, hängen vom Abschnittshandler ab, den Sie zum Lesen Ihrer Einstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e9f25-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="e9f25-155">Wenn Sie einen Konfigurationsabschnittshandler in der *Datei Machine.config* deklarieren, können Sie den Konfigurationsabschnitt in jeder Anwendungskonfigurationsdatei auf diesem Computer verwenden, es sei denn, das **allowDefinition-Attribut** gibt etwas anderes an.</span><span class="sxs-lookup"><span data-stu-id="e9f25-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="e9f25-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9f25-156">Example</span></span>

<span data-ttu-id="e9f25-157">Das folgende Beispiel zeigt, wie Sie einen Konfigurationsabschnitt definieren und Einstellungen für diesen Abschnitt definieren:</span><span class="sxs-lookup"><span data-stu-id="e9f25-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler"
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="e9f25-158">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="e9f25-158">Configuration file</span></span>

<span data-ttu-id="e9f25-159">Dieses Element kann in der Anwendungskonfigurationsdatei, der Computerkonfigurationsdatei (*Machine.config*) und *web.config-Dateien* verwendet werden, die sich nicht auf Anwendungsverzeichnisebene befinden.</span><span class="sxs-lookup"><span data-stu-id="e9f25-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9f25-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9f25-160">See also</span></span>

- [<span data-ttu-id="e9f25-161">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e9f25-161">Configuration file schema for the .NET Framework</span></span>](index.md)
