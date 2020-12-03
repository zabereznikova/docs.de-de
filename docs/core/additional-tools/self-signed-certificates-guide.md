---
title: 'Übersicht: Generieren von selbstsignierten Zertifikaten'
description: Eine Übersicht über das Microsoft dotnet dev-certs-Tool, das Funktionen für .NET Core- und ASP.NET Core-Projekte sowie weitere Optionen für die Verwendung selbstsignierter Zertifikate umfasst.
author: angee
ms.date: 11/19/2020
ms.openlocfilehash: b5bf4b719495c2d6ec248e8592367ac452be91c1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032176"
---
# <a name="generate-self-signed-certificates-with-the-net-cli"></a><span data-ttu-id="d7170-103">Generieren von selbstsignierten Zertifikaten mit der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="d7170-103">Generate self-signed certificates with the .NET CLI</span></span>

<span data-ttu-id="d7170-104">Wenn Sie selbstsignierte Zertifikate verwenden, gibt es verschiedene Möglichkeiten, um sie zu erstellen und für die Bereitstellung sowie für Testszenarios zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7170-104">When using self-signed certificates, there are different ways to create and use them for development and testing scenarios.</span></span>  <span data-ttu-id="d7170-105">In diesem Leitfaden erhalten Sie Informationen zur Verwendung von selbstsignierten Zertifikaten mit `dotnet dev-certs` und anderen Optionen wie `PowerShell` und `OpenSSL`.</span><span class="sxs-lookup"><span data-stu-id="d7170-105">In this guide, you'll cover using self-signed certificates with `dotnet dev-certs`, and other options like `PowerShell` and `OpenSSL`.</span></span>

<span data-ttu-id="d7170-106">Sie können dann mithilfe eines Beispiels überprüfen, ob das Zertifikat geladen wird, z. B. mit einer [ASP.NET Core-App](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md), die in einem Container gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="d7170-106">You can then validate that the certificate will load using an example such as an [ASP.NET Core app](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md) hosted in a container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d7170-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d7170-107">Prerequisites</span></span>

<span data-ttu-id="d7170-108">Im Beispiel können Sie entweder .NET Core 3.1 oder .NET 5 verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7170-108">In the sample, you can utilize either .NET Core 3.1 or .NET 5.</span></span>

<span data-ttu-id="d7170-109">Stellen Sie für `dotnet dev-certs` sicher, dass Sie die richtige Version von .NET installiert haben:</span><span class="sxs-lookup"><span data-stu-id="d7170-109">For `dotnet dev-certs`, be sure to have the appropriate version of .NET installed:</span></span>

* [<span data-ttu-id="d7170-110">Installieren von .NET unter Windows</span><span class="sxs-lookup"><span data-stu-id="d7170-110">Install .NET on Windows</span></span>](../install/windows.md)
* [<span data-ttu-id="d7170-111">Installieren von .NET unter Linux</span><span class="sxs-lookup"><span data-stu-id="d7170-111">Install .NET on Linux</span></span>](../install/linux.md)
* [<span data-ttu-id="d7170-112">Installieren von .NET unter macOS</span><span class="sxs-lookup"><span data-stu-id="d7170-112">Install .NET on macOS</span></span>](../install/macos.md)

