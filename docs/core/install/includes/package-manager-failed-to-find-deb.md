---
ms.openlocfilehash: 9d4c031eda291b0a8832c824789efdffe4084926
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132942"
---

<span data-ttu-id="38161-101">Wenn eine Fehlermeldung wie **Unable to locate package {netcore-package}** (Das Paket {netcore-package} konnte nicht gefunden werden) oder **Some packages could not be installed** (Einige Pakete konnten nicht installiert werden) angezeigt wird, führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="38161-101">If you receive an error message similar to **Unable to locate package {netcore-package}** or **Some packages could not be installed**, run the following commands.</span></span>

<span data-ttu-id="38161-102">Die folgende Befehlsgruppe enthält zwei Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="38161-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="38161-103">Dieser steht für das .NET Core-Paket, das Sie installieren,z. B. `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="38161-103">This represents the .NET Core package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="38161-104">, und wird im nachstehenden Befehl `sudo apt-get install` verwendet.</span><span class="sxs-lookup"><span data-stu-id="38161-104">This is used in the `sudo apt-get install` command below.</span></span>

- `{os-version}`\
<span data-ttu-id="38161-105">Dies steht für die von Ihnen genutzte Linux-Version,</span><span class="sxs-lookup"><span data-stu-id="38161-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="38161-106">und wird im nachstehenden Befehl `wget` verwendet.</span><span class="sxs-lookup"><span data-stu-id="38161-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="38161-107">Versuchen Sie zunächst, die Paketliste zu löschen:</span><span class="sxs-lookup"><span data-stu-id="38161-107">First, try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

<span data-ttu-id="38161-108">Versuchen Sie dann, .NET Core neu zu installieren.</span><span class="sxs-lookup"><span data-stu-id="38161-108">Then, try to install .NET Core again.</span></span> <span data-ttu-id="38161-109">Wenn dies nicht funktioniert, können Sie mithilfe der folgenden Befehle eine manuelle Installation ausführen:</span><span class="sxs-lookup"><span data-stu-id="38161-109">If that doesn't work, you can run a manual install with the following commands:</span></span>
