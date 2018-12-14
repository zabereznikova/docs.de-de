---
title: 'global.json: Übersicht'
description: In diesem Artikel erfahren Sie, wie Sie mit der global.json-Datei die .NET Core SDK-Version beim Ausführen eines .NET Core-CLI-Befehls festgelegen.
author: mairaw
ms.author: mairaw
ms.date: 12/03/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 7cb118c16460ed593d210f5e816b2a6fd5af2ee3
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150852"
---
# <a name="globaljson-overview"></a><span data-ttu-id="e2e03-103">global.json: Übersicht</span><span class="sxs-lookup"><span data-stu-id="e2e03-103">global.json overview</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

<span data-ttu-id="e2e03-104">Mit der *global.json*-Datei können Sie definieren, welche .NET Core SDK-Version verwendet wird, wenn Sie .NET Core-CLI-Befehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="e2e03-104">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="e2e03-105">Die Auswahl der .NET Core SDK ist unabhängig von der Angabe der Laufzeit Ihrer Projektziele.</span><span class="sxs-lookup"><span data-stu-id="e2e03-105">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="e2e03-106">Die .NET Core SDK-Version gibt an, welche Versionen der .NET Core-CLI-Tools verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2e03-106">The .NET Core SDK version indicates which versions of the .NET Core CLI tools are used.</span></span> <span data-ttu-id="e2e03-107">Wenn Sie die neueste Version der Tools verwenden möchten, wird in der Regel keine *global.json*-Datei benötigt.</span><span class="sxs-lookup"><span data-stu-id="e2e03-107">In general, you want to use the latest version of the tools, so no *global.json* file is needed.</span></span>

