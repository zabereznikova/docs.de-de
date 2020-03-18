---
title: Standardüberprüfung – .NET Core
description: Übersicht über die Überprüfungslogik in System.Runtime.Loader.AssemblyLoadContext.Default von .NET Core zum Suchen von Abhängigkeiten.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 500ee6ee863b1f311970a9e718936f57f7d4efd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398004"
---
# <a name="default-probing"></a><span data-ttu-id="e5406-103">Standardüberprüfung</span><span class="sxs-lookup"><span data-stu-id="e5406-103">Default probing</span></span>

<span data-ttu-id="e5406-104">Die <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>-Instanz ist für das Suchen der Abhängigkeiten einer Assembly verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="e5406-104">The <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance is responsible for locating an assembly's dependencies.</span></span> <span data-ttu-id="e5406-105">In diesem Artikel wird die Überprüfungslogik der <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>-Instanz beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e5406-105">This article describes the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance's probing logic.</span></span>

## <a name="host-configured-probing-properties"></a><span data-ttu-id="e5406-106">Vom Host konfigurierte Überprüfungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="e5406-106">Host configured probing properties</span></span>

<span data-ttu-id="e5406-107">Wenn die Runtime gestartet wird, stellt der Laufzeithost eine Reihe von benannten Überprüfungseigenschaften bereit, mit denen die Testpfade im <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e5406-107">When the runtime is started, the runtime host provides a set of named probing properties that configure <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> probe paths.</span></span>

<span data-ttu-id="e5406-108">Jede der Überprüfungseigenschaften ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5406-108">Each probing property is optional.</span></span> <span data-ttu-id="e5406-109">Ist eine Eigenschaft vorhanden, ist sie ein Zeichenfolgenwert, der eine durch Trennzeichen getrennte Liste absoluter Pfade enthält.</span><span class="sxs-lookup"><span data-stu-id="e5406-109">If present, each property is a string value that contains a delimited list of absolute paths.</span></span> <span data-ttu-id="e5406-110">Das Trennzeichen ist unter Windows „;“ und auf allen anderen Plattformen „:“.</span><span class="sxs-lookup"><span data-stu-id="e5406-110">The delimiter is ';' on Windows and ':' on all other platforms.</span></span>

|<span data-ttu-id="e5406-111">Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="e5406-111">Property Name</span></span>                 |<span data-ttu-id="e5406-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5406-112">Description</span></span>  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | <span data-ttu-id="e5406-113">Liste der Plattform- und Anwendungsassembly-Dateipfade</span><span class="sxs-lookup"><span data-stu-id="e5406-113">List of platform and application assembly file paths.</span></span> |
|`PLATFORM_RESOURCE_ROOTS`       | <span data-ttu-id="e5406-114">Liste der Verzeichnispfade für die Suche nach Satellitenressourcenassemblys</span><span class="sxs-lookup"><span data-stu-id="e5406-114">List of directory paths to search for satellite resource assemblies.</span></span> |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | <span data-ttu-id="e5406-115">Liste der Verzeichnispfade für die Suche nach nicht verwalteten (nativen) Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="e5406-115">List of directory paths to search for unmanaged (native) libraries.</span></span>        |
|`APP_PATHS`                     | <span data-ttu-id="e5406-116">Liste der Verzeichnispfade für die Suche nach verwalteten Assemblys</span><span class="sxs-lookup"><span data-stu-id="e5406-116">List of directory paths to search for managed assemblies.</span></span> |
|`APP_NI_PATHS`                  | <span data-ttu-id="e5406-117">Liste der Verzeichnispfade für die Suche nach nativen Images verwalteter Assemblys</span><span class="sxs-lookup"><span data-stu-id="e5406-117">List of directory paths to search for native images of managed assemblies.</span></span> |

### <a name="how-are-the-properties-populated"></a><span data-ttu-id="e5406-118">Wie werden diese Eigenschaften aufgefüllt?</span><span class="sxs-lookup"><span data-stu-id="e5406-118">How are the properties populated?</span></span>

<span data-ttu-id="e5406-119">Es gibt zwei Hauptszenarien für das Auffüllen der Eigenschaften, die davon abhängen, ob eine Datei *\<meineapp>.deps.json* vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e5406-119">There are two main scenarios for populating the properties depending on whether the *\<myapp>.deps.json* file exists.</span></span>

- <span data-ttu-id="e5406-120">Wenn eine *\*.deps.json*-Datei vorhanden ist, wird sie analysiert, um die Überprüfungseigenschaften aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="e5406-120">When the *\*.deps.json* file is present, it's parsed to populate the probing properties.</span></span>
- <span data-ttu-id="e5406-121">Wenn keine *\*.deps.json*-Datei vorhanden ist, wird davon ausgegangen, dass alle Abhängigkeiten im Anwendungsverzeichnis enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e5406-121">When the *\*.deps.json* file isn't present, the application's directory is assumed to contain all the dependencies.</span></span> <span data-ttu-id="e5406-122">Der Inhalt des Verzeichnisses wird dann verwendet, um die Überprüfungseigenschaften aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="e5406-122">The directory's contents are used to populate the probing properties.</span></span>

<span data-ttu-id="e5406-123">Außerdem werden die *\*.deps.json*-Dateien auf die gleiche Weise auf referenzierte Frameworks analysiert.</span><span class="sxs-lookup"><span data-stu-id="e5406-123">Additionally, the *\*.deps.json* files for any referenced frameworks are similarly parsed.</span></span>

