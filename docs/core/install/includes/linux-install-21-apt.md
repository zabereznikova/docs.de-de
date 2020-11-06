---
ms.openlocfilehash: 188fef66444cd60f59a3cb9619c0d86efd155f99
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93136113"
---

### <a name="install-the-sdk"></a><span data-ttu-id="52388-101">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="52388-101">Install the SDK</span></span>

<span data-ttu-id="52388-102">Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="52388-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="52388-103">Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="52388-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="52388-104">Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren:</span><span class="sxs-lookup"><span data-stu-id="52388-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="52388-105">Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket dotnet-sdk-2.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung für APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="52388-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-2.1** , see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="52388-106">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="52388-106">Install the runtime</span></span>

<span data-ttu-id="52388-107">Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="52388-107">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="52388-108">Durch die folgenden Befehle wird die ASP.NET Core-Runtime installiert, die Runtime für .NET Core mit der höchsten Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="52388-108">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="52388-109">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="52388-109">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="52388-110">Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket aspnetcore-runtime-2.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung für APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="52388-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-2.1** , see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="52388-111">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet: Ersetzen Sie dazu im vorangegangenen Befehl `aspnetcore-runtime-2.1` durch `dotnet-runtime-2.1`.</span><span class="sxs-lookup"><span data-stu-id="52388-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the previous command with `dotnet-runtime-2.1`.</span></span>

```bash
sudo apt-get install -y dotnet-runtime-2.1
```
