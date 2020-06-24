---
ms.openlocfilehash: 164d7a8277cf985735b959c73eb87391944e795b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602675"
---

### <a name="install-the-sdk"></a><span data-ttu-id="e9835-101">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="e9835-101">Install the SDK</span></span>

<span data-ttu-id="e9835-102">Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e9835-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="e9835-103">Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="e9835-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="e9835-104">Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren:</span><span class="sxs-lookup"><span data-stu-id="e9835-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="e9835-105">Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket dotnet-sdk-2.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung für APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="e9835-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-2.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="e9835-106">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="e9835-106">Install the runtime</span></span>

<span data-ttu-id="e9835-107">Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="e9835-107">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="e9835-108">Die folgenden Befehle installieren die ASP.NET Core-Runtime, die die kompatibelste Runtime für .NET Core ist.</span><span class="sxs-lookup"><span data-stu-id="e9835-108">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="e9835-109">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="e9835-109">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="e9835-110">Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket aspnetcore-runtime-2.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung für APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="e9835-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-2.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="e9835-111">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet. Ersetzen Sie im obigen Befehl `aspnetcore-runtime-2.1` durch `dotnet-runtime-2.1`.</span><span class="sxs-lookup"><span data-stu-id="e9835-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the command above with `dotnet-runtime-2.1`.</span></span>

```bash
sudo apt-get install -y dotnet-runtime-2.1
```
