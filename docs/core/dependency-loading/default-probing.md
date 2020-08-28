---
title: Standardüberprüfung – .NET Core
description: Übersicht über die Überprüfungslogik in System.Runtime.Loader.AssemblyLoadContext.Default von .NET Core zum Suchen von Abhängigkeiten.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 13ce4c7de5f6ce1b76b2e61db810c0f19717540f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608427"
---
# <a name="default-probing"></a><span data-ttu-id="09c4d-103">Standardüberprüfung</span><span class="sxs-lookup"><span data-stu-id="09c4d-103">Default probing</span></span>

<span data-ttu-id="09c4d-104">Die <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>-Instanz ist für das Suchen der Abhängigkeiten einer Assembly verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="09c4d-104">The <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance is responsible for locating an assembly's dependencies.</span></span> <span data-ttu-id="09c4d-105">In diesem Artikel wird die Überprüfungslogik der <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>-Instanz beschrieben.</span><span class="sxs-lookup"><span data-stu-id="09c4d-105">This article describes the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance's probing logic.</span></span>

## <a name="host-configured-probing-properties"></a><span data-ttu-id="09c4d-106">Vom Host konfigurierte Überprüfungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="09c4d-106">Host configured probing properties</span></span>

<span data-ttu-id="09c4d-107">Wenn die Runtime gestartet wird, stellt der Laufzeithost eine Reihe von benannten Überprüfungseigenschaften bereit, mit denen die Testpfade im <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="09c4d-107">When the runtime is started, the runtime host provides a set of named probing properties that configure <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> probe paths.</span></span>

<span data-ttu-id="09c4d-108">Jede der Überprüfungseigenschaften ist optional.</span><span class="sxs-lookup"><span data-stu-id="09c4d-108">Each probing property is optional.</span></span> <span data-ttu-id="09c4d-109">Ist eine Eigenschaft vorhanden, ist sie ein Zeichenfolgenwert, der eine durch Trennzeichen getrennte Liste absoluter Pfade enthält.</span><span class="sxs-lookup"><span data-stu-id="09c4d-109">If present, each property is a string value that contains a delimited list of absolute paths.</span></span> <span data-ttu-id="09c4d-110">Das Trennzeichen ist unter Windows „;“ und auf allen anderen Plattformen „:“.</span><span class="sxs-lookup"><span data-stu-id="09c4d-110">The delimiter is ';' on Windows and ':' on all other platforms.</span></span>

|<span data-ttu-id="09c4d-111">Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="09c4d-111">Property Name</span></span>                 |<span data-ttu-id="09c4d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09c4d-112">Description</span></span>  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | <span data-ttu-id="09c4d-113">Liste der Plattform- und Anwendungsassembly-Dateipfade</span><span class="sxs-lookup"><span data-stu-id="09c4d-113">List of platform and application assembly file paths.</span></span> |
|`PLATFORM_RESOURCE_ROOTS`       | <span data-ttu-id="09c4d-114">Liste der Verzeichnispfade für die Suche nach Satellitenressourcenassemblys</span><span class="sxs-lookup"><span data-stu-id="09c4d-114">List of directory paths to search for satellite resource assemblies.</span></span> |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | <span data-ttu-id="09c4d-115">Liste der Verzeichnispfade für die Suche nach nicht verwalteten (nativen) Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="09c4d-115">List of directory paths to search for unmanaged (native) libraries.</span></span>        |
|`APP_PATHS`                     | <span data-ttu-id="09c4d-116">Liste der Verzeichnispfade für die Suche nach verwalteten Assemblys</span><span class="sxs-lookup"><span data-stu-id="09c4d-116">List of directory paths to search for managed assemblies.</span></span> |
|`APP_NI_PATHS`                  | <span data-ttu-id="09c4d-117">Liste der Verzeichnispfade für die Suche nach nativen Images verwalteter Assemblys</span><span class="sxs-lookup"><span data-stu-id="09c4d-117">List of directory paths to search for native images of managed assemblies.</span></span> |

### <a name="how-are-the-properties-populated"></a><span data-ttu-id="09c4d-118">Wie werden diese Eigenschaften aufgefüllt?</span><span class="sxs-lookup"><span data-stu-id="09c4d-118">How are the properties populated?</span></span>