<span data-ttu-id="d7170-113">Für dieses Beispiel benötigen Sie den [Docker-Client](https://www.docker.com/products/docker) [Docker 17.06](https://docs.docker.com/release-notes/docker-ce) oder höher.</span><span class="sxs-lookup"><span data-stu-id="d7170-113">This sample requires [Docker 17.06](https://docs.docker.com/release-notes/docker-ce) or later of the [Docker client](https://www.docker.com/products/docker).</span></span>

## <a name="prepare-sample-app"></a><span data-ttu-id="d7170-114">Vorbereiten der Beispiel-App</span><span class="sxs-lookup"><span data-stu-id="d7170-114">Prepare sample app</span></span>

<span data-ttu-id="d7170-115">Sie müssen die Beispiel-App je nach Runtime vorbereiten, die Sie zum Testen verwenden möchten, entweder [.NET Core 3.1](#net-core-31-sample-app) oder [.NET 5](#net-5-sample-app).</span><span class="sxs-lookup"><span data-stu-id="d7170-115">You'll need to prepare the sample app depending on which runtime you'd like to use for testing, either [.NET Core 3.1](#net-core-31-sample-app) or [.NET 5](#net-5-sample-app).</span></span>

<span data-ttu-id="d7170-116">Verwenden Sie für diese Anleitung eine [Beispiel-App](https://hub.docker.com/_/microsoft-dotnet-samples), und nehmen Sie wenn nötig Anpassungen vor.</span><span class="sxs-lookup"><span data-stu-id="d7170-116">For this guide, you'll use a [sample app](https://hub.docker.com/_/microsoft-dotnet-samples) and make changes where appropriate.</span></span>

### <a name="net-core-31-sample-app"></a><span data-ttu-id="d7170-117">Beispiel-App für .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="d7170-117">.NET Core 3.1 sample app</span></span>

<span data-ttu-id="d7170-118">Abrufen der Beispiel-App</span><span class="sxs-lookup"><span data-stu-id="d7170-118">Get the sample app.</span></span>

```console
git clone https://github.com/dotnet/dotnet-docker/
```

<span data-ttu-id="d7170-119">Navigieren Sie auf lokaler Ebene zum Repository, und öffnen Sie den Arbeitsbereich in einem Editor.</span><span class="sxs-lookup"><span data-stu-id="d7170-119">Navigate to the repository locally and open up the workspace in an editor.</span></span>

> [!NOTE]
> <span data-ttu-id="d7170-120">Wenn Sie dotnet publish-Parameter zum *Trimmen* der Bereitstellung verwenden möchten, sollten Sie sicherstellen, dass die entsprechenden Abhängigkeiten zur Unterstützung von SSL-Zertifikaten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d7170-120">If you're looking to use dotnet publish parameters to *trim* the deployment, you should make sure that the appropriate dependencies are included for supporting SSL certificates.</span></span>
<span data-ttu-id="d7170-121">Aktualisieren Sie die Datei [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj), um sicherzustellen, dass die richtigen Assemblys zum Container hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d7170-121">Update the [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) to ensure that the appropriate assemblies are included in the container.</span></span> <span data-ttu-id="d7170-122">Informieren Sie sich in diesem Zusammenhang darüber, wie Sie die CSPROJ-Datei so aktualisieren können, dass [SSL-Zertifikate unterstützt](../deploying/trim-self-contained.md#support-for-ssl-certificates) werden, wenn Sie Trimming für eigenständige Bereitstellungen einsetzen.</span><span class="sxs-lookup"><span data-stu-id="d7170-122">For reference, check how to update the .csproj file to [support ssl certificates](../deploying/trim-self-contained.md#support-for-ssl-certificates) when using trimming for self-contained deployments.</span></span>

<span data-ttu-id="d7170-123">Stellen Sie sicher, dass die Datei `aspnetapp.csproj` ein passendes Zielframework enthält:</span><span class="sxs-lookup"><span data-stu-id="d7170-123">Make sure the `aspnetapp.csproj` includes the appropriate target framework:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>.netcoreapp3.1</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

<span data-ttu-id="d7170-124">Ändern Sie das Dockerfile, um sicherzustellen, dass die Runtime auf .NET Core 3.1 verweist:</span><span class="sxs-lookup"><span data-stu-id="d7170-124">Modify the Dockerfile to make sure the runtime points to .NET Core 3.1:</span></span>

```Dockerfile
# https://hub.docker.com/_/microsoft-dotnet-core
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
WORKDIR /source

# copy csproj and restore as distinct layers
COPY *.sln .
COPY aspnetapp/*.csproj ./aspnetapp/
RUN dotnet restore

# copy everything else and build app
COPY aspnetapp/. ./aspnetapp/
WORKDIR /source/aspnetapp
RUN dotnet publish -c release -o /app --no-restore

# final stage/image
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["dotnet", "aspnetapp.dll"]
```

<span data-ttu-id="d7170-125">Stellen Sie sicher, dass Sie auf die Beispiel-App verweisen.</span><span class="sxs-lookup"><span data-stu-id="d7170-125">Make sure you're pointing to the sample app.</span></span>

```console
cd .\dotnet-docker\samples\aspnetapp
```

<span data-ttu-id="d7170-126">Erstellen Sie den Container zum Testen auf lokaler Ebene.</span><span class="sxs-lookup"><span data-stu-id="d7170-126">Build the container for testing locally.</span></span>

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

### <a name="net-5-sample-app"></a><span data-ttu-id="d7170-127">.NET 5-Beispiel-App</span><span class="sxs-lookup"><span data-stu-id="d7170-127">.NET 5 sample app</span></span>

<span data-ttu-id="d7170-128">Überprüfen Sie für diese Anleitung das Beispiel [aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples) auf .NET 5.</span><span class="sxs-lookup"><span data-stu-id="d7170-128">For this guide, the [sample aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples) should be checked for .NET 5.</span></span>

<span data-ttu-id="d7170-129">Überprüfen Sie, ob das [Dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile) für die Beispiel-App .NET 5 verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7170-129">Check sample app [Dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile) is using .NET 5.</span></span>

<span data-ttu-id="d7170-130">Je nach Hostbetriebssystem muss die ASP.NET-Runtime gegebenenfalls aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="d7170-130">Depending on the host OS, the ASP.NET runtime may need to be updated.</span></span> <span data-ttu-id="d7170-131">Wenn Sie im Dockerfile beispielsweise von `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` zu `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` wechseln, können Sie besser eine passende Windows-Runtime als Ziel festlegen.</span><span class="sxs-lookup"><span data-stu-id="d7170-131">For example, changing from `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` to `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` in the Dockerfile will help with targeting the appropriate Windows runtime.</span></span>

<span data-ttu-id="d7170-132">Dies hilft beispielsweise beim Testen der Zertifikate unter Windows:</span><span class="sxs-lookup"><span data-stu-id="d7170-132">For example, this will help with testing the certificates on Windows:</span></span>

```Dockerfile
# https://hub.docker.com/_/microsoft-dotnet
FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /source

# copy csproj and restore as distinct layers
COPY *.sln .
COPY aspnetapp/*.csproj ./aspnetapp/
RUN dotnet restore -r win-x64

# copy everything else and build app
COPY aspnetapp/. ./aspnetapp/
WORKDIR /source/aspnetapp
RUN dotnet publish -c release -o /app -r win-x64 --self-contained false --no-restore

# final stage/image
# Uses the 2009 release; 2004, 1909, and 1809 are other choices
FROM mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["aspnetapp"]

```

<span data-ttu-id="d7170-133">Wenn wir die Zertifikate unter Linux testen, können Sie das vorhandene Dockerfile verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7170-133">If we're testing the certificates on Linux, you can use the existing Dockerfile.</span></span>

<span data-ttu-id="d7170-134">Stellen Sie sicher, dass die Datei `aspnetapp.csproj` ein passendes Zielframework enthält:</span><span class="sxs-lookup"><span data-stu-id="d7170-134">Make sure the `aspnetapp.csproj` includes the appropriate target framework:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

> [!NOTE]
> <span data-ttu-id="d7170-135">Wenn Sie `dotnet publish`-Parameter zum *Trimmen* der Bereitstellung verwenden möchten, sollten Sie sicherstellen, dass die passenden Abhängigkeiten zur Unterstützung von SSL-Zertifikaten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d7170-135">If you want to use `dotnet publish` parameters to *trim* the deployment, make sure that the appropriate dependencies are included for supporting SSL certificates.</span></span>
<span data-ttu-id="d7170-136">Aktualisieren Sie die Datei [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj), um sicherzustellen, dass die richtigen Assemblys zum Container hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d7170-136">Update the [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) to ensure that the appropriate assemblies are included in the container.</span></span> <span data-ttu-id="d7170-137">Informieren Sie sich in diesem Zusammenhang darüber, wie Sie die CSPROJ-Datei so aktualisieren können, dass [SSL-Zertifikate unterstützt](../deploying/trim-self-contained.md#support-for-ssl-certificates) werden, wenn Sie Trimming für eigenständige Bereitstellungen einsetzen.</span><span class="sxs-lookup"><span data-stu-id="d7170-137">For reference, check how to update the .csproj file to [support ssl certificates](../deploying/trim-self-contained.md#support-for-ssl-certificates) when using trimming for self-contained deployments.</span></span>

<span data-ttu-id="d7170-138">Stellen Sie sicher, dass Sie auf die Beispiel-App verweisen.</span><span class="sxs-lookup"><span data-stu-id="d7170-138">Make sure you're pointing to the sample app.</span></span>

```console
cd .\dotnet-docker\samples\aspnetapp
```

<span data-ttu-id="d7170-139">Erstellen Sie den Container zum Testen auf lokaler Ebene.</span><span class="sxs-lookup"><span data-stu-id="d7170-139">Build the container for testing locally.</span></span>

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="d7170-140">Erstellen eines selbstsignierten Zertifikats</span><span class="sxs-lookup"><span data-stu-id="d7170-140">Create a self-signed certificate</span></span>

<span data-ttu-id="d7170-141">Sie können mithilfe der folgenden Tools ein selbstsigniertes Zertifikat erstellen:</span><span class="sxs-lookup"><span data-stu-id="d7170-141">You can create a self-signed certificate:</span></span>

- [<span data-ttu-id="d7170-142">Mit dotnet dev-certs</span><span class="sxs-lookup"><span data-stu-id="d7170-142">With dotnet dev-certs</span></span>](#with-dotnet-dev-certs)
- [<span data-ttu-id="d7170-143">Mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7170-143">With PowerShell</span></span>](#with-powershell)
- [<span data-ttu-id="d7170-144">Mit OpenSSL</span><span class="sxs-lookup"><span data-stu-id="d7170-144">With OpenSSL</span></span>](#with-openssl)

### <a name="with-dotnet-dev-certs"></a><span data-ttu-id="d7170-145">Mit dotnet dev-certs</span><span class="sxs-lookup"><span data-stu-id="d7170-145">With dotnet dev-certs</span></span>

<span data-ttu-id="d7170-146">Sie können `dotnet dev-certs` verwenden, um mit selbstsignierten Zertifikaten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d7170-146">You can use `dotnet dev-certs` to work with self-signed certificates.</span></span> <span data-ttu-id="d7170-147">In diesem Beispiel wird eine PowerShell-Konsole verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7170-147">This example uses a PowerShell console.</span></span>

```console
dotnet dev-certs https -ep $env:USERPROFILE\.aspnet\https\aspnetapp.pfx -p crypticpassword
dotnet dev-certs https --trust
```

> [!NOTE]
> <span data-ttu-id="d7170-148">Der Zertifikatsname, in diesem Fall *aspnettapp*.pfx, muss mit dem Projektassemblynamen identisch sein.</span><span class="sxs-lookup"><span data-stu-id="d7170-148">The certificate name, in this case *aspnetapp*.pfx must match the project assembly name.</span></span> <span data-ttu-id="d7170-149">`crypticpassword` wird als Ersatz für ein Kennwort Ihrer Wahl verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7170-149">`crypticpassword` is used as a stand-in for a password of your own choosing.</span></span> <span data-ttu-id="d7170-150">Wenn die Konsole die Meldung "A valid HTTPS certificate is already present" (Es gibt bereit ein gültiges HTTPS-Zertifikat) zurückgibt, gibt es bereits ein vertrauenswürdiges Zertifikat in Ihrem Speicher.</span><span class="sxs-lookup"><span data-stu-id="d7170-150">If console returns "A valid HTTPS certificate is already present.", a trusted certificate already exists in your store.</span></span> <span data-ttu-id="d7170-151">Dieses können Sie mithilfe der MMC-Konsole exportieren.</span><span class="sxs-lookup"><span data-stu-id="d7170-151">It can be exported using MMC Console.</span></span>

<span data-ttu-id="d7170-152">Konfigurieren Sie die Anwendungsgeheimnisse für das Zertifikat:</span><span class="sxs-lookup"><span data-stu-id="d7170-152">Configure application secrets, for the certificate:</span></span>

```console
dotnet user-secrets -p aspnetapp\aspnetapp.csproj set "Kestrel:Certificates:Development:Password" "crypticpassword"
```

> [!NOTE]
> <span data-ttu-id="d7170-153">Hinweis: Das Kennwort muss dem Kennwort entsprechen, das für das Zertifikat verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7170-153">Note: The password must match the password used for the certificate.</span></span>

<span data-ttu-id="d7170-154">Führen Sie das Containerimage mit einer für HTTPS konfigurierten ASP.NET Core-Instanz aus:</span><span class="sxs-lookup"><span data-stu-id="d7170-154">Run the container image with ASP.NET Core configured for HTTPS:</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -v $env:APPDATA\microsoft\UserSecrets\:C:\Users\ContainerUser\AppData\Roaming\microsoft\UserSecrets -v $env:USERPROFILE\.aspnet\https:C:\Users\ContainerUser\AppData\Roaming\ASP.NET\Https mcr.microsoft.com/dotnet/samples:aspnetapp
```

<span data-ttu-id="d7170-155">Sobald die Anwendung gestartet wurde, navigieren Sie in Ihrem Webbrowser zu `https://localhost:8001`.</span><span class="sxs-lookup"><span data-stu-id="d7170-155">Once the application starts, navigate to `https://localhost:8001` in your web browser.</span></span>

#### <a name="clean-up"></a><span data-ttu-id="d7170-156">Bereinigung</span><span class="sxs-lookup"><span data-stu-id="d7170-156">Clean up</span></span>

<span data-ttu-id="d7170-157">Wenn die Geheimnisse und Zertifikate nicht verwendet werden, sollten Sie diese löschen.</span><span class="sxs-lookup"><span data-stu-id="d7170-157">If the secrets and certificates are not in use, be sure to clean them up.</span></span>

```console
dotnet user-secrets remove "Kestrel:Certificates:Development:Password" -p aspnetapp\aspnetapp.csproj
dotnet dev-certs https --clean
```

### <a name="with-powershell"></a><span data-ttu-id="d7170-158">Mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7170-158">With PowerShell</span></span>

<span data-ttu-id="d7170-159">Sie können PowerShell verwenden, um selbstsignierte Zertifikate zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d7170-159">You can use PowerShell to generate self-signed certificates.</span></span> <span data-ttu-id="d7170-160">Dabei hilft Ihnen der [PKI-Client](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true).</span><span class="sxs-lookup"><span data-stu-id="d7170-160">The [PKI Client](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true) can be used to generate a self-signed certificate.</span></span>

```powershell
$cert = New-SelfSignedCertificate -DnsName @("contoso.com", "www.contoso.com") -CertStoreLocation "cert:\LocalMachine\My"
```

<span data-ttu-id="d7170-161">Wenn das Zertifikat generiert wird, sollte es in einem Zertifikatspeicher gespeichert werden, um Tests im Browser durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="d7170-161">The certificate will be generated, but for the purposes of testing, should be placed in a cert store for testing in a browser.</span></span>

```powershell
$certKeyPath = "c:\certs\contoso.com.pfx"
$password = ConvertTo-SecureString 'password' -AsPlainText -Force
$cert | Export-PfxCertificate -FilePath $certKeyPath -Password $password
$rootCert = $(Import-PfxCertificate -FilePath $certKeyPath -CertStoreLocation 'Cert:\LocalMachine\Root' -Password $password)
```

<span data-ttu-id="d7170-162">An dieser Stellen sollten die Zertifikate über ein [MMC-Snap-In](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) abrufbar sein.</span><span class="sxs-lookup"><span data-stu-id="d7170-162">At this point, the certificates should be viewable from an [MMC snap-in](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

<span data-ttu-id="d7170-163">Sie können den Beispielcontainer im Windows-Subsystem für Linux (WSL) ausführen:</span><span class="sxs-lookup"><span data-stu-id="d7170-163">You can run the sample container in Windows Subsystem for Linux (WSL):</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> <span data-ttu-id="d7170-164">Mit der Volumebereitstellung kann der Dateipfad je nach Host anders aufgebaut sein.</span><span class="sxs-lookup"><span data-stu-id="d7170-164">Note that with the volume mount the file path could be handled differently based on host.</span></span>  <span data-ttu-id="d7170-165">Beispielsweise können Sie in WSL */c/certs* durch */mnt/c/certs* ersetzen.</span><span class="sxs-lookup"><span data-stu-id="d7170-165">For example, in WSL we may replace */c/certs* with */mnt/c/certs*.</span></span>

<span data-ttu-id="d7170-166">Wenn Sie den Container verwenden, der zuvor für Windows erstellt wurde, sieht der Ausführungsbefehl wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d7170-166">If you're using the container built earlier for Windows, the run command would look like the following:</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="d7170-167">Navigieren Sie in einem Browser zu „contoso.com:8001“, sobald die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d7170-167">Once the application is up, navigate to contoso.com:8001 in a browser.</span></span>

<span data-ttu-id="d7170-168">Stellen Sie sicher, dass die Hosteinträge aktualisiert werden, damit `contoso.com` auf einer passenden IP-Adresse (z. B. 127.0.0.1) antwortet.</span><span class="sxs-lookup"><span data-stu-id="d7170-168">Be sure that the host entries are updated for `contoso.com` to answer on  the appropriate ip address (for example 127.0.0.1).</span></span> <span data-ttu-id="d7170-169">Wenn das Zertifikat nicht erkannt wird, sollten Sie sich vergewissern, dass das Zertifikat, das mit dem Container geladen wird, ebenfalls vom Host als vertrauenswürdig eingestuft wird, und dass es passende SAN-/DNS-Einträge für `contoso.com` gibt.</span><span class="sxs-lookup"><span data-stu-id="d7170-169">If the certificate isn't recognized, make sure that the certificate that is loaded with the container is also trusted on the host, and that there's appropriate SAN / DNS entries for `contoso.com`.</span></span>

#### <a name="clean-up"></a><span data-ttu-id="d7170-170">Bereinigung</span><span class="sxs-lookup"><span data-stu-id="d7170-170">Clean up</span></span>

```powershell
$cert | Remove-Item
Get-ChildItem $certFilePath | Remove-Item
$rootCert | Remove-item
```

### <a name="with-openssl"></a><span data-ttu-id="d7170-171">Mit OpenSSL</span><span class="sxs-lookup"><span data-stu-id="d7170-171">With OpenSSL</span></span>

<span data-ttu-id="d7170-172">Sie können [OpenSSL](https://www.openssl.org/) verwenden, um selbstsignierte Zertifikate zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d7170-172">You can use [OpenSSL](https://www.openssl.org/) to create self-signed certificates.</span></span> <span data-ttu-id="d7170-173">In diesem Beispiel werden WSL/Ubuntu und eine Bash-Shell mit `OpenSSL` verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7170-173">This example will use WSL / Ubuntu and a bash shell with `OpenSSL`.</span></span>

<span data-ttu-id="d7170-174">Hierdurch werden eine CRT- und eine KEY-Datei generiert.</span><span class="sxs-lookup"><span data-stu-id="d7170-174">This will generate a .crt and a .key.</span></span>

```bash
PARENT="contoso.com"
openssl req \
-x509 \
-newkey rsa:4096 \
-sha256 \
-days 365 \
-nodes \
-keyout $PARENT.key \
-out $PARENT.crt \
-subj "/CN=${PARENT}" \
-extensions v3_ca \
-extensions v3_req \
-config <( \
  echo '[req]'; \
  echo 'default_bits= 4096'; \
  echo 'distinguished_name=req'; \
  echo 'x509_extension = v3_ca'; \
  echo 'req_extensions = v3_req'; \
  echo '[v3_req]'; \
  echo 'basicConstraints = CA:FALSE'; \
  echo 'keyUsage = nonRepudiation, digitalSignature, keyEncipherment'; \
  echo 'subjectAltName = @alt_names'; \
  echo '[ alt_names ]'; \
  echo "DNS.1 = www.${PARENT}"; \
  echo "DNS.2 = ${PARENT}"; \
  echo '[ v3_ca ]'; \
  echo 'subjectKeyIdentifier=hash'; \
  echo 'authorityKeyIdentifier=keyid:always,issuer'; \
  echo 'basicConstraints = critical, CA:TRUE, pathlen:0'; \
  echo 'keyUsage = critical, cRLSign, keyCertSign'; \
  echo 'extendedKeyUsage = serverAuth, clientAuth')

openssl x509 -noout -text -in $PARENT.crt
```

<span data-ttu-id="d7170-175">Wenn Sie eine PFX-Datei erstellen möchten, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="d7170-175">To get a .pfx, use the following command:</span></span>

```bash
openssl pkcs12 -export -out $PARENT.pfx -inkey $PARENT.key -in $PARENT.crt
```

> [!NOTE]
> <span data-ttu-id="d7170-176">Das Beispiel „.aspnetcore 3.1“ verwendet `.pfx` und ein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="d7170-176">The .aspnetcore 3.1 example will use `.pfx` and a password.</span></span> <span data-ttu-id="d7170-177">Ab der Runtime `.net 5` kann Kestrel ebenfalls `.crt`-Dateien und PEM-codierte `.key`-Dateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7170-177">Starting with the `.net 5` runtime, Kestrel can also take `.crt` and PEM-encoded `.key` files.</span></span>

<span data-ttu-id="d7170-178">Je nach Hostbetriebssystem muss das Zertifikat als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="d7170-178">Depending on the host os, the certificate will need to be trusted.</span></span> <span data-ttu-id="d7170-179">Auf einem Linux-Host werden Zertifikate auf andere Weise und in Abhängigkeit mit der Distribution als vertrauenswürdig eingestuft.</span><span class="sxs-lookup"><span data-stu-id="d7170-179">On a Linux host, 'trusting' the certificate is different and distro dependent.</span></span>

<span data-ttu-id="d7170-180">Für diesen Leitfaden stellen wir das folgende Beispiel für Windows unter Verwendung von PowerShell bereit:</span><span class="sxs-lookup"><span data-stu-id="d7170-180">For the purposes of this guide, here's an example in Windows using PowerShell:</span></span>

```powershell
Import-Certificate -FilePath $certFilePath -CertStoreLocation 'Cert:\LocalMachine\Root'
```

<span data-ttu-id="d7170-181">Führen Sie für .NET Core 3.1 den folgenden Befehl in WSL aus:</span><span class="sxs-lookup"><span data-stu-id="d7170-181">For .NET Core 3.1, run the following command in WSL:</span></span>

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/path/to/certs/:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

<span data-ttu-id="d7170-182">Ab .NET 5 kann Kestrel `.crt`-Dateien und PEM-codierte `.key`-Dateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7170-182">Starting with .NET 5, Kestrel can take the `.crt` and PEM-encoded `.key` files.</span></span> <span data-ttu-id="d7170-183">Sie können das Beispiel mithilfe des folgenden Befehls für .NET 5 ausführen:</span><span class="sxs-lookup"><span data-stu-id="d7170-183">You can run the sample with the following command for .NET 5:</span></span>

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=/https/contoso.com.key -v /c/path/to/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> <span data-ttu-id="d7170-184">In WSL kann der Pfad der Volumebereitstellung je nach Konfiguration abweichen.</span><span class="sxs-lookup"><span data-stu-id="d7170-184">Note that in WSL, the volume mount path may change depending on the configuration.</span></span>

<span data-ttu-id="d7170-185">Führen Sie für .NET Core 3.1 unter Windows den folgenden Befehl in `Powershell` aus:</span><span class="sxs-lookup"><span data-stu-id="d7170-185">For .NET Core 3.1 in Windows, run the following command in `Powershell`:</span></span>

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="d7170-186">Führen Sie für .NET 5 unter Windows den folgenden Befehl in PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="d7170-186">For .NET 5 in Windows, run the following command in PowerShell:</span></span>

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=c:\https\contoso.com.key -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="d7170-187">Navigieren Sie in einem Browser zu „contoso.com:8001“, sobald die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d7170-187">Once the application is up, navigate to contoso.com:8001 in a browser.</span></span>

<span data-ttu-id="d7170-188">Stellen Sie sicher, dass die Hosteinträge aktualisiert werden, damit `contoso.com` auf einer passenden IP-Adresse (z. B. 127.0.0.1) antwortet.</span><span class="sxs-lookup"><span data-stu-id="d7170-188">Be sure that the host entries are updated for `contoso.com` to answer on  the appropriate ip address (for example 127.0.0.1).</span></span> <span data-ttu-id="d7170-189">Wenn das Zertifikat nicht erkannt wird, sollten Sie sich vergewissern, dass das Zertifikat, das mit dem Container geladen wird, ebenfalls vom Host als vertrauenswürdig eingestuft wird, und dass es passende SAN-/DNS-Einträge für `contoso.com` gibt.</span><span class="sxs-lookup"><span data-stu-id="d7170-189">If the certificate isn't recognized, make sure that the certificate that is loaded with the container is also trusted on the host, and that there's appropriate SAN / DNS entries for `contoso.com`.</span></span>

#### <a name="clean-up"></a><span data-ttu-id="d7170-190">Bereinigung</span><span class="sxs-lookup"><span data-stu-id="d7170-190">Clean up</span></span>

<span data-ttu-id="d7170-191">Stellen Sie sicher, dass Sie die selbstsignierten Zertifikate nach Abschluss der Tests löschen.</span><span class="sxs-lookup"><span data-stu-id="d7170-191">Be sure to clean up the self-signed certificates once done testing.</span></span>

```powershell
Get-ChildItem $certFilePath | Remove-Item
```
