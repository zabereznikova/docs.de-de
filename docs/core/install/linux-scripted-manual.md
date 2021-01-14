---
title: 'Manuelles Installieren von .NET unter Linux: .NET'
description: In diesem Artikel wird veranschaulicht, wie Sie das .NET SDK und die .NET-Runtime ohne Paket-Manager unter Linux installieren. Verwenden Sie das Installationsskript, oder extrahieren Sie die Binärdateien manuell.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 5879d4d66aba8bfa00caadbe3c33d6df0d7da59a
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970925"
---
# <a name="install-the-net-sdk-or-the-net-runtime-manually"></a><span data-ttu-id="f3273-104">Manuelles Installieren des .NET SDK oder der .NET-Runtime</span><span class="sxs-lookup"><span data-stu-id="f3273-104">Install the .NET SDK or the .NET Runtime manually</span></span>

<span data-ttu-id="f3273-105">.NET wird unter Linux unterstützt. In diesem Artikel wird beschrieben, wie Sie .NET mithilfe des Installationsskripts oder durch Extrahieren der Binärdateien unter Linux installieren.</span><span class="sxs-lookup"><span data-stu-id="f3273-105">.NET is supported on Linux and this article describes how to install .NET on Linux using the install script or by extracting the binaries.</span></span> <span data-ttu-id="f3273-106">Eine Liste der Distributionen, die den integrierten Paket-Manager unterstützen, finden Sie unter [Installieren von .NET unter Linux](linux.md).</span><span class="sxs-lookup"><span data-stu-id="f3273-106">For a list of distributions that support the built-in package manager, see [Install .NET on Linux](linux.md).</span></span>

<span data-ttu-id="f3273-107">Sie können .NET auch mithilfe von Snap installieren.</span><span class="sxs-lookup"><span data-stu-id="f3273-107">You can also install .NET with snap.</span></span> <span data-ttu-id="f3273-108">Weitere Informationen finden Sie unter [Installieren des .NET SDK oder der .NET-Runtime mithilfe von Snap](linux-snap.md).</span><span class="sxs-lookup"><span data-stu-id="f3273-108">For more information, see [Install the .NET SDK or the .NET Runtime with Snap](linux-snap.md).</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="net-releases"></a><span data-ttu-id="f3273-109">.NET-Releases</span><span class="sxs-lookup"><span data-stu-id="f3273-109">.NET releases</span></span>

<span data-ttu-id="f3273-110">In der folgenden Tabelle sind die Versionen von .NET (und .NET Core) aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="f3273-110">The following table lists the .NET (and .NET Core) releases:</span></span>

| <span data-ttu-id="f3273-111">✔️ Unterstützt</span><span class="sxs-lookup"><span data-stu-id="f3273-111">✔️ Supported</span></span> | <span data-ttu-id="f3273-112">❌ Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="f3273-112">❌ Unsupported</span></span> |
|-------------|---------------|
| <span data-ttu-id="f3273-113">5.0</span><span class="sxs-lookup"><span data-stu-id="f3273-113">5.0</span></span>         | <span data-ttu-id="f3273-114">3.0</span><span class="sxs-lookup"><span data-stu-id="f3273-114">3.0</span></span>           |
| <span data-ttu-id="f3273-115">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="f3273-115">3.1 (LTS)</span></span>   | <span data-ttu-id="f3273-116">2.2</span><span class="sxs-lookup"><span data-stu-id="f3273-116">2.2</span></span>           |
| <span data-ttu-id="f3273-117">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="f3273-117">2.1 (LTS)</span></span>   | <span data-ttu-id="f3273-118">2.0</span><span class="sxs-lookup"><span data-stu-id="f3273-118">2.0</span></span>           |
|             | <span data-ttu-id="f3273-119">1.1</span><span class="sxs-lookup"><span data-stu-id="f3273-119">1.1</span></span>           |
|             | <span data-ttu-id="f3273-120">1.0</span><span class="sxs-lookup"><span data-stu-id="f3273-120">1.0</span></span>           |

