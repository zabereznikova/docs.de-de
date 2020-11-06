---
ms.openlocfilehash: 36f1ee26def82d426b6637ae96f382fc89791a2f
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93135848"
---

### <a name="install-the-sdk"></a><span data-ttu-id="5b4a7-101">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="5b4a7-101">Install the SDK</span></span>

<span data-ttu-id="5b4a7-102">Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5b4a7-102">The .NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="5b4a7-103">Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren.</span><span class="sxs-lookup"><span data-stu-id="5b4a7-103">To install the .NET Core SDK, run the following commands.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

### <a name="install-the-runtime"></a><span data-ttu-id="5b4a7-104">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="5b4a7-104">Install the runtime</span></span>

<span data-ttu-id="5b4a7-105">Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="5b4a7-105">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="5b4a7-106">Durch die folgenden Befehle wird die ASP.NET Core-Runtime installiert, die am besten kompatible Runtime für .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5b4a7-106">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="5b4a7-107">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="5b4a7-107">In your terminal, run the following commands.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

<span data-ttu-id="5b4a7-108">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet: Ersetzen Sie im vorangegangenen Befehl `aspnetcore-runtime-2.1` durch `dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="5b4a7-108">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the previous command with `dotnet-runtime-3.1`.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```
