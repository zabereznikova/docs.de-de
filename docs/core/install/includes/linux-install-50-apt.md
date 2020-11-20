---
ms.openlocfilehash: 87c7abf6a20dd8e9769f3b3b3cbe271d32fd62c3
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506974"
---

### <a name="install-the-sdk"></a><span data-ttu-id="c9872-101">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="c9872-101">Install the SDK</span></span>

<span data-ttu-id="c9872-102">Das .NET SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET.</span><span class="sxs-lookup"><span data-stu-id="c9872-102">The .NET SDK allows you to develop apps with .NET.</span></span> <span data-ttu-id="c9872-103">Wenn Sie das .NET SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="c9872-103">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="c9872-104">Führen Sie die folgenden Befehle aus, um das .NET SDK zu installieren:</span><span class="sxs-lookup"><span data-stu-id="c9872-104">To install the .NET SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-5.0
```

> [!IMPORTANT]
> <span data-ttu-id="c9872-105">Wenn Sie eine Fehlermeldung wie **Unable to locate package dotnet-sdk-5.0** (Das Paket „dotnet-sdk-5.0“ wurde nicht gefunden) erhalten, lesen Sie den Abschnitt [Problembehandlung für APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="c9872-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-5.0**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="c9872-106">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="c9872-106">Install the runtime</span></span>

<span data-ttu-id="c9872-107">Die ASP.NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="c9872-107">The ASP.NET Core Runtime allows you to run apps that were made with .NET that didn't provide the runtime.</span></span> <span data-ttu-id="c9872-108">Durch die folgenden Befehle wird die ASP.NET Core-Runtime installiert, die Runtime für .NET mit der höchsten Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="c9872-108">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET.</span></span> <span data-ttu-id="c9872-109">Führen Sie in Ihrem Terminal die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="c9872-109">In your terminal, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-5.0
```

> [!IMPORTANT]
> <span data-ttu-id="c9872-110">Wenn Sie eine Fehlermeldung wie **Unable to locate package aspnetcore-runtime-5.0** (Das Paket „aspnetcore-runtime-5.0“ wurde nicht gefunden) erhalten, lesen Sie den Abschnitt [Problembehandlung für APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="c9872-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-5.0**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="c9872-111">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet: Ersetzen Sie dazu im vorangegangenen Befehl `aspnetcore-runtime-5.0` durch `dotnet-runtime-5.0`:</span><span class="sxs-lookup"><span data-stu-id="c9872-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-5.0` in the previous command with `dotnet-runtime-5.0`:</span></span>

```bash
sudo apt-get install -y dotnet-runtime-5.0
```
