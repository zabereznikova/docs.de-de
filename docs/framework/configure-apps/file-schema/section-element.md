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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153728"
---
# <a name="section-element"></a><span data-ttu-id="bed25-102">\<section>-Element</span><span class="sxs-lookup"><span data-stu-id="bed25-102">\<section> element</span></span>

<span data-ttu-id="bed25-103">Enthält eine Konfigurations Abschnitts Deklaration.</span><span class="sxs-lookup"><span data-stu-id="bed25-103">Contains a configuration section declaration.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

## <a name="syntax"></a><span data-ttu-id="bed25-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bed25-104">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="bed25-105">Erforderliche Attribute</span><span class="sxs-lookup"><span data-stu-id="bed25-105">Required attributes</span></span>

|           | <span data-ttu-id="bed25-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bed25-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="bed25-107">**name**</span><span class="sxs-lookup"><span data-stu-id="bed25-107">**name**</span></span>  | <span data-ttu-id="bed25-108">Gibt den Namen des Konfigurations Abschnitts an.</span><span class="sxs-lookup"><span data-stu-id="bed25-108">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="bed25-109">**type**</span><span class="sxs-lookup"><span data-stu-id="bed25-109">**type**</span></span>  | <span data-ttu-id="bed25-110">Gibt den Namen der Konfigurations Abschnitts-Handlerklasse an, die den Abschnitt aus der Konfigurationsdatei liest.</span><span class="sxs-lookup"><span data-stu-id="bed25-110">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="bed25-111">Der Typwert weist die Syntax "vollständig qualifiziert-section-Handler-Class-Name, Simple-Assembly-Name" auf.</span><span class="sxs-lookup"><span data-stu-id="bed25-111">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="bed25-112">Der einfache Assemblyname ist der Stamm Dateiname ohne die *dll* -Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="bed25-112">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="bed25-113">Optionale Attribute</span><span class="sxs-lookup"><span data-stu-id="bed25-113">Optional attributes</span></span>

<span data-ttu-id="bed25-114">Die folgenden Attribute sind nur für ASP.NET-Anwendungen anwendbar.</span><span class="sxs-lookup"><span data-stu-id="bed25-114">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="bed25-115">Das Konfigurationssystem ignoriert diese Attribute für andere Anwendungs Typen.</span><span class="sxs-lookup"><span data-stu-id="bed25-115">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="bed25-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bed25-116">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="bed25-117">**AllowDefinition**</span><span class="sxs-lookup"><span data-stu-id="bed25-117">**allowDefinition**</span></span> | <span data-ttu-id="bed25-118">Gibt an, in welcher Konfigurationsdatei der Abschnitt verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bed25-118">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="bed25-119">Verwenden Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="bed25-119">Use one of the following values:</span></span><br><br><span data-ttu-id="bed25-120">**Überall**</span><span class="sxs-lookup"><span data-stu-id="bed25-120">**Everywhere**</span></span><br><span data-ttu-id="bed25-121">Ermöglicht die Verwendung des Abschnitts in jeder beliebigen Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="bed25-121">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="bed25-122">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="bed25-122">This is the default.</span></span><br><span data-ttu-id="bed25-123">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="bed25-123">**MachineOnly**</span></span><br><span data-ttu-id="bed25-124">Ermöglicht die Verwendung des Abschnitts nur in der Computer Konfigurationsdatei (*Machine. config*).</span><span class="sxs-lookup"><span data-stu-id="bed25-124">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="bed25-125">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="bed25-125">**MachineToApplication**</span></span><br><span data-ttu-id="bed25-126">Ermöglicht die Verwendung des Abschnitts in der Computer Konfigurationsdatei oder der Anwendungs Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="bed25-126">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="bed25-127">**AllowLocation**</span><span class="sxs-lookup"><span data-stu-id="bed25-127">**allowLocation**</span></span>   | <span data-ttu-id="bed25-128">Bestimmt, ob der-Abschnitt innerhalb des-Elements verwendet werden kann **\<location>** .</span><span class="sxs-lookup"><span data-stu-id="bed25-128">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="bed25-129">Verwenden Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="bed25-129">Use one of the following values:</span></span><br><br><span data-ttu-id="bed25-130">**true**</span><span class="sxs-lookup"><span data-stu-id="bed25-130">**true**</span></span><br><span data-ttu-id="bed25-131">Ermöglicht die Verwendung des Abschnitts innerhalb des- **\<location>** Elements.</span><span class="sxs-lookup"><span data-stu-id="bed25-131">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="bed25-132">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="bed25-132">This is the default.</span></span><br><span data-ttu-id="bed25-133">**false**</span><span class="sxs-lookup"><span data-stu-id="bed25-133">**false**</span></span><br><span data-ttu-id="bed25-134">Lässt nicht zu, dass der-Abschnitt innerhalb des-Elements verwendet wird **\<location>** .</span><span class="sxs-lookup"><span data-stu-id="bed25-134">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="bed25-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bed25-135">Parent elements</span></span>

|     | <span data-ttu-id="bed25-136">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bed25-136">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="bed25-137">**\<configSections>** Gewisses</span><span class="sxs-lookup"><span data-stu-id="bed25-137">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="bed25-138">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="bed25-138">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="bed25-139">**\<sectionGroup>** Gewisses</span><span class="sxs-lookup"><span data-stu-id="bed25-139">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="bed25-140">Definiert einen Namespace für Konfigurations Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="bed25-140">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="bed25-141">Ein- **\<section>** Element ist ein untergeordnetes Element von entweder **\<configSections>** oder, **\<sectionGroup>** aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="bed25-141">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="bed25-142">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bed25-142">Child elements</span></span>

<span data-ttu-id="bed25-143">Keine</span><span class="sxs-lookup"><span data-stu-id="bed25-143">None</span></span>

## <a name="remarks"></a><span data-ttu-id="bed25-144">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bed25-144">Remarks</span></span>

<span data-ttu-id="bed25-145">Das Deklarieren eines Konfigurations Abschnitts definiert im Wesentlichen ein neues Element für die Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="bed25-145">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="bed25-146">Das neue-Element enthält die Einstellungen, die ein Konfigurations Abschnitts Handler (d. h. eine Klasse, die die- <xref:System.Configuration.IConfigurationSectionHandler> Schnittstelle implementiert) liest.</span><span class="sxs-lookup"><span data-stu-id="bed25-146">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="bed25-147">Die Attribute und untergeordneten Elemente eines Abschnitts, den Sie definieren, sind von dem Abschnitts Handler abhängig, den Sie zum Lesen der Einstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="bed25-147">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="bed25-148">Wenn Sie einen Konfigurations Abschnitts Handler in der Datei *Machine. config* deklarieren, können Sie den Konfigurations Abschnitt in jeder beliebigen Anwendungs Konfigurationsdatei auf diesem Computer verwenden, es sei denn, das **AllowDefinition** -Attribut gibt andernfalls an.</span><span class="sxs-lookup"><span data-stu-id="bed25-148">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="bed25-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bed25-149">Example</span></span>

<span data-ttu-id="bed25-150">Im folgenden Beispiel wird gezeigt, wie ein Konfigurations Abschnitt definiert und Einstellungen für diesen Abschnitt definiert werden:</span><span class="sxs-lookup"><span data-stu-id="bed25-150">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="bed25-151">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="bed25-151">Configuration file</span></span>

<span data-ttu-id="bed25-152">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="bed25-152">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="bed25-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bed25-153">See also</span></span>

- [<span data-ttu-id="bed25-154">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bed25-154">Configuration file schema for the .NET Framework</span></span>](index.md)
