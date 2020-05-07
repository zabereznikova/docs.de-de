---
title: Installieren von .NET Core auf SLES 15 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf SLES 15 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: be5a21db8c3942bfe8827dfbce41bcf88aec342a
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595614"
---
# <a name="sles-15-package-manager---install-net-core"></a><span data-ttu-id="b3935-103">SLES 15-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="b3935-103">SLES 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="b3935-104">In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf SLES 15 installieren.</span><span class="sxs-lookup"><span data-stu-id="b3935-104">This article describes how to use a package manager to install .NET Core on SLES 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="b3935-105">Hinzufügen des Microsoft-Repositoryschlüssels und -Feeds</span><span class="sxs-lookup"><span data-stu-id="b3935-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="b3935-106">Vor der Installation von .NET müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="b3935-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="b3935-107">Fügen Sie der Liste der vertrauenswürdigen Schlüssel den Microsoft-Paketsignaturschlüssel hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3935-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="b3935-108">Fügen Sie das Repository dem Paket-Manager hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3935-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="b3935-109">Installieren Sie erforderliche Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="b3935-109">Install required dependencies.</span></span>

<span data-ttu-id="b3935-110">Dies muss nur einmal pro Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b3935-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="b3935-111">Öffnen Sie ein Terminal, und führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="b3935-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="b3935-112">Das Setuppaket für das Microsoft-Repository „SLES 15“ installiert zurzeit die Datei *microsoft-prod.repo* im falschen Verzeichnis, sodass zypper die .NET Core-Pakete nicht finden kann.</span><span class="sxs-lookup"><span data-stu-id="b3935-112">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="b3935-113">Erstellen Sie einen Symlink im richtigen Verzeichnis, um dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="b3935-113">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="b3935-114">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="b3935-114">Install the .NET Core SDK</span></span>

<span data-ttu-id="b3935-115">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann das .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="b3935-115">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="b3935-116">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="b3935-116">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="b3935-117">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="b3935-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="b3935-118">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die ASP.NET-Runtime.</span><span class="sxs-lookup"><span data-stu-id="b3935-118">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="b3935-119">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="b3935-119">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="b3935-120">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="b3935-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="b3935-121">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="b3935-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="b3935-122">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="b3935-122">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="b3935-123">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="b3935-123">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="b3935-124">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="b3935-124">Troubleshoot the package manager</span></span>

<span data-ttu-id="b3935-125">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="b3935-125">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="b3935-126">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="b3935-126">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-rpm.md)]
