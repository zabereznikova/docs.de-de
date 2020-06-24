---
ms.openlocfilehash: 7d398df060c031ae891218b82a2712d74f4c33b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602747"
---

<span data-ttu-id="c6703-101">Führen Sie die folgenden Befehle aus, wenn Sie eine ähnliche Fehlermeldung wie **Das Paket {netcore-package} wurde nicht gefunden** erhalten.</span><span class="sxs-lookup"><span data-stu-id="c6703-101">If you receive an error message similar to **Unable to locate package {netcore-package}**, run the following commands.</span></span>

<span data-ttu-id="c6703-102">Die folgende Befehlsgruppe enthält zwei Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="c6703-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="c6703-103">Dieser steht für das .NET Core-Paket, das Sie installieren,z. B. `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="c6703-103">This represents the .NET Core package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="c6703-104">, und wird im nachstehenden Befehl `sudo apt-get install` verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6703-104">This is used in the `sudo apt-get install` command below.</span></span>

- `{os-version}`\
<span data-ttu-id="c6703-105">Dies steht für die von Ihnen genutzte Linux-Version,</span><span class="sxs-lookup"><span data-stu-id="c6703-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="c6703-106">und wird im nachstehenden Befehl `wget` verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6703-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="c6703-107">Löschen Sie die Paketliste:</span><span class="sxs-lookup"><span data-stu-id="c6703-107">Try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {dotnet-package}
```

<span data-ttu-id="c6703-108">Wenn dies nicht funktioniert, können Sie mithilfe der folgenden Befehle eine manuelle Installation ausführen:</span><span class="sxs-lookup"><span data-stu-id="c6703-108">If that doesn't work, you can run a manual install with the following commands:</span></span>
