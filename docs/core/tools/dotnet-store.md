---
title: dotnet store-befehl
description: Der „dotnet store“-Befehl speichert die angegebenen Assemblys im Laufzeitpaketspeicher.
ms.date: 02/14/2020
ms.openlocfilehash: da1d132b2b873ff55ec104b5bb092d0194889bdc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503578"
---
# <a name="dotnet-store"></a><span data-ttu-id="c5a64-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="c5a64-103">dotnet store</span></span>

<span data-ttu-id="c5a64-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="c5a64-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c5a64-105">Name</span><span class="sxs-lookup"><span data-stu-id="c5a64-105">Name</span></span>

<span data-ttu-id="c5a64-106">`dotnet store`: speichert die angegebenen Assemblys im [Laufzeitpaketspeicher](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="c5a64-106">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="c5a64-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c5a64-107">Synopsis</span></span>

```dotnetcli
dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]
```

## <a name="description"></a><span data-ttu-id="c5a64-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5a64-108">Description</span></span>

<span data-ttu-id="c5a64-109">`dotnet store`: speichert die angegebenen Assemblys im [Laufzeitpaketspeicher](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="c5a64-109">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="c5a64-110">Assemblys werden standardmäßig für die Ziellaufzeit und das Zielframework optimiert.</span><span class="sxs-lookup"><span data-stu-id="c5a64-110">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="c5a64-111">Weitere Informationen finden Sie unter [Laufzeitpaketspeicher](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="c5a64-111">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="c5a64-112">Erforderliche Optionen</span><span class="sxs-lookup"><span data-stu-id="c5a64-112">Required options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c5a64-113">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c5a64-113">Specifies the [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="c5a64-114">Das Zielframework muss in der Projektdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c5a64-114">The target framework has to be specified in the project file.</span></span>

- **`-m|--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="c5a64-115">Die *Manifestdatei des Paketspeichers* ist eine XML-Datei, die die Liste der zu speichernden Pakete enthält.</span><span class="sxs-lookup"><span data-stu-id="c5a64-115">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="c5a64-116">Das Format der Manifestdatei ist mit dem SDK-Projektformat kompatibel.</span><span class="sxs-lookup"><span data-stu-id="c5a64-116">The format of the manifest file is compatible with the SDK-style project format.</span></span> <span data-ttu-id="c5a64-117">Also kann eine Projektdatei, die auf das gewünschte Paket verweist, mit der Option `-m|--manifest` verwendet werden, um Assemblys im Laufzeitpaketspeicher zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c5a64-117">So, a project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="c5a64-118">Wiederholen Sie die Option und den Pfad für jede Datei, um mehrere Manifestdateien anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c5a64-118">To specify multiple manifest files, repeat the option and path for each file.</span></span> <span data-ttu-id="c5a64-119">Beispiel: `--manifest packages1.csproj --manifest packages2.csproj`.</span><span class="sxs-lookup"><span data-stu-id="c5a64-119">For example: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="c5a64-120">Der als Ziel zu verwendende [Laufzeitbezeichner](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c5a64-120">The [runtime identifier](../rid-catalog.md) to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="c5a64-121">Optionale Optionen</span><span class="sxs-lookup"><span data-stu-id="c5a64-121">Optional options</span></span>

- **`--framework-version <FRAMEWORK_VERSION>`**

  <span data-ttu-id="c5a64-122">Gibt die Version des .NET Core SDK an.</span><span class="sxs-lookup"><span data-stu-id="c5a64-122">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="c5a64-123">Mit dieser Option können Sie eine bestimmte Frameworkversion auswählen, die nicht das von der `-f|--framework`-Option angegebene Framework ist.</span><span class="sxs-lookup"><span data-stu-id="c5a64-123">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c5a64-124">Zeigt Hilfeinformationen</span><span class="sxs-lookup"><span data-stu-id="c5a64-124">Shows help information.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="c5a64-125">Gibt den Pfad zum Laufzeitpaketspeicher an.</span><span class="sxs-lookup"><span data-stu-id="c5a64-125">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="c5a64-126">Wenn nicht angegeben, wird das Unterverzeichnis *store* des .NET Core-Installationsverzeichnisses des Benutzerprofils als Standardeinstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c5a64-126">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

- **`--skip-optimization`**

  <span data-ttu-id="c5a64-127">Überspringt die Optimierungsphase</span><span class="sxs-lookup"><span data-stu-id="c5a64-127">Skips the optimization phase.</span></span>

- **`--skip-symbols`**

  <span data-ttu-id="c5a64-128">Überspringt die Symbolgenerierung.</span><span class="sxs-lookup"><span data-stu-id="c5a64-128">Skips symbol generation.</span></span> <span data-ttu-id="c5a64-129">Sie können aktuell nur unter Windows und Linux Symbole generieren.</span><span class="sxs-lookup"><span data-stu-id="c5a64-129">Currently, you can only generate symbols on Windows and Linux.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="c5a64-130">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="c5a64-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c5a64-131">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c5a64-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`-w|--working-dir <WORKING_DIRECTORY>`**

  <span data-ttu-id="c5a64-132">Das Arbeitsverzeichnis, das vom Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c5a64-132">The working directory used by the command.</span></span> <span data-ttu-id="c5a64-133">Wenn nicht angegeben, wird das Unterverzeichnis *obj* des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="c5a64-133">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="c5a64-134">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c5a64-134">Examples</span></span>

- <span data-ttu-id="c5a64-135">Speichern Sie die in der Projektdatei *packages.csproj* für .NET Core 2.0.0 angegebenen Pakete:</span><span class="sxs-lookup"><span data-stu-id="c5a64-135">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --framework-version 2.0.0
  ```

- <span data-ttu-id="c5a64-136">Speichern Sie die in der Datei *packages.csproj* angegebenen Pakete ohne Optimierung:</span><span class="sxs-lookup"><span data-stu-id="c5a64-136">Store the packages specified in the *packages.csproj* without optimization:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --skip-optimization
  ```

## <a name="see-also"></a><span data-ttu-id="c5a64-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5a64-137">See also</span></span>

- [<span data-ttu-id="c5a64-138">Laufzeitpaketspeicher</span><span class="sxs-lookup"><span data-stu-id="c5a64-138">Runtime package store</span></span>](../deploying/runtime-store.md)
