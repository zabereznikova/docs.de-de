---
ms.openlocfilehash: b8a1454dba1651911563557557cfddc38de24375
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93136292"
---

### <a name="install-the-sdk"></a><span data-ttu-id="ab298-101">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="ab298-101">Install the SDK</span></span>

<span data-ttu-id="ab298-102">Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ab298-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="ab298-103">Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="ab298-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="ab298-104">Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren:</span><span class="sxs-lookup"><span data-stu-id="ab298-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo yum install dotnet-sdk-3.1
```

### <a name="install-the-runtime"></a><span data-ttu-id="ab298-105">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="ab298-105">Install the runtime</span></span>

<span data-ttu-id="ab298-106">Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="ab298-106">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="ab298-107">Durch die folgenden Befehle wird die ASP.NET Core-Runtime installiert, die am besten kompatible Runtime für .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ab298-107">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="ab298-108">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="ab298-108">In your terminal, run the following commands.</span></span>

```bash
sudo yum install aspnetcore-runtime-3.1
```

<span data-ttu-id="ab298-109">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet: Ersetzen Sie im vorangegangenen Befehl `aspnetcore-runtime-2.1` durch `dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="ab298-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the previous command with `dotnet-runtime-3.1`.</span></span>

```bash
sudo yum install dotnet-runtime-3.1
```
