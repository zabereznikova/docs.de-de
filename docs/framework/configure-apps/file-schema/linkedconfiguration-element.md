---
title: <linkedConfiguration>-Element
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
ms.openlocfilehash: 14ee2275ecf690ab16ffaabd71fbbe7e1a4897bc
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087967"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="524ee-102">\<linkedconfiguration >-Element</span><span class="sxs-lookup"><span data-stu-id="524ee-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="524ee-103">Gibt eine einzuschließende Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="524ee-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="524ee-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="524ee-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="524ee-105">&nbsp;&nbsp;[ **\<assemblyBinding->** ](assemblybinding-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="524ee-105">&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)</span></span>\
<span data-ttu-id="524ee-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<linkedconfiguration >**</span><span class="sxs-lookup"><span data-stu-id="524ee-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="524ee-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="524ee-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="524ee-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="524ee-108">Attribute</span></span>

|           | <span data-ttu-id="524ee-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="524ee-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="524ee-110">**href**</span><span class="sxs-lookup"><span data-stu-id="524ee-110">**href**</span></span>  | <span data-ttu-id="524ee-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="524ee-111">Required attribute.</span></span><br><br><span data-ttu-id="524ee-112">Die URL der einzuschließenden Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="524ee-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="524ee-113">Das einzige unterstützte Format für das **href** -Attribut ist `file://`.</span><span class="sxs-lookup"><span data-stu-id="524ee-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="524ee-114">Lokale Dateien und UNC-Dateien werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="524ee-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="524ee-115">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="524ee-115">Parent element</span></span>

|     | <span data-ttu-id="524ee-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="524ee-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="524ee-117"> **\<assemblyBinding >** Gewisses</span><span class="sxs-lookup"><span data-stu-id="524ee-117">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="524ee-118">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="524ee-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="524ee-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="524ee-119">Child elements</span></span>

<span data-ttu-id="524ee-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="524ee-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="524ee-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="524ee-121">Remarks</span></span>

<span data-ttu-id="524ee-122">Das **\<linkedconfiguration >** -Element vereinfacht die Wartung für Komponentenassemblys.</span><span class="sxs-lookup"><span data-stu-id="524ee-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="524ee-123">Wenn eine oder mehrere Anwendungen eine Assembly verwenden, die über eine Konfigurationsdatei an einem bekannten Speicherort verfügt, können die Konfigurationsdateien der Anwendungen, die die Assembly verwenden, das **\<linkedconfiguration >** -Element verwenden, um die Assemblykonfigurationsdatei einzuschließen, anstatt Konfigurationsinformationen direkt einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="524ee-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="524ee-124">Wenn die Komponentenassembly gewartet wird, werden bei der Aktualisierung der allgemeinen Konfigurationsdatei für alle Anwendungen, die die Assembly verwenden, aktualisierte Konfigurationsinformationen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="524ee-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="524ee-125">Das **\<linkedconfiguration >** -Element wird für Anwendungen mit parallelen Windows-Manifesten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="524ee-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="524ee-126">Die folgenden Regeln bestimmen die Verwendung von verknüpften Konfigurationsdateien:</span><span class="sxs-lookup"><span data-stu-id="524ee-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="524ee-127">Die Einstellungen in den enthaltenen Konfigurationsdateien wirken sich nur auf die Richtlinie für die Lade Programme aus und werden nur vom Lade Modul verwendet.</span><span class="sxs-lookup"><span data-stu-id="524ee-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="524ee-128">Die enthaltenen Konfigurationsdateien können andere Einstellungen als Bindungs Richtlinien aufweisen. diese Einstellungen haben jedoch keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="524ee-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="524ee-129">Das einzige unterstützte Format für das `href`-Attribut ist `file://`.</span><span class="sxs-lookup"><span data-stu-id="524ee-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="524ee-130">Lokale Dateien und UNC-Dateien werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="524ee-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="524ee-131">Es gibt keine Einschränkung für die Anzahl der verknüpften Konfigurationen pro Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="524ee-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="524ee-132">Alle verknüpften Konfigurationsdateien werden zusammengeführt, um eine Datei zu bilden, ähnlich wie das Verhalten der `#include`-C++Direktive in C/.</span><span class="sxs-lookup"><span data-stu-id="524ee-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="524ee-133">Das **\<linkedconfiguration >** -Element ist nur in Anwendungs Konfigurationsdateien zulässig. Sie wird in " *Machine. config*" ignoriert.</span><span class="sxs-lookup"><span data-stu-id="524ee-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="524ee-134">Zirkuläre Verweise werden erkannt und beendet.</span><span class="sxs-lookup"><span data-stu-id="524ee-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="524ee-135">Das heißt, wenn die **\<linkedconfiguration >** Elemente einer Reihe von Konfigurationsdateien eine Schleife bilden, wird die Schleife erkannt und beendet.</span><span class="sxs-lookup"><span data-stu-id="524ee-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="524ee-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="524ee-136">Example</span></span>

<span data-ttu-id="524ee-137">Das folgende Beispiel zeigt, wie Sie die Konfigurationsdatei von der lokalen Festplatte einschließen:</span><span class="sxs-lookup"><span data-stu-id="524ee-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="524ee-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="524ee-138">See also</span></span>

- [<span data-ttu-id="524ee-139"> **\<assemblyBinding >** Gewisses</span><span class="sxs-lookup"><span data-stu-id="524ee-139">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="524ee-140">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="524ee-140">Configuration file schema for the .NET Framework</span></span>](index.md)
