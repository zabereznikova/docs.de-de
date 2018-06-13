---
title: '&lt;LinkedConfiguration&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 71769efa1233fc8a693219dc02ae56ea39c164e7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743796"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="7ede9-102">\<LinkedConfiguration >-Element</span><span class="sxs-lookup"><span data-stu-id="7ede9-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="7ede9-103">Gibt eine einzuschließende Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="7ede9-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="7ede9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="7ede9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="7ede9-105">&nbsp;&nbsp;[**\<AssemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="7ede9-105">&nbsp;&nbsp;[**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
<span data-ttu-id="7ede9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<LinkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="7ede9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7ede9-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ede9-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="7ede9-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="7ede9-108">Attribute</span></span>

|           | <span data-ttu-id="7ede9-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ede9-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="7ede9-110">**href**</span><span class="sxs-lookup"><span data-stu-id="7ede9-110">**href**</span></span>  | <span data-ttu-id="7ede9-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="7ede9-111">Required attribute.</span></span><br><br><span data-ttu-id="7ede9-112">Die URL der Konfigurationsdatei enthalten.</span><span class="sxs-lookup"><span data-stu-id="7ede9-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="7ede9-113">Das einzige Format, unterstützt die **Href** -Attribut ist `file://`.</span><span class="sxs-lookup"><span data-stu-id="7ede9-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="7ede9-114">Lokale Dateien und UNC-Dateien werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7ede9-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="7ede9-115">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="7ede9-115">Parent element</span></span>

|     | <span data-ttu-id="7ede9-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ede9-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7ede9-117">**\<AssemblyBinding >** Element</span><span class="sxs-lookup"><span data-stu-id="7ede9-117">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="7ede9-118">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="7ede9-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7ede9-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ede9-119">Child elements</span></span>

<span data-ttu-id="7ede9-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="7ede9-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="7ede9-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ede9-121">Remarks</span></span>

<span data-ttu-id="7ede9-122">Die  **\<LinkedConfiguration >** Element vereinfacht die Wartung für Komponentenassemblys.</span><span class="sxs-lookup"><span data-stu-id="7ede9-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="7ede9-123">Wenn eine oder mehrere Anwendungen eine Assembly, die über eine Konfigurationsdatei, die sich in einem bekannten Speicherort befinden verwenden, können die Konfigurationsdateien der Anwendungen, die die Assembly verwenden die  **\<LinkedConfiguration >** Element, das die Konfigurationsdatei für die Assembly, anstatt direkt einschließlich der Konfigurationsinformationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="7ede9-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="7ede9-124">Wenn der Komponentenassembly gewartet wird, enthält die Konfigurationsdatei mit allgemeinen aktualisieren aktualisierte Konfigurationsinformationen für alle Anwendungen, die Assembly zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ede9-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="7ede9-125">Die  **\<LinkedConfiguration >** Element wird für Anwendungen mit Windows-Seite-an-Seite-Manifeste nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7ede9-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="7ede9-126">Die folgenden Regeln bestimmen die Verwendung von verknüpfte Konfigurationsdateien:</span><span class="sxs-lookup"><span data-stu-id="7ede9-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="7ede9-127">Die Einstellungen in Konfigurationsdateien enthalten nur betreffen Lademodul Bindungsrichtlinie und werden nur vom Ladeprogramm verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ede9-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="7ede9-128">Die enthalten Konfigurationsdateien können andere als die Bindung von Richtlinien zu verwenden, aber diese Einstellungen nicht haben keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="7ede9-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="7ede9-129">Das einzige Format, unterstützt die `href` -Attribut ist `file://`.</span><span class="sxs-lookup"><span data-stu-id="7ede9-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="7ede9-130">Lokale Dateien und UNC-Dateien werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7ede9-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="7ede9-131">Es gibt keine Einschränkung für die Anzahl der verknüpften Konfigurationen pro Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7ede9-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="7ede9-132">Alle verknüpften Konfigurationsdateien werden zusammengeführt, um eine Datei bilden die `#include` in C/C++-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="7ede9-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="7ede9-133">Die  **\<LinkedConfiguration >** Element ist nur in Anwendungskonfigurationsdateien zulässig; sie wird ignoriert, *"Machine.config"*.</span><span class="sxs-lookup"><span data-stu-id="7ede9-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="7ede9-134">Zirkelverweise werden erkannt und beendet.</span><span class="sxs-lookup"><span data-stu-id="7ede9-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="7ede9-135">D. h., wenn die  **\<LinkedConfiguration >** Elemente einer Reihe von Konfigurationsdateien bilden eine Schleife, die Schleife wird erkannt und beendet.</span><span class="sxs-lookup"><span data-stu-id="7ede9-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="7ede9-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7ede9-136">Example</span></span>

<span data-ttu-id="7ede9-137">Das folgende Beispiel zeigt, wie Sie die Konfigurationsdatei von der lokalen Festplatte enthalten:</span><span class="sxs-lookup"><span data-stu-id="7ede9-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7ede9-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ede9-138">See also</span></span>

<span data-ttu-id="7ede9-139">[**\<AssemblyBinding >** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="7ede9-139">[**\<assemblyBinding>** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
[<span data-ttu-id="7ede9-140">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7ede9-140">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
