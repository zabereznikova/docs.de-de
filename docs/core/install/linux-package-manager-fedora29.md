---
title: Installieren von .NET Core auf Fedora 29 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf Fedora 29 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: d917c867e0d8cdb066b7dee64a9dbd767b56072d
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920810"
---
# <a name="fedora-29-package-manager---install-net-core"></a><span data-ttu-id="4253d-103">Fedora 29-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="4253d-103">Fedora 29 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="4253d-104">In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf Fedora 29 installieren.</span><span class="sxs-lookup"><span data-stu-id="4253d-104">This article describes how to use a package manager to install .NET Core on Fedora 29.</span></span> <span data-ttu-id="4253d-105">Wenn Sie die Runtime installieren, wird die Installation der [ASP.NET Core-Runtime](#install-the-aspnet-core-runtime) empfohlen, da diese sowohl .NET Core- als auch ASP.NET Core-Runtimes umfasst.</span><span class="sxs-lookup"><span data-stu-id="4253d-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="4253d-106">Registrieren von Microsoft-Schlüsseln und -Feeds</span><span class="sxs-lookup"><span data-stu-id="4253d-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="4253d-107">Vor der Installation von .NET müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="4253d-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="4253d-108">Registrieren Sie den Microsoft-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="4253d-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="4253d-109">Registrieren Sie das Produktrepository.</span><span class="sxs-lookup"><span data-stu-id="4253d-109">Register the product repository.</span></span>
- <span data-ttu-id="4253d-110">Installieren Sie erforderliche Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="4253d-110">Install required dependencies.</span></span>

<span data-ttu-id="4253d-111">Dies muss nur einmal pro Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4253d-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="4253d-112">Öffnen Sie ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="4253d-112">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="4253d-113">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="4253d-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="4253d-114">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann das .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="4253d-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="4253d-115">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="4253d-115">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="4253d-116">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="4253d-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="4253d-117">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die ASP.NET-Runtime.</span><span class="sxs-lookup"><span data-stu-id="4253d-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="4253d-118">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="4253d-118">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="4253d-119">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="4253d-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="4253d-120">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="4253d-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="4253d-121">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="4253d-121">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="4253d-122">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="4253d-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="4253d-123">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="4253d-123">Troubleshoot the package manager</span></span>

<span data-ttu-id="4253d-124">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="4253d-124">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="4253d-125">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="4253d-125">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
