---
title: Installieren von .NET Core auf Ubuntu 18.04 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf Ubuntu 18.04 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: f590430ea10dc7188c32814641aca739b04ffa50
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595639"
---
# <a name="ubuntu-1804-package-manager---install-net-core"></a><span data-ttu-id="9f5bf-103">Ubuntu 18.04-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="9f5bf-103">Ubuntu 18.04 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="9f5bf-104">In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf Ubuntu 18.04 installieren.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-104">This article describes how to use a package manager to install .NET Core on Ubuntu 18.04.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="9f5bf-105">Hinzufügen des Microsoft-Repositoryschlüssels und -Feeds</span><span class="sxs-lookup"><span data-stu-id="9f5bf-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="9f5bf-106">Vor der Installation von .NET müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="9f5bf-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="9f5bf-107">Fügen Sie der Liste der vertrauenswürdigen Schlüssel den Microsoft-Paketsignaturschlüssel hinzu.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="9f5bf-108">Fügen Sie das Repository dem Paket-Manager hinzu.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="9f5bf-109">Installieren Sie erforderliche Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-109">Install required dependencies.</span></span>

<span data-ttu-id="9f5bf-110">Dies muss nur einmal pro Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="9f5bf-111">Öffnen Sie ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-111">Open a terminal and run the following commands.</span></span>

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="9f5bf-112">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="9f5bf-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="9f5bf-113">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann das .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="9f5bf-114">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-114">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="9f5bf-115">Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket dotnet-sdk-3.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung des Paket-Managers](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="9f5bf-115">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="9f5bf-116">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="9f5bf-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="9f5bf-117">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die ASP.NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-117">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="9f5bf-118">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-118">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="9f5bf-119">Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket aspnetcore-runtime-3.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung des Paket-Managers](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="9f5bf-119">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="9f5bf-120">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="9f5bf-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="9f5bf-121">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="9f5bf-122">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-122">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="9f5bf-123">Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket dotnet-runtime-3.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung des Paket-Managers](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="9f5bf-123">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="9f5bf-124">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="9f5bf-124">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="9f5bf-125">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="9f5bf-125">Troubleshoot the package manager</span></span>

<span data-ttu-id="9f5bf-126">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-126">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="9f5bf-127">Auffinden nicht möglich</span><span class="sxs-lookup"><span data-stu-id="9f5bf-127">Unable to locate</span></span>

<span data-ttu-id="9f5bf-128">Führen Sie die folgenden Befehle aus, wenn Sie eine ähnliche Fehlermeldung wie **Das Paket {das .NET Core-Paket} wurde nicht gefunden** erhalten.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-128">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="9f5bf-129">Wenn dies nicht funktioniert, können Sie eine manuelle Installation mit den folgenden Befehlen ausführen.</span><span class="sxs-lookup"><span data-stu-id="9f5bf-129">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/18.04/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="9f5bf-130">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="9f5bf-130">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
