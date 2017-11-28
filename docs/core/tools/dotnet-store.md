---
title: dotnet store-befehl
description: "Der „dotnet store“-Befehl speichert die angegebenen Assemblys im Laufzeitpaketspeicher."
author: bleroy
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: fcf1eeba0709e05cff124bc3ae7bb93f4ca57128
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-store"></a><span data-ttu-id="f3889-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="f3889-103">dotnet store</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="f3889-104">Name</span><span class="sxs-lookup"><span data-stu-id="f3889-104">Name</span></span>

<span data-ttu-id="f3889-105">`dotnet store`: speichert die angegebenen Assemblys im [Laufzeitpaketspeicher](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="f3889-105">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="f3889-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f3889-106">Synopsis</span></span>

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a><span data-ttu-id="f3889-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3889-107">Description</span></span>

<span data-ttu-id="f3889-108">`dotnet store`: speichert die angegebenen Assemblys im [Laufzeitpaketspeicher](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="f3889-108">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="f3889-109">Assemblys werden standardmäßig für die Ziellaufzeit und das Zielframework optimiert.</span><span class="sxs-lookup"><span data-stu-id="f3889-109">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="f3889-110">Weitere Informationen finden Sie unter [Laufzeitpaketspeicher](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="f3889-110">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="f3889-111">Erforderliche Optionen</span><span class="sxs-lookup"><span data-stu-id="f3889-111">Required options</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="f3889-112">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="f3889-112">Specifies the [target framework](../../standard/frameworks.md).</span></span>

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="f3889-113">Die *Manifestdatei des Paketspeichers* ist eine XML-Datei, die die Liste der zu speichernden Pakete enthält.</span><span class="sxs-lookup"><span data-stu-id="f3889-113">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="f3889-114">Das Format der Manifestdatei ist mit dem *csproj*-Format kompatibel.</span><span class="sxs-lookup"><span data-stu-id="f3889-114">The format of the manifest file is compatible with the *csproj* format.</span></span> <span data-ttu-id="f3889-115">Also kann eine *csproj*-Projektdatei, die auf das gewünschte Paket verweist, mit der Option `-m|--manifest` verwendet werden, um Assemblys im Laufzeitpaketspeicher zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f3889-115">So, a *csproj* project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="f3889-116">Um mehrere Manifestdateien anzugeben, wiederholen Sie die Option und den Pfad für jede Datei: `--manifest packages1.csproj --manifest packages2.csproj`.</span><span class="sxs-lookup"><span data-stu-id="f3889-116">To specify multiple manifest files, repeat the option and path for each file: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="f3889-117">Der als Ziel zu verwendende Laufzeitbezeichner.</span><span class="sxs-lookup"><span data-stu-id="f3889-117">The runtime identifier to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="f3889-118">Optionale Optionen</span><span class="sxs-lookup"><span data-stu-id="f3889-118">Optional options</span></span>

`--framework-version <FRAMEWORK_VERSION>`

<span data-ttu-id="f3889-119">Gibt die Version des .NET Core SDK an.</span><span class="sxs-lookup"><span data-stu-id="f3889-119">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="f3889-120">Mit dieser Option können Sie eine bestimmte Frameworkversion auswählen, die nicht das von der `-f|--framework`-Option angegebene Framework ist.</span><span class="sxs-lookup"><span data-stu-id="f3889-120">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

`-h|--help`

<span data-ttu-id="f3889-121">Zeigt Hilfeinformationen</span><span class="sxs-lookup"><span data-stu-id="f3889-121">Shows help information.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f3889-122">Gibt den Pfad zum Laufzeitpaketspeicher an.</span><span class="sxs-lookup"><span data-stu-id="f3889-122">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="f3889-123">Wenn nicht angegeben, wird das Unterverzeichnis *store* des .NET Core-Installationsverzeichnisses des Benutzerprofils als Standardeinstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f3889-123">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

`--skip-optimization`

<span data-ttu-id="f3889-124">Überspringt die Optimierungsphase</span><span class="sxs-lookup"><span data-stu-id="f3889-124">Skips the optimization phase.</span></span>

`--skip-symbols`

<span data-ttu-id="f3889-125">Überspringt die Symbolgenerierung.</span><span class="sxs-lookup"><span data-stu-id="f3889-125">Skips symbol generation.</span></span> <span data-ttu-id="f3889-126">Sie können aktuell nur unter Windows und Linux Symbole generieren.</span><span class="sxs-lookup"><span data-stu-id="f3889-126">Currently, you can only generate symbols on Windows and Linux.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f3889-127">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="f3889-127">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f3889-128">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f3889-128">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

<span data-ttu-id="f3889-129">Das Arbeitsverzeichnis, das vom Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f3889-129">The working directory used by the command.</span></span> <span data-ttu-id="f3889-130">Wenn nicht angegeben, wird das Unterverzeichnis *obj* des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="f3889-130">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="f3889-131">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f3889-131">Examples</span></span>

<span data-ttu-id="f3889-132">Speichern Sie die in der Projektdatei *packages.csproj* für .NET Core 2.0.0 angegebenen Pakete:</span><span class="sxs-lookup"><span data-stu-id="f3889-132">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

<span data-ttu-id="f3889-133">Speichern Sie die in der Datei *packages.csproj* angegebenen Pakete ohne Optimierung:</span><span class="sxs-lookup"><span data-stu-id="f3889-133">Store the packages specified in the *packages.csproj* without optimization:</span></span>

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a><span data-ttu-id="f3889-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3889-134">See also</span></span>

[<span data-ttu-id="f3889-135">Laufzeitpaketspeicher</span><span class="sxs-lookup"><span data-stu-id="f3889-135">Runtime package store</span></span>](../deploying/runtime-store.md)   
