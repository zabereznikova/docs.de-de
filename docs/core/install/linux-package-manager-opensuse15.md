---
title: Installieren von .NET Core auf openSUSE 15 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf openSUSE 15 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 3b5f51161dad4b0d7851421810506d6ed9f676f9
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134229"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="5d4a7-103">openSUSE 15-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="5d4a7-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="5d4a7-104">In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf openSUSE 15 installieren.</span><span class="sxs-lookup"><span data-stu-id="5d4a7-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="5d4a7-105">Registrieren von Microsoft-Schlüsseln und -Feeds</span><span class="sxs-lookup"><span data-stu-id="5d4a7-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="5d4a7-106">Vor der Installation von .NET müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="5d4a7-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="5d4a7-107">Registrieren Sie den Microsoft-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="5d4a7-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="5d4a7-108">Registrieren Sie das Produktrepository.</span><span class="sxs-lookup"><span data-stu-id="5d4a7-108">Register the product repository.</span></span>
- <span data-ttu-id="5d4a7-109">Installieren Sie erforderliche Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="5d4a7-109">Install required dependencies.</span></span>

<span data-ttu-id="5d4a7-110">Dies muss nur einmal pro Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5d4a7-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="5d4a7-111">Öffnen Sie ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="5d4a7-111">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="5d4a7-112">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="5d4a7-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="5d4a7-113">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann das .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="5d4a7-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="5d4a7-114">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="5d4a7-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="5d4a7-115">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="5d4a7-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="5d4a7-116">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die ASP.NET-Runtime.</span><span class="sxs-lookup"><span data-stu-id="5d4a7-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="5d4a7-117">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="5d4a7-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="5d4a7-118">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="5d4a7-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="5d4a7-119">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="5d4a7-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="5d4a7-120">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="5d4a7-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="5d4a7-121">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="5d4a7-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="5d4a7-122">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="5d4a7-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="5d4a7-123">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="5d4a7-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="5d4a7-124">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="5d4a7-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
