---
title: dotnet store-befehl
description: Der „dotnet store“-Befehl speichert die angegebenen Assemblys im Laufzeitpaketspeicher.
author: bleroy
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: a12738d0cc8edcbb65d5b6fab6e7c8b209b0f4b5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47208065"
---
# <a name="dotnet-store"></a><span data-ttu-id="885c4-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="885c4-103">dotnet store</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="885c4-104">name</span><span class="sxs-lookup"><span data-stu-id="885c4-104">Name</span></span>

<span data-ttu-id="885c4-105">`dotnet store`: speichert die angegebenen Assemblys im [Laufzeitpaketspeicher](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="885c4-105">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="885c4-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="885c4-106">Synopsis</span></span>

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a><span data-ttu-id="885c4-107">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="885c4-107">Description</span></span>

<span data-ttu-id="885c4-108">`dotnet store`: speichert die angegebenen Assemblys im [Laufzeitpaketspeicher](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="885c4-108">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="885c4-109">Assemblys werden standardmäßig für die Ziellaufzeit und das Zielframework optimiert.</span><span class="sxs-lookup"><span data-stu-id="885c4-109">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="885c4-110">Weitere Informationen finden Sie unter [Laufzeitpaketspeicher](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="885c4-110">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="885c4-111">Erforderliche Optionen</span><span class="sxs-lookup"><span data-stu-id="885c4-111">Required options</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="885c4-112">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="885c4-112">Specifies the [target framework](../../standard/frameworks.md).</span></span>

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="885c4-113">Die *Manifestdatei des Paketspeichers* ist eine XML-Datei, die die Liste der zu speichernden Pakete enthält.</span><span class="sxs-lookup"><span data-stu-id="885c4-113">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="885c4-114">Das Format der Manifestdatei ist mit dem SDK-Projektformat kompatibel.</span><span class="sxs-lookup"><span data-stu-id="885c4-114">The format of the manifest file is compatible with the SDK-style project format.</span></span> <span data-ttu-id="885c4-115">Also kann eine Projektdatei, die auf das gewünschte Paket verweist, mit der Option `-m|--manifest` verwendet werden, um Assemblys im Laufzeitpaketspeicher zu speichern.</span><span class="sxs-lookup"><span data-stu-id="885c4-115">So, a project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="885c4-116">Wiederholen Sie die Option und den Pfad für jede Datei, um mehrere Manifestdateien anzugeben.</span><span class="sxs-lookup"><span data-stu-id="885c4-116">To specify multiple manifest files, repeat the option and path for each file.</span></span> <span data-ttu-id="885c4-117">Beispiel: `--manifest packages1.csproj --manifest packages2.csproj`.</span><span class="sxs-lookup"><span data-stu-id="885c4-117">For example: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="885c4-118">Der als Ziel zu verwendende [Laufzeitbezeichner](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="885c4-118">The [runtime identifier](../rid-catalog.md) to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="885c4-119">Optionale Optionen</span><span class="sxs-lookup"><span data-stu-id="885c4-119">Optional options</span></span>

`--framework-version <FRAMEWORK_VERSION>`

<span data-ttu-id="885c4-120">Gibt die Version des .NET Core SDK an.</span><span class="sxs-lookup"><span data-stu-id="885c4-120">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="885c4-121">Mit dieser Option können Sie eine bestimmte Frameworkversion auswählen, die nicht das von der `-f|--framework`-Option angegebene Framework ist.</span><span class="sxs-lookup"><span data-stu-id="885c4-121">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

`-h|--help`

<span data-ttu-id="885c4-122">Zeigt Hilfeinformationen</span><span class="sxs-lookup"><span data-stu-id="885c4-122">Shows help information.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="885c4-123">Gibt den Pfad zum Laufzeitpaketspeicher an.</span><span class="sxs-lookup"><span data-stu-id="885c4-123">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="885c4-124">Wenn nicht angegeben, wird das Unterverzeichnis *store* des .NET Core-Installationsverzeichnisses des Benutzerprofils als Standardeinstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="885c4-124">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

`--skip-optimization`

<span data-ttu-id="885c4-125">Überspringt die Optimierungsphase</span><span class="sxs-lookup"><span data-stu-id="885c4-125">Skips the optimization phase.</span></span>

`--skip-symbols`

<span data-ttu-id="885c4-126">Überspringt die Symbolgenerierung.</span><span class="sxs-lookup"><span data-stu-id="885c4-126">Skips symbol generation.</span></span> <span data-ttu-id="885c4-127">Sie können aktuell nur unter Windows und Linux Symbole generieren.</span><span class="sxs-lookup"><span data-stu-id="885c4-127">Currently, you can only generate symbols on Windows and Linux.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="885c4-128">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="885c4-128">Sets the verbosity level of the command.</span></span> <span data-ttu-id="885c4-129">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="885c4-129">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

<span data-ttu-id="885c4-130">Das Arbeitsverzeichnis, das vom Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="885c4-130">The working directory used by the command.</span></span> <span data-ttu-id="885c4-131">Wenn nicht angegeben, wird das Unterverzeichnis *obj* des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="885c4-131">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="885c4-132">Beispiele</span><span class="sxs-lookup"><span data-stu-id="885c4-132">Examples</span></span>

<span data-ttu-id="885c4-133">Speichern Sie die in der Projektdatei *packages.csproj* für .NET Core 2.0.0 angegebenen Pakete:</span><span class="sxs-lookup"><span data-stu-id="885c4-133">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

<span data-ttu-id="885c4-134">Speichern Sie die in der Datei *packages.csproj* angegebenen Pakete ohne Optimierung:</span><span class="sxs-lookup"><span data-stu-id="885c4-134">Store the packages specified in the *packages.csproj* without optimization:</span></span>

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a><span data-ttu-id="885c4-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="885c4-135">See also</span></span>

* [<span data-ttu-id="885c4-136">Laufzeitpaketspeicher</span><span class="sxs-lookup"><span data-stu-id="885c4-136">Runtime package store</span></span>](../deploying/runtime-store.md)