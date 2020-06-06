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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087967"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="5a4c9-102">\<linkedConfiguration>-Element</span><span class="sxs-lookup"><span data-stu-id="5a4c9-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="5a4c9-103">Gibt eine einzuschließende Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-103">Specifies a configuration file to include.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**

## <a name="syntax"></a><span data-ttu-id="5a4c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a4c9-104">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="5a4c9-105">attribute</span><span class="sxs-lookup"><span data-stu-id="5a4c9-105">Attribute</span></span>

|           | <span data-ttu-id="5a4c9-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5a4c9-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="5a4c9-107">**href**</span><span class="sxs-lookup"><span data-stu-id="5a4c9-107">**href**</span></span>  | <span data-ttu-id="5a4c9-108">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-108">Required attribute.</span></span><br><br><span data-ttu-id="5a4c9-109">Die URL der einzuschließenden Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-109">The URL of the configuration file to include.</span></span> <span data-ttu-id="5a4c9-110">Das einzige unterstützte Format für das **href** -Attribut ist `file://` .</span><span class="sxs-lookup"><span data-stu-id="5a4c9-110">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="5a4c9-111">Lokale Dateien und UNC-Dateien werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-111">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="5a4c9-112">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="5a4c9-112">Parent element</span></span>

|     | <span data-ttu-id="5a4c9-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5a4c9-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5a4c9-114">**\<assemblyBinding>** Gewisses</span><span class="sxs-lookup"><span data-stu-id="5a4c9-114">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="5a4c9-115">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-115">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5a4c9-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a4c9-116">Child elements</span></span>

<span data-ttu-id="5a4c9-117">Keine</span><span class="sxs-lookup"><span data-stu-id="5a4c9-117">None</span></span>

## <a name="remarks"></a><span data-ttu-id="5a4c9-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5a4c9-118">Remarks</span></span>

<span data-ttu-id="5a4c9-119">Das- **\<linkedConfiguration>** Element vereinfacht die Wartung von Komponentenassemblys</span><span class="sxs-lookup"><span data-stu-id="5a4c9-119">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="5a4c9-120">Wenn eine oder mehrere Anwendungen eine Assembly verwenden, die über eine Konfigurationsdatei an einem bekannten Speicherort verfügt, können die Konfigurationsdateien der Anwendungen, die die Assembly verwenden, das- **\<linkedConfiguration>** Element verwenden, um die Assemblykonfigurationsdatei einzuschließen, anstatt Konfigurationsinformationen direkt einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-120">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="5a4c9-121">Wenn die Komponentenassembly gewartet wird, werden bei der Aktualisierung der allgemeinen Konfigurationsdatei für alle Anwendungen, die die Assembly verwenden, aktualisierte Konfigurationsinformationen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-121">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="5a4c9-122">Das- **\<linkedConfiguration>** Element wird nicht für Anwendungen mit parallelen Windows-Manifesten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-122">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="5a4c9-123">Die folgenden Regeln bestimmen die Verwendung von verknüpften Konfigurationsdateien:</span><span class="sxs-lookup"><span data-stu-id="5a4c9-123">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="5a4c9-124">Die Einstellungen in den enthaltenen Konfigurationsdateien wirken sich nur auf die Richtlinie für die Lade Programme aus und werden nur vom Lade Modul verwendet.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-124">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="5a4c9-125">Die enthaltenen Konfigurationsdateien können andere Einstellungen als Bindungs Richtlinien aufweisen. diese Einstellungen haben jedoch keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-125">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="5a4c9-126">Das einzige unterstützte Format für das- `href` Attribut ist `file://` .</span><span class="sxs-lookup"><span data-stu-id="5a4c9-126">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="5a4c9-127">Lokale Dateien und UNC-Dateien werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-127">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="5a4c9-128">Es gibt keine Einschränkung für die Anzahl der verknüpften Konfigurationen pro Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-128">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="5a4c9-129">Alle verknüpften Konfigurationsdateien werden zusammengeführt, um eine Datei zu bilden, ähnlich wie das Verhalten der `#include` Direktive in C/C++.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-129">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="5a4c9-130">Das **\<linkedConfiguration>** -Element ist nur in Anwendungs Konfigurationsdateien zulässig. es wird in *Machine. config*ignoriert.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-130">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="5a4c9-131">Zirkuläre Verweise werden erkannt und beendet.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-131">Circular references are detected and terminated.</span></span> <span data-ttu-id="5a4c9-132">Das heißt, wenn die **\<linkedConfiguration>** Elemente einer Reihe von Konfigurationsdateien eine Schleife bilden, wird die Schleife erkannt und beendet.</span><span class="sxs-lookup"><span data-stu-id="5a4c9-132">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="5a4c9-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a4c9-133">Example</span></span>

<span data-ttu-id="5a4c9-134">Das folgende Beispiel zeigt, wie Sie die Konfigurationsdatei von der lokalen Festplatte einschließen:</span><span class="sxs-lookup"><span data-stu-id="5a4c9-134">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="5a4c9-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a4c9-135">See also</span></span>

- [<span data-ttu-id="5a4c9-136">**\<assemblyBinding>** Gewisses</span><span class="sxs-lookup"><span data-stu-id="5a4c9-136">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="5a4c9-137">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5a4c9-137">Configuration file schema for the .NET Framework</span></span>](index.md)
