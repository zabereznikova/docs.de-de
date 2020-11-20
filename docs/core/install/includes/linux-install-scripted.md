---
ms.openlocfilehash: 07dd58c314c826c426193b829ea1f64669fb888b
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594571"
---

<span data-ttu-id="dc7ab-101">Die [dotnet-install-Skripts](../../tools/dotnet-install-script.md) werden für die Automatisierung sowie für Installationen von **SDK** und **Runtime** durch Benutzer ohne Administratorrechte verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc7ab-101">The [dotnet-install scripts](../../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK** and **Runtime**.</span></span> <span data-ttu-id="dc7ab-102">Sie können das Skript unter <https://dot.net/v1/dotnet-install.sh> herunterladen.</span><span class="sxs-lookup"><span data-stu-id="dc7ab-102">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="dc7ab-103">Das Skript installiert standardmäßig die neueste [LTS](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)-SDK-Version (Long-Term Support), die derzeit .NET 3.1 entspricht.</span><span class="sxs-lookup"><span data-stu-id="dc7ab-103">The script defaults to installing the latest SDK [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET 3.1.</span></span> <span data-ttu-id="dc7ab-104">Um die aktuelle Version zu installieren, bei der es sich möglicherweise nicht um eine LTS-Version handelt, nutzen Sie den Parameter `-c Current`.</span><span class="sxs-lookup"><span data-stu-id="dc7ab-104">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="dc7ab-105">Geben Sie den Parameter `--runtime` an, um die .NET-Runtime anstelle des SDK zu installieren.</span><span class="sxs-lookup"><span data-stu-id="dc7ab-105">To install .NET Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

<span data-ttu-id="dc7ab-106">Sie können eine bestimmte Version installieren, indem Sie mit dem Parameter `-c` die gewünschte Version angeben.</span><span class="sxs-lookup"><span data-stu-id="dc7ab-106">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="dc7ab-107">Mit dem folgenden Befehl wird .NET SDK 5.0 installiert.</span><span class="sxs-lookup"><span data-stu-id="dc7ab-107">The following command installs .NET SDK 5.0.</span></span>

```bash
./dotnet-install.sh -c 5.0
```

<span data-ttu-id="dc7ab-108">Weitere Informationen finden Sie in der [ Referenz zu dotnet-install-Skripts](../../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="dc7ab-108">For more information, see [dotnet-install scripts reference](../../tools/dotnet-install-script.md).</span></span>
