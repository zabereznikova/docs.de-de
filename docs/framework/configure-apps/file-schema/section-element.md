---
title: <section> Element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7147173dc9f132fa2dd14d20526d59927a183bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115268"
---
# <a name="section-element"></a><span data-ttu-id="fc74f-102">\<Abschnitts > Element</span><span class="sxs-lookup"><span data-stu-id="fc74f-102">\<section> element</span></span>

<span data-ttu-id="fc74f-103">Enthält eine Konfigurations Abschnitts Deklaration.</span><span class="sxs-lookup"><span data-stu-id="fc74f-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="fc74f-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="fc74f-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="fc74f-105">&nbsp;&nbsp;[ **\<configabschnitts >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="fc74f-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="fc74f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Abschnitt >**</span><span class="sxs-lookup"><span data-stu-id="fc74f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="fc74f-107">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="fc74f-107">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="fc74f-108">&nbsp;&nbsp;[ **\<configabschnitts >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="fc74f-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="fc74f-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup >** ](sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="fc74f-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="fc74f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Abschnitt >**</span><span class="sxs-lookup"><span data-stu-id="fc74f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fc74f-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc74f-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="fc74f-112">Erforderliche Attribute</span><span class="sxs-lookup"><span data-stu-id="fc74f-112">Required attributes</span></span>

|           | <span data-ttu-id="fc74f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc74f-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="fc74f-114">**name**</span><span class="sxs-lookup"><span data-stu-id="fc74f-114">**name**</span></span>  | <span data-ttu-id="fc74f-115">Gibt den Namen des Konfigurations Abschnitts an.</span><span class="sxs-lookup"><span data-stu-id="fc74f-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="fc74f-116">**Typ**</span><span class="sxs-lookup"><span data-stu-id="fc74f-116">**type**</span></span>  | <span data-ttu-id="fc74f-117">Gibt den Namen der Konfigurations Abschnitts-Handlerklasse an, die den Abschnitt aus der Konfigurationsdatei liest.</span><span class="sxs-lookup"><span data-stu-id="fc74f-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="fc74f-118">Der Typwert weist die Syntax "vollständig qualifiziert-section-Handler-Class-Name, Simple-Assembly-Name" auf.</span><span class="sxs-lookup"><span data-stu-id="fc74f-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="fc74f-119">Der einfache Assemblyname ist der Stamm Dateiname ohne die *dll* -Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="fc74f-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="fc74f-120">Optionale Attribute</span><span class="sxs-lookup"><span data-stu-id="fc74f-120">Optional attributes</span></span>

<span data-ttu-id="fc74f-121">Die folgenden Attribute sind nur für ASP.NET-Anwendungen anwendbar.</span><span class="sxs-lookup"><span data-stu-id="fc74f-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="fc74f-122">Das Konfigurationssystem ignoriert diese Attribute für andere Anwendungs Typen.</span><span class="sxs-lookup"><span data-stu-id="fc74f-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="fc74f-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc74f-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="fc74f-124">**AllowDefinition**</span><span class="sxs-lookup"><span data-stu-id="fc74f-124">**allowDefinition**</span></span> | <span data-ttu-id="fc74f-125">Gibt an, in welcher Konfigurationsdatei der Abschnitt verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fc74f-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="fc74f-126">Verwenden Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="fc74f-126">Use one of the following values:</span></span><br><br><span data-ttu-id="fc74f-127">**Überall**</span><span class="sxs-lookup"><span data-stu-id="fc74f-127">**Everywhere**</span></span><br><span data-ttu-id="fc74f-128">Ermöglicht die Verwendung des Abschnitts in jeder beliebigen Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fc74f-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="fc74f-129">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="fc74f-129">This is the default.</span></span><br><span data-ttu-id="fc74f-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="fc74f-130">**MachineOnly**</span></span><br><span data-ttu-id="fc74f-131">Ermöglicht die Verwendung des Abschnitts nur in der Computer Konfigurationsdatei (*Machine. config*).</span><span class="sxs-lookup"><span data-stu-id="fc74f-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="fc74f-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="fc74f-132">**MachineToApplication**</span></span><br><span data-ttu-id="fc74f-133">Ermöglicht die Verwendung des Abschnitts in der Computer Konfigurationsdatei oder der Anwendungs Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fc74f-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="fc74f-134">**AllowLocation**</span><span class="sxs-lookup"><span data-stu-id="fc74f-134">**allowLocation**</span></span>   | <span data-ttu-id="fc74f-135">Bestimmt, ob der Abschnitt innerhalb der **\<Speicherort >** Elements verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fc74f-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="fc74f-136">Verwenden Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="fc74f-136">Use one of the following values:</span></span><br><br><span data-ttu-id="fc74f-137">**true**</span><span class="sxs-lookup"><span data-stu-id="fc74f-137">**true**</span></span><br><span data-ttu-id="fc74f-138">Ermöglicht die Verwendung des Abschnitts innerhalb des **\<Speicherort >** Elements.</span><span class="sxs-lookup"><span data-stu-id="fc74f-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="fc74f-139">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="fc74f-139">This is the default.</span></span><br><span data-ttu-id="fc74f-140">**false**</span><span class="sxs-lookup"><span data-stu-id="fc74f-140">**false**</span></span><br><span data-ttu-id="fc74f-141">Lässt nicht zu, dass der Abschnitt innerhalb der **\<Speicherort >** Elements verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fc74f-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="fc74f-142">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc74f-142">Parent elements</span></span>

|     | <span data-ttu-id="fc74f-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc74f-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fc74f-144"> **\<configabschnitts >** Gewisses</span><span class="sxs-lookup"><span data-stu-id="fc74f-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="fc74f-145">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="fc74f-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="fc74f-146"> **\<sectionGroup >** Gewisses</span><span class="sxs-lookup"><span data-stu-id="fc74f-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="fc74f-147">Definiert einen Namespace für Konfigurations Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="fc74f-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="fc74f-148">Ein **\<Abschnitt >** Element ist ein untergeordnetes Element von **\<configabschnitts >** oder **\<sectionGroup >** , aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="fc74f-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="fc74f-149">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc74f-149">Child elements</span></span>

<span data-ttu-id="fc74f-150">Keiner</span><span class="sxs-lookup"><span data-stu-id="fc74f-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="fc74f-151">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc74f-151">Remarks</span></span>

<span data-ttu-id="fc74f-152">Das Deklarieren eines Konfigurations Abschnitts definiert im Wesentlichen ein neues Element für die Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fc74f-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="fc74f-153">Das neue-Element enthält die Einstellungen, die ein Konfigurations Abschnitts Handler (d. h. eine Klasse, die die <xref:System.Configuration.IConfigurationSectionHandler>-Schnittstelle implementiert) liest.</span><span class="sxs-lookup"><span data-stu-id="fc74f-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="fc74f-154">Die Attribute und untergeordneten Elemente eines Abschnitts, den Sie definieren, sind von dem Abschnitts Handler abhängig, den Sie zum Lesen der Einstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc74f-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="fc74f-155">Wenn Sie einen Konfigurations Abschnitts Handler in der Datei *Machine. config* deklarieren, können Sie den Konfigurations Abschnitt in jeder beliebigen Anwendungs Konfigurationsdatei auf diesem Computer verwenden, es sei denn, das **AllowDefinition** -Attribut gibt andernfalls an.</span><span class="sxs-lookup"><span data-stu-id="fc74f-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="fc74f-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc74f-156">Example</span></span>

<span data-ttu-id="fc74f-157">Im folgenden Beispiel wird gezeigt, wie ein Konfigurations Abschnitt definiert und Einstellungen für diesen Abschnitt definiert werden:</span><span class="sxs-lookup"><span data-stu-id="fc74f-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="fc74f-158">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="fc74f-158">Configuration file</span></span>

<span data-ttu-id="fc74f-159">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="fc74f-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc74f-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc74f-160">See also</span></span>

- [<span data-ttu-id="fc74f-161">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fc74f-161">Configuration file schema for the .NET Framework</span></span>](index.md)
