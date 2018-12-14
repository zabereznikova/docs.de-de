---
title: Entfernen von .NET Core Runtime und SDK
description: In diesem Artikel wird beschrieben, wie Sie feststellen können, welche Versionen von .NET Core Runtime und SDK derzeit installiert sind, und wie Sie sie unter Windows, Mac und Linux entfernen.
ms.date: 07/28/2018
author: billwagner
ms.author: wiwagn
ms.custom: seodec18
ms.openlocfilehash: 6204a28200f1db6350e695a9ab29502c46c25590
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129700"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a><span data-ttu-id="ce826-103">Entfernen von .NET Core-Runtime und SDK</span><span class="sxs-lookup"><span data-stu-id="ce826-103">How to remove the .NET Core Runtime and SDK</span></span>

<span data-ttu-id="ce826-104">Wenn Sie im Laufe der Zeit aktualisierte Versionen der .NET Core-Runtime und des SDK installieren, sollten Sie veraltete .NET Core-Versionen von Ihrem Computer entfernen.</span><span class="sxs-lookup"><span data-stu-id="ce826-104">Over time, as you install updated versions of the .NET Core runtime and SDK, you may want to remove outdated versions of .NET Core from your machine.</span></span> <span data-ttu-id="ce826-105">Durch das Entfernen älterer Runtime-Versionen ändert sich möglicherweise die für die Ausführung der freigegebenen Frameworkanwendungen ausgewählte Runtime. Dies wird im Artikel zu [Auswahl von .NET Core-Versionen](selection.md) ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ce826-105">Removing older versions of the runtime may change the runtime chosen to run shared framework applications, as detailed in the article on [.NET Core version selection](selection.md).</span></span>

## <a name="should-i-remove-a-version"></a><span data-ttu-id="ce826-106">Sollte ich eine Version entfernen?</span><span class="sxs-lookup"><span data-stu-id="ce826-106">Should I remove a version?</span></span>

<span data-ttu-id="ce826-107">Durch das Verhalten bei der [.NET Core-Versionsauswahl](selection.md) und die Laufzeitkompatibilität von .NET Core zwischen Updates können frühere Versionen sicher entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="ce826-107">The [.NET Core version selection](selection.md) behaviors and the runtime compatibility of .NET Core across updates enables safe removal of previous versions.</span></span> <span data-ttu-id="ce826-108">Updates für die .NET Core-Runtime sind innerhalb des „Bereichs“ einer Hauptversion kompatibel, wie z.B. 1.x und 2.x.</span><span class="sxs-lookup"><span data-stu-id="ce826-108">.NET Core runtime updates are compatible within a major version 'band' such as 1.x and 2.x.</span></span> <span data-ttu-id="ce826-109">Darüber hinaus können in neueren Versionen des .NET Core SDK in der Regel Anwendungen erstellt werden, die mit früheren Versionen der Laufzeit kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="ce826-109">Additionally, newer releases of the .NET Core SDK generally maintain the ability to build applications that target previous versions of the runtime in a compatible manner.</span></span>

<span data-ttu-id="ce826-110">Im Allgemeinen benötigen Sie nur das neueste SDK und die neueste Patchversion der Laufzeiten, die für Ihre Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ce826-110">In general, you only need the latest SDK and latest patch version of the runtimes required for your application.</span></span> <span data-ttu-id="ce826-111">Instanzen mit älteren SDK- oder Runtime-Versionen beinhalten die Verwaltung von auf **project.json** basierenden Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ce826-111">Instances where retaining older SDK or Runtime versions include maintaining **project.json**-based applications.</span></span> <span data-ttu-id="ce826-112">Sie können ältere Versionen sicher entfernen, wenn Ihre Anwendung keine bestimmten Gründe für frühere SDKs oder Laufzeiten aufweist.</span><span class="sxs-lookup"><span data-stu-id="ce826-112">Unless your application has specific reasons for earlier SDKs or runtimes, you may safely remove older versions.</span></span>

## <a name="determine-what-is-installed"></a><span data-ttu-id="ce826-113">Feststellen, was installiert ist</span><span class="sxs-lookup"><span data-stu-id="ce826-113">Determine what is installed</span></span>

