---
title: Installieren von .NET Core auf Ubuntu 16.04 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf Ubuntu 16.04 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: eae847232f5f89e81acfb90027c555d8ccd1a0b8
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740631"
---
# <a name="ubuntu-1604-package-manager---install-net-core"></a><span data-ttu-id="ab7c5-103">Ubuntu 16.04-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="ab7c5-103">Ubuntu 16.04 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="ab7c5-104">In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf Ubuntu 16.04 installieren.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-104">This article describes how to use a package manager to install .NET Core on Ubuntu 16.04.</span></span> <span data-ttu-id="ab7c5-105">Wenn Sie die Runtime installieren, wird die Installation der [ASP.NET Core-Runtime](#install-the-aspnet-core-runtime) empfohlen, da diese sowohl .NET Core- als auch ASP.NET Core-Runtimes umfasst.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="ab7c5-106">Registrieren von Microsoft-Schlüsseln und -Feeds</span><span class="sxs-lookup"><span data-stu-id="ab7c5-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="ab7c5-107">Vor der Installation von .NET müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ab7c5-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="ab7c5-108">Registrieren Sie den Microsoft-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="ab7c5-109">Registrieren Sie das Produktrepository.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-109">Register the product repository.</span></span>
- <span data-ttu-id="ab7c5-110">Installieren Sie erforderliche Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-110">Install required dependencies.</span></span>

<span data-ttu-id="ab7c5-111">Dies muss nur einmal pro Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="ab7c5-112">Öffnen Sie ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-112">Open a terminal and run the following commands.</span></span>

```bash
wget -q https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="ab7c5-113">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="ab7c5-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="ab7c5-114">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann das .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="ab7c5-115">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-115">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="ab7c5-116">Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket dotnet-sdk-3.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung des Paket-Managers](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="ab7c5-116">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="ab7c5-117">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="ab7c5-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="ab7c5-118">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die ASP.NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-118">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="ab7c5-119">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-119">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="ab7c5-120">Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket aspnetcore-runtime-3.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung des Paket-Managers](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="ab7c5-120">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="ab7c5-121">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="ab7c5-121">Install the .NET Core runtime</span></span>

<span data-ttu-id="ab7c5-122">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-122">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="ab7c5-123">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-123">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="ab7c5-124">Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket dotnet-runtime-3.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung des Paket-Managers](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="ab7c5-124">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="ab7c5-125">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="ab7c5-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="ab7c5-126">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="ab7c5-126">Troubleshoot the package manager</span></span>

<span data-ttu-id="ab7c5-127">Führen Sie die folgenden Befehle aus, wenn Sie eine ähnliche Fehlermeldung wie **Das Paket {das .NET Core-Paket} wurde nicht gefunden** erhalten.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-127">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="ab7c5-128">Wenn dies nicht funktioniert, können Sie eine manuelle Installation mit den folgenden Befehlen ausführen.</span><span class="sxs-lookup"><span data-stu-id="ab7c5-128">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/ubuntu/16.04/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```
