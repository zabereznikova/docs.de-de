---
title: Entfernen von .NET Core Runtime und SDK
description: In diesem Artikel wird beschrieben, wie Sie feststellen können, welche Versionen von .NET Core Runtime und SDK derzeit installiert sind, und wie Sie sie unter Windows, Mac und Linux entfernen.
ms.date: 12/17/2019
author: billwagner
ms.author: wiwagn
ms.custom: updateeachrelease
ms.openlocfilehash: 71c11825981c6259a779e1ac8f947a41618e922d
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503462"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a><span data-ttu-id="064ed-103">Entfernen von .NET Core-Runtime und SDK</span><span class="sxs-lookup"><span data-stu-id="064ed-103">How to remove the .NET Core Runtime and SDK</span></span>

<span data-ttu-id="064ed-104">Wenn Sie im Laufe der Zeit aktualisierte Versionen der .NET Core-Runtime und des SDK installieren, sollten Sie veraltete .NET Core-Versionen von Ihrem Computer entfernen.</span><span class="sxs-lookup"><span data-stu-id="064ed-104">Over time, as you install updated versions of the .NET Core runtime and SDK, you may want to remove outdated versions of .NET Core from your machine.</span></span> <span data-ttu-id="064ed-105">Durch das Entfernen älterer Runtime-Versionen ändert sich möglicherweise die für die Ausführung der freigegebenen Frameworkanwendungen ausgewählte Runtime. Dies wird im Artikel zu [Auswahl von .NET Core-Versionen](selection.md) ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="064ed-105">Removing older versions of the runtime may change the runtime chosen to run shared framework applications, as detailed in the article on [.NET Core version selection](selection.md).</span></span>

## <a name="should-i-remove-a-version"></a><span data-ttu-id="064ed-106">Sollte ich eine Version entfernen?</span><span class="sxs-lookup"><span data-stu-id="064ed-106">Should I remove a version?</span></span>

<span data-ttu-id="064ed-107">Durch das Verhalten bei der [.NET Core-Versionsauswahl](selection.md) und die Laufzeitkompatibilität von .NET Core zwischen Updates können frühere Versionen sicher entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="064ed-107">The [.NET Core version selection](selection.md) behaviors and the runtime compatibility of .NET Core across updates enables safe removal of previous versions.</span></span> <span data-ttu-id="064ed-108">Updates für die .NET Core-Runtime sind innerhalb des „Bereichs“ einer Hauptversion kompatibel, wie z.B. 1.x und 2.x.</span><span class="sxs-lookup"><span data-stu-id="064ed-108">.NET Core runtime updates are compatible within a major version 'band' such as 1.x and 2.x.</span></span> <span data-ttu-id="064ed-109">Darüber hinaus können in neueren Versionen des .NET Core SDK in der Regel Anwendungen erstellt werden, die mit früheren Versionen der Laufzeit kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="064ed-109">Additionally, newer releases of the .NET Core SDK generally maintain the ability to build applications that target previous versions of the runtime in a compatible manner.</span></span>

<span data-ttu-id="064ed-110">Im Allgemeinen benötigen Sie nur das neueste SDK und die neueste Patchversion der Laufzeiten, die für Ihre Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="064ed-110">In general, you only need the latest SDK and latest patch version of the runtimes required for your application.</span></span> <span data-ttu-id="064ed-111">Instanzen mit älteren SDK- oder Runtimeversionen beinhalten die Verwaltung von auf **project.json** basierenden Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="064ed-111">Instances where keeping older SDK or Runtime versions include maintaining **project.json**-based applications.</span></span> <span data-ttu-id="064ed-112">Sie können ältere Versionen sicher entfernen, wenn Ihre Anwendung keine bestimmten Gründe für frühere SDKs oder Laufzeiten aufweist.</span><span class="sxs-lookup"><span data-stu-id="064ed-112">Unless your application has specific reasons for earlier SDKs or runtimes, you may safely remove older versions.</span></span>

## <a name="determine-what-is-installed"></a><span data-ttu-id="064ed-113">Feststellen, was installiert ist</span><span class="sxs-lookup"><span data-stu-id="064ed-113">Determine what is installed</span></span>

