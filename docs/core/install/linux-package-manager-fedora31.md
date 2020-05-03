---
title: '.NET Core: Installieren von .NET Core auf Fedora 31 mit einem Paket-Manager'
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf Fedora 31 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 56e5789132af2aa1171ea51698ae55d1eea5d457
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645315"
---
# <a name="fedora-31-package-manager---install-net-core"></a><span data-ttu-id="a4c63-103">Fedora 31-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="a4c63-103">Fedora 31 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="a4c63-104">In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf Fedora 31 installieren.</span><span class="sxs-lookup"><span data-stu-id="a4c63-104">This article describes how to use a package manager to install .NET Core on Fedora 31.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="a4c63-105">Hinzufügen des Microsoft-Repositoryschlüssels und -Feeds</span><span class="sxs-lookup"><span data-stu-id="a4c63-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="a4c63-106">Vor der Installation von .NET müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="a4c63-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="a4c63-107">Fügen Sie der Liste der vertrauenswürdigen Schlüssel den Microsoft-Paketsignaturschlüssel hinzu.</span><span class="sxs-lookup"><span data-stu-id="a4c63-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="a4c63-108">Fügen Sie das Repository dem Paket-Manager hinzu.</span><span class="sxs-lookup"><span data-stu-id="a4c63-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="a4c63-109">Installieren Sie erforderliche Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="a4c63-109">Install required dependencies.</span></span>

<span data-ttu-id="a4c63-110">Dies muss nur einmal pro Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a4c63-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="a4c63-111">Öffnen Sie ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="a4c63-111">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="a4c63-112">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="a4c63-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="a4c63-113">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann das .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="a4c63-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="a4c63-114">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="a4c63-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="a4c63-115">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="a4c63-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="a4c63-116">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die ASP.NET-Runtime.</span><span class="sxs-lookup"><span data-stu-id="a4c63-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="a4c63-117">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="a4c63-117">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="a4c63-118">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="a4c63-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="a4c63-119">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="a4c63-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="a4c63-120">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="a4c63-120">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="a4c63-121">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="a4c63-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="a4c63-122">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="a4c63-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="a4c63-123">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="a4c63-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="a4c63-124">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="a4c63-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
