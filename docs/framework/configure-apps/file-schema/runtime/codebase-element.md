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
ms.openlocfilehash: bd170b817c5ccc337711f8f79968653c29f3eda4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252744"
---
# <a name="codebase-element"></a><span data-ttu-id="832ed-102">\<CodeBase >-Element</span><span class="sxs-lookup"><span data-stu-id="832ed-102">\<codeBase> Element</span></span>

<span data-ttu-id="832ed-103">Gibt an, wo die Common Language Runtime eine Assembly finden kann.</span><span class="sxs-lookup"><span data-stu-id="832ed-103">Specifies where the common language runtime can find an assembly.</span></span>

<span data-ttu-id="832ed-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="832ed-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="832ed-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="832ed-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="832ed-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding->** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="832ed-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="832ed-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly->** ](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="832ed-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="832ed-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<codeBase>**</span><span class="sxs-lookup"><span data-stu-id="832ed-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<codeBase>**</span></span>

## <a name="syntax"></a><span data-ttu-id="832ed-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="832ed-109">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="832ed-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="832ed-110">Attributes and Elements</span></span>

<span data-ttu-id="832ed-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="832ed-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="832ed-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="832ed-112">Attributes</span></span>

|<span data-ttu-id="832ed-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="832ed-113">Attribute</span></span>|<span data-ttu-id="832ed-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="832ed-114">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="832ed-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="832ed-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="832ed-116">Gibt die URL an, unter der die Laufzeit die angegebene Version der Assembly finden kann.</span><span class="sxs-lookup"><span data-stu-id="832ed-116">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="832ed-117">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="832ed-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="832ed-118">Gibt die Version der Assembly an, auf die sich die Codebasis bezieht.</span><span class="sxs-lookup"><span data-stu-id="832ed-118">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="832ed-119">Das Format einer Assemblyversionsnummer ist *Hauptversion. neben Version. Build. Revision*.</span><span class="sxs-lookup"><span data-stu-id="832ed-119">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="832ed-120">Versions Attribut</span><span class="sxs-lookup"><span data-stu-id="832ed-120">version Attribute</span></span>

|<span data-ttu-id="832ed-121">Wert</span><span class="sxs-lookup"><span data-stu-id="832ed-121">Value</span></span>|<span data-ttu-id="832ed-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="832ed-122">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="832ed-123">Gültige Werte für jeden Teil der Versionsnummer sind 0 bis 65535.</span><span class="sxs-lookup"><span data-stu-id="832ed-123">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="832ed-124">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="832ed-124">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="832ed-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="832ed-125">Child Elements</span></span>

<span data-ttu-id="832ed-126">Keine</span><span class="sxs-lookup"><span data-stu-id="832ed-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="832ed-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="832ed-127">Parent Elements</span></span>

|<span data-ttu-id="832ed-128">Element</span><span class="sxs-lookup"><span data-stu-id="832ed-128">Element</span></span>|<span data-ttu-id="832ed-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="832ed-129">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="832ed-130">Definiert eine Auflistung von Buildanbietern, die zum Kompilieren benutzerdefinierter Ressourcendateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="832ed-130">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="832ed-131">Sie können eine beliebige Anzahl von Buildanbietern verwenden.</span><span class="sxs-lookup"><span data-stu-id="832ed-131">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="832ed-132">Konfiguriert alle von ASP.NET verwendeten Kompilierungs Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="832ed-132">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="832ed-133">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="832ed-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="832ed-134">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="832ed-134">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="832ed-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="832ed-135">Remarks</span></span>

<span data-ttu-id="832ed-136">Damit die Laufzeit die  **\<CodeBase->** Einstellung in einer Computer Konfigurationsdatei oder Herausgeber Richtlinien Datei verwendet, muss die Datei auch die Assemblyversion umleiten.</span><span class="sxs-lookup"><span data-stu-id="832ed-136">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="832ed-137">Anwendungs Konfigurationsdateien können eine Codebasis-Einstellung aufweisen, ohne die Assemblyversion umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="832ed-137">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="832ed-138">Nachdem Sie bestimmt haben, welche Assemblyversion verwendet werden soll, wendet die Laufzeit die Codebasis-Einstellung aus der Datei an, die die Version bestimmt.</span><span class="sxs-lookup"><span data-stu-id="832ed-138">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="832ed-139">Wenn keine Codebasis angegeben ist, testet die Runtime die Assembly auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="832ed-139">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="832ed-140">Wenn die Assembly einen starken Namen hat, kann sich die Codebasis-Einstellung im lokalen Intranet oder im Internet befinden.</span><span class="sxs-lookup"><span data-stu-id="832ed-140">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="832ed-141">Wenn die Assembly eine private Assembly ist, muss die Codebasis-Einstellung ein Pfad relativ zum Anwendungsverzeichnis sein.</span><span class="sxs-lookup"><span data-stu-id="832ed-141">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="832ed-142">Für Assemblys ohne starken Namen wird die Version ignoriert, und das Lade Modul verwendet die \<erste Darstellung der CodeBase-> in \<dependentAssembly >.</span><span class="sxs-lookup"><span data-stu-id="832ed-142">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="832ed-143">Wenn in der Anwendungs Konfigurationsdatei ein Eintrag vorhanden ist, der die Bindung an eine andere Assembly umleitet, hat die Umleitung Vorrang, auch wenn die Assemblyversion nicht mit der Bindungs Anforderung identisch ist.</span><span class="sxs-lookup"><span data-stu-id="832ed-143">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="832ed-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="832ed-144">Example</span></span>

<span data-ttu-id="832ed-145">Im folgenden Beispiel wird gezeigt, wie angegeben wird, wo die Common Language Runtime eine Assembly finden kann.</span><span class="sxs-lookup"><span data-stu-id="832ed-145">The following example shows how to specify where the runtime can find an assembly.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="832ed-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="832ed-146">See also</span></span>

- [<span data-ttu-id="832ed-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="832ed-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="832ed-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="832ed-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="832ed-149">Festlegen des Speicherortes einer Assembly</span><span class="sxs-lookup"><span data-stu-id="832ed-149">Specifying an Assembly's Location</span></span>](../../specify-assembly-location.md)
- [<span data-ttu-id="832ed-150">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="832ed-150">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
