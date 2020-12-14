---
title: Installieren zusätzlicher ML.NET-Abhängigkeiten
description: In diesem Artikel erfahren Sie, wie Sie native Bibliotheken installieren, von denen ML.NET-Pakete abhängig sind, die jedoch nicht in der Installation von NuGet-Paketen enthalten sind.
ms.date: 04/02/2020
author: natke
ms.author: nakersha
ms.custom: how-to
ms.openlocfilehash: 75d29c6bafdce5c9bb104229ddc8d7b847f57e29
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366808"
---
# <a name="install-extra-mlnet-dependencies"></a><span data-ttu-id="057ca-103">Installieren zusätzlicher ML.NET-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="057ca-103">Install extra ML.NET dependencies</span></span>

<span data-ttu-id="057ca-104">In den meisten Fällen ist die Installation von ML.NET auf allen Betriebssystem einfach, da lediglich die entsprechenden NuGet-Pakete referenziert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="057ca-104">In most cases, on all operating systems, installing ML.NET is as simple as referencing the appropriate NuGet package.</span></span>

```dotnetcli
dotnet add package Microsoft.ML
```

<span data-ttu-id="057ca-105">In den manchen Fällen gibt es zusätzliche jedoch Installationsanforderungen, insbesondere, wenn native Komponenten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="057ca-105">In some cases though, there are additional installation requirements, particularly when native components are required.</span></span> <span data-ttu-id="057ca-106">In dieser Dokumentation werden die Installationsanforderungen für solche Fälle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="057ca-106">This document describes the installation requirements for those cases.</span></span> <span data-ttu-id="057ca-107">Die Abschnitte sind nach den jeweiligen `Microsoft.ML.*`-NuGet-Paketen unterteilt, die die zusätzliche Abhängigkeit enthalten.</span><span class="sxs-lookup"><span data-stu-id="057ca-107">The sections are broken down by the specific `Microsoft.ML.*` NuGet package that has the additional dependency.</span></span>

## <a name="microsoftmltimeseries-microsoftmlautoml"></a><span data-ttu-id="057ca-108">Microsoft.ML.TimeSeries und Microsoft.ML.AutoML</span><span class="sxs-lookup"><span data-stu-id="057ca-108">Microsoft.ML.TimeSeries, Microsoft.ML.AutoML</span></span>

<span data-ttu-id="057ca-109">Beide dieser Pakete verfügen über eine Abhängigkeit vom Paket `Microsoft.ML.MKL.Redist`, das wiederum eine Abhängigkeit von `libomp` aufweist.</span><span class="sxs-lookup"><span data-stu-id="057ca-109">Both of these packages have a dependency on `Microsoft.ML.MKL.Redist`, which has a dependency on `libomp`.</span></span>

### <a name="windows"></a><span data-ttu-id="057ca-110">Windows</span><span class="sxs-lookup"><span data-stu-id="057ca-110">Windows</span></span>

<span data-ttu-id="057ca-111">Es sind keine weiteren Installationsschritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="057ca-111">No extra installation steps required.</span></span> <span data-ttu-id="057ca-112">Die Bibliothek wird installiert, wenn das NuGet-Paket zu einem Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="057ca-112">The library is installed when the NuGet package is added to the project.</span></span>

### <a name="linux"></a><span data-ttu-id="057ca-113">Linux</span><span class="sxs-lookup"><span data-stu-id="057ca-113">Linux</span></span>

1. <span data-ttu-id="057ca-114">Installieren Sie den GPG-Schlüssel für das Repository.</span><span class="sxs-lookup"><span data-stu-id="057ca-114">Install the GPG key for the repository</span></span>

    ```bash
    sudo bash
    # <type your user password when prompted.  this will put you in a root shell>
    # cd to /tmp where this shell has write permission
    cd /tmp
    # now get the key:
    wget https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    # now install that key
    apt-key add GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    # now remove the public key file exit the root shell
    rm GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    exit
    ```

2. <span data-ttu-id="057ca-115">Fügen Sie das APT-Repository für MKL hinzu.</span><span class="sxs-lookup"><span data-stu-id="057ca-115">Add the APT Repository for MKL</span></span>

    ```bash
    sudo sh -c 'echo deb https://apt.repos.intel.com/mkl all main > /etc/apt/sources.list.d/intel-mkl.list'
    ```

3. <span data-ttu-id="057ca-116">Aktualisieren von Paketen</span><span class="sxs-lookup"><span data-stu-id="057ca-116">Update packages</span></span>

    ```bash
    sudo apt-get update
    ```

4. <span data-ttu-id="057ca-117">Installieren Sie MKL.</span><span class="sxs-lookup"><span data-stu-id="057ca-117">Install MKL</span></span>

    ```bash
    sudo apt-get install <COMPONENT>-<VERSION>.<UPDATE>-<BUILD_NUMBER>
    ```

    <span data-ttu-id="057ca-118">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="057ca-118">For example:</span></span>

    ```bash
    sudo apt-get install intel-mkl-64bit-2020.0-088
    ```

    <span data-ttu-id="057ca-119">Ermitteln Sie den Speicherort von `libiomp.so`.</span><span class="sxs-lookup"><span data-stu-id="057ca-119">Determine the location of `libiomp.so`</span></span>

    ```bash
    find /opt -name "libiomp5.so"
    ```

    <span data-ttu-id="057ca-120">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="057ca-120">For example:</span></span>

    ```output
    /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_lin/libiomp5.so
    ```

5. <span data-ttu-id="057ca-121">Fügen Sie diesen Speicherort zum Pfad zum Laden der Bibliothek hinzu:</span><span class="sxs-lookup"><span data-stu-id="057ca-121">Add this location to the load library path:</span></span>

    ```bash
    sudo ldconfig /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_lin
    ```

### <a name="mac"></a><span data-ttu-id="057ca-122">Mac</span><span class="sxs-lookup"><span data-stu-id="057ca-122">Mac</span></span>

1. <span data-ttu-id="057ca-123">Installieren Sie die Bibliothek mit `Homebrew`.</span><span class="sxs-lookup"><span data-stu-id="057ca-123">Install the library with `Homebrew`</span></span>

    ```bash
    brew update && brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/f5b1ac99a7fba27c19cee0bc4f036775c889b359/Formula/libomp.rb && brew link libomp --force
    ```
