---
ms.openlocfilehash: e7d35045892c62f759aad5067962ac5c15a9fb8b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602699"
---

<span data-ttu-id="3f707-101">Sowohl das .NET Core SDK als auch die .NET Core-Runtime können nach dem Herunterladen manuell installiert werden.</span><span class="sxs-lookup"><span data-stu-id="3f707-101">Both .NET Core SDK and .NET Core Runtime can be manually installed after they've been downloaded.</span></span> <span data-ttu-id="3f707-102">Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="3f707-102">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="3f707-103">Laden Sie zunächst eine binäre Version entweder für das SDK oder die Runtime von einer der folgenden Websites herunter:</span><span class="sxs-lookup"><span data-stu-id="3f707-103">First, download a binary release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="3f707-104">✔️ [.NET 5.0 Preview herunterladen](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="3f707-104">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="3f707-105">✔️ [.NET Core 3.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="3f707-105">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="3f707-106">❌ [.NET Core 3.0 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span><span class="sxs-lookup"><span data-stu-id="3f707-106">❌ [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span></span>
- <span data-ttu-id="3f707-107">❌ [.NET Core 2.2 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/2.2)</span><span class="sxs-lookup"><span data-stu-id="3f707-107">❌ [.NET Core 2.2 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2)</span></span>
- <span data-ttu-id="3f707-108">✔️ [.NET Core 2.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="3f707-108">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>

<span data-ttu-id="3f707-109">Extrahieren Sie als Nächstes die heruntergeladene Datei, und führen Sie den Befehl `export` aus, um von . NET Core verwendete Variablen festzulegen. Stellen Sie anschließend sicher, dass sich .NET Core in PATH befindet.</span><span class="sxs-lookup"><span data-stu-id="3f707-109">Next, extract the downloaded file and use the `export` command to set variables used by .NET Core and then ensure .NET Core is in PATH.</span></span>

<span data-ttu-id="3f707-110">Laden Sie zunächst eine binäre .NET Core-Version herunter, um die Runtime zu extrahieren und die .NET Core-CLI-Befehle im Terminal bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3f707-110">To extract the runtime and make the .NET Core CLI commands available at the terminal, first download a .NET Core binary release.</span></span> <span data-ttu-id="3f707-111">Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle im Verzeichnis aus, in dem die Datei gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="3f707-111">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="3f707-112">Mit den oben aufgeführten `export`-Befehlen werden nur die .NET Core-CLI-Befehle für die Terminalsitzung bereitgestellt, in der sie ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="3f707-112">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="3f707-113">Sie können Ihr Shell-Profil bearbeiten, um diese Befehle dauerhaft hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3f707-113">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="3f707-114">Für Linux sind verschiedene Shells verfügbar, die jeweils über ein anderes Profil verfügen.</span><span class="sxs-lookup"><span data-stu-id="3f707-114">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="3f707-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f707-115">For example:</span></span>
>
> - <span data-ttu-id="3f707-116">**Bash-Shell**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="3f707-116">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="3f707-117">**Korn-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="3f707-117">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="3f707-118">**Z-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="3f707-118">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="3f707-119">Bearbeiten Sie die geeignete Quelldatei für die Shell, und fügen Sie `:$HOME/dotnet` am Ende der vorhandenen `PATH`-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="3f707-119">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="3f707-120">Wenn keine `PATH`-Anweisung enthalten ist, fügen Sie eine neue Zeile mit `export PATH=$PATH:$HOME/dotnet` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3f707-120">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="3f707-121">Fügen Sie außerdem `export DOTNET_ROOT=$HOME/dotnet` am Ende der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="3f707-121">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="3f707-122">Bei diesem Ansatz können Sie unterschiedliche Versionen an separaten Speicherorten installieren und explizit auswählen, welche Version von welcher Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3f707-122">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>
