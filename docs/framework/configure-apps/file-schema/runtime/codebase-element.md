---
title: <codeBase>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: a06daa0b2aa5374c9959cbbe778d62856819a40e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663866"
---
# <a name="codebase-element"></a><span data-ttu-id="03321-102">\<CodeBase >-Element</span><span class="sxs-lookup"><span data-stu-id="03321-102">\<codeBase> Element</span></span>

<span data-ttu-id="03321-103">Gibt an, wo die Common Language Runtime eine Assembly finden kann.</span><span class="sxs-lookup"><span data-stu-id="03321-103">Specifies where the common language runtime can find an assembly.</span></span>

<span data-ttu-id="03321-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span><span class="sxs-lookup"><span data-stu-id="03321-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span></span>

## <a name="syntax"></a><span data-ttu-id="03321-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="03321-105">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="03321-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="03321-106">Attributes and Elements</span></span>

<span data-ttu-id="03321-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="03321-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="03321-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="03321-108">Attributes</span></span>

|<span data-ttu-id="03321-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="03321-109">Attribute</span></span>|<span data-ttu-id="03321-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03321-110">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="03321-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="03321-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="03321-112">Gibt die URL an, unter der die Laufzeit die angegebene Version der Assembly finden kann.</span><span class="sxs-lookup"><span data-stu-id="03321-112">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="03321-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="03321-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="03321-114">Gibt die Version der Assembly an, auf die sich die Codebasis bezieht.</span><span class="sxs-lookup"><span data-stu-id="03321-114">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="03321-115">Das Format einer Assemblyversionsnummer ist *Hauptversion. neben Version. Build. Revision*.</span><span class="sxs-lookup"><span data-stu-id="03321-115">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="03321-116">Versions Attribut</span><span class="sxs-lookup"><span data-stu-id="03321-116">version Attribute</span></span>

|<span data-ttu-id="03321-117">Wert</span><span class="sxs-lookup"><span data-stu-id="03321-117">Value</span></span>|<span data-ttu-id="03321-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03321-118">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="03321-119">Gültige Werte für jeden Teil der Versionsnummer sind 0 bis 65535.</span><span class="sxs-lookup"><span data-stu-id="03321-119">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="03321-120">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="03321-120">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="03321-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="03321-121">Child Elements</span></span>

<span data-ttu-id="03321-122">Keine</span><span class="sxs-lookup"><span data-stu-id="03321-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="03321-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="03321-123">Parent Elements</span></span>

|<span data-ttu-id="03321-124">Element</span><span class="sxs-lookup"><span data-stu-id="03321-124">Element</span></span>|<span data-ttu-id="03321-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03321-125">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="03321-126">Definiert eine Auflistung von Buildanbietern, die zum Kompilieren benutzerdefinierter Ressourcendateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="03321-126">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="03321-127">Sie können eine beliebige Anzahl von Buildanbietern verwenden.</span><span class="sxs-lookup"><span data-stu-id="03321-127">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="03321-128">Konfiguriert alle von ASP.NET verwendeten Kompilierungs Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="03321-128">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="03321-129">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="03321-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="03321-130">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="03321-130">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="03321-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03321-131">Remarks</span></span>

<span data-ttu-id="03321-132">Damit die Laufzeit die  **\<CodeBase->** Einstellung in einer Computer Konfigurationsdatei oder Herausgeber Richtlinien Datei verwendet, muss die Datei auch die Assemblyversion umleiten.</span><span class="sxs-lookup"><span data-stu-id="03321-132">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="03321-133">Anwendungs Konfigurationsdateien können eine Codebasis-Einstellung aufweisen, ohne die Assemblyversion umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="03321-133">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="03321-134">Nachdem Sie bestimmt haben, welche Assemblyversion verwendet werden soll, wendet die Laufzeit die Codebasis-Einstellung aus der Datei an, die die Version bestimmt.</span><span class="sxs-lookup"><span data-stu-id="03321-134">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="03321-135">Wenn keine Codebasis angegeben ist, testet die Runtime die Assembly auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="03321-135">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="03321-136">Wenn die Assembly einen starken Namen hat, kann sich die Codebasis-Einstellung im lokalen Intranet oder im Internet befinden.</span><span class="sxs-lookup"><span data-stu-id="03321-136">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="03321-137">Wenn die Assembly eine private Assembly ist, muss die Codebasis-Einstellung ein Pfad relativ zum Anwendungsverzeichnis sein.</span><span class="sxs-lookup"><span data-stu-id="03321-137">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="03321-138">Für Assemblys ohne starken Namen wird die Version ignoriert, und das Lade Modul verwendet die \<erste Darstellung der CodeBase-> in \<dependentAssembly >.</span><span class="sxs-lookup"><span data-stu-id="03321-138">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="03321-139">Wenn in der Anwendungs Konfigurationsdatei ein Eintrag vorhanden ist, der die Bindung an eine andere Assembly umleitet, hat die Umleitung Vorrang, auch wenn die Assemblyversion nicht mit der Bindungs Anforderung identisch ist.</span><span class="sxs-lookup"><span data-stu-id="03321-139">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="03321-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03321-140">Example</span></span>

<span data-ttu-id="03321-141">Im folgenden Beispiel wird gezeigt, wie angegeben wird, wo die Common Language Runtime eine Assembly finden kann.</span><span class="sxs-lookup"><span data-stu-id="03321-141">The following example shows how to specify where the runtime can find an assembly.</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly"
                              publicKeyToken="32ab4ba45e0a69a1"
                              culture="neutral" />
            <codeBase version="2.0.0.0"
                      href="http://www.litwareinc.com/myAssembly.dll"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="03321-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03321-142">See also</span></span>

- [<span data-ttu-id="03321-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="03321-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="03321-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="03321-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="03321-145">Festlegen des Speicherortes einer Assembly</span><span class="sxs-lookup"><span data-stu-id="03321-145">Specifying an Assembly's Location</span></span>](../../specify-assembly-location.md)
- [<span data-ttu-id="03321-146">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="03321-146">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
