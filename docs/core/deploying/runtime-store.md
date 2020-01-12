---
title: Laufzeitpaketspeicher
description: Erfahren Sie, wie Sie den Laufzeitpaketspeicher für Manifeste nutzen, die von .NET Core verwendet werden.
author: bleroy
ms.date: 08/12/2017
ms.openlocfilehash: aa0fd3a0895bc79ddb80aeb599d3e3820b3be6db
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714458"
---
# <a name="runtime-package-store"></a><span data-ttu-id="77da9-103">Laufzeitpaketspeicher</span><span class="sxs-lookup"><span data-stu-id="77da9-103">Runtime package store</span></span>

<span data-ttu-id="77da9-104">Ab .NET Core 2.0 ist es möglich, Apps mit einer bekannten Reihe von Paketen, die in der Zielumgebung vorhanden sind, zu verpacken und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="77da9-104">Starting with .NET Core 2.0, it's possible to package and deploy apps against a known set of packages that exist in the target environment.</span></span> <span data-ttu-id="77da9-105">Die Vorteile sind eine schnellere Bereitstellung, ein geringerer Speicherplatzverbrauch auf dem Datenträger und in manchen Fällen eine verbesserte Startleistung.</span><span class="sxs-lookup"><span data-stu-id="77da9-105">The benefits are faster deployments, lower disk space usage, and improved startup performance in some cases.</span></span>

