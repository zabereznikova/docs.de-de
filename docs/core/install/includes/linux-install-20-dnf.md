---
ms.openlocfilehash: 787b0a04c5bf312ad3f3e7834664e70dae9678e0
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93135996"
---

### <a name="install-the-sdk"></a><span data-ttu-id="794ac-101">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="794ac-101">Install the SDK</span></span>

<span data-ttu-id="794ac-102">Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="794ac-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="794ac-103">Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="794ac-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="794ac-104">Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren:</span><span class="sxs-lookup"><span data-stu-id="794ac-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo dnf install dotnet-sdk-2.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="794ac-105">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="794ac-105">Install the runtime</span></span>

<span data-ttu-id="794ac-106">Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="794ac-106">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="794ac-107">Durch die folgenden Befehle wird die ASP.NET Core-Runtime installiert, die am besten kompatible Runtime für .NET Core.</span><span class="sxs-lookup"><span data-stu-id="794ac-107">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="794ac-108">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="794ac-108">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install aspnetcore-runtime-2.0
```

<span data-ttu-id="794ac-109">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet: Ersetzen Sie im vorangegangenen Befehl `aspnetcore-runtime-2.0` durch `dotnet-runtime-2.0`.</span><span class="sxs-lookup"><span data-stu-id="794ac-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.0` in the previous command with `dotnet-runtime-2.0`.</span></span>

```bash
sudo dnf install dotnet-runtime-2.0
```
