---
ms.openlocfilehash: 0d29407896145bc3b2ed8284c839ae8f2f0521b2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602717"
---

<span data-ttu-id="e105c-101">Die [dotnet-install-Skripts](../../tools/dotnet-install-script.md) werden für die Automatisierung und Installation des **SDK** ohne Administratorrechte verwendet.</span><span class="sxs-lookup"><span data-stu-id="e105c-101">The [dotnet-install scripts](../../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK**.</span></span> <span data-ttu-id="e105c-102">Sie können das Skript unter <https://dot.net/v1/dotnet-install.sh> herunterladen.</span><span class="sxs-lookup"><span data-stu-id="e105c-102">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="e105c-103">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="e105c-103">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="e105c-104">Um die aktuelle Version zu installieren, bei der es sich möglicherweise nicht um eine LTS-Version handelt, nutzen Sie den Parameter `-c Current`.</span><span class="sxs-lookup"><span data-stu-id="e105c-104">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="e105c-105">Um die .NET Core-Runtime anstelle des SDK zu installieren, geben Sie den Parameter `--runtime` an.</span><span class="sxs-lookup"><span data-stu-id="e105c-105">To install .NET Core Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime
```

<span data-ttu-id="e105c-106">Sie können eine bestimmte Version installieren, indem Sie mit dem Parameter `-c` die gewünschte Version angeben.</span><span class="sxs-lookup"><span data-stu-id="e105c-106">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="e105c-107">Mit dem folgenden Befehl wird .NET Core SDK 3.1 installiert.</span><span class="sxs-lookup"><span data-stu-id="e105c-107">The following command installs .NET Core SDK 3.1.</span></span>

```bash
./dotnet-install.sh -c 3.1
```

<span data-ttu-id="e105c-108">Weitere Informationen finden Sie in der [ Referenz zu dotnet-install-Skripts](../../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="e105c-108">For more information, see [dotnet-install scripts reference](../../tools/dotnet-install-script.md).</span></span>
