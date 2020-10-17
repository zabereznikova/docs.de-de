---
title: dotnet nuget verify-Befehl
description: Der dotnet nuget verify-Befehl überprüft ein signiertes Paket.
author: kartheekp-ms
ms.date: 10/08/2020
ms.openlocfilehash: 6cb368e2b6c203f3774b4450c0831c5d6b2dc0e8
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957091"
---
# <a name="dotnet-nuget-verify"></a><span data-ttu-id="22312-103">dotnet nuget verify</span><span class="sxs-lookup"><span data-stu-id="22312-103">dotnet nuget verify</span></span>

<span data-ttu-id="22312-104">**Dieser Artikel gilt für:** ✔️ .NET 5.0.100-rc.2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="22312-104">**This article applies to:** ✔️ .NET 5.0.100-rc.2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="22312-105">Name</span><span class="sxs-lookup"><span data-stu-id="22312-105">Name</span></span>

<span data-ttu-id="22312-106">`dotnet nuget verify`: Hiermit wird ein signiertes NuGet-Paket überprüft.</span><span class="sxs-lookup"><span data-stu-id="22312-106">`dotnet nuget verify` - Verifies a signed NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="22312-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="22312-107">Synopsis</span></span>

```dotnetcli
dotnet nuget verify [<package-path(s)>]
    [--all]
    [--certificate-fingerprint <FINGERPRINT>]
    [-v|--verbosity <LEVEL>]

dotnet nuget verify -h|--help
```

## <a name="description"></a><span data-ttu-id="22312-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22312-108">Description</span></span>

<span data-ttu-id="22312-109">Mit dem `dotnet nuget verify`-Befehl wird ein signiertes NuGet-Paket überprüft.</span><span class="sxs-lookup"><span data-stu-id="22312-109">The `dotnet nuget verify` command verifies a signed NuGet package.</span></span>

## <a name="arguments"></a><span data-ttu-id="22312-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="22312-110">Arguments</span></span>

- **`package-path(s)`**

  <span data-ttu-id="22312-111">Hiermit wird der Dateipfad der Pakete angegeben, die überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="22312-111">Specifies the file path to the package(s) to be verified.</span></span> <span data-ttu-id="22312-112">Zur Überprüfung mehrere Pakete können mehrere Argumente übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="22312-112">Multiple position arguments can be passed in to verify multiple packages.</span></span>

## <a name="options"></a><span data-ttu-id="22312-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="22312-113">Options</span></span>

- **`--all`**

  <span data-ttu-id="22312-114">Hiermit wird angegeben, dass alle Überprüfungen für die Pakete ausgeführt werden sollen, die möglich sind.</span><span class="sxs-lookup"><span data-stu-id="22312-114">Specifies that all verifications possible should be performed on the package(s).</span></span> <span data-ttu-id="22312-115">Standardmäßig finden nur `signatures`-Überprüfungen statt.</span><span class="sxs-lookup"><span data-stu-id="22312-115">By default, only `signatures` are verified.</span></span>

> [!NOTE]
> <span data-ttu-id="22312-116">Dieser Befehl unterstützt aktuell nur die `signature`-Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="22312-116">This command currently supports only `signature` verification.</span></span>

- **`--certificate-fingerprint <FINGERPRINT>`**

  <span data-ttu-id="22312-117">Hiermit wird überprüft, ob das Signaturzertifikat mit einem der angegebenen `SHA256`-Fingerabdrücke übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="22312-117">Verify that the signer certificate matches with one of the specified `SHA256` fingerprints.</span></span> <span data-ttu-id="22312-118">Diese Option kann mehrfach bereitgestellt werden, um mehrere Fingerabdrücke bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="22312-118">This option can be supplied multiple times to provide multiple fingerprints.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="22312-119">Legt den MSBuild-Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="22312-119">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="22312-120">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="22312-120">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="22312-121">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="22312-121">The default is `normal`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="22312-122">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="22312-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="22312-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="22312-123">Examples</span></span>

- <span data-ttu-id="22312-124">Überprüfen Sie *foo.nupkg:*</span><span class="sxs-lookup"><span data-stu-id="22312-124">Verify *foo.nupkg*:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg
  ```

- <span data-ttu-id="22312-125">Hiermit werden mehrere NuGet-Pakete überprüft: *foo.nupkg* sowie *alle NUPGK-Dateien im angegebenen Verzeichnis:*</span><span class="sxs-lookup"><span data-stu-id="22312-125">Verify multiple NuGet packages - *foo.nupkg* and *all .nupkg files in the directory specified*:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg c:\mydir\*.nupkg
  ```

- <span data-ttu-id="22312-126">Hiermit wird überprüft, ob die *foo.nupgk*-Signatur mit dem angegebenen Zertifikatfingerabdruck übereinstimmt:</span><span class="sxs-lookup"><span data-stu-id="22312-126">Verify *foo.nupkg* signature matches with the specified certificate fingerprint:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039
  ```

- <span data-ttu-id="22312-127">Hiermit wird überprüft, ob die *foo.nupgk*-Signatur mit einem der angegebenen Zertifikatfingerabdrücken übereinstimmt:</span><span class="sxs-lookup"><span data-stu-id="22312-127">Verify *foo.nupkg* signature matches with one of the specified certificate fingerprints:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039 --certificate-fingerprint EC10992GG5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E027
  ```