<span data-ttu-id="f3273-121">Weitere Informationen zum Lebenszyklus von .NET-Versionen finden Sie in der [Richtlinie zur Unterstützung von .NET Core und .NET 5](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="f3273-121">For more information about the life cycle of .NET releases, see [.NET Core and .NET 5 Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="dependencies"></a><span data-ttu-id="f3273-122">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f3273-122">Dependencies</span></span>

<span data-ttu-id="f3273-123">Es ist möglich, dass bei der Installation von .NET bestimmte Abhängigkeiten möglicherweise nicht installiert werden, z. B. wenn Sie [manuell installieren](#manual-install).</span><span class="sxs-lookup"><span data-stu-id="f3273-123">It's possible that when you install .NET, specific dependencies may not be installed, such as when [manually installing](#manual-install).</span></span> <span data-ttu-id="f3273-124">In der folgenden Liste werden die von Microsoft unterstützten Linux-Distributionen mit Abhängigkeiten erläutert, die Sie möglicherweise installieren müssen.</span><span class="sxs-lookup"><span data-stu-id="f3273-124">The following list details Linux distributions that are supported by Microsoft and have dependencies you may need to install.</span></span> <span data-ttu-id="f3273-125">Weitere Informationen finden Sie auf der Seite zur Distribution:</span><span class="sxs-lookup"><span data-stu-id="f3273-125">Check the distribution page for more information:</span></span>

- [<span data-ttu-id="f3273-126">Alpine</span><span class="sxs-lookup"><span data-stu-id="f3273-126">Alpine</span></span>](linux-alpine.md#dependencies)
- [<span data-ttu-id="f3273-127">Debian</span><span class="sxs-lookup"><span data-stu-id="f3273-127">Debian</span></span>](linux-debian.md#dependencies)
- [<span data-ttu-id="f3273-128">CentOS</span><span class="sxs-lookup"><span data-stu-id="f3273-128">CentOS</span></span>](linux-centos.md#dependencies)
- [<span data-ttu-id="f3273-129">Fedora</span><span class="sxs-lookup"><span data-stu-id="f3273-129">Fedora</span></span>](linux-fedora.md#dependencies)
- [<span data-ttu-id="f3273-130">RHEL</span><span class="sxs-lookup"><span data-stu-id="f3273-130">RHEL</span></span>](linux-rhel.md#dependencies)
- [<span data-ttu-id="f3273-131">SLES</span><span class="sxs-lookup"><span data-stu-id="f3273-131">SLES</span></span>](linux-sles.md#dependencies)
- [<span data-ttu-id="f3273-132">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="f3273-132">Ubuntu</span></span>](linux-ubuntu.md#dependencies)

<span data-ttu-id="f3273-133">Weitere Informationen zu den Abhängigkeiten finden Sie unter [Self-contained Linux apps (Eigenständige Linux-Apps)](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="f3273-133">For generic information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

### <a name="rpm-dependencies"></a><span data-ttu-id="f3273-134">RPM-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f3273-134">RPM dependencies</span></span>

<span data-ttu-id="f3273-135">Wenn Ihre Distribution zuvor nicht aufgelistet wurde und auf RPM basiert, benötigen Sie möglicherweise die folgenden Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="f3273-135">If your distribution wasn't previously listed, and is RPM-based, you may need the following dependencies:</span></span>

- <span data-ttu-id="f3273-136">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="f3273-136">krb5-libs</span></span>
- <span data-ttu-id="f3273-137">libicu</span><span class="sxs-lookup"><span data-stu-id="f3273-137">libicu</span></span>
- <span data-ttu-id="f3273-138">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="f3273-138">openssl-libs</span></span>

<span data-ttu-id="f3273-139">Wenn die OpenSSL-Version der Zielruntime-Umgebung 1.1 oder neuer ist, müssen Sie **compat-openssl10** installieren.</span><span class="sxs-lookup"><span data-stu-id="f3273-139">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

### <a name="deb-dependencies"></a><span data-ttu-id="f3273-140">DEB-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f3273-140">DEB dependencies</span></span>

<span data-ttu-id="f3273-141">Wenn Ihre Distribution zuvor nicht aufgelistet wurde und auf Debian basiert, benötigen Sie möglicherweise die folgenden Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="f3273-141">If your distribution wasn't previously listed, and is debian-based, you may need the following dependencies:</span></span>

- <span data-ttu-id="f3273-142">libc6</span><span class="sxs-lookup"><span data-stu-id="f3273-142">libc6</span></span>
- <span data-ttu-id="f3273-143">libgcc1</span><span class="sxs-lookup"><span data-stu-id="f3273-143">libgcc1</span></span>
- <span data-ttu-id="f3273-144">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="f3273-144">libgssapi-krb5-2</span></span>
- <span data-ttu-id="f3273-145">libicu67</span><span class="sxs-lookup"><span data-stu-id="f3273-145">libicu67</span></span>
- <span data-ttu-id="f3273-146">libssl1.1</span><span class="sxs-lookup"><span data-stu-id="f3273-146">libssl1.1</span></span>
- <span data-ttu-id="f3273-147">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="f3273-147">libstdc++6</span></span>
- <span data-ttu-id="f3273-148">zlib1g</span><span class="sxs-lookup"><span data-stu-id="f3273-148">zlib1g</span></span>

### <a name="common-dependencies"></a><span data-ttu-id="f3273-149">Allgemeine Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f3273-149">Common dependencies</span></span>

<span data-ttu-id="f3273-150">Für .NET-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="f3273-150">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="f3273-151">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="f3273-151">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="f3273-152">Sie können eine neuere Version von *libgdiplus* installieren, indem Sie Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f3273-152">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="f3273-153">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="f3273-153">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="f3273-154">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="f3273-154">Scripted install</span></span>

<span data-ttu-id="f3273-155">Die [dotnet-install-Skripts](../tools/dotnet-install-script.md) werden für die Automatisierung sowie für Installationen von **SDK** und **Runtime** durch Benutzer ohne Administratorrechte verwendet.</span><span class="sxs-lookup"><span data-stu-id="f3273-155">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK** and **Runtime**.</span></span> <span data-ttu-id="f3273-156">Sie können das Skript unter <https://dot.net/v1/dotnet-install.sh> herunterladen.</span><span class="sxs-lookup"><span data-stu-id="f3273-156">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="f3273-157">Das Skript installiert standardmäßig die neueste [LTS](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)-SDK-Version (Long-Term Support), die derzeit .NET Core 3.1 entspricht.</span><span class="sxs-lookup"><span data-stu-id="f3273-157">The script defaults to installing the latest SDK [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="f3273-158">Um die aktuelle Version zu installieren, bei der es sich möglicherweise nicht um eine LTS-Version handelt, nutzen Sie den Parameter `-c Current`.</span><span class="sxs-lookup"><span data-stu-id="f3273-158">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="f3273-159">Geben Sie den Parameter `--runtime` an, um die .NET-Runtime anstelle des SDK zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f3273-159">To install .NET Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

<span data-ttu-id="f3273-160">Sie können eine bestimmte Version installieren, indem Sie mit dem Parameter `-c` die gewünschte Version angeben.</span><span class="sxs-lookup"><span data-stu-id="f3273-160">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="f3273-161">Mit dem folgenden Befehl wird .NET SDK 5.0 installiert.</span><span class="sxs-lookup"><span data-stu-id="f3273-161">The following command installs .NET SDK 5.0.</span></span>

```bash
./dotnet-install.sh -c 5.0
```

<span data-ttu-id="f3273-162">Weitere Informationen finden Sie in der [ Referenz zu dotnet-install-Skripts](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="f3273-162">For more information, see [dotnet-install scripts reference](../tools/dotnet-install-script.md).</span></span>

## <a name="manual-install"></a><span data-ttu-id="f3273-163">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="f3273-163">Manual install</span></span>

<!-- Note, this content is copied in macos.md. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="f3273-164">Als Alternative zu den Paket-Managern können Sie das SDK und die Runtime herunterladen und manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="f3273-164">As an alternative to the package managers, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="f3273-165">Die manuelle Installation wird in der Regel im Rahmen von Continuous Integration-Tests oder unter nicht unterstützten Linux-Distributionen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f3273-165">Manual install is commonly used as part of continuous integration testing or on an unsupported Linux distribution.</span></span> <span data-ttu-id="f3273-166">Für Entwickler oder Benutzer ist die Verwendung eines Paket-Managers besser geeignet.</span><span class="sxs-lookup"><span data-stu-id="f3273-166">For a developer or user, it's better to use a package manager.</span></span>

<span data-ttu-id="f3273-167">Wenn Sie das .NET SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="f3273-167">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="f3273-168">Laden Sie zunächst entweder für das SDK oder die Runtime eine **binäre** Version auf einer der folgenden Websites herunter:</span><span class="sxs-lookup"><span data-stu-id="f3273-168">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="f3273-169">✔️ [.NET 5.0-Downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="f3273-169">✔️ [.NET 5.0 downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="f3273-170">✔️ [.NET Core 3.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="f3273-170">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="f3273-171">✔️ [.NET Core 2.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="f3273-171">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="f3273-172">Alle .NET Core-Downloads</span><span class="sxs-lookup"><span data-stu-id="f3273-172">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="f3273-173">Extrahieren Sie als Nächstes die heruntergeladene Datei, und führen Sie den Befehl `export` aus, um von .NET verwendete Variablen festzulegen. Stellen Sie anschließend sicher, dass sich .NET in PATH befindet.</span><span class="sxs-lookup"><span data-stu-id="f3273-173">Next, extract the downloaded file and use the `export` command to set variables used by .NET and then ensure .NET is in PATH.</span></span>

<span data-ttu-id="f3273-174">Laden Sie zunächst ein binäres .NET-Release herunter, um die Runtime zu extrahieren und die .NET-CLI-Befehle im Terminal bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f3273-174">To extract the runtime and make the .NET CLI commands available at the terminal, first download a .NET binary release.</span></span> <span data-ttu-id="f3273-175">Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle im Verzeichnis aus, in dem die Datei gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="f3273-175">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="f3273-176">Je nachdem, was Sie heruntergeladen haben, kann der Name der Archivdatei abweichen.</span><span class="sxs-lookup"><span data-stu-id="f3273-176">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="f3273-177">**Verwenden Sie den folgenden Befehl, um die Runtime zu extrahieren:**</span><span class="sxs-lookup"><span data-stu-id="f3273-177">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="f3273-178">**Verwenden Sie den folgenden Befehl, um das SDK zu extrahieren:**</span><span class="sxs-lookup"><span data-stu-id="f3273-178">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="f3273-179">Mit den oben aufgeführten `export`-Befehlen werden nur die .NET-CLI-Befehle für die Terminalsitzung bereitgestellt, in der sie ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="f3273-179">The preceding `export` commands only make the .NET CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="f3273-180">Sie können Ihr Shell-Profil bearbeiten, um diese Befehle dauerhaft hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f3273-180">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="f3273-181">Für Linux sind verschiedene Shells verfügbar, die jeweils über ein anderes Profil verfügen.</span><span class="sxs-lookup"><span data-stu-id="f3273-181">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="f3273-182">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f3273-182">For example:</span></span>
>
> - <span data-ttu-id="f3273-183">**Bash-Shell**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="f3273-183">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="f3273-184">**Korn-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="f3273-184">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="f3273-185">**Z-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="f3273-185">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="f3273-186">Bearbeiten Sie die geeignete Quelldatei für die Shell, und fügen Sie `:$HOME/dotnet` am Ende der vorhandenen `PATH`-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3273-186">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="f3273-187">Wenn keine `PATH`-Anweisung enthalten ist, fügen Sie eine neue Zeile mit `export PATH=$PATH:$HOME/dotnet` hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3273-187">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="f3273-188">Fügen Sie außerdem `export DOTNET_ROOT=$HOME/dotnet` am Ende der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3273-188">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="f3273-189">Bei diesem Ansatz können Sie unterschiedliche Versionen an separaten Speicherorten installieren und explizit auswählen, welche Version von welcher Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f3273-189">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f3273-190">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f3273-190">Next steps</span></span>

- [<span data-ttu-id="f3273-191">Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="f3273-191">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="f3273-192">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f3273-192">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