<span data-ttu-id="e2e03-108">Weitere Informationen zum Angeben der Laufzeit finden Sie unter [Zielframeworks](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e2e03-108">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="e2e03-109">.NET Core SDK sucht im aktuellen Arbeitsverzeichnis (das nicht dem Projektverzeichnis entsprechen muss) oder in einem übergeordneten Verzeichnis nach einer *global.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="e2e03-109">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="e2e03-110">global.json-Schema</span><span class="sxs-lookup"><span data-stu-id="e2e03-110">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="e2e03-111">SDK</span><span class="sxs-lookup"><span data-stu-id="e2e03-111">sdk</span></span>

<span data-ttu-id="e2e03-112">Typ: Objekt</span><span class="sxs-lookup"><span data-stu-id="e2e03-112">Type: Object</span></span>

<span data-ttu-id="e2e03-113">Gibt Informationen zum auszuwählenden .NET Core SDK an.</span><span class="sxs-lookup"><span data-stu-id="e2e03-113">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="e2e03-114">Version</span><span class="sxs-lookup"><span data-stu-id="e2e03-114">version</span></span>

<span data-ttu-id="e2e03-115">Typ: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e2e03-115">Type: String</span></span>

<span data-ttu-id="e2e03-116">Die Version des zu verwendenden .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="e2e03-116">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="e2e03-117">Beachten Sie, dass dieses Feld:</span><span class="sxs-lookup"><span data-stu-id="e2e03-117">Note that this field:</span></span>

- <span data-ttu-id="e2e03-118">Keine Platzhalter unterstützt, d. h. die vollständige Versionsnummer muss angegeben werden</span><span class="sxs-lookup"><span data-stu-id="e2e03-118">Doesn't have globbing support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="e2e03-119">Keine Versionsbereiche unterstützt</span><span class="sxs-lookup"><span data-stu-id="e2e03-119">Doesn't support version ranges.</span></span>

<span data-ttu-id="e2e03-120">Das folgende Beispiel zeigt den Inhalt einer *global.json*-Datei an.</span><span class="sxs-lookup"><span data-stu-id="e2e03-120">The following example shows the contents of a *global.json* file:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="e2e03-121">global.json und die .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="e2e03-121">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="e2e03-122">Es ist nützlich zu wissen, welche Versionen verfügbar sind, um in der *global.json*-Datei eine Version festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e2e03-122">It's helpful to know which versions are available in order to set one in the *global.json* file.</span></span> <span data-ttu-id="e2e03-123">Eine vollständige Liste der unterstützten und verfügbaren SDKs finden Sie auf der Website mit den [.NET-Downloads](https://www.microsoft.com/net/download/all).</span><span class="sxs-lookup"><span data-stu-id="e2e03-123">You can find the full list of supported available SDKs at the [.NET Downloads](https://www.microsoft.com/net/download/all) site.</span></span> <span data-ttu-id="e2e03-124">Ab .NET Core 2.1 SDK können Sie den folgenden Befehl ausführen, um zu überprüfen, welche SDK-Versionen bereits auf Ihrem Computer installiert sind:</span><span class="sxs-lookup"><span data-stu-id="e2e03-124">Starting with .NET Core 2.1 SDK, you can run the following command to verify which SDK versions are already installed on your machine:</span></span>

```console
dotnet --list-sdks
```

<span data-ttu-id="e2e03-125">Um auf Ihrem Computer zusätzliche .NET Core SDK-Versionen zu installieren, besuchen Sie die Website mit den [.NET-Downloads](https://www.microsoft.com/net/download/all).</span><span class="sxs-lookup"><span data-stu-id="e2e03-125">To install additional .NET Core SDK versions on your machine, visit the [.NET Downloads](https://www.microsoft.com/net/download/all) site.</span></span>

<span data-ttu-id="e2e03-126">Sie können im aktuellen Verzeichnis eine neue *global.json*-Datei erstellen, indem Sie den Befehl [dotnet new](dotnet-new.md) ausführen, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e2e03-126">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```console
dotnet new globaljson --sdk-version 2.2.100
```

## <a name="matching-rules"></a><span data-ttu-id="e2e03-127">Abgleichsregeln</span><span class="sxs-lookup"><span data-stu-id="e2e03-127">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="e2e03-128">Die Abgleichsregeln werden vom App-Host bestimmt, der der .NET Core-Laufzeit unterliegt.</span><span class="sxs-lookup"><span data-stu-id="e2e03-128">The matching rules are governed by the apphost, which is part of the .NET Core runtime.</span></span>
> <span data-ttu-id="e2e03-129">Wenn Sie mehrere Laufzeiten nebeneinander installiert haben, wird die neueste Version des Hosts verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2e03-129">The latest version of the host is used when you have multiple runtimes installed side-by-side.</span></span>

<span data-ttu-id="e2e03-130">Ab .NET Core 2.0 legen die folgenden Regeln fest, welche SDK-Version verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="e2e03-130">Starting with .NET Core 2.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="e2e03-131">Wenn keine *global.json*-Datei gefunden wird oder *global.json* keine SDK-Version angibt, wird die neueste installierte SDK-Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2e03-131">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="e2e03-132">Die neueste SDK-Version kann ein Release oder eine Vorabversion sein, es gilt die höchste Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="e2e03-132">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>
- <span data-ttu-id="e2e03-133">Wenn *global.json* eine SDK-Version angibt:</span><span class="sxs-lookup"><span data-stu-id="e2e03-133">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="e2e03-134">Wenn die angegebene SDK-Version auf dem Computer gefunden wird, wird genaue diese Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2e03-134">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="e2e03-135">Wenn die angegebene SDK-Version auf dem Computer nicht gefunden wird, wird die neueste installierte SDK-**Patchversion** der Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2e03-135">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="e2e03-136">Die neueste installierte SDK-**Patchversion** kann ein Release oder eine Vorabversion sein, es gilt die höchste Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="e2e03-136">Latest installed SDK **patch version** can be either release or pre-release - the highest version number wins.</span></span> <span data-ttu-id="e2e03-137">In .NET Core 2.1 und höher werden die **Patchversionen**, die niedriger als die angegebene **Patchversion** sind, bei der SDK-Auswahl ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e2e03-137">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="e2e03-138">Wenn die angegebene SDK-Version und eine entsprechende SDK-**Patchversion** nicht gefunden werden, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e2e03-138">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="e2e03-139">Die SDK-Version hat zurzeit folgende Bestandteile:</span><span class="sxs-lookup"><span data-stu-id="e2e03-139">The SDK version is currently composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="e2e03-140">Die **Funktionsfreigabe** von .NET Core SDK wird für SDK-Versionen ab 2.1.100 von der ersten Ziffer (`x`) im letzten Teil der Nummer (`xyz`) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e2e03-140">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="e2e03-141">Generell hat .NET Core SDK einen schnelleren Releasezyklus als .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2e03-141">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="e2e03-142">Die **Patchversion** wird für SDK-Versionen ab 2.1.100 von den letzten beiden Ziffern (`yz`) im letzten Teil der Nummer (`xyz`) definiert.</span><span class="sxs-lookup"><span data-stu-id="e2e03-142">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="e2e03-143">Wenn Sie beispielsweise `2.1.300` als SDK-Version angeben, werden für die SDK-Auswahl Versionen bis `2.1.399` berücksichtigt, allerdings wird `2.1.400` nicht als Patchversion von `2.1.300` betrachtet.</span><span class="sxs-lookup"><span data-stu-id="e2e03-143">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="e2e03-144">.NET Core SDK-Versionen `2.1.100` bis `2.1.201` wurden beim Übergang zwischen Versionsnummerschemen freigegeben und halten die `xyz`-Notation nicht ordnungsgemäß ein.</span><span class="sxs-lookup"><span data-stu-id="e2e03-144">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="e2e03-145">Falls Sie diese Versionen in der *global.json*-Datei angeben, wird dringend empfohlen sicherzustellen, dass sich die angegebenen Versionen auf den Zielcomputern befinden.</span><span class="sxs-lookup"><span data-stu-id="e2e03-145">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

<span data-ttu-id="e2e03-146">Mit .NET Core SDK 1.x wurde die neueste installierte SDK-Version verwendet, wenn Sie eine Version angegeben haben und keine genaue Übereinstimmung gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="e2e03-146">With .NET Core SDK 1.x, if you specified a version and no exact match was found, the latest installed SDK version was used.</span></span> <span data-ttu-id="e2e03-147">Die neueste SDK-Version kann ein Release oder eine Vorabversion sein, es gilt die höchste Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="e2e03-147">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>

## <a name="troubleshooting-build-warnings"></a><span data-ttu-id="e2e03-148">Problembehandlung bei Buildwarnungen</span><span class="sxs-lookup"><span data-stu-id="e2e03-148">Troubleshooting build warnings</span></span>

> [!WARNING]
> <span data-ttu-id="e2e03-149">Sie verwenden eine Vorschauversion von .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="e2e03-149">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="e2e03-150">Sie können die SDK-Version über eine global.json-Datei im aktuellen Projekt definieren.</span><span class="sxs-lookup"><span data-stu-id="e2e03-150">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="e2e03-151">Weitere Informationen finden Sie unter <https://go.microsoft.com/fwlink/?linkid=869452>.</span><span class="sxs-lookup"><span data-stu-id="e2e03-151">More at <https://go.microsoft.com/fwlink/?linkid=869452></span></span>

<span data-ttu-id="e2e03-152">Diese Warnung weist darauf hin, dass das Projekt mit einer .NET Core SDK-Vorschauversion kompiliert wird, wie im Abschnitt [Abgleichsregeln](#matching-rules) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e2e03-152">This warning indicates that your project is being compiled using a preview version of the .NET Core SDK, as explained in the [Matching rules](#matching-rules) section.</span></span> <span data-ttu-id="e2e03-153">.NET Core SDK-Versionen haben einen Verlauf und weisen eine hohe Qualität auf.</span><span class="sxs-lookup"><span data-stu-id="e2e03-153">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="e2e03-154">Wenn Sie jedoch keine Vorschauversion verwenden möchten, fügen Sie Ihrer Projekthierarchiestruktur eine *global.json*-Datei hinzu, um die zu verwendende SDK-Version anzugeben, und bestätigen Sie mithilfe von `dotnet --list-sdks`, dass die Version auf Ihrem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e2e03-154">However, if you don't want to use a preview version, add a *global.json* file to your project hierarchy structure to specify which SDK version to use, and use `dotnet --list-sdks` to confirm that the version is installed on your machine.</span></span> <span data-ttu-id="e2e03-155">Wenn eine neue Version verfügbar ist, entfernen Sie entweder die *global.json*-Datei oder aktualisieren Sie sie, um die neuere Version zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2e03-155">When a new version is released, to use the new version, either remove the *global.json* file or update it to use the newer version.</span></span>

> [!WARNING]
> <span data-ttu-id="e2e03-156">Das Startprojekt „{startupProject}“ gibt Version „{targetFrameworkVersion}“ von Framework „.NETCoreApp“ als Ziel an.</span><span class="sxs-lookup"><span data-stu-id="e2e03-156">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="e2e03-157">Diese Version der Entity Framework Core .NET-Befehlszeilentools unterstützt nur Version 2.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="e2e03-157">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="e2e03-158">Weitere Informationen zur Verwendung älterer Toolversionen finden Sie unter <https://go.microsoft.com/fwlink/?linkid=871254>.</span><span class="sxs-lookup"><span data-stu-id="e2e03-158">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254></span></span>

<span data-ttu-id="e2e03-159">Ab .NET Core 2.1 SDK (Version 2.1.300) ist der Befehl `dotnet ef` im SDK enthalten.</span><span class="sxs-lookup"><span data-stu-id="e2e03-159">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="e2e03-160">Diese Warnung weist darauf hin, dass das Projekt EF Core 1.0 oder 1.1 als Ziel angibt, das nicht mit .NET Core 2.1 SDK oder höher kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="e2e03-160">This warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions.</span></span> <span data-ttu-id="e2e03-161">Um Ihr Projekt zu kompilieren, installieren Sie das .NET Core 2.0 SDK (Version 2.1.201) und früher auf Ihrem Computer, und legen Sie mithilfe der Datei *global.json* die gewünschte SDK-Version fest.</span><span class="sxs-lookup"><span data-stu-id="e2e03-161">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) and earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="e2e03-162">Weitere Informationen zu dem Befehl `dotnet ef` finden Sie unter [EF Core .NET-Befehlszeilentools](/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="e2e03-162">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="e2e03-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2e03-163">See also</span></span>

- [<span data-ttu-id="e2e03-164">Wie Projekt-SDKs gelöst werden</span><span class="sxs-lookup"><span data-stu-id="e2e03-164">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)