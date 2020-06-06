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
ms.openlocfilehash: 475b7df55ed509157c1da0aeb8f979de238c72b5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70971889"
---
# <a name="codebase-element"></a><span data-ttu-id="b4c6e-102">\<codeBase>-Element</span><span class="sxs-lookup"><span data-stu-id="b4c6e-102">\<codeBase> Element</span></span>

<span data-ttu-id="b4c6e-103">Gibt an, wo die Common Language Runtime eine Assembly finden kann.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-103">Specifies where the common language runtime can find an assembly.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<codeBase>**

## <a name="syntax"></a><span data-ttu-id="b4c6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4c6e-104">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b4c6e-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b4c6e-105">Attributes and Elements</span></span>

<span data-ttu-id="b4c6e-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b4c6e-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="b4c6e-107">Attributes</span></span>

|<span data-ttu-id="b4c6e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b4c6e-108">Attribute</span></span>|<span data-ttu-id="b4c6e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b4c6e-109">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="b4c6e-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="b4c6e-111">Gibt die URL an, unter der die Laufzeit die angegebene Version der Assembly finden kann.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-111">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="b4c6e-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="b4c6e-113">Gibt die Version der Assembly an, auf die sich die Codebasis bezieht.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-113">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="b4c6e-114">Das Format einer Assemblyversionsnummer ist *Hauptversion. neben Version. Build. Revision*.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-114">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="b4c6e-115">Versions Attribut</span><span class="sxs-lookup"><span data-stu-id="b4c6e-115">version Attribute</span></span>

|<span data-ttu-id="b4c6e-116">Wert</span><span class="sxs-lookup"><span data-stu-id="b4c6e-116">Value</span></span>|<span data-ttu-id="b4c6e-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b4c6e-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="b4c6e-118">Gültige Werte für jeden Teil der Versionsnummer sind 0 bis 65535.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-118">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="b4c6e-119">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-119">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b4c6e-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4c6e-120">Child Elements</span></span>

<span data-ttu-id="b4c6e-121">Keine</span><span class="sxs-lookup"><span data-stu-id="b4c6e-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b4c6e-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4c6e-122">Parent Elements</span></span>

|<span data-ttu-id="b4c6e-123">Element</span><span class="sxs-lookup"><span data-stu-id="b4c6e-123">Element</span></span>|<span data-ttu-id="b4c6e-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4c6e-124">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="b4c6e-125">Definiert eine Auflistung von Buildanbietern, die zum Kompilieren benutzerdefinierter Ressourcendateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-125">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="b4c6e-126">Sie können eine beliebige Anzahl von Buildanbietern verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-126">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="b4c6e-127">Konfiguriert alle von ASP.NET verwendeten Kompilierungs Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-127">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="b4c6e-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="b4c6e-129">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-129">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b4c6e-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b4c6e-130">Remarks</span></span>

<span data-ttu-id="b4c6e-131">Damit die-Laufzeit die **\<codeBase>** Einstellung in einer Computer Konfigurationsdatei oder Herausgeber Richtlinien Datei verwendet, muss die Datei auch die Assemblyversion umleiten.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-131">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="b4c6e-132">Anwendungs Konfigurationsdateien können eine Codebasis-Einstellung aufweisen, ohne die Assemblyversion umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-132">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="b4c6e-133">Nachdem Sie bestimmt haben, welche Assemblyversion verwendet werden soll, wendet die Laufzeit die Codebasis-Einstellung aus der Datei an, die die Version bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-133">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="b4c6e-134">Wenn keine Codebasis angegeben ist, testet die Runtime die Assembly auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-134">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="b4c6e-135">Wenn die Assembly einen starken Namen hat, kann sich die Codebasis-Einstellung im lokalen Intranet oder im Internet befinden.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-135">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="b4c6e-136">Wenn die Assembly eine private Assembly ist, muss die Codebasis-Einstellung ein Pfad relativ zum Anwendungsverzeichnis sein.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-136">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="b4c6e-137">Für Assemblys ohne starken Namen wird die Version ignoriert, und das Lade Modul verwendet die erste Darstellung von \<codebase> in \<dependentAssembly> .</span><span class="sxs-lookup"><span data-stu-id="b4c6e-137">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="b4c6e-138">Wenn in der Anwendungs Konfigurationsdatei ein Eintrag vorhanden ist, der die Bindung an eine andere Assembly umleitet, hat die Umleitung Vorrang, auch wenn die Assemblyversion nicht mit der Bindungs Anforderung identisch ist.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-138">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="b4c6e-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4c6e-139">Example</span></span>

<span data-ttu-id="b4c6e-140">Im folgenden Beispiel wird gezeigt, wie angegeben wird, wo die Common Language Runtime eine Assembly finden kann.</span><span class="sxs-lookup"><span data-stu-id="b4c6e-140">The following example shows how to specify where the runtime can find an assembly.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b4c6e-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4c6e-141">See also</span></span>

- [<span data-ttu-id="b4c6e-142">Lauf Zeit Einstellungs Schema</span><span class="sxs-lookup"><span data-stu-id="b4c6e-142">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="b4c6e-143">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="b4c6e-143">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="b4c6e-144">Speicherort einer Assembly angeben</span><span class="sxs-lookup"><span data-stu-id="b4c6e-144">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="b4c6e-145">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="b4c6e-145">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
