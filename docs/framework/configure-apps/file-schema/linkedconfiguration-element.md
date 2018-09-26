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
ms.openlocfilehash: c5186aa94993ba551252db6fef55853b5b554789
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170820"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="19376-102">\<LinkedConfiguration >-Element</span><span class="sxs-lookup"><span data-stu-id="19376-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="19376-103">Gibt eine einzuschließende Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="19376-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="19376-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="19376-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="19376-105">&nbsp;&nbsp;[**\<AssemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="19376-105">&nbsp;&nbsp;[**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
<span data-ttu-id="19376-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<LinkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="19376-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="19376-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="19376-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="19376-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="19376-108">Attribute</span></span>

|           | <span data-ttu-id="19376-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19376-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="19376-110">**href**</span><span class="sxs-lookup"><span data-stu-id="19376-110">**href**</span></span>  | <span data-ttu-id="19376-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="19376-111">Required attribute.</span></span><br><br><span data-ttu-id="19376-112">Die URL der Konfigurationsdatei eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="19376-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="19376-113">Die einzige unterstützte Format für die **Href** Attribut `file://`.</span><span class="sxs-lookup"><span data-stu-id="19376-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="19376-114">Lokale Dateien und UNC-Dateien werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="19376-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="19376-115">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="19376-115">Parent element</span></span>

|     | <span data-ttu-id="19376-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19376-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="19376-117">**\<AssemblyBinding >** Element</span><span class="sxs-lookup"><span data-stu-id="19376-117">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="19376-118">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="19376-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="19376-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="19376-119">Child elements</span></span>

<span data-ttu-id="19376-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="19376-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="19376-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19376-121">Remarks</span></span>

<span data-ttu-id="19376-122">Die  **\<LinkedConfiguration >** Element vereinfacht die Wartung für Komponentenassemblys.</span><span class="sxs-lookup"><span data-stu-id="19376-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="19376-123">Wenn eine oder mehrere Anwendungen eine Assembly zu, die über eine Konfigurationsdatei, die sich in einem bekannten Speicherort befinden verwenden, können die Konfigurationsdateien der Anwendungen, die die Assembly der  **\<LinkedConfiguration >** Element, das die Konfigurationsdatei der Assembly, anstatt direkt darunter von Konfigurationsinformationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="19376-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="19376-124">Wenn die Komponentenassembly gewartet wird, stellt das Aktualisieren der allgemeinen Konfigurationsdatei aktualisierte Konfigurationsinformationen für alle Anwendungen, die die Assembly zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="19376-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="19376-125">Die  **\<LinkedConfiguration >** Element wird für Anwendungen mit Windows-Seite-an-Seite-Manifeste nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="19376-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="19376-126">Die folgenden Regeln bestimmen die Verwendung von verknüpfte Konfigurationsdateien:</span><span class="sxs-lookup"><span data-stu-id="19376-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="19376-127">Die Einstellungen in Konfigurationsdateien enthalten nur Auswirkungen auf das Ladeprogramm Bindungsrichtlinie und werden nur vom Ladeprogramm verwendet.</span><span class="sxs-lookup"><span data-stu-id="19376-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="19376-128">Die enthaltenen Konfigurationsdateien haben Einstellungen als die Bindung von Richtlinien, aber diese Einstellungen haben keinerlei Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="19376-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="19376-129">Die einzige unterstützte Format für die `href` Attribut `file://`.</span><span class="sxs-lookup"><span data-stu-id="19376-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="19376-130">Lokale Dateien und UNC-Dateien werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="19376-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="19376-131">Es gibt keine Einschränkung für die Anzahl der verknüpften Konfigurationen pro Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="19376-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="19376-132">Alle verknüpften Konfigurationsdateien werden zusammengeführt, um eine Datei, vergleichbar mit dem Verhalten von bilden die `#include` in C/C++-Direktive.</span><span class="sxs-lookup"><span data-stu-id="19376-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="19376-133">Die  **\<LinkedConfiguration >** Element ist nur in Anwendungskonfigurationsdateien zulässig; es wird ignoriert, *"Machine.config"*.</span><span class="sxs-lookup"><span data-stu-id="19376-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="19376-134">Zirkelverweise werden erkannt und beendet.</span><span class="sxs-lookup"><span data-stu-id="19376-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="19376-135">D.h., wenn die  **\<LinkedConfiguration >** Elemente aus einer Reihe von Konfigurationsdateien bilden eine Schleife, die Schleife erkannt und gestoppt wird.</span><span class="sxs-lookup"><span data-stu-id="19376-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="19376-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19376-136">Example</span></span>

<span data-ttu-id="19376-137">Das folgende Beispiel zeigt, wie Sie die Konfigurationsdatei aus der lokalen Festplatte enthalten:</span><span class="sxs-lookup"><span data-stu-id="19376-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="19376-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19376-138">See also</span></span>

<span data-ttu-id="19376-139">[**\<AssemblyBinding >** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="19376-139">[**\<assemblyBinding>** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
[<span data-ttu-id="19376-140">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="19376-140">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
