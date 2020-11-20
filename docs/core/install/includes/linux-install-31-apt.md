---
ms.openlocfilehash: cac1fbd2369277b3a322247a7008f07929502437
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507017"
---

### <a name="install-the-sdk"></a><span data-ttu-id="9f243-101">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="9f243-101">Install the SDK</span></span>

<span data-ttu-id="9f243-102">Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9f243-102">The .NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="9f243-103">Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="9f243-103">If you install the .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="9f243-104">Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren:</span><span class="sxs-lookup"><span data-stu-id="9f243-104">To install the .NET Core SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="9f243-105">Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket dotnet-sdk-3.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung für APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="9f243-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="9f243-106">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="9f243-106">Install the runtime</span></span>

<span data-ttu-id="9f243-107">Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="9f243-107">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="9f243-108">Durch die folgenden Befehle wird die ASP.NET Core-Runtime installiert, die am besten kompatible Runtime für .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9f243-108">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="9f243-109">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="9f243-109">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="9f243-110">Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket aspnetcore-runtime-3.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung für APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="9f243-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="9f243-111">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet: Ersetzen Sie dazu im vorangegangenen Befehl `aspnetcore-runtime-3.1` durch `dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="9f243-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-3.1` in the previous command with `dotnet-runtime-3.1`.</span></span>

```bash
sudo apt-get install -y dotnet-runtime-3.1
```
