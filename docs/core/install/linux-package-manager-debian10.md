---
title: Installieren von .NET Core auf Debian 10 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf Debian 10 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: fd6f42684aa9fb3ea9429b80f858459698a1b825
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134318"
---
# <a name="debian-10-package-manager---install-net-core"></a><span data-ttu-id="56a3b-103">Debian 10-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="56a3b-103">Debian 10 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="56a3b-104">In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf Debian 10 installieren.</span><span class="sxs-lookup"><span data-stu-id="56a3b-104">This article describes how to use a package manager to install .NET Core on Debian 10.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="56a3b-105">Registrieren von Microsoft-Schlüsseln und -Feeds</span><span class="sxs-lookup"><span data-stu-id="56a3b-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="56a3b-106">Vor der Installation von .NET müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="56a3b-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="56a3b-107">Registrieren Sie den Microsoft-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="56a3b-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="56a3b-108">Registrieren Sie das Produktrepository.</span><span class="sxs-lookup"><span data-stu-id="56a3b-108">Register the product repository.</span></span>
- <span data-ttu-id="56a3b-109">Installieren Sie erforderliche Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="56a3b-109">Install required dependencies.</span></span>

<span data-ttu-id="56a3b-110">Dies muss nur einmal pro Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="56a3b-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="56a3b-111">Öffnen Sie ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="56a3b-111">Open a terminal and run the following commands.</span></span>

```bash
wget -O- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="56a3b-112">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="56a3b-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="56a3b-113">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann das .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="56a3b-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="56a3b-114">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="56a3b-114">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="56a3b-115">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="56a3b-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="56a3b-116">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die ASP.NET-Runtime.</span><span class="sxs-lookup"><span data-stu-id="56a3b-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="56a3b-117">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="56a3b-117">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="56a3b-118">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="56a3b-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="56a3b-119">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="56a3b-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="56a3b-120">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="56a3b-120">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="56a3b-121">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="56a3b-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="56a3b-122">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="56a3b-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="56a3b-123">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="56a3b-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="56a3b-124">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="56a3b-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
