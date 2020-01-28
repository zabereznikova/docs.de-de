---
title: dotnet store-befehl
description: Der „dotnet store“-Befehl speichert die angegebenen Assemblys im Laufzeitpaketspeicher.
ms.date: 05/29/2018
ms.openlocfilehash: cc5b4b6160ba296e1529f006c15e238746d9e08a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733050"
---
# <a name="dotnet-store"></a><span data-ttu-id="6d111-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="6d111-103">dotnet store</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="6d111-104">name</span><span class="sxs-lookup"><span data-stu-id="6d111-104">Name</span></span>

<span data-ttu-id="6d111-105">`dotnet store`: speichert die angegebenen Assemblys im [Laufzeitpaketspeicher](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="6d111-105">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="6d111-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="6d111-106">Synopsis</span></span>

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a><span data-ttu-id="6d111-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d111-107">Description</span></span>

<span data-ttu-id="6d111-108">`dotnet store`: speichert die angegebenen Assemblys im [Laufzeitpaketspeicher](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="6d111-108">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="6d111-109">Assemblys werden standardmäßig für die Ziellaufzeit und das Zielframework optimiert.</span><span class="sxs-lookup"><span data-stu-id="6d111-109">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="6d111-110">Weitere Informationen finden Sie unter [Laufzeitpaketspeicher](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="6d111-110">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="6d111-111">Erforderliche Optionen</span><span class="sxs-lookup"><span data-stu-id="6d111-111">Required options</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="6d111-112">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="6d111-112">Specifies the [target framework](../../standard/frameworks.md).</span></span>

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="6d111-113">Die *Manifestdatei des Paketspeichers* ist eine XML-Datei, die die Liste der zu speichernden Pakete enthält.</span><span class="sxs-lookup"><span data-stu-id="6d111-113">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="6d111-114">Das Format der Manifestdatei ist mit dem SDK-Projektformat kompatibel.</span><span class="sxs-lookup"><span data-stu-id="6d111-114">The format of the manifest file is compatible with the SDK-style project format.</span></span> <span data-ttu-id="6d111-115">Also kann eine Projektdatei, die auf das gewünschte Paket verweist, mit der Option `-m|--manifest` verwendet werden, um Assemblys im Laufzeitpaketspeicher zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6d111-115">So, a project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="6d111-116">Wiederholen Sie die Option und den Pfad für jede Datei, um mehrere Manifestdateien anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6d111-116">To specify multiple manifest files, repeat the option and path for each file.</span></span> <span data-ttu-id="6d111-117">Beispiel: `--manifest packages1.csproj --manifest packages2.csproj`.</span><span class="sxs-lookup"><span data-stu-id="6d111-117">For example: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="6d111-118">Der als Ziel zu verwendende [Laufzeitbezeichner](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="6d111-118">The [runtime identifier](../rid-catalog.md) to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="6d111-119">Optionale Optionen</span><span class="sxs-lookup"><span data-stu-id="6d111-119">Optional options</span></span>

`--framework-version <FRAMEWORK_VERSION>`

<span data-ttu-id="6d111-120">Gibt die Version des .NET Core SDK an.</span><span class="sxs-lookup"><span data-stu-id="6d111-120">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="6d111-121">Mit dieser Option können Sie eine bestimmte Frameworkversion auswählen, die nicht das von der `-f|--framework`-Option angegebene Framework ist.</span><span class="sxs-lookup"><span data-stu-id="6d111-121">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

`-h|--help`

<span data-ttu-id="6d111-122">Zeigt Hilfeinformationen</span><span class="sxs-lookup"><span data-stu-id="6d111-122">Shows help information.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="6d111-123">Gibt den Pfad zum Laufzeitpaketspeicher an.</span><span class="sxs-lookup"><span data-stu-id="6d111-123">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="6d111-124">Wenn nicht angegeben, wird das Unterverzeichnis *store* des .NET Core-Installationsverzeichnisses des Benutzerprofils als Standardeinstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d111-124">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

`--skip-optimization`

<span data-ttu-id="6d111-125">Überspringt die Optimierungsphase</span><span class="sxs-lookup"><span data-stu-id="6d111-125">Skips the optimization phase.</span></span>

`--skip-symbols`

<span data-ttu-id="6d111-126">Überspringt die Symbolgenerierung.</span><span class="sxs-lookup"><span data-stu-id="6d111-126">Skips symbol generation.</span></span> <span data-ttu-id="6d111-127">Sie können aktuell nur unter Windows und Linux Symbole generieren.</span><span class="sxs-lookup"><span data-stu-id="6d111-127">Currently, you can only generate symbols on Windows and Linux.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="6d111-128">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="6d111-128">Sets the verbosity level of the command.</span></span> <span data-ttu-id="6d111-129">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6d111-129">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

<span data-ttu-id="6d111-130">Das Arbeitsverzeichnis, das vom Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6d111-130">The working directory used by the command.</span></span> <span data-ttu-id="6d111-131">Wenn nicht angegeben, wird das Unterverzeichnis *obj* des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d111-131">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="6d111-132">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6d111-132">Examples</span></span>

<span data-ttu-id="6d111-133">Speichern Sie die in der Projektdatei *packages.csproj* für .NET Core 2.0.0 angegebenen Pakete:</span><span class="sxs-lookup"><span data-stu-id="6d111-133">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

<span data-ttu-id="6d111-134">Speichern Sie die in der Datei *packages.csproj* angegebenen Pakete ohne Optimierung:</span><span class="sxs-lookup"><span data-stu-id="6d111-134">Store the packages specified in the *packages.csproj* without optimization:</span></span>

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a><span data-ttu-id="6d111-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d111-135">See also</span></span>

- [<span data-ttu-id="6d111-136">Laufzeitpaketspeicher</span><span class="sxs-lookup"><span data-stu-id="6d111-136">Runtime package store</span></span>](../deploying/runtime-store.md)