<span data-ttu-id="09c4d-119">Es gibt zwei Hauptszenarios für das Auffüllen der Eigenschaften, die davon abhängen, ob eine *\<myapp>.deps.json*-Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="09c4d-119">There are two main scenarios for populating the properties depending on whether the *\<myapp>.deps.json* file exists.</span></span>

- <span data-ttu-id="09c4d-120">Wenn eine *\*.deps.json*-Datei vorhanden ist, wird sie analysiert, um die Überprüfungseigenschaften aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="09c4d-120">When the *\*.deps.json* file is present, it's parsed to populate the probing properties.</span></span>
- <span data-ttu-id="09c4d-121">Wenn keine *\*.deps.json*-Datei vorhanden ist, wird davon ausgegangen, dass alle Abhängigkeiten im Anwendungsverzeichnis enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="09c4d-121">When the *\*.deps.json* file isn't present, the application's directory is assumed to contain all the dependencies.</span></span> <span data-ttu-id="09c4d-122">Der Inhalt des Verzeichnisses wird dann verwendet, um die Überprüfungseigenschaften aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="09c4d-122">The directory's contents are used to populate the probing properties.</span></span>

<span data-ttu-id="09c4d-123">Außerdem werden die *\*.deps.json*-Dateien auf die gleiche Weise auf referenzierte Frameworks analysiert.</span><span class="sxs-lookup"><span data-stu-id="09c4d-123">Additionally, the *\*.deps.json* files for any referenced frameworks are similarly parsed.</span></span>

<span data-ttu-id="09c4d-124">Schließlich kann auch die Umgebungsvariable `ADDITIONAL_DEPS` verwendet werden, um zusätzliche Abhängigkeiten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="09c4d-124">Finally the environment variable `ADDITIONAL_DEPS` can be used to add additional dependencies.</span></span>  <span data-ttu-id="09c4d-125">`dotnet.exe` enthält auch einen optionalen `--additional-deps`-Parameter, um diesen Wert beim Anwendungsstart festzulegen.</span><span class="sxs-lookup"><span data-stu-id="09c4d-125">`dotnet.exe` also contains an `--additional-deps` optional parameter to set this value on application startup.</span></span>

<span data-ttu-id="09c4d-126">Die Eigenschaften `APP_PATHS` und `APP_NI_PATHS` werden nicht standardmäßig aufgefüllt und für die meisten Anwendungen weggelassen.</span><span class="sxs-lookup"><span data-stu-id="09c4d-126">The `APP_PATHS` and `APP_NI_PATHS` properties are not populated by default and are omitted for most applications.</span></span>

<span data-ttu-id="09c4d-127">Die Liste aller *\*.deps.json*-Dateien, die von der Anwendung verwendet werden, kann über `System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="09c4d-127">The list of all *\*.deps.json* files used by the application can be accessed via `System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")`.</span></span>

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a><span data-ttu-id="09c4d-128">Wie kann ich die Überprüfungseigenschaften von verwaltetem Code anzeigen?</span><span class="sxs-lookup"><span data-stu-id="09c4d-128">How do I see the probing properties from managed code?</span></span>

<span data-ttu-id="09c4d-129">Jede Eigenschaft ist über einen Aufruf der <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType>-Funktion mit dem Eigenschaftennamen aus der obigen Tabelle verfügbar.</span><span class="sxs-lookup"><span data-stu-id="09c4d-129">Each property is available by calling the <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> function with the property name from the table above.</span></span>

### <a name="how-do-i-debug-the-probing-properties-construction"></a><span data-ttu-id="09c4d-130">Wie debugge ich die Erstellung der Überprüfungseigenschaften?</span><span class="sxs-lookup"><span data-stu-id="09c4d-130">How do I debug the probing properties' construction?</span></span>

<span data-ttu-id="09c4d-131">Der .NET Core-Laufzeithost gibt nützliche Ablaufverfolgungsmeldungen aus, wenn bestimmte Umgebungsvariablen aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="09c4d-131">The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:</span></span>