<span data-ttu-id="064ed-114">Ab .NET Core 2.1 verfügt die .NET-CLI über Optionen, mit denen Sie die auf Ihrem Computer installierten Versionen des SDK und der Runtime auflisten können.</span><span class="sxs-lookup"><span data-stu-id="064ed-114">Starting with .NET Core 2.1, the .NET CLI has options you can use to list the versions of the SDK and runtime that are installed on your machine.</span></span>  <span data-ttu-id="064ed-115">Verwenden Sie [`dotnet --list-sdks`](../tools/dotnet.md#options) zum Anzeigen der Liste der auf Ihrem Computer installierten SDKs.</span><span class="sxs-lookup"><span data-stu-id="064ed-115">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) to see the list of SDKs installed on your machine.</span></span> <span data-ttu-id="064ed-116">Verwenden Sie [`dotnet --list-runtimes`](../tools/dotnet.md#options) zum Anzeigen der Liste der auf Ihrem Computer installierten Runtimes.</span><span class="sxs-lookup"><span data-stu-id="064ed-116">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) to see the list of runtimes installed on your machine.</span></span> <span data-ttu-id="064ed-117">Der folgende Text zeigt eine typische Ausgabe für Windows, macOS oder Linux:</span><span class="sxs-lookup"><span data-stu-id="064ed-117">The following text shows typical output for Windows, macOS, or Linux:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="064ed-118">Windows</span><span class="sxs-lookup"><span data-stu-id="064ed-118">Windows</span></span>](#tab/windows)

<span data-ttu-id="064ed-119">Durch Ausführen des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="064ed-119">By running the following command:</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="064ed-120">Erhalten Sie eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="064ed-120">You get output similar to the following:</span></span>

```console
2.1.200-preview-007474 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007480 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007509 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007570 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007576 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007587 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007589 [C:\Program Files\dotnet\sdk]
2.1.200 [C:\Program Files\dotnet\sdk]
2.1.201 [C:\Program Files\dotnet\sdk]
2.1.202 [C:\Program Files\dotnet\sdk]
2.1.300-preview2-008533 [C:\Program Files\dotnet\sdk]
2.1.300 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009063 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009088 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009171 [C:\Program Files\dotnet\sdk]
```

<span data-ttu-id="064ed-121">Und durch Ausführen des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="064ed-121">And by running the following command:</span></span>

```dotnetcli
dotnet --list-runtimes
```

<span data-ttu-id="064ed-122">Erhalten Sie eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="064ed-122">You get output similar to the following:</span></span>

```console
Microsoft.AspNetCore.All 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.0.6 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.7 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.9 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
```

# <a name="linux"></a>[<span data-ttu-id="064ed-123">Linux</span><span class="sxs-lookup"><span data-stu-id="064ed-123">Linux</span></span>](#tab/linux)

<span data-ttu-id="064ed-124">Durch Ausführen des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="064ed-124">By running the following command:</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="064ed-125">Erhalten Sie eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="064ed-125">You get output similar to the following:</span></span>

```console
1.0.1 [/usr/share/dotnet/sdk]
1.0.4 [/usr/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/share/dotnet/sdk]
2.0.0 [/usr/share/dotnet/sdk]
2.1.4 [/usr/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/share/dotnet/sdk]
2.1.300 [/usr/share/dotnet/sdk]
2.1.301 [/usr/share/dotnet/sdk]
```

<span data-ttu-id="064ed-126">Und durch Ausführen des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="064ed-126">And by running the following command:</span></span>

```dotnetcli
dotnet --list-runtimes
```

<span data-ttu-id="064ed-127">Erhalten Sie eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="064ed-127">You get output similar to the following:</span></span>

```console
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
```

# <a name="macos"></a>[<span data-ttu-id="064ed-128">macOS</span><span class="sxs-lookup"><span data-stu-id="064ed-128">macOS</span></span>](#tab/macos)

<span data-ttu-id="064ed-129">Durch Ausführen des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="064ed-129">By running the following command:</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="064ed-130">Erhalten Sie eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="064ed-130">You get output similar to the following:</span></span>

```console
1.0.1 [/usr/local/share/dotnet/sdk]
1.0.4 [/usr/local/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/local/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/local/share/dotnet/sdk]
2.0.0 [/usr/local/share/dotnet/sdk]
2.1.4 [/usr/local/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/local/share/dotnet/sdk]
2.1.300 [/usr/local/share/dotnet/sdk]
2.1.301 [/usr/local/share/dotnet/sdk]
```

<span data-ttu-id="064ed-131">Und durch Ausführen des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="064ed-131">And by running the following command:</span></span>

```dotnetcli
dotnet --list-runtimes
```

<span data-ttu-id="064ed-132">Erhalten Sie eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="064ed-132">You get output similar to the following:</span></span>

```console
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

---

## <a name="uninstall-net-core"></a><span data-ttu-id="064ed-133">Deinstallieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="064ed-133">Uninstall .NET Core</span></span>

# <a name="windows"></a>[<span data-ttu-id="064ed-134">Windows</span><span class="sxs-lookup"><span data-stu-id="064ed-134">Windows</span></span>](#tab/windows)

<span data-ttu-id="064ed-135">.NET Core entfernt über das Windows-Dialogfeld **Programme hinzufügen/entfernen** Versionen der .NET Core-Runtime und des SDK.</span><span class="sxs-lookup"><span data-stu-id="064ed-135">.NET Core uses the Windows **Add/Remove Programs** dialog to remove versions of the .NET Core runtime and SDK.</span></span> <span data-ttu-id="064ed-136">Die folgende Abbildung zeigt das Dialogfeld **Programme hinzufügen/entfernen** mit mehreren installierten Versionen der .NET-Runtime und des SDK.</span><span class="sxs-lookup"><span data-stu-id="064ed-136">The following figure shows the **Add/Remove Programs** dialog with several versions of the .NET runtime and SDK installed.</span></span>

![Hinzufügen/Entfernen von Programmen zum Entfernen von .NET Core](./media/remove-runtime-sdk-versions/programs-and-features.png)

<span data-ttu-id="064ed-138">Wählen Sie sämtliche Versionen aus, die Sie von Ihrem Computer entfernen möchten, und klicken Sie auf **Deinstallieren**.</span><span class="sxs-lookup"><span data-stu-id="064ed-138">Select any versions you want to remove from your machine and click **Uninstall**.</span></span>

# <a name="linux"></a>[<span data-ttu-id="064ed-139">Linux</span><span class="sxs-lookup"><span data-stu-id="064ed-139">Linux</span></span>](#tab/linux)

<span data-ttu-id="064ed-140">Für die Deinstallation von .NET Core (Runtime oder SDK) unter Linux gibt es weitere Optionen.</span><span class="sxs-lookup"><span data-stu-id="064ed-140">There are more options to uninstall .NET Core (either SDK or runtime) on Linux.</span></span> <span data-ttu-id="064ed-141">Die beste Möglichkeit zur Deinstallation von .NET Core besteht in der Spiegelung der für die Installation von .NET Core verwendeten Aktion.</span><span class="sxs-lookup"><span data-stu-id="064ed-141">The best way for you to uninstall .NET Core is to mirror the action you used to install .NET Core.</span></span> <span data-ttu-id="064ed-142">Die Details hängen davon ab, welche Verteilung und Installationsmethode Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="064ed-142">The specifics depend on your chosen distribution and the installation method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="064ed-143">Informationen zur Installation und Deinstallation von .NET Core unter Red Hat finden Sie im [Leitfaden für erste Schritte von Red Hat](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel).</span><span class="sxs-lookup"><span data-stu-id="064ed-143">For Red Hat installations, consult the [Red Hat Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) for information on installing and uninstalling .NET Core.</span></span>

<span data-ttu-id="064ed-144">Ab .NET Core 2.1 muss das .NET Core SDK nicht mehr deinstalliert werden, wenn mithilfe eines Paket-Managers ein Upgrade durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="064ed-144">Starting with .NET Core 2.1, there's no need to uninstall the .NET Core SDK when upgrading it using a package manager.</span></span> <span data-ttu-id="064ed-145">Mit dem Befehl `update` oder `refresh` des Paket-Managers werden die älteren Versionen nach erfolgreicher Installation einer neueren Version automatisch entfernt.</span><span class="sxs-lookup"><span data-stu-id="064ed-145">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span>

<span data-ttu-id="064ed-146">Wenn Sie .NET Core mithilfe eines Paket-Managers installiert haben, können Sie für die Deinstallation des .NET SDK oder der -Runtime denselben Paket-Manager verwenden.</span><span class="sxs-lookup"><span data-stu-id="064ed-146">If you installed .NET Core using a package manager, you use that same package manager to uninstall .NET SDK or runtime.</span></span> <span data-ttu-id="064ed-147">.NET Core-Installationen unterstützen die am häufigsten verwendeten Paket-Manager.</span><span class="sxs-lookup"><span data-stu-id="064ed-147">.NET Core installations support most popular package managers.</span></span> <span data-ttu-id="064ed-148">In der Dokumentation zu dem Paket-Manager Ihrer Verteilung finden Sie die genaue Syntax in Ihrer Umgebung:</span><span class="sxs-lookup"><span data-stu-id="064ed-148">Consult the documentation for your distribution's package manager for the precise syntax on your environment:</span></span>

- <span data-ttu-id="064ed-149">[apt-get(8)](https://linux.die.net/man/8/apt-get) wird von Debian-basierten Systemen, einschließlich Ubuntu, verwendet.</span><span class="sxs-lookup"><span data-stu-id="064ed-149">[apt-get(8)](https://linux.die.net/man/8/apt-get) is used by Debian based systems, including Ubuntu.</span></span>
- <span data-ttu-id="064ed-150">[yum(8)](https://linux.die.net/man/8/yum) wird unter Fedora, CentOS und Oracle Linux verwendet.</span><span class="sxs-lookup"><span data-stu-id="064ed-150">[yum(8)](https://linux.die.net/man/8/yum) is used on Fedora, CentOS, and Oracle Linux.</span></span>
- <span data-ttu-id="064ed-151">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) wird unter openSUSE und SUSE Linux Enterprise System (SLES) verwendet.</span><span class="sxs-lookup"><span data-stu-id="064ed-151">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) is used on openSUSE and SUSE Linux Enterprise System (SLES).</span></span>
- <span data-ttu-id="064ed-152">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) wird unter Fedora verwendet.</span><span class="sxs-lookup"><span data-stu-id="064ed-152">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) is used on Fedora.</span></span>

<span data-ttu-id="064ed-153">In fast allen Fällen lautet der Befehl zum Entfernen eines Pakets `remove`.</span><span class="sxs-lookup"><span data-stu-id="064ed-153">In almost all cases, the command to remove a package is `remove`.</span></span>

<span data-ttu-id="064ed-154">Der Paketname für die .NET Core SDK-Installation lautet bei den meisten Paket-Managern `dotnet-sdk`, gefolgt von der Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="064ed-154">The package name for the .NET Core SDK installation for most package managers is `dotnet-sdk`, followed by the version number.</span></span> <span data-ttu-id="064ed-155">Ab Version 2.1.300 des .NET Core SDK und Version `2.1` der Runtime sind nur die Nummern der Haupt-und Nebenversionen erforderlich: So kann beispielsweise mit dem Paket `dotnet-sdk-2.1` auf Version 2.1.300 des .NET Core SDK verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="064ed-155">Starting with the version 2.1.300 of the .NET Core SDK and version `2.1` of the runtime, only the major and minor version numbers are necessary: for example, the .NET Core SDK version 2.1.300 can be referenced as the package `dotnet-sdk-2.1`.</span></span> <span data-ttu-id="064ed-156">Bei früheren Versionen ist die gesamte Versionszeichenfolge erforderlich: Für Version 2.1.200 des .NET Core SDK wäre z.B. `dotnet-sdk-2.1.200` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="064ed-156">Prior versions require the entire version string: for example, `dotnet-sdk-2.1.200` would be required for version 2.1.200 of the .NET Core SDK.</span></span>

<span data-ttu-id="064ed-157">Bei Computern, auf denen nur die Runtime und nicht das SDK installiert ist, lautet der Paketname für die .NET Core-Runtime `dotnet-runtime-<version>` und für den gesamten Laufzeitstapel `aspnetcore-runtime-<version>`.</span><span class="sxs-lookup"><span data-stu-id="064ed-157">For machines that have installed only the runtime, and not the SDK, the package name is `dotnet-runtime-<version>` for the .NET Core runtime, and `aspnetcore-runtime-<version>` for the entire runtime stack.</span></span>

<span data-ttu-id="064ed-158">Bei .NET Core-Installationen vor Version 2.0 wurde die Hostanwendung nicht deinstalliert, wenn das SDK mit dem Paket-Manager deinstalliert wurde.</span><span class="sxs-lookup"><span data-stu-id="064ed-158">.NET Core installations earlier than 2.0 didn't uninstall the host application when the SDK was uninstalled using the package manager.</span></span> <span data-ttu-id="064ed-159">Bei Verwendung von `apt-get` lautet der Befehl wie folgt:</span><span class="sxs-lookup"><span data-stu-id="064ed-159">Using `apt-get`, the command is:</span></span>

```bash
apt-get remove dotnet-host
```

<span data-ttu-id="064ed-160">Beachten Sie, dass keine Version an `dotnet-host` angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="064ed-160">Note that there's no version attached to `dotnet-host`.</span></span>

<span data-ttu-id="064ed-161">Wenn Sie die Installation mit einem Tarball durchgeführt haben, müssen Sie .NET Core manuell entfernen.</span><span class="sxs-lookup"><span data-stu-id="064ed-161">If you installed using a tarball, you must remove .NET Core using the manual method.</span></span>

<span data-ttu-id="064ed-162">Die SDKs und Runtimes werden separat entfernt, indem das Verzeichnis entfernt wird, das diese Version enthält.</span><span class="sxs-lookup"><span data-stu-id="064ed-162">You remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="064ed-163">Zum Entfernen des SDK und der Runtime von Version 1.0.1 würden Sie beispielsweise die folgenden Bash-Befehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="064ed-163">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="064ed-164">Die übergeordneten Verzeichnisse für das SDK und die Runtime werden in der Ausgabe des Befehls `dotnet --list-sdks` und `dotnet --list-runtimes` aufgeführt, wie in der obigen Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="064ed-164">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

# <a name="macos"></a>[<span data-ttu-id="064ed-165">macOS</span><span class="sxs-lookup"><span data-stu-id="064ed-165">macOS</span></span>](#tab/macos)

<span data-ttu-id="064ed-166">Unter Mac müssen die SDKs und Runtimes separat entfernt werden, indem das Verzeichnis entfernt wird, das diese Version enthält.</span><span class="sxs-lookup"><span data-stu-id="064ed-166">On Mac, you must remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="064ed-167">Zum Entfernen des SDK und der Runtime von Version 1.0.1 würden Sie beispielsweise die folgenden Bash-Befehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="064ed-167">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/local/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="064ed-168">Die übergeordneten Verzeichnisse für das SDK und die Runtime werden in der Ausgabe des Befehls `dotnet --list-sdks` und `dotnet --list-runtimes` aufgeführt, wie in der obigen Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="064ed-168">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

---

## <a name="net-core-uninstall-tool"></a><span data-ttu-id="064ed-169">.NET Core-Deinstallationstool</span><span class="sxs-lookup"><span data-stu-id="064ed-169">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="064ed-170">Mit dem [.NET Core-Deinstallationstool](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) können Sie .NET Core SDKs und .NET Core-Runtimes aus einem System entfernen.</span><span class="sxs-lookup"><span data-stu-id="064ed-170">The [.NET Core Uninstall Tool](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and runtimes from a system.</span></span> <span data-ttu-id="064ed-171">Hierfür stehen Ihnen verschiedene Optionen zur Verfügung, um anzugeben, welche Versionen deinstalliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="064ed-171">A collection of options is available to specify which versions should be uninstalled.</span></span>

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a><span data-ttu-id="064ed-172">Visual Studio-Abhängigkeit von .NET Core SDK Versionen</span><span class="sxs-lookup"><span data-stu-id="064ed-172">Visual Studio dependency on .NET Core SDK versions</span></span>

<span data-ttu-id="064ed-173">Vor Visual Studio 2019 Version 16.3 haben Visual Studio-Installer den eigenständigen .NET Core SDK-Installer aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="064ed-173">Before Visual Studio 2019 version 16.3, Visual Studio installers called the standalone .NET Core SDK installer.</span></span> <span data-ttu-id="064ed-174">Folglich werden die SDK-Versionen im Dialogfeld Windows-Dialogfeld **Software** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="064ed-174">As a result, the SDK versions appear in the Windows **Add/Remove Programs** dialog.</span></span> <span data-ttu-id="064ed-175">Das Entfernen von .Core SDKs, die von Visual Studio mit dem eigenständigen Installer installiert wurden, kann dazu führen, dass Visual Studio nicht mehr funktioniert.</span><span class="sxs-lookup"><span data-stu-id="064ed-175">Removing .NET Core SDKs that were installed by Visual Studio using the standalone installer may break Visual Studio.</span></span> <span data-ttu-id="064ed-176">Wenn in Visual Studio nach der Deinstallation von SDKs Probleme auftreten, führen Sie „Reparieren“ für diese bestimmte Version von Visual Studio aus.</span><span class="sxs-lookup"><span data-stu-id="064ed-176">If Visual Studio has problems after you uninstall SDKs, run Repair on that specific version of Visual Studio.</span></span> <span data-ttu-id="064ed-177">In der folgenden Tabelle werden einige der Visual Studio-Abhängigkeiten von .NET Core SDK-Versionen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="064ed-177">The following table shows some of the Visual Studio dependencies on .NET Core SDK versions:</span></span>

| <span data-ttu-id="064ed-178">Visual Studio-Version</span><span class="sxs-lookup"><span data-stu-id="064ed-178">Visual Studio version</span></span> | <span data-ttu-id="064ed-179">.NET Core SDK-Version</span><span class="sxs-lookup"><span data-stu-id="064ed-179">.NET Core SDK version</span></span> |
| -- | -- |
| <span data-ttu-id="064ed-180">Visual Studio 2019 Version 16.2</span><span class="sxs-lookup"><span data-stu-id="064ed-180">Visual Studio 2019 version 16.2</span></span> | <span data-ttu-id="064ed-181">.NET Core SDK 2.2.4xx, 2.1.8xx</span><span class="sxs-lookup"><span data-stu-id="064ed-181">.NET Core SDK 2.2.4xx, 2.1.8xx</span></span> |
| <span data-ttu-id="064ed-182">Visual Studio 2019 Version 16.1</span><span class="sxs-lookup"><span data-stu-id="064ed-182">Visual Studio 2019 version 16.1</span></span> | <span data-ttu-id="064ed-183">.NET Core SDK 2.2.3xx, 2.1.7xx</span><span class="sxs-lookup"><span data-stu-id="064ed-183">.NET Core SDK 2.2.3xx, 2.1.7xx</span></span> |
| <span data-ttu-id="064ed-184">Visual Studio 2019, Version 16.0</span><span class="sxs-lookup"><span data-stu-id="064ed-184">Visual Studio 2019 version 16.0</span></span> | <span data-ttu-id="064ed-185">.NET Core SDK 2.2.2xx, 2.1.6xx</span><span class="sxs-lookup"><span data-stu-id="064ed-185">.NET Core SDK 2.2.2xx, 2.1.6xx</span></span> |
| <span data-ttu-id="064ed-186">Visual Studio 2017 Version 15.9</span><span class="sxs-lookup"><span data-stu-id="064ed-186">Visual Studio 2017 version 15.9</span></span> | <span data-ttu-id="064ed-187">.NET Core SDK 2.2.1xx, 2.1.5xx</span><span class="sxs-lookup"><span data-stu-id="064ed-187">.NET Core SDK 2.2.1xx, 2.1.5xx</span></span> |
| <span data-ttu-id="064ed-188">Visual Studio 2017 Version 15.8</span><span class="sxs-lookup"><span data-stu-id="064ed-188">Visual Studio 2017 version 15.8</span></span> | <span data-ttu-id="064ed-189">.NET Core SDK 2.1.4xx</span><span class="sxs-lookup"><span data-stu-id="064ed-189">.NET Core SDK 2.1.4xx</span></span> |

<span data-ttu-id="064ed-190">Ab Visual Studio 2019, Version 16.3, verwaltet Visual Studio eine eigene Kopie des .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="064ed-190">Starting with Visual Studio 2019 version 16.3, Visual Studio is in charge of its own copy of the .NET Core SDK.</span></span> <span data-ttu-id="064ed-191">Aus diesem Grund werden diese SDK-Versionen nicht mehr im Dialogfeld **Software** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="064ed-191">For that reason, you no longer see those SDK versions in the **Add/Remove Programs** dialog.</span></span>

## <a name="remove-the-nuget-fallback-folder"></a><span data-ttu-id="064ed-192">Entfernen des NuGet-Fallbackordners</span><span class="sxs-lookup"><span data-stu-id="064ed-192">Remove the NuGet fallback folder</span></span>

<span data-ttu-id="064ed-193">Vor dem .NET Core 3.0 SDK verwendeten die .NET Core SDK-Installer den Ordner *NuGetFallbackFolder-* , um einen Cache mit NuGet-Paketen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="064ed-193">Before .NET Core 3.0 SDK, the .NET Core SDK installers used the *NuGetFallbackFolder* to store a cache of NuGet packages.</span></span> <span data-ttu-id="064ed-194">Dieser Cache wurde bei Vorgängen wie `dotnet restore` oder `dotnet build /t:Restore`verwendet.</span><span class="sxs-lookup"><span data-stu-id="064ed-194">This cache was used during operations such as `dotnet restore` or `dotnet build /t:Restore`.</span></span> <span data-ttu-id="064ed-195">`NuGetFallbackFolder` befindet sich unter Windows unter *C:\Programme\dotnet\sdk* und unter macOS unter */usr/local/share/dotnet/sdk*.</span><span class="sxs-lookup"><span data-stu-id="064ed-195">The `NuGetFallbackFolder` is located at *C:\Program Files\dotnet\sdk* on Windows and at */usr/local/share/dotnet/sdk* on macOS.</span></span>

<span data-ttu-id="064ed-196">Möglicherweise möchten Sie diesen Ordner entfernen, wenn Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="064ed-196">You may want to remove this folder, if:</span></span>

* <span data-ttu-id="064ed-197">Sie entwickeln nur mit dem .NET Core 3.0 SDK oder höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="064ed-197">You're only developing using .NET Core 3.0 SDK or later versions.</span></span>
* <span data-ttu-id="064ed-198">Sie entwickeln mit .NET Core SDK-Versionen vor 3.0, können aber online arbeiten, und Geschwindigkeit ist nicht immer wichtig.</span><span class="sxs-lookup"><span data-stu-id="064ed-198">You're developing using .NET Core SDK versions earlier than 3.0, but you can work online and things can be slower once.</span></span>

<span data-ttu-id="064ed-199">Wenn Sie den NuGet-Fallbackordner entfernen möchten, können Sie ihn löschen, aber hierfür benötigen Sie Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="064ed-199">If you want to remove the NuGet fallback folder, you can delete it, but you'll need admin privileges to do so.</span></span>

<span data-ttu-id="064ed-200">Es wird nicht empfohlen, den Ordner *dotnet* zu löschen.</span><span class="sxs-lookup"><span data-stu-id="064ed-200">It's not recommended to delete the *dotnet* folder.</span></span> <span data-ttu-id="064ed-201">Dadurch würden Sie alle globalen Tools entfernen, die Sie zuvor installiert haben.</span><span class="sxs-lookup"><span data-stu-id="064ed-201">Doing so would remove any global tools you've previously installed.</span></span> <span data-ttu-id="064ed-202">Unter Windows gilt außerdem:</span><span class="sxs-lookup"><span data-stu-id="064ed-202">Also, on Windows:</span></span>

- <span data-ttu-id="064ed-203">Sie verlieren die Funktionalität von Visual Studio 2019 Version 16.3 und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="064ed-203">You'll break Visual Studio 2019 version 16.3 and later versions.</span></span> <span data-ttu-id="064ed-204">Zum Wiederherstellen können Sie **Reparieren** ausführen.</span><span class="sxs-lookup"><span data-stu-id="064ed-204">You can run **Repair** to recover.</span></span>
- <span data-ttu-id="064ed-205">Wenn .NET Core SDK-Einträge im Dialogfeld **Software** angezeigt werden, sind sie verwaist.</span><span class="sxs-lookup"><span data-stu-id="064ed-205">If there are .NET Core SDK entries in the **Add/Remove Programs** dialog, they'll be orphaned.</span></span>
