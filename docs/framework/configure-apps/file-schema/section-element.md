---
title: '&lt;Abschnitt&gt; Element'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e7de6e5ce6415c58deeca14df74c26e24957054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="section-element"></a><span data-ttu-id="fb727-102">\<Abschnitt >-Element</span><span class="sxs-lookup"><span data-stu-id="fb727-102">\<section> element</span></span>

<span data-ttu-id="fb727-103">Enthält eine Deklaration der Konfiguration im Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="fb727-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="fb727-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="fb727-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="fb727-105">&nbsp;&nbsp;[**\<ConfigSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="fb727-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="fb727-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Abschnitt >**</span><span class="sxs-lookup"><span data-stu-id="fb727-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="fb727-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="fb727-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="fb727-108">&nbsp;&nbsp;[**\<ConfigSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="fb727-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="fb727-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<SectionGroup >**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="fb727-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="fb727-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Abschnitt >**</span><span class="sxs-lookup"><span data-stu-id="fb727-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fb727-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb727-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="fb727-112">Erforderliche Attribute</span><span class="sxs-lookup"><span data-stu-id="fb727-112">Required attributes</span></span>

|           | <span data-ttu-id="fb727-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb727-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="fb727-114">**name**</span><span class="sxs-lookup"><span data-stu-id="fb727-114">**name**</span></span>  | <span data-ttu-id="fb727-115">Gibt den Namen des Konfigurationsabschnitts.</span><span class="sxs-lookup"><span data-stu-id="fb727-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="fb727-116">**Typ**</span><span class="sxs-lookup"><span data-stu-id="fb727-116">**type**</span></span>  | <span data-ttu-id="fb727-117">Gibt den Namen der Konfiguration im Abschnitt Handler-Klasse, die im Abschnitt aus der Konfigurationsdatei liest.</span><span class="sxs-lookup"><span data-stu-id="fb727-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="fb727-118">Der Typwert wurde die Syntax "Fully-qualified-section-handler-class-name, einfache Assemblyname".</span><span class="sxs-lookup"><span data-stu-id="fb727-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="fb727-119">Der einfachen Assemblynamen ist der Stamm-Dateiname ohne die *DLL* Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="fb727-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="fb727-120">Optionale Attribute</span><span class="sxs-lookup"><span data-stu-id="fb727-120">Optional attributes</span></span>

<span data-ttu-id="fb727-121">Die folgenden Attribute gelten nur für ASP.NET-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="fb727-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="fb727-122">Das Konfigurationssystem ignoriert diese Attribute für andere Anwendungstypen.</span><span class="sxs-lookup"><span data-stu-id="fb727-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="fb727-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb727-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="fb727-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="fb727-124">**allowDefinition**</span></span> | <span data-ttu-id="fb727-125">Gibt die Konfigurationsdatei an, die in Abschnitt verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb727-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="fb727-126">Verwenden Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="fb727-126">Use one of the following values:</span></span><br><br><span data-ttu-id="fb727-127">**Überall**</span><span class="sxs-lookup"><span data-stu-id="fb727-127">**Everywhere**</span></span><br><span data-ttu-id="fb727-128">Können den Abschnitt in einer beliebigen Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb727-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="fb727-129">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="fb727-129">This is the default.</span></span><br><span data-ttu-id="fb727-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="fb727-130">**MachineOnly**</span></span><br><span data-ttu-id="fb727-131">Der Abschnitt kann nur in der Computerkonfigurationsdatei verwendet werden (*"Machine.config"*).</span><span class="sxs-lookup"><span data-stu-id="fb727-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="fb727-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="fb727-132">**MachineToApplication**</span></span><br><span data-ttu-id="fb727-133">Können den Abschnitt in der Konfigurationsdatei des Computers oder der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb727-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="fb727-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="fb727-134">**allowLocation**</span></span>   | <span data-ttu-id="fb727-135">Bestimmt, ob in der Abschnitt verwendet werden kann die  **\<Speicherort >** Element.</span><span class="sxs-lookup"><span data-stu-id="fb727-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="fb727-136">Verwenden Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="fb727-136">Use one of the following values:</span></span><br><br><span data-ttu-id="fb727-137">**true**</span><span class="sxs-lookup"><span data-stu-id="fb727-137">**true**</span></span><br><span data-ttu-id="fb727-138">Im Abschnitt zu verwendenden ermöglicht die  **\<Speicherort >** Element.</span><span class="sxs-lookup"><span data-stu-id="fb727-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="fb727-139">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="fb727-139">This is the default.</span></span><br><span data-ttu-id="fb727-140">**false**</span><span class="sxs-lookup"><span data-stu-id="fb727-140">**false**</span></span><br><span data-ttu-id="fb727-141">Im Abschnitt zu verwendenden lässt nicht zu den  **\<Speicherort >** Element.</span><span class="sxs-lookup"><span data-stu-id="fb727-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="fb727-142">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb727-142">Parent elements</span></span>

|     | <span data-ttu-id="fb727-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb727-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fb727-144">**\<ConfigSections >** Element</span><span class="sxs-lookup"><span data-stu-id="fb727-144">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="fb727-145">Enthält die Konfiguration im Abschnitt und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="fb727-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="fb727-146">**\<SectionGroup >** Element</span><span class="sxs-lookup"><span data-stu-id="fb727-146">**\<sectionGroup>** Element</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="fb727-147">Definiert einen Namespace für Konfigurationsabschnitte.</span><span class="sxs-lookup"><span data-stu-id="fb727-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="fb727-148">Ein  **\<Abschnitt >** Element ist ein untergeordnetes Element des entweder  **\<ConfigSections >** oder  **\<SectionGroup >** jedoch nicht beide.</span><span class="sxs-lookup"><span data-stu-id="fb727-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="fb727-149">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb727-149">Child elements</span></span>

<span data-ttu-id="fb727-150">Keiner</span><span class="sxs-lookup"><span data-stu-id="fb727-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="fb727-151">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb727-151">Remarks</span></span>

<span data-ttu-id="fb727-152">Deklarieren einen Konfigurationsabschnitt im Wesentlichen wird ein neues Element für die Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="fb727-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="fb727-153">Das neue Element enthält Einstellungen, die eine Konfiguration Handler im Abschnitt (d. h. eine Klasse, implementiert die <xref:System.Configuration.IConfigurationSectionHandler> Schnittstelle) liest.</span><span class="sxs-lookup"><span data-stu-id="fb727-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="fb727-154">Die Attribute und untergeordnete Elemente von einem Abschnitt auf den von den Ihnen definierten richten sich nach den Abschnittshandler, den Sie verwenden, um Ihre Einstellungen zu lesen.</span><span class="sxs-lookup"><span data-stu-id="fb727-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="fb727-155">Deklarieren einen Konfigurationsabschnittshandler in der *"Machine.config"* Datei können Sie den Konfigurationsabschnitt in jeder Konfigurationsdatei der Anwendung auf diesem Computer zu verwenden, es sei denn, die **AllowDefinition**Attribut gibt andernfalls an.</span><span class="sxs-lookup"><span data-stu-id="fb727-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="fb727-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb727-156">Example</span></span>

<span data-ttu-id="fb727-157">Das folgende Beispiel veranschaulicht einen Konfigurationsabschnitt zu definieren, und definieren Sie Einstellungen für diesen Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="fb727-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="fb727-158">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="fb727-158">Configuration file</span></span>

<span data-ttu-id="fb727-159">Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="fb727-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb727-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb727-160">See also</span></span>

[<span data-ttu-id="fb727-161">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fb727-161">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
