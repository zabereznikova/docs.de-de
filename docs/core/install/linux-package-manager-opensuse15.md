---
title: Installieren von .NET Core auf openSUSE 15 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf openSUSE 15 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: fc4c9e30ddb0cfd3e6fe79fa4f78206f4700eeee
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645664"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="acd03-103">openSUSE 15-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="acd03-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="acd03-104">In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf openSUSE 15 installieren.</span><span class="sxs-lookup"><span data-stu-id="acd03-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="acd03-105">Hinzufügen des Microsoft-Repositoryschlüssels und -Feeds</span><span class="sxs-lookup"><span data-stu-id="acd03-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="acd03-106">Vor der Installation von .NET müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="acd03-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="acd03-107">Fügen Sie der Liste der vertrauenswürdigen Schlüssel den Microsoft-Paketsignaturschlüssel hinzu.</span><span class="sxs-lookup"><span data-stu-id="acd03-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="acd03-108">Fügen Sie das Repository dem Paket-Manager hinzu.</span><span class="sxs-lookup"><span data-stu-id="acd03-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="acd03-109">Installieren Sie erforderliche Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="acd03-109">Install required dependencies.</span></span>

<span data-ttu-id="acd03-110">Dies muss nur einmal pro Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="acd03-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="acd03-111">Öffnen Sie ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="acd03-111">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="acd03-112">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="acd03-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="acd03-113">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann das .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="acd03-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="acd03-114">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="acd03-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="acd03-115">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="acd03-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="acd03-116">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die ASP.NET-Runtime.</span><span class="sxs-lookup"><span data-stu-id="acd03-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="acd03-117">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="acd03-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="acd03-118">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="acd03-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="acd03-119">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="acd03-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="acd03-120">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="acd03-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="acd03-121">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="acd03-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="acd03-122">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="acd03-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="acd03-123">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="acd03-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="acd03-124">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="acd03-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
