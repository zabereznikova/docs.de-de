---
ms.openlocfilehash: aba7b473af7685aa45f7e093a2f75311687593df
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506958"
---

<span data-ttu-id="df0e7-101">Wenn eine Fehlermeldung wie **Unable to locate package {dotnet-package}** (Das Paket {dotnet-package} konnte nicht gefunden werden) oder **Some packages could not be installed** (Einige Pakete konnten nicht installiert werden) angezeigt wird, führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="df0e7-101">If you receive an error message similar to **Unable to locate package {dotnet-package}** or **Some packages could not be installed**, run the following commands.</span></span>

<span data-ttu-id="df0e7-102">Die folgende Befehlsgruppe enthält zwei Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="df0e7-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="df0e7-103">Dieser steht für das .NET-Paket, das Sie installieren, z. B. `aspnetcore-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="df0e7-103">This represents the .NET package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="df0e7-104">Dies wird im folgenden Befehl `sudo apt-get install` verwendet.</span><span class="sxs-lookup"><span data-stu-id="df0e7-104">This is used in the following `sudo apt-get install` command.</span></span>

- `{os-version}`\
<span data-ttu-id="df0e7-105">Dies steht für die von Ihnen genutzte Linux-Version,</span><span class="sxs-lookup"><span data-stu-id="df0e7-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="df0e7-106">und wird im nachstehenden Befehl `wget` verwendet.</span><span class="sxs-lookup"><span data-stu-id="df0e7-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="df0e7-107">Versuchen Sie zunächst, die Paketliste zu löschen:</span><span class="sxs-lookup"><span data-stu-id="df0e7-107">First, try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

<span data-ttu-id="df0e7-108">Versuchen Sie dann, .NET noch mal zu installieren.</span><span class="sxs-lookup"><span data-stu-id="df0e7-108">Then, try to install .NET again.</span></span> <span data-ttu-id="df0e7-109">Wenn dies nicht funktioniert, können Sie mithilfe der folgenden Befehle eine manuelle Installation ausführen:</span><span class="sxs-lookup"><span data-stu-id="df0e7-109">If that doesn't work, you can run a manual install with the following commands:</span></span>