<span data-ttu-id="77da9-106">Dieses Feature wird als *Laufzeitpaketspeicher* implementiert. Dabei handelt es sich um ein Verzeichnis auf der Festplatte, in dem Pakete gespeichert werden (normalerweise unter */usr/local/share/dotnet/store* unter macOS/Linux und *C:/Programme/dotnet/store* unter Windows).</span><span class="sxs-lookup"><span data-stu-id="77da9-106">This feature is implemented as a *runtime package store*, which is a directory on disk where packages are stored (typically at */usr/local/share/dotnet/store* on macOS/Linux and *C:/Program Files/dotnet/store* on Windows).</span></span> <span data-ttu-id="77da9-107">In diesem Verzeichnis gibt es Unterverzeichnisse für Architekturen und [target frameworks (Zielframeworks)](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="77da9-107">Under this directory, there are subdirectories for architectures and [target frameworks](../../standard/frameworks.md).</span></span> <span data-ttu-id="77da9-108">Das Dateilayout ist ähnlich wie [NuGet assets are laid out on disk (die Anordnung von NuGet-Objekten auf der Festplatte)](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span><span class="sxs-lookup"><span data-stu-id="77da9-108">The file layout is similar to the way that [NuGet assets are laid out on disk](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span></span>

```
\dotnet
    \store
        \x64
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
        \x86
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
```

<span data-ttu-id="77da9-109">Die Pakete im Laufzeitpaketspeicher werden in einer *Zielmanifestdatei* aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="77da9-109">A *target manifest* file lists the packages in the runtime package store.</span></span> <span data-ttu-id="77da9-110">Entwickler können auf dieses Manifest abzielen, wenn sie ihre App veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="77da9-110">Developers can target this manifest when publishing their app.</span></span> <span data-ttu-id="77da9-111">Das Zielmanifest wird normalerweise vom Besitzer der als Ziel festgelegten Produktionsumgebung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="77da9-111">The target manifest is typically provided by the owner of the targeted production environment.</span></span>

## <a name="preparing-a-runtime-environment"></a><span data-ttu-id="77da9-112">Vorbereiten einer Laufzeitumgebung</span><span class="sxs-lookup"><span data-stu-id="77da9-112">Preparing a runtime environment</span></span>

<span data-ttu-id="77da9-113">Der Administrator einer Laufzeitumgebung kann Apps für eine schnellere Bereitstellung und einen geringeren Speicherplatzverbrauch auf der Festplatte optimieren, indem er einen Laufzeitpaketspeicher und ein entsprechendes Zielmanifest erstellt.</span><span class="sxs-lookup"><span data-stu-id="77da9-113">The administrator of a runtime environment can optimize apps for faster deployments and lower disk space use by building a runtime package store and the corresponding target manifest.</span></span>

<span data-ttu-id="77da9-114">Zuerst muss ein *Paketspeichermanifest* erstellt werden, das die Pakete auflistet, aus denen sich der Laufzeitpaketspeicher zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="77da9-114">The first step is to create a *package store manifest* that lists the packages that compose the runtime package store.</span></span> <span data-ttu-id="77da9-115">Dieses Dateiformat ist kompatibel mit dem Projektdateiformat (*csproj*).</span><span class="sxs-lookup"><span data-stu-id="77da9-115">This file format is compatible with the project file format (*csproj*).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="<NUGET_PACKAGE>" Version="<VERSION>" />
    <!-- Include additional packages here -->
  </ItemGroup>
</Project>
```

<span data-ttu-id="77da9-116">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="77da9-116">**Example**</span></span>

<span data-ttu-id="77da9-117">Das im folgenden Beispiel dargestellte Paketspeichermanifest (*packages.csproj*) wird verwendet, um [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) und [`Moq`](https://www.nuget.org/packages/moq/) zu einem Laufzeitpaketspeicher hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="77da9-117">The following example package store manifest (*packages.csproj*) is used to add [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) and [`Moq`](https://www.nuget.org/packages/moq/) to a runtime package store:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.3" />
    <PackageReference Include="Moq" Version="4.7.63" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="77da9-118">Bereitstellen des Laufzeitpaketspeichers durch Ausführen von `dotnet store` mit dem Paketspeichermanifest, der Laufzeit und dem Framework:</span><span class="sxs-lookup"><span data-stu-id="77da9-118">Provision the runtime package store by executing `dotnet store` with the package store manifest, runtime, and framework:</span></span>

```dotnetcli
dotnet store --manifest <PATH_TO_MANIFEST_FILE> --runtime <RUNTIME_IDENTIFIER> --framework <FRAMEWORK>
```

<span data-ttu-id="77da9-119">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="77da9-119">**Example**</span></span>

```dotnetcli
dotnet store --manifest packages.csproj --runtime win10-x64 --framework netcoreapp2.0 --framework-version 2.0.0
```

<span data-ttu-id="77da9-120">Sie können mehrere Zielpfade von Paketspeichermanifesten an einen einzigen [`dotnet store`](../tools/dotnet-store.md)-Befehl übergeben, indem Sie die Option und den Pfad im Befehl wiederholen.</span><span class="sxs-lookup"><span data-stu-id="77da9-120">You can pass multiple target package store manifest paths to a single [`dotnet store`](../tools/dotnet-store.md) command by repeating the option and path in the command.</span></span>

<span data-ttu-id="77da9-121">Standardmäßig ist die Ausgabe des Befehls ein Paketspeicher, der sich im Unterverzeichnis *.dotnet/store* des Benutzerprofils befindet.</span><span class="sxs-lookup"><span data-stu-id="77da9-121">By default, the output of the command is a package store under the *.dotnet/store* subdirectory of the user's profile.</span></span> <span data-ttu-id="77da9-122">Sie können einen anderen Speicherort angeben, indem Sie die Option `--output <OUTPUT_DIRECTORY>` verwenden.</span><span class="sxs-lookup"><span data-stu-id="77da9-122">You can specify a different location using the `--output <OUTPUT_DIRECTORY>` option.</span></span> <span data-ttu-id="77da9-123">Das Stammverzeichnis des Speichers enthält die Zielmanifestdatei *artifact.xml*.</span><span class="sxs-lookup"><span data-stu-id="77da9-123">The root directory of the store contains a target manifest *artifact.xml* file.</span></span> <span data-ttu-id="77da9-124">Diese Datei kann zum Download zur Verfügung gestellt und von App-Autoren verwendet werden, die diesen Speicher bei der Veröffentlichung anzielen möchten.</span><span class="sxs-lookup"><span data-stu-id="77da9-124">This file can be made available for download and be used by app authors who want to target this store when publishing.</span></span>

<span data-ttu-id="77da9-125">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="77da9-125">**Example**</span></span>

<span data-ttu-id="77da9-126">Die Datei *artifact.xml* wird erzeugt, nachdem das vorherige Beispiel ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="77da9-126">The following *artifact.xml* file is produced after running the previous example.</span></span> <span data-ttu-id="77da9-127">Beachten Sie, dass es sich bei [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) um eine Abhängigkeit von `Moq` handelt, sodass dieses automatisch integriert und in der Manifestdatei *artifact.xml* angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="77da9-127">Note that [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) is a dependency of `Moq`, so it's included automatically and appears in the *artifacts.xml* manifest file.</span></span>

```xml
<StoreArtifacts>
  <Package Id="Newtonsoft.Json" Version="10.0.3" />
  <Package Id="Castle.Core" Version="4.1.0" />
  <Package Id="Moq" Version="4.7.63" />
</StoreArtifacts>
```

## <a name="publishing-an-app-against-a-target-manifest"></a><span data-ttu-id="77da9-128">Veröffentlichen einer App mit einem Zielmanifest</span><span class="sxs-lookup"><span data-stu-id="77da9-128">Publishing an app against a target manifest</span></span>

<span data-ttu-id="77da9-129">Wenn Sie eine Zielmanifestdatei auf Ihrer Festplatte haben, geben Sie den Pfad zu dieser Datei an, wenn Sie Ihre App mit dem [`dotnet publish`](../tools/dotnet-publish.md)-Befehl veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="77da9-129">If you have a target manifest file on disk, you specify the path to the file when publishing your app with the [`dotnet publish`](../tools/dotnet-publish.md) command:</span></span>

```dotnetcli
dotnet publish --manifest <PATH_TO_MANIFEST_FILE>
```

<span data-ttu-id="77da9-130">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="77da9-130">**Example**</span></span>

```dotnetcli
dotnet publish --manifest manifest.xml
```

<span data-ttu-id="77da9-131">Sie stellen die resultierende veröffentlichte App für eine Umgebung bereit, die die im Zielmanifest beschriebenen Pakete enthält.</span><span class="sxs-lookup"><span data-stu-id="77da9-131">You deploy the resulting published app to an environment that has the packages described in the target manifest.</span></span> <span data-ttu-id="77da9-132">Wenn dies nicht der Fall ist, führt das zu einem Startfehler der App.</span><span class="sxs-lookup"><span data-stu-id="77da9-132">Failing to do so results in the app failing to start.</span></span>

<span data-ttu-id="77da9-133">Geben Sie mehrere Zielmanifeste an, wenn Sie eine App veröffentlichen, indem Sie die Option und den Pfad wiederholen (zum Beispiel `--manifest manifest1.xml --manifest manifest2.xml`).</span><span class="sxs-lookup"><span data-stu-id="77da9-133">Specify multiple target manifests when publishing an app by repeating the option and path (for example, `--manifest manifest1.xml --manifest manifest2.xml`).</span></span> <span data-ttu-id="77da9-134">Wenn Sie dies tun, wird die App für die Vereinigungsmenge der Pakete zugeschnitten, die in den für den Befehl bereitgestellten Zielmanifestdateien angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="77da9-134">When you do so, the app is trimmed for the union of packages specified in the target manifest files provided to the command.</span></span>

## <a name="specifying-target-manifests-in-the-project-file"></a><span data-ttu-id="77da9-135">Angeben von Zielmanifesten in der Projektdatei</span><span class="sxs-lookup"><span data-stu-id="77da9-135">Specifying target manifests in the project file</span></span>

<span data-ttu-id="77da9-136">Eine Alternative zum Angeben von Zielmanifesten mit dem [`dotnet publish`](../tools/dotnet-publish.md)-Befehl ist, diese in der Projektdatei als eine durch Semikolons getrennte Liste von Pfaden unter dem Tag **\<TargetManifestFiles>** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="77da9-136">An alternative to specifying target manifests with the [`dotnet publish`](../tools/dotnet-publish.md) command is to specify them in the project file as a semicolon-separated list of paths under a **\<TargetManifestFiles>** tag.</span></span>

```xml
<PropertyGroup>
  <TargetManifestFiles>manifest1.xml;manifest2.xml</TargetManifestFiles>
</PropertyGroup>
```

<span data-ttu-id="77da9-137">Geben Sie die Zielmanifeste nur in der Projektdatei an, wenn die Zielumgebung für die App bekannt ist, zum Beispiel bei .NET Core-Projekten.</span><span class="sxs-lookup"><span data-stu-id="77da9-137">Specify the target manifests in the project file only when the target environment for the app is well-known, such as for .NET Core projects.</span></span> <span data-ttu-id="77da9-138">Für Open-Source-Projekte ist dies nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="77da9-138">This isn't the case for open-source projects.</span></span> <span data-ttu-id="77da9-139">Die Benutzer von Open-Source-Projekten stellen diese üblicherweise für verschiedene Produktionsumgebungen bereit.</span><span class="sxs-lookup"><span data-stu-id="77da9-139">The users of an open-source project typically deploy it to different production environments.</span></span> <span data-ttu-id="77da9-140">Diese Produktionsumgebungen verfügen im Allgemeinen über verschiedene vorinstallierte Pakete.</span><span class="sxs-lookup"><span data-stu-id="77da9-140">These production environments generally have different sets of packages pre-installed.</span></span> <span data-ttu-id="77da9-141">Sie können keine Annahmen über die Zielmanifeste in solchen Umgebungen machen, deshalb sollten Sie die Option `--manifest` von [`dotnet publish`](../tools/dotnet-publish.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="77da9-141">You can't make assumptions about the target manifest in such environments, so you should use the `--manifest` option of [`dotnet publish`](../tools/dotnet-publish.md).</span></span>

## <a name="aspnet-core-implicit-store"></a><span data-ttu-id="77da9-142">Impliziter Speicher für ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="77da9-142">ASP.NET Core implicit store</span></span>

<span data-ttu-id="77da9-143">Der implizite Speicher für ASP.NET Core gilt nur für ASP.NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="77da9-143">The ASP.NET Core implicit store applies only to ASP.NET Core 2.0.</span></span> <span data-ttu-id="77da9-144">Es wird dringend empfohlen, ASP.NET Core 2.1 und höher für Anwendungen zu verwenden, die den impliziten Speicher **nicht** verwenden.</span><span class="sxs-lookup"><span data-stu-id="77da9-144">We strongly recommend applications use ASP.NET Core 2.1 and later, which does **not** use the implicit store.</span></span> <span data-ttu-id="77da9-145">ASP.NET Core 2.1 und höher verwenden das freigegebene Framework.</span><span class="sxs-lookup"><span data-stu-id="77da9-145">ASP.NET Core 2.1 and later use the shared framework.</span></span>

<span data-ttu-id="77da9-146">Das Feature für den Laufzeitpaketspeicher wird implizit von einer ASP.NET Core-App verwendet, wenn die App als [Framework-abhängige Bereitstellung (FDD)](index.md#framework-dependent-deployments-fdd) bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="77da9-146">The runtime package store feature is used implicitly by an ASP.NET Core app when the app is deployed as a [framework-dependent deployment (FDD)](index.md#framework-dependent-deployments-fdd) app.</span></span> <span data-ttu-id="77da9-147">Die Ziele in [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) beinhalten Manifeste, die auf implizite Paketspeicher auf dem Zielsystem verweisen.</span><span class="sxs-lookup"><span data-stu-id="77da9-147">The targets in [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) include manifests referencing the implicit package store on the target system.</span></span> <span data-ttu-id="77da9-148">Darüber hinaus resultiert jede FDD-App, die vom Paket `Microsoft.AspNetCore.All` abhängig ist, in einer veröffentlichten App, die nur die App und ihre Objekte enthält, nicht aber die Pakete, die im Metapaket `Microsoft.AspNetCore.All` aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="77da9-148">Additionally, any FDD app that depends on the `Microsoft.AspNetCore.All` package results in a published app that contains only the app and its assets and not the packages listed in the `Microsoft.AspNetCore.All` metapackage.</span></span> <span data-ttu-id="77da9-149">Es wird davon ausgegangen, dass diese Pakete auf dem Zielsystem vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="77da9-149">It's assumed that those packages are present on the target system.</span></span>

<span data-ttu-id="77da9-150">Der Laufzeitpaketspeicher wird bei der Installation des .NET Core SDK auf dem Host installiert.</span><span class="sxs-lookup"><span data-stu-id="77da9-150">The runtime package store is installed on the host when the .NET Core SDK is installed.</span></span> <span data-ttu-id="77da9-151">Andere Installationsprogramme stellen möglicherweise den Laufzeitpaketspeicher bereit, einschließlich der Zip-/Tarball-Installationen des .NET Core SDK, `apt-get`, Red Hat Yum, dem .NET Core Windows Server-Hostingpakets und manuellen Installationen des Laufzeitpaketspeichers.</span><span class="sxs-lookup"><span data-stu-id="77da9-151">Other installers may provide the runtime package store, including Zip/tarball installations of the .NET Core SDK, `apt-get`, Red Hat Yum, the .NET Core Windows Server Hosting bundle, and manual runtime package store installations.</span></span>

<span data-ttu-id="77da9-152">Versichern Sie sich, dass das .NET Core SDK in der Zielumgebung installiert ist, wenn Sie eine App für [Framework-abhängige Bereitstellung (FDD)](index.md#framework-dependent-deployments-fdd) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="77da9-152">When deploying a [framework-dependent deployment (FDD)](index.md#framework-dependent-deployments-fdd) app, make sure that the target environment has the .NET Core SDK installed.</span></span> <span data-ttu-id="77da9-153">Wenn die App für eine Umgebung bereitgestellt wird, die ASP.NET Core nicht enthält, können Sie den impliziten Speicher deaktivieren, indem Sie **\<PublishWithAspNetCoreTargetManifest>** angeben, das in der Projektdatei wie im folgenden Beispiel auf `false` festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="77da9-153">If the app is deployed to an environment that doesn't include ASP.NET Core, you can opt out of the implicit store by specifying  **\<PublishWithAspNetCoreTargetManifest>** set to `false` in the project file as in the following example:</span></span>

```xml
<PropertyGroup>
  <PublishWithAspNetCoreTargetManifest>false</PublishWithAspNetCoreTargetManifest>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="77da9-154">Bei Apps für die [eigenständige Bereitstellung (SCD)](index.md#self-contained-deployments-scd) wird davon ausgegangen, dass das Zielsystem die erforderlichen Manifestpakete nicht unbedingt enthält.</span><span class="sxs-lookup"><span data-stu-id="77da9-154">For [self-contained deployment (SCD)](index.md#self-contained-deployments-scd) apps, it's assumed that the target system doesn't necessarily contain the required manifest packages.</span></span> <span data-ttu-id="77da9-155">Deshalb kann **\<PublishWithAspNetCoreTargetManifest>** für eine SCD-App nicht auf `true` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="77da9-155">Therefore, **\<PublishWithAspNetCoreTargetManifest>** cannot be set to `true` for an SCD app.</span></span>

<span data-ttu-id="77da9-156">Wenn Sie eine Anwendung bereitstellen, die von einem in der Bereitstellung vorhandenen Manifest abhängig ist (die Assembly ist im Ordner *bin* enthalten), wird der Laufzeitpaketspeicher für diese Assembly auf dem Host *nicht verwendet*.</span><span class="sxs-lookup"><span data-stu-id="77da9-156">If you deploy an application with a manifest dependency that's present in the deployment (the assembly is present in the *bin* folder), the runtime package store *isn't used* on the host for that assembly.</span></span> <span data-ttu-id="77da9-157">Die Assembly im Ordner *bin* wird unabhängig von ihrem Vorhandensein im Laufzeitpaketspeicher auf dem Host verwendet.</span><span class="sxs-lookup"><span data-stu-id="77da9-157">The *bin* folder assembly is used regardless of its presence in the runtime package store on the host.</span></span>

<span data-ttu-id="77da9-158">Die Version der Abhängigkeit, die im Manifest angegeben ist, muss mit der Version der Abhängigkeit im Laufzeitpaketspeicher übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="77da9-158">The version of the dependency indicated in the manifest must match the version of the dependency in the runtime package store.</span></span> <span data-ttu-id="77da9-159">Wenn ein Versionskonflikt zwischen der Abhängigkeit im Zielmanifest und der Version im Laufzeitpaketspeicher vorliegt, und die App in ihrer Bereitstellung nicht die erforderliche Version des Pakets enthält, führt dies zu einem Fehlstart der App.</span><span class="sxs-lookup"><span data-stu-id="77da9-159">If you have a version mismatch between the dependency in the target manifest and the version that exists in the runtime package store and the app doesn't include the required version of the package in its deployment, the app fails to start.</span></span> <span data-ttu-id="77da9-160">Die Ausnahme enthält den Namen des Zielmanifests, das die Assembly im Laufzeitpaketspeicher aufgerufen hat. Das hilft Ihnen bei der Behebung des Konflikts.</span><span class="sxs-lookup"><span data-stu-id="77da9-160">The exception includes the name of the target manifest that called for the runtime package store assembly, which helps you troubleshoot the mismatch.</span></span>

<span data-ttu-id="77da9-161">Wenn die Bereitstellung bei der Veröffentlichung *gekürzt* ist, werden nur die spezifischen Versionen der Manifestpakete, die Sie angeben, aus der veröffentlichten Ausgabe zurückbehalten.</span><span class="sxs-lookup"><span data-stu-id="77da9-161">When the deployment is *trimmed* on publish, only the specific versions of the manifest packages you indicate are withheld from the published output.</span></span> <span data-ttu-id="77da9-162">Die Pakete der angegebenen Versionen müssen auf dem Host vorhanden sein, damit die App starten kann.</span><span class="sxs-lookup"><span data-stu-id="77da9-162">The packages at the versions indicated must be present on the host for the app to start.</span></span>

## <a name="see-also"></a><span data-ttu-id="77da9-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77da9-163">See also</span></span>

- [<span data-ttu-id="77da9-164">dotnet-publish</span><span class="sxs-lookup"><span data-stu-id="77da9-164">dotnet-publish</span></span>](../tools/dotnet-publish.md)
- [<span data-ttu-id="77da9-165">dotnet-store</span><span class="sxs-lookup"><span data-stu-id="77da9-165">dotnet-store</span></span>](../tools/dotnet-store.md)
