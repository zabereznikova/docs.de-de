---
title: Installieren von .NET Core auf SLES 12 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf SLES 12 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: c81f9046fc96e640848f26d86e4a513916fa07ba
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998918"
---
# <a name="sles-12-package-manager---install-net-core"></a><span data-ttu-id="ced41-103">SLES 12-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="ced41-103">SLES 12 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="ced41-104">In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf SLES 12 installieren.</span><span class="sxs-lookup"><span data-stu-id="ced41-104">This article describes how to use a package manager to install .NET Core on SLES 12.</span></span> <span data-ttu-id="ced41-105">Wenn Sie die Runtime installieren, wird die Installation der [ASP.NET Core-Runtime](#install-the-aspnet-core-runtime) empfohlen, da diese sowohl .NET Core- als auch ASP.NET Core-Runtimes umfasst.</span><span class="sxs-lookup"><span data-stu-id="ced41-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="ced41-106">Registrieren von Microsoft-Schlüsseln und -Feeds</span><span class="sxs-lookup"><span data-stu-id="ced41-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="ced41-107">Vor der Installation von .NET müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ced41-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="ced41-108">Registrieren Sie den Microsoft-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="ced41-108">Register the Microsoft key</span></span>
- <span data-ttu-id="ced41-109">Registrieren Sie das Produktrepository.</span><span class="sxs-lookup"><span data-stu-id="ced41-109">register the product repository</span></span>
- <span data-ttu-id="ced41-110">Installieren Sie erforderliche Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="ced41-110">Install required dependencies</span></span>

<span data-ttu-id="ced41-111">Dies muss nur einmal pro Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ced41-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="ced41-112">Öffnen Sie ein Terminal, und führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="ced41-112">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="ced41-113">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="ced41-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="ced41-114">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann das .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="ced41-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="ced41-115">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="ced41-115">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="ced41-116">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="ced41-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="ced41-117">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die ASP.NET-Runtime.</span><span class="sxs-lookup"><span data-stu-id="ced41-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="ced41-118">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="ced41-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="ced41-119">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="ced41-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="ced41-120">Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="ced41-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="ced41-121">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="ced41-121">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="ced41-122">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="ced41-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