|<span data-ttu-id="09c4d-132">Umgebungsvariable</span><span class="sxs-lookup"><span data-stu-id="09c4d-132">Environment Variable</span></span>        |<span data-ttu-id="09c4d-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09c4d-133">Description</span></span>  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |<span data-ttu-id="09c4d-134">Aktiviert die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="09c4d-134">Enables tracing.</span></span>|
|`COREHOST_TRACEFILE=<path>` |<span data-ttu-id="09c4d-135">Gibt die Ablaufverfolgung in einem Dateipfad anstelle der Standardausgabe an `stderr` aus</span><span class="sxs-lookup"><span data-stu-id="09c4d-135">Traces to a file path instead of the default `stderr`.</span></span>|
|`COREHOST_TRACE_VERBOSITY`  |<span data-ttu-id="09c4d-136">Legt die Ausführlichkeit zwischen 1 (niedrigste) und 4 (höchste) fest</span><span class="sxs-lookup"><span data-stu-id="09c4d-136">Sets the verbosity from 1 (lowest) to 4 (highest).</span></span>|

## <a name="managed-assembly-default-probing"></a><span data-ttu-id="09c4d-137">Standardüberprüfung verwalteter Assemblys</span><span class="sxs-lookup"><span data-stu-id="09c4d-137">Managed assembly default probing</span></span>

<span data-ttu-id="09c4d-138">Beim Überprüfen einer verwalteten Assembly sucht der <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> in der folgenden Reihenfolge:</span><span class="sxs-lookup"><span data-stu-id="09c4d-138">When probing to locate a managed assembly, the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> looks in order at:</span></span>

- <span data-ttu-id="09c4d-139">Dateien, die mit dem <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` übereinstimmen (nach dem Entfernen von Dateierweiterungen)</span><span class="sxs-lookup"><span data-stu-id="09c4d-139">Files matching the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (after removing file extensions).</span></span>
- <span data-ttu-id="09c4d-140">Assemblydateien für native Images in `APP_NI_PATHS` mit allgemeinen Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="09c4d-140">Native image assembly files in `APP_NI_PATHS` with common file extensions.</span></span>
- <span data-ttu-id="09c4d-141">Assemblydateien in `APP_PATHS` mit allgemeinen Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="09c4d-141">Assembly files in `APP_PATHS` with common file extensions.</span></span>

## <a name="satellite-resource-assembly-probing"></a><span data-ttu-id="09c4d-142">Überprüfungen von Satellitenassemblys (Ressourcen)</span><span class="sxs-lookup"><span data-stu-id="09c4d-142">Satellite (resource) assembly probing</span></span>

<span data-ttu-id="09c4d-143">Um eine Satellitenassembly für eine bestimmte Kultur zu suchen, erstellen Sie einen Satz von Dateipfaden.</span><span class="sxs-lookup"><span data-stu-id="09c4d-143">To find a satellite assembly for a specific culture, construct a set of file paths.</span></span>

<span data-ttu-id="09c4d-144">Fügen Sie für jeden Pfad in `PLATFORM_RESOURCE_ROOTS` und dann `APP_PATHS` die Zeichenfolge <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>, ein Verzeichnistrennzeichen, die Zeichenfolge <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> und die Erweiterung „.dll“ an.</span><span class="sxs-lookup"><span data-stu-id="09c4d-144">For each path in `PLATFORM_RESOURCE_ROOTS` and then `APP_PATHS`, append the <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> string, a directory separator, the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> string, and the extension '.dll'.</span></span>

<span data-ttu-id="09c4d-145">Wenn eine übereinstimmende Datei vorhanden ist, versuchen Sie, diese zu laden und zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="09c4d-145">If any matching file exists, attempt to load and return it.</span></span>

## <a name="unmanaged-native-library-probing"></a><span data-ttu-id="09c4d-146">Überprüfung nicht verwalteter (nativer) Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="09c4d-146">Unmanaged (native) library probing</span></span>

<span data-ttu-id="09c4d-147">Bei einer Überprüfung einer nicht verwalteten Bibliothek werden die `NATIVE_DLL_SEARCH_DIRECTORIES` nach einer übereinstimmenden Bibliothek durchsucht.</span><span class="sxs-lookup"><span data-stu-id="09c4d-147">When probing to locate an unmanaged library, the `NATIVE_DLL_SEARCH_DIRECTORIES` are searched looking for a matching library.</span></span>
