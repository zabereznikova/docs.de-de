---
ms.openlocfilehash: db89539982c1afe0df374027d54826f3265f0fee
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602771"
---

### <a name="install-the-sdk"></a><span data-ttu-id="1ce7c-101">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="1ce7c-101">Install the SDK</span></span>

<span data-ttu-id="1ce7c-102">Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1ce7c-102">The .NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="1ce7c-103">Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1ce7c-103">To install the .NET Core SDK, run the following commands.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

### <a name="install-the-runtime"></a><span data-ttu-id="1ce7c-104">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="1ce7c-104">Install the runtime</span></span>

<span data-ttu-id="1ce7c-105">Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="1ce7c-105">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="1ce7c-106">Die folgenden Befehle installieren die ASP.NET Core-Runtime, die die kompatibelste Runtime für .NET Core ist.</span><span class="sxs-lookup"><span data-stu-id="1ce7c-106">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="1ce7c-107">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="1ce7c-107">In your terminal, run the following commands.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

<span data-ttu-id="1ce7c-108">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet. Ersetzen Sie im obigen Befehl `aspnetcore-runtime-2.1` durch `dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="1ce7c-108">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the command above with `dotnet-runtime-3.1`.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```
