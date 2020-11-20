---
ms.openlocfilehash: ed269683f5c4569c21ae53e9a3c1ec65eb5ebd43
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506851"
---

### <a name="install-the-sdk"></a><span data-ttu-id="45cb2-101">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="45cb2-101">Install the SDK</span></span>

<span data-ttu-id="45cb2-102">Das .NET SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET.</span><span class="sxs-lookup"><span data-stu-id="45cb2-102">The .NET SDK allows you to develop apps with .NET.</span></span> <span data-ttu-id="45cb2-103">Wenn Sie das .NET SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="45cb2-103">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="45cb2-104">Führen Sie die folgenden Befehle aus, um das .NET SDK zu installieren:</span><span class="sxs-lookup"><span data-stu-id="45cb2-104">To install the .NET SDK, run the following commands:</span></span>

```bash
sudo zypper install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="45cb2-105">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="45cb2-105">Install the runtime</span></span>

<span data-ttu-id="45cb2-106">Die ASP.NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="45cb2-106">The ASP.NET Core Runtime allows you to run apps that were made with .NET that didn't provide the runtime.</span></span> <span data-ttu-id="45cb2-107">Durch die folgenden Befehle wird die ASP.NET Core-Runtime installiert, d. h. die Runtime für .NET mit der höchsten Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="45cb2-107">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET.</span></span> <span data-ttu-id="45cb2-108">Führen Sie in Ihrem Terminal die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="45cb2-108">In your terminal, run the following commands:</span></span>

```bash
sudo zypper install aspnetcore-runtime-5.0
```

<span data-ttu-id="45cb2-109">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet: Ersetzen Sie dazu im vorangegangenen Befehl `aspnetcore-runtime-5.0` durch `dotnet-runtime-5.0`:</span><span class="sxs-lookup"><span data-stu-id="45cb2-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-5.0` in the previous command with `dotnet-runtime-5.0`:</span></span>

```bash
sudo zypper install dotnet-runtime-5.0
```