<span data-ttu-id="ce826-114">Ab .NET Core 2.1 verfügt die .NET-CLI über Optionen, mit denen Sie die auf Ihrem Computer installierten Versionen des SDK und der Runtime auflisten können.</span><span class="sxs-lookup"><span data-stu-id="ce826-114">Starting with .NET Core 2.1, the .NET CLI has options you can use to list the versions of the SDK and runtime that are installed on your machine.</span></span>  <span data-ttu-id="ce826-115">Verwenden Sie [`dotnet --list-sdks`](../tools/dotnet.md#options) zum Anzeigen der Liste der auf Ihrem Computer installierten SDKs.</span><span class="sxs-lookup"><span data-stu-id="ce826-115">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) to see the list of SDKs installed on your machine.</span></span> <span data-ttu-id="ce826-116">Verwenden Sie [`dotnet --list-runtimes`](../tools/dotnet.md#options) zum Anzeigen der Liste der auf Ihrem Computer installierten Runtimes.</span><span class="sxs-lookup"><span data-stu-id="ce826-116">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) to see the list of runtimes installed on your machine.</span></span> <span data-ttu-id="ce826-117">Der folgende Text zeigt eine typische Ausgabe für Windows, macOS oder Linux:</span><span class="sxs-lookup"><span data-stu-id="ce826-117">The following text shows typical output for Windows, macOS, or Linux:</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="ce826-118">Windows</span><span class="sxs-lookup"><span data-stu-id="ce826-118">Windows</span></span>](#tab/windows)

```console
C:\> dotnet --list-sdks
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

C:\> dotnet --list-runtimes
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

# <a name="linuxtablinux"></a>[<span data-ttu-id="ce826-119">Linux</span><span class="sxs-lookup"><span data-stu-id="ce826-119">Linux</span></span>](#tab/linux)

```console
$ dotnet --list-sdks
1.0.1 [/usr/share/dotnet/sdk]
1.0.4 [/usr/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/share/dotnet/sdk]
2.0.0 [/usr/share/dotnet/sdk]
2.1.4 [/usr/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/share/dotnet/sdk]
2.1.300 [/usr/share/dotnet/sdk]
2.1.301 [/usr/share/dotnet/sdk]

$ dotnet --list-runtimes
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

# <a name="macostabmacos"></a>[<span data-ttu-id="ce826-120">macOS</span><span class="sxs-lookup"><span data-stu-id="ce826-120">macOS</span></span>](#tab/macos)

```console
$ dotnet --list-sdks
1.0.1 [/usr/local/share/dotnet/sdk]
1.0.4 [/usr/local/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/local/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/local/share/dotnet/sdk]
2.0.0 [/usr/local/share/dotnet/sdk]
2.1.4 [/usr/local/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/local/share/dotnet/sdk]
2.1.300 [/usr/local/share/dotnet/sdk]
2.1.301 [/usr/local/share/dotnet/sdk]

$ dotnet --list-runtimes
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

***

## <a name="uninstalling-net-core"></a><span data-ttu-id="ce826-121">Deinstallieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="ce826-121">Uninstalling .NET Core</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="ce826-122">Windows</span><span class="sxs-lookup"><span data-stu-id="ce826-122">Windows</span></span>](#tab/windows)

<span data-ttu-id="ce826-123">.NET Core entfernt über das Windows-Dialogfeld **Programme hinzufügen/entfernen** Versionen der .NET Core-Runtime und des SDK.</span><span class="sxs-lookup"><span data-stu-id="ce826-123">.NET Core uses the Windows **Add/Remove Programs** dialog to remove versions of the .NET Core runtime and SDK.</span></span> <span data-ttu-id="ce826-124">Die folgende Abbildung zeigt das Dialogfeld **Programme hinzufügen/entfernen** mit mehreren installierten Versionen der .NET-Runtime und des SDK.</span><span class="sxs-lookup"><span data-stu-id="ce826-124">The following figure shows the **Add/Remove Programs** dialog with several versions of the .NET runtime and SDK installed.</span></span>

![Hinzufügen/Entfernen von Programmen zum Entfernen von .NET Core](./media/remove-runtime-sdk-versions/programs-and-features.png)

<span data-ttu-id="ce826-126">Wählen Sie sämtliche Versionen aus, die Sie von Ihrem Computer entfernen möchten, und klicken Sie auf **Deinstallieren**.</span><span class="sxs-lookup"><span data-stu-id="ce826-126">Select any versions you want to remove from your machine and click **Uninstall**.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="ce826-127">Linux</span><span class="sxs-lookup"><span data-stu-id="ce826-127">Linux</span></span>](#tab/linux)

<span data-ttu-id="ce826-128">Für die Deinstallation von .NET Core (Runtime oder SDK) unter Linux gibt es weitere Optionen.</span><span class="sxs-lookup"><span data-stu-id="ce826-128">There are more options to uninstall .NET Core (either SDK or runtime) on Linux.</span></span> <span data-ttu-id="ce826-129">Die beste Möglichkeit zur Deinstallation von .NET Core besteht in der Spiegelung der für die Installation von .NET Core verwendeten Aktion.</span><span class="sxs-lookup"><span data-stu-id="ce826-129">The best way for you to uninstall .NET Core is to mirror the action you used to install .NET Core.</span></span> <span data-ttu-id="ce826-130">Die Details hängen davon ab, welche Verteilung und Installationsmethode Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="ce826-130">The specifics depend on your chosen distribution and the installation method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce826-131">Informationen zur Installation und Deinstallation von .NET Core unter Red Hat finden Sie im [Leitfaden für erste Schritte von Red Hat](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel).</span><span class="sxs-lookup"><span data-stu-id="ce826-131">For Red Hat installations, consult the [Red Hat Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) for information on installing and uninstalling .NET Core.</span></span>

<span data-ttu-id="ce826-132">Ab .NET Core 2.1 muss das .NET Core SDK nicht mehr deinstalliert werden, wenn mithilfe eines Paket-Managers ein Upgrade durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ce826-132">Starting with .NET Core 2.1, there is no need to uninstall the .NET Core SDK when upgrading it using a package manager.</span></span> <span data-ttu-id="ce826-133">Mit dem Befehl `update` oder `refresh` des Paket-Managers werden die älteren Versionen nach erfolgreicher Installation einer neueren Version automatisch entfernt.</span><span class="sxs-lookup"><span data-stu-id="ce826-133">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span>

<span data-ttu-id="ce826-134">Wenn Sie .NET Core mithilfe eines Paket-Managers installiert haben, können Sie für die Deinstallation des .NET SDK oder der -Runtime denselben Paket-Manager verwenden.</span><span class="sxs-lookup"><span data-stu-id="ce826-134">If you installed .NET Core using a package manager, you use that same package manager to uninstall .NET SDK or runtime.</span></span> <span data-ttu-id="ce826-135">.NET Core-Installationen unterstützen die am häufigsten verwendeten Paket-Manager.</span><span class="sxs-lookup"><span data-stu-id="ce826-135">.NET Core installations support most popular package managers.</span></span> <span data-ttu-id="ce826-136">In der Dokumentation zu dem Paket-Manager Ihrer Verteilung finden Sie die genaue Syntax in Ihrer Umgebung:</span><span class="sxs-lookup"><span data-stu-id="ce826-136">Consult the documentation for your distribution's package manager for the precise syntax on your environment:</span></span>

- <span data-ttu-id="ce826-137">[apt-get(8)](https://linux.die.net/man/8/apt-get) wird von Debian-basierten Systemen, einschließlich Ubuntu, verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce826-137">[apt-get(8)](https://linux.die.net/man/8/apt-get) is used by Debian based systems, including Ubuntu.</span></span>
- <span data-ttu-id="ce826-138">[yum(8)](https://linux.die.net/man/8/yum) wird unter Fedora, CentOS und Oracle Linux verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce826-138">[yum(8)](https://linux.die.net/man/8/yum) is used on Fedora, CentOS, and Oracle Linux.</span></span>
- <span data-ttu-id="ce826-139">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) wird unter openSUSE und SUSE Linux Enterprise System (SLES) verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce826-139">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) is used on openSUSE and SUSE Linux Enterprise System (SLES).</span></span>
- <span data-ttu-id="ce826-140">[dnf(8)](https://dnf.readthedocs.io/latest/command_ref.html) wird unter Fedora verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce826-140">[dnf(8)](https://dnf.readthedocs.io/latest/command_ref.html) is used on Fedora.</span></span>

<span data-ttu-id="ce826-141">In fast allen Fällen lautet der Befehl zum Entfernen eines Pakets `remove`.</span><span class="sxs-lookup"><span data-stu-id="ce826-141">In almost all cases, the command to remove a package is `remove`.</span></span>

<span data-ttu-id="ce826-142">Der Paketname für die .NET Core SDK-Installation lautet bei den meisten Paket-Managern `dotnet-sdk`, gefolgt von der Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="ce826-142">The package name for the .NET Core SDK installation for most package managers is `dotnet-sdk`, followed by the version number.</span></span> <span data-ttu-id="ce826-143">Ab Version 2.1.300 des .NET Core SDK und Version `2.1` der Runtime sind nur die Nummern der Haupt-und Nebenversionen erforderlich: So kann beispielsweise mit dem Paket `dotnet-sdk-2.1` auf Version 2.1.300 des .NET Core SDK verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ce826-143">Starting with the version 2.1.300 of the .NET Core SDK and version `2.1` of the runtime, only the major and minor version numbers are necessary: for example, the .NET Core SDK version 2.1.300 can be referenced as the package `dotnet-sdk-2.1`.</span></span> <span data-ttu-id="ce826-144">Bei früheren Versionen ist die gesamte Versionszeichenfolge erforderlich: Für Version 2.1.200 des .NET Core SDK wäre z.B. `dotnet-sdk-2.1.200` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce826-144">Prior versions require the entire version string: for example, `dotnet-sdk-2.1.200` would be required for version 2.1.200 of the .NET Core SDK.</span></span>

<span data-ttu-id="ce826-145">Bei Computern, auf denen nur die Runtime und nicht das SDK installiert ist, lautet der Paketname für die .NET Core-Runtime `dotnet-runtime-<version>` und für den gesamten Laufzeitstapel `aspnetcore-runtime-<version>`.</span><span class="sxs-lookup"><span data-stu-id="ce826-145">For machines that have installed only the runtime, and not the SDK, the package name is `dotnet-runtime-<version>` for the .NET Core runtime, and `aspnetcore-runtime-<version>` for the entire runtime stack.</span></span>

<span data-ttu-id="ce826-146">Bei .NET Core-Installationen vor Version 2.0 wurde die Hostanwendung nicht deinstalliert, wenn das SDK mit dem Paket-Manager deinstalliert wurde.</span><span class="sxs-lookup"><span data-stu-id="ce826-146">.NET Core installations prior to 2.0 did not uninstall the host application when the SDK was uninstalled using the package manager.</span></span> <span data-ttu-id="ce826-147">Bei Verwendung von `apt-get` lautet der Befehl wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ce826-147">Using `apt-get`, the command is:</span></span>

```bash
apt-get remove dotnet-host
```

<span data-ttu-id="ce826-148">Beachten Sie, dass keine Version an `dotnet-host` angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="ce826-148">Note that there is no version attached to `dotnet-host`.</span></span>

<span data-ttu-id="ce826-149">Wenn Sie die Installation mit einem Tarball durchgeführt haben, müssen Sie .NET Core manuell entfernen.</span><span class="sxs-lookup"><span data-stu-id="ce826-149">If you installed using a tarball, you must remove .NET Core using the manual method.</span></span>

<span data-ttu-id="ce826-150">Die SDKs und Runtimes werden separat entfernt, indem das Verzeichnis entfernt wird, das diese Version enthält.</span><span class="sxs-lookup"><span data-stu-id="ce826-150">You remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="ce826-151">Zum Entfernen des SDK und der Runtime von Version 1.0.1 würden Sie beispielsweise die folgenden Bash-Befehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="ce826-151">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="ce826-152">Die übergeordneten Verzeichnisse für das SDK und die Runtime werden in der Ausgabe des Befehls `dotnet --list-sdks` und `dotnet --list-runtimes` aufgeführt, wie in der obigen Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ce826-152">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="ce826-153">macOS</span><span class="sxs-lookup"><span data-stu-id="ce826-153">macOS</span></span>](#tab/macos)

<span data-ttu-id="ce826-154">Unter Mac müssen die SDKs und Runtimes separat entfernt werden, indem das Verzeichnis entfernt wird, das diese Version enthält.</span><span class="sxs-lookup"><span data-stu-id="ce826-154">On Mac, you must remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="ce826-155">Zum Entfernen des SDK und der Runtime von Version 1.0.1 würden Sie beispielsweise die folgenden Bash-Befehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="ce826-155">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/local/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="ce826-156">Die übergeordneten Verzeichnisse für das SDK und die Runtime werden in der Ausgabe des Befehls `dotnet --list-sdks` und `dotnet --list-runtimes` aufgeführt, wie in der obigen Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ce826-156">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

---