<span data-ttu-id="e5406-124">Schließlich kann auch die Umgebungsvariable `ADDITIONAL_DEPS` verwendet werden, um zusätzliche Abhängigkeiten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e5406-124">Finally the environment variable `ADDITIONAL_DEPS` can be used to add additional dependencies.</span></span>

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a><span data-ttu-id="e5406-125">Wie kann ich die Überprüfungseigenschaften von verwaltetem Code anzeigen?</span><span class="sxs-lookup"><span data-stu-id="e5406-125">How do I see the probing properties from managed code?</span></span>

<span data-ttu-id="e5406-126">Jede Eigenschaft ist über einen Aufruf der <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType>-Funktion mit dem Eigenschaftennamen aus der obigen Tabelle verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e5406-126">Each property is available by calling the <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> function with the property name from the table above.</span></span>

### <a name="how-do-i-debug-the-probing-properties-construction"></a><span data-ttu-id="e5406-127">Wie debugge ich die Erstellung der Überprüfungseigenschaften?</span><span class="sxs-lookup"><span data-stu-id="e5406-127">How do I debug the probing properties' construction?</span></span>

<span data-ttu-id="e5406-128">Der .NET Core-Laufzeithost gibt nützliche Ablaufverfolgungsmeldungen aus, wenn bestimmte Umgebungsvariablen aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="e5406-128">The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:</span></span>

|<span data-ttu-id="e5406-129">Umgebungsvariable</span><span class="sxs-lookup"><span data-stu-id="e5406-129">Environment Variable</span></span>        |<span data-ttu-id="e5406-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5406-130">Description</span></span>  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |<span data-ttu-id="e5406-131">Aktiviert die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="e5406-131">Enables tracing.</span></span>|
|`COREHOST_TRACEFILE=<path>` |<span data-ttu-id="e5406-132">Gibt die Ablaufverfolgung in einem Dateipfad anstelle der Standardausgabe an `stderr` aus</span><span class="sxs-lookup"><span data-stu-id="e5406-132">Traces to a file path instead of the default `stderr`.</span></span>|
|`COREHOST_TRACE_VERBOSITY`  |<span data-ttu-id="e5406-133">Legt die Ausführlichkeit zwischen 1 (niedrigste) und 4 (höchste) fest</span><span class="sxs-lookup"><span data-stu-id="e5406-133">Sets the verbosity from 1 (lowest) to 4 (highest).</span></span>|

## <a name="managed-assembly-default-probing"></a><span data-ttu-id="e5406-134">Standardüberprüfung verwalteter Assemblys</span><span class="sxs-lookup"><span data-stu-id="e5406-134">Managed assembly default probing</span></span>

<span data-ttu-id="e5406-135">Beim Überprüfen einer verwalteten Assembly sucht der <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> in der folgenden Reihenfolge:</span><span class="sxs-lookup"><span data-stu-id="e5406-135">When probing to locate a managed assembly, the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> looks in order at:</span></span>

- <span data-ttu-id="e5406-136">Dateien, die mit dem <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` übereinstimmen (nach dem Entfernen von Dateierweiterungen)</span><span class="sxs-lookup"><span data-stu-id="e5406-136">Files matching the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (after removing file extensions).</span></span>
- <span data-ttu-id="e5406-137">Assemblydateien für native Images in `APP_NI_PATHS` mit allgemeinen Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="e5406-137">Native image assembly files in `APP_NI_PATHS` with common file extensions.</span></span>
- <span data-ttu-id="e5406-138">Assemblydateien in `APP_PATHS` mit allgemeinen Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="e5406-138">Assembly files in `APP_PATHS` with common file extensions.</span></span>

## <a name="satellite-resource-assembly-probing"></a><span data-ttu-id="e5406-139">Überprüfungen von Satellitenassemblys (Ressourcen)</span><span class="sxs-lookup"><span data-stu-id="e5406-139">Satellite (resource) assembly probing</span></span>

<span data-ttu-id="e5406-140">Um eine Satellitenassembly für eine bestimmte Kultur zu suchen, erstellen Sie einen Satz von Dateipfaden.</span><span class="sxs-lookup"><span data-stu-id="e5406-140">To find a satellite assembly for a specific culture, construct a set of file paths.</span></span>

<span data-ttu-id="e5406-141">Fügen Sie für jeden Pfad in `PLATFORM_RESOURCE_ROOTS` und dann `APP_PATHS` die Zeichenfolge <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>, ein Verzeichnistrennzeichen, die Zeichenfolge <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> und die Erweiterung „.dll“ an.</span><span class="sxs-lookup"><span data-stu-id="e5406-141">For each path in `PLATFORM_RESOURCE_ROOTS` and then `APP_PATHS`, append the <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> string, a directory separator, the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> string, and the extension '.dll'.</span></span>

<span data-ttu-id="e5406-142">Wenn eine übereinstimmende Datei vorhanden ist, versuchen Sie, diese zu laden und zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="e5406-142">If any matching file exists, attempt to load and return it.</span></span>

## <a name="unmanaged-native-library-probing"></a><span data-ttu-id="e5406-143">Überprüfung nicht verwalteter (nativer) Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="e5406-143">Unmanaged (native) library probing</span></span>

<span data-ttu-id="e5406-144">Bei einer Überprüfung einer nicht verwalteten Bibliothek werden die `NATIVE_DLL_SEARCH_DIRECTORIES` nach einer übereinstimmenden Bibliothek durchsucht.</span><span class="sxs-lookup"><span data-stu-id="e5406-144">When probing to locate an unmanaged library, the `NATIVE_DLL_SEARCH_DIRECTORIES` are searched looking for a matching library.</span></span>
