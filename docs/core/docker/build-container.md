---
title: 'Tutorial: Containerisieren einer .NET Core-App mit Docker'
description: In diesem Tutorial erfahren Sie, wie Sie eine .NET Core-Anwendung mit Docker containerisieren können.
ms.date: 04/27/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: b6775c760ef3f5bf1c9519430b038f149c9cf30f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538500"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="10356-103">Tutorial: Containerisieren einer .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="10356-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="10356-104">In diesem Tutorial erfahren Sie, wie Sie eine .NET Core-Anwendung mit Docker containerisieren können.</span><span class="sxs-lookup"><span data-stu-id="10356-104">In this tutorial, you'll learn how to containerize a .NET Core application with Docker.</span></span> <span data-ttu-id="10356-105">Container haben viele Features und Vorteile, z. B. eine unveränderliche Infrastruktur, eine portable Architektur und die Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="10356-105">Containers have many features and benefits, such as being an immutable infrastructure, providing a portable architecture, and enabling scalability.</span></span> <span data-ttu-id="10356-106">Das Image kann zum Erstellen von Containern für Ihre lokale Entwicklungsumgebung, eine private Cloud oder eine öffentliche Cloud verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10356-106">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="10356-107">In diesem Tutorial:</span><span class="sxs-lookup"><span data-stu-id="10356-107">In this tutorial, you:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="10356-108">Erstellen und Veröffentlichen einer einfachen .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="10356-108">Create and publish a simple .NET Core app</span></span>
> - <span data-ttu-id="10356-109">Erstellen und Konfigurieren einer Dockerfile-Datei für .NET Core</span><span class="sxs-lookup"><span data-stu-id="10356-109">Create and configure a Dockerfile for .NET Core</span></span>
> - <span data-ttu-id="10356-110">Erstellen eines Docker-Images</span><span class="sxs-lookup"><span data-stu-id="10356-110">Build a Docker image</span></span>
> - <span data-ttu-id="10356-111">Erstellen und Ausführen eines Docker-Containers</span><span class="sxs-lookup"><span data-stu-id="10356-111">Create and run a Docker container</span></span>

<span data-ttu-id="10356-112">Hier erfahren Sie mehr über die Aufgaben für das Erstellen und Bereitstellen von Docker-Containern für eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="10356-112">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="10356-113">Die *Docker-Plattform* verwendet die *Docker-Engine*, um Pakete schnell als *Docker-Images* zu erstellen und zu packen.</span><span class="sxs-lookup"><span data-stu-id="10356-113">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="10356-114">Diese Images werden im *Dockerfile*-Format geschrieben, um in einem mehrstufigen Container bereitgestellt und ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="10356-114">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

> [!NOTE]
> <span data-ttu-id="10356-115">Dieses Tutorial gilt **nicht** für ASP.NET Core-Apps.</span><span class="sxs-lookup"><span data-stu-id="10356-115">This tutorial **is not** for ASP.NET Core apps.</span></span> <span data-ttu-id="10356-116">Wenn Sie mit ASP.NET Core arbeiten, lesen Sie das Tutorial [Informationen zum Containerisieren einer ASP.NET Core-Anwendung](/aspnet/core/host-and-deploy/docker/building-net-docker-images).</span><span class="sxs-lookup"><span data-stu-id="10356-116">If you're using ASP.NET Core, see the [Learn how to containerize an ASP.NET Core application](/aspnet/core/host-and-deploy/docker/building-net-docker-images) tutorial.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="10356-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="10356-117">Prerequisites</span></span>

<span data-ttu-id="10356-118">Die folgenden Komponenten müssen installiert sein:</span><span class="sxs-lookup"><span data-stu-id="10356-118">Install the following prerequisites:</span></span>

- <span data-ttu-id="10356-119">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="10356-119">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="10356-120">Wenn Sie .NET Core installiert haben, verwenden Sie den Befehl `dotnet --info`, um festzustellen, welches SDK Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="10356-120">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>
- [<span data-ttu-id="10356-121">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="10356-121">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)
- <span data-ttu-id="10356-122">Ein temporärer Arbeitsordner für das *Dockerfile* und eine .NET Core-Beispiel-App.</span><span class="sxs-lookup"><span data-stu-id="10356-122">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="10356-123">In diesem Tutorial trägt der Arbeitsordner den Namen *docker-working*.</span><span class="sxs-lookup"><span data-stu-id="10356-123">In this tutorial, the name *docker-working* is used as the working folder.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="10356-124">Erstellen der .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="10356-124">Create .NET Core app</span></span>

<span data-ttu-id="10356-125">Sie benötigen eine.NET Core-App, die der Docker-Container ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="10356-125">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="10356-126">Öffnen Sie Ihr Terminal, erstellen Sie einen Arbeitsordner, falls noch nicht geschehen, und geben Sie den Ordnernamen ein.</span><span class="sxs-lookup"><span data-stu-id="10356-126">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="10356-127">Führen Sie im Arbeitsordner den folgenden Befehl aus, um ein neues Projekt im Unterverzeichnis *app* zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="10356-127">In the working folder, run the following command to create a new project in a subdirectory named *app*:</span></span>

```dotnetcli
dotnet new console -o App -n NetCore.Docker
```

<span data-ttu-id="10356-128">Ihre Ordnerstruktur sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="10356-128">Your folder tree will look like the following:</span></span>

```
docker-working
    └──App
        ├──NetCore.Docker.csproj
        ├──Program.cs
        └──obj
            ├──NetCore.Docker.csproj.nuget.dgspec.json
            ├──NetCore.Docker.csproj.nuget.g.props
            ├──NetCore.Docker.csproj.nuget.g.targets
            ├──project.assets.json
            └──project.nuget.cache
```

<span data-ttu-id="10356-129">Über den Befehl `dotnet new` wird ein neuer Ordner namens *App* erstellt und eine „Hallo Welt“-Konsolenanwendung generiert.</span><span class="sxs-lookup"><span data-stu-id="10356-129">The `dotnet new` command creates a new folder named *App* and generates a "Hello World" console application.</span></span> <span data-ttu-id="10356-130">Ändern Sie die Verzeichnisse, und navigieren Sie in der Terminalsitzung zum Ordner *App*.</span><span class="sxs-lookup"><span data-stu-id="10356-130">Change directories and navigate into the *App* folder, from your terminal session.</span></span> <span data-ttu-id="10356-131">Verwenden Sie den `dotnet run`-Befehl, um die App zu starten.</span><span class="sxs-lookup"><span data-stu-id="10356-131">Use the `dotnet run` command to start the app.</span></span> <span data-ttu-id="10356-132">Die Anwendung wird ausgeführt, und `Hello World!` wird unter dem Befehl ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="10356-132">The application will run, and print `Hello World!` below the command:</span></span>

```dotnetcli
dotnet run
Hello World!
```

<span data-ttu-id="10356-133">Die Standardvorlage erstellt eine App, die eine Ausgabe im Terminal anzeigt und dann sofort beendet wird.</span><span class="sxs-lookup"><span data-stu-id="10356-133">The default template creates an app that prints to the terminal and then immediately terminates.</span></span> <span data-ttu-id="10356-134">Für dieses Tutorial verwenden Sie eine App, die auf unbestimmte Zeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="10356-134">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="10356-135">Öffnen Sie die Datei *Program.cs* in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="10356-135">Open the *Program.cs* file in a text editor.</span></span>

> [!TIP]
> <span data-ttu-id="10356-136">Wenn Sie Visual Studio Code verwenden, geben Sie in der vorherigen Terminalsitzung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="10356-136">If you're using Visual Studio Code, from the previous terminal session type the following command:</span></span>
>
> ```console
> code .
> ```
>
> <span data-ttu-id="10356-137">Dadurch wird der Ordner *App* geöffnet, der das Projekt in Visual Studio Code enthält.</span><span class="sxs-lookup"><span data-stu-id="10356-137">This will open the *App* folder that contains the project in Visual Studio Code.</span></span>

<span data-ttu-id="10356-138">Die *Program.cs*-Datei sollte dem folgenden C#-Code entsprechen:</span><span class="sxs-lookup"><span data-stu-id="10356-138">The *Program.cs* should look like the following C# code:</span></span>

```csharp
using System;

namespace NetCore.Docker
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="10356-139">Ersetzen Sie die Datei durch den folgenden Code, der die Zahlen pro Sekunde zählt:</span><span class="sxs-lookup"><span data-stu-id="10356-139">Replace the file with the following code that counts numbers every second:</span></span>

```csharp
using System;
using System.Threading.Tasks;

namespace NetCore.Docker
{
    class Program
    {
        static async Task Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                Console.WriteLine($"Counter: {++counter}");
                await Task.Delay(1000);
            }
        }
    }
}
```

<span data-ttu-id="10356-140">Speichern Sie die Datei, und testen Sie das Programm erneut mit `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="10356-140">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="10356-141">Denken Sie daran, dass diese App auf unbestimmte Zeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="10356-141">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="10356-142">Verwenden Sie zum Beenden den Befehl <kbd>STRG+C</kbd>, um diese anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="10356-142">Use the cancel command <kbd>Ctrl+C</kbd> to stop it.</span></span> <span data-ttu-id="10356-143">Nachfolgend sehen Sie eine Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="10356-143">The following is an example output:</span></span>

```dotnetcli
dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="10356-144">Wenn Sie eine Zahl auf der Kommandozeile an die App übergeben, zählt sie nur bis zu diesem Betrag und wird dann beendet.</span><span class="sxs-lookup"><span data-stu-id="10356-144">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="10356-145">Probieren Sie es mit`dotnet run -- 5`, um bis Fünf zu zählen.</span><span class="sxs-lookup"><span data-stu-id="10356-145">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10356-146">Jegliche Parameter, die auf `--` folgen, werden nicht an den Befehl `dotnet run`, sondern an Ihre Anwendung übergeben.</span><span class="sxs-lookup"><span data-stu-id="10356-146">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="10356-147">Veröffentlichen der .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="10356-147">Publish .NET Core app</span></span>

<span data-ttu-id="10356-148">Bevor Sie die .NET Core-App dem Docker-Image hinzufügen, muss sie veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="10356-148">Before adding the .NET Core app to the Docker image, first it must be published.</span></span> <span data-ttu-id="10356-149">Es ist am besten, wenn der Container die veröffentlichte Version der App ausführt.</span><span class="sxs-lookup"><span data-stu-id="10356-149">It is best to have the container run the published version of the app.</span></span> <span data-ttu-id="10356-150">Führen Sie den folgenden Befehl aus, um die App zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="10356-150">To publish the app, run the following command:</span></span>

```dotnetcli
dotnet publish -c Release
```

<span data-ttu-id="10356-151">Dieser Befehl kompiliert Ihre App in den Ordner *publish*.</span><span class="sxs-lookup"><span data-stu-id="10356-151">This command compiles your app to the *publish* folder.</span></span> <span data-ttu-id="10356-152">Der Pfad zum Ordner *publish* aus dem Arbeitsordner sollte wie folgt lauten: `.\App\bin\Release\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="10356-152">The path to the *publish* folder from the working folder should be `.\App\bin\Release\netcoreapp3.1\publish\`</span></span>

#### <a name="windows"></a>[<span data-ttu-id="10356-153">Windows</span><span class="sxs-lookup"><span data-stu-id="10356-153">Windows</span></span>](#tab/windows)

<span data-ttu-id="10356-154">Rufen Sie über den Ordner *App* eine Verzeichnisliste des Veröffentlichungsordners ab, um sicherzustellen, dass die Datei *NetCore.Docker.dll* erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="10356-154">From the *App* folder, get a directory listing of the publish folder to verify that the *NetCore.Docker.dll* file was created.</span></span>

```powershell
dir .\bin\Release\netcoreapp3.1\publish\

    Directory: C:\Users\dapine\App\bin\Release\netcoreapp3.1\publish

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        4/27/2020   8:27 AM            434 NetCore.Docker.deps.json
-a----        4/27/2020   8:27 AM           6144 NetCore.Docker.dll
-a----        4/27/2020   8:27 AM         171520 NetCore.Docker.exe
-a----        4/27/2020   8:27 AM            860 NetCore.Docker.pdb
-a----        4/27/2020   8:27 AM            154 NetCore.Docker.runtimeconfig.json
```

#### <a name="linux"></a>[<span data-ttu-id="10356-155">Linux</span><span class="sxs-lookup"><span data-stu-id="10356-155">Linux</span></span>](#tab/linux)

<span data-ttu-id="10356-156">Verwenden Sie den Befehl `ls`, um eine Verzeichnisliste abzurufen, und überprüfen Sie, ob die Datei *NetCore.Docker.dll* erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="10356-156">Use the `ls` command to get a directory listing and verify that the *NetCore.Docker.dll* file was created.</span></span>

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
```

---

## <a name="create-the-dockerfile"></a><span data-ttu-id="10356-157">Erstellen der Dockerfile</span><span class="sxs-lookup"><span data-stu-id="10356-157">Create the Dockerfile</span></span>

<span data-ttu-id="10356-158">Die *Dockerfile*-Datei wird vom Befehl `docker build` zum Erstellen des Containerimage verwendet.</span><span class="sxs-lookup"><span data-stu-id="10356-158">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="10356-159">Diese Datei ist eine Textdatei mit dem Namen *Dockerfile*, die keine Erweiterung besitzt.</span><span class="sxs-lookup"><span data-stu-id="10356-159">This file is a text file named *Dockerfile* that doesn't have an extension.</span></span>

<span data-ttu-id="10356-160">Erstellen Sie eine Datei namens *Dockerfile* in dem Verzeichnis mit der *CSPROJ*-Datei, und öffnen Sie sie in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="10356-160">Create a file named *Dockerfile* in directory containing the *.csproj* and open it in a text editor.</span></span> <span data-ttu-id="10356-161">In diesem Tutorial wird das ASP.NET Core-Runtimeimage (das das .NET Core-Runtimeimage enthält) verwendet, das der .NET Core-Konsolenanwendung entspricht.</span><span class="sxs-lookup"><span data-stu-id="10356-161">This tutorial will use the ASP.NET Core runtime image (which contains the .NET Core runtime image) and corresponds with the .NET Core console application.</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
```

> [!NOTE]
> <span data-ttu-id="10356-162">Das ASP.NET Core-Runtimeimage wird hier absichtlich verwendet, obwohl auch das `mcr.microsoft.com/dotnet/core/runtime:3.1`-Image verwendet werden könnte.</span><span class="sxs-lookup"><span data-stu-id="10356-162">The ASP.NET Core runtime image is used intentionally here, although the `mcr.microsoft.com/dotnet/core/runtime:3.1` image could have been used.</span></span>

<span data-ttu-id="10356-163">Für das `FROM`-Schlüsselwort ist der vollqualifizierte Name des Docker-Containerimages erforderlich.</span><span class="sxs-lookup"><span data-stu-id="10356-163">The `FROM` keyword requires a fully qualified Docker container image name.</span></span> <span data-ttu-id="10356-164">Die Microsoft Container Registry (MCR, mcr.microsoft.com) ist ein Konsortium von Docker Hub, das öffentlich zugängliche Container hostet.</span><span class="sxs-lookup"><span data-stu-id="10356-164">The Microsoft Container Registry (MCR, mcr.microsoft.com) is a syndicate of Docker Hub - which hosts publicly accessible containers.</span></span> <span data-ttu-id="10356-165">Das `dotnet/core`-Segment ist das Containerrepository, wobei das `aspnet`-Segment der Name des Containerimages ist.</span><span class="sxs-lookup"><span data-stu-id="10356-165">The `dotnet/core` segment is the container repository, where as the `aspnet` segment is the container image name.</span></span> <span data-ttu-id="10356-166">Das Image wird für die Versionsverwaltung mit `3.1` gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="10356-166">The image is tagged with `3.1`, which is used for versioning.</span></span> <span data-ttu-id="10356-167">Daher entspricht `mcr.microsoft.com/dotnet/core/aspnet:3.1` der .NET Core 3.1-Runtime.</span><span class="sxs-lookup"><span data-stu-id="10356-167">Thus, `mcr.microsoft.com/dotnet/core/aspnet:3.1` is the .NET Core 3.1 runtime.</span></span> <span data-ttu-id="10356-168">Stellen Sie sicher, dass Sie die .NET Core-Runtimeversion pullen, die der Runtime entspricht, die das Ziel Ihres SDK ist.</span><span class="sxs-lookup"><span data-stu-id="10356-168">Make sure that you pull the runtime version that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="10356-169">Beispielsweise verwendet die im vorherigen Abschnitt erstellte App das .NET Core 3.1 SDK, und das Basisimage, auf das in der *Dockerfile*-Datei verwiesen wird, ist mit **3.1** gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="10356-169">For example, the app created in the previous section used the .NET Core 3.1 SDK and the base image referred to in the *Dockerfile* is tagged with **3.1**.</span></span>

<span data-ttu-id="10356-170">Speichern Sie das *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="10356-170">Save the *Dockerfile* file.</span></span> <span data-ttu-id="10356-171">Die Verzeichnisstruktur des Arbeitsordners sollte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="10356-171">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="10356-172">Einige Dateien und Ordner, die sich auf tieferen Ebenen befinden, sind in diesem Beispiel nicht enthalten, um Platz zu sparen:</span><span class="sxs-lookup"><span data-stu-id="10356-172">Some of the deeper-level files and folders have been omitted to save space in the article:</span></span>

```
docker-working
    └──App
        ├──Dockerfile
        ├──NetCore.Docker.csproj
        ├──Program.cs
        ├──bin
        │   └──Release
        │       └──netcoreapp3.1
        │           └──publish
        │               ├──NetCore.Docker.deps.json
        │               ├──NetCore.Docker.exe
        │               ├──NetCore.Docker.dll
        │               ├──NetCore.Docker.pdb
        │               └──NetCore.Docker.runtimeconfig.json
        └──obj
            └──...
```

<span data-ttu-id="10356-173">Führen Sie in Ihrem Terminal den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="10356-173">From your terminal, run the following command:</span></span>

```console
docker build -t counter-image -f Dockerfile .
```

<span data-ttu-id="10356-174">Docker verarbeitet die einzelnen Zeilen aus dem *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="10356-174">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="10356-175">Durch den Punkt `.` im Befehl `docker build` wird Docker angewiesen, im aktuellen Ordner nach einem *Dockerfile* zu suchen.</span><span class="sxs-lookup"><span data-stu-id="10356-175">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="10356-176">Dieser Befehl erstellt das Image und ein lokales Repository namens **counter-image**, das auf dieses Image zeigt.</span><span class="sxs-lookup"><span data-stu-id="10356-176">This command builds the image and creates a local repository named **counter-image** that points to that image.</span></span> <span data-ttu-id="10356-177">Nachdem dieser Befehl abgeschlossen ist, führen Sie `docker images` aus, um eine Liste der installierten Images anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="10356-177">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              e6780479db63        4 days ago          190MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 e6780479db63        4 days ago          190MB
```

<span data-ttu-id="10356-178">Beachten Sie, dass die beiden Images den gleichen **IMAGE ID**-Wert haben.</span><span class="sxs-lookup"><span data-stu-id="10356-178">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="10356-179">Der Wert ist zwischen beiden Images gleich, da der einzige Befehl in der *Dockerfile* war, das neue Image auf Basis eines vorhandenen Images zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="10356-179">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="10356-180">Fügen Sie drei Befehle zum *Dockerfile* hinzu.</span><span class="sxs-lookup"><span data-stu-id="10356-180">Let's add three commands to the *Dockerfile*.</span></span> <span data-ttu-id="10356-181">Jeder Befehl erstellt eine neue Imageebene, wobei der letzte Befehl das Image darstellt, auf das der Repositoryeintrag **counter-image** verweist.</span><span class="sxs-lookup"><span data-stu-id="10356-181">Each command creates a new image layer with the final command representing the **counter-image** repository entry points to.</span></span>

```dockerfile
COPY bin/Release/netcoreapp3.1/publish/ App/
WORKDIR /App
ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
```

<span data-ttu-id="10356-182">Der Befehl `COPY` weist Docker an, den angegebenen Ordner auf Ihrem Computer in einen Ordner im Container zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="10356-182">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="10356-183">In diesem Beispiel wird der Ordner *publish* in einen Ordner mit dem Namen *App* im Container kopiert.</span><span class="sxs-lookup"><span data-stu-id="10356-183">In this example, the *publish* folder is copied to a folder named *App* in the container.</span></span>

<span data-ttu-id="10356-184">Mit dem Befehl `WORKDIR` wird das **aktuelle Verzeichnis** im Container in *App* geändert.</span><span class="sxs-lookup"><span data-stu-id="10356-184">The `WORKDIR` command changes the **current directory** inside of the container to *App*.</span></span>

<span data-ttu-id="10356-185">Der nächste Befehl, `ENTRYPOINT`, weist Docker an, den Container so zu konfigurieren, dass er als ausführbare Datei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="10356-185">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="10356-186">Wenn der Container gestartet wird, wird die `ENTRYPOINT`-Befehl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="10356-186">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="10356-187">Wenn dieser Befehl beendet wird, wird der Container automatisch beendet.</span><span class="sxs-lookup"><span data-stu-id="10356-187">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="10356-188">Führen Sie von Ihrem Terminal aus `docker build -t counter-image -f Dockerfile .` aus, und wenn dieser Befehl abgeschlossen ist, führen Sie `docker images` aus.</span><span class="sxs-lookup"><span data-stu-id="10356-188">From your terminal, run `docker build -t counter-image -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

```console
docker build -t counter-image -f Dockerfile .
Sending build context to Docker daemon  1.117MB
Step 1/4 : FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
 ---> e6780479db63
Step 2/4 : COPY bin/Release/netcoreapp3.1/publish/ App/
 ---> d1732740eed2
Step 3/4 : WORKDIR /App
 ---> Running in b1701a42f3ff
Removing intermediate container b1701a42f3ff
 ---> 919aab5b95e3
Step 4/4 : ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
 ---> Running in c12aebd26ced
Removing intermediate container c12aebd26ced
 ---> cd11c3df9b19
Successfully built cd11c3df9b19
Successfully tagged counter-image:latest

docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              cd11c3df9b19        41 seconds ago      190MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 e6780479db63        4 days ago          190MB
```

<span data-ttu-id="10356-189">Jeder Befehl in der *Dockerfile* generierte eine Ebene und erstellte eine **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="10356-189">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="10356-190">Der endgültige **IMAGE ID**-Wert (Ihrer wird anders sein) ist **cd11c3df9b19**. Als Nächstes erstellen Sie einen Container auf Grundlage dieses Images.</span><span class="sxs-lookup"><span data-stu-id="10356-190">The final **IMAGE ID** (yours will be different) is **cd11c3df9b19** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="10356-191">Erstellen eines Containers</span><span class="sxs-lookup"><span data-stu-id="10356-191">Create a container</span></span>

<span data-ttu-id="10356-192">Da Sie nun ein Image haben, das Ihre App enthält, können Sie einen Container erstellen.</span><span class="sxs-lookup"><span data-stu-id="10356-192">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="10356-193">Für die Erstellung eines Containers haben Sie zwei Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="10356-193">You can create a container in two ways.</span></span> <span data-ttu-id="10356-194">Erstellen Sie zunächst einen neuen Container, der beendet wird.</span><span class="sxs-lookup"><span data-stu-id="10356-194">First, create a new container that is stopped.</span></span>

```console
docker create --name core-counter counter-image
0f281cb3af994fba5d962cc7d482828484ea14ead6bfe386a35e5088c0058851
```

<span data-ttu-id="10356-195">Der obige Befehl `docker create` erstellt einen Container auf Grundlage des Images **counter-image**.</span><span class="sxs-lookup"><span data-stu-id="10356-195">The `docker create` command from above will create a container based on the **counter-image** image.</span></span> <span data-ttu-id="10356-196">Die Ausgabe dieses Befehls zeigt Ihnen die **CONTAINER ID** (Ihre wird anders sein) des erstellten Containers.</span><span class="sxs-lookup"><span data-stu-id="10356-196">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="10356-197">Um eine Liste *aller* Container zu erhalten, verwenden Sie den `docker ps -a`-Befehl:</span><span class="sxs-lookup"><span data-stu-id="10356-197">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED           STATUS     PORTS    NAMES
0f281cb3af99    counter-image    "dotnet NetCore.Dock…"    40 seconds ago    Created             core-counter
```

### <a name="manage-the-container"></a><span data-ttu-id="10356-198">Verwalten des Containers</span><span class="sxs-lookup"><span data-stu-id="10356-198">Manage the container</span></span>

<span data-ttu-id="10356-199">Der Container wurde mit dem spezifischen Namen `core-counter` erstellt, der zum Verwalten des Containers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="10356-199">The container was created with a specific name `core-counter`, this name is used to manage the container.</span></span> <span data-ttu-id="10356-200">Das folgende Beispiel verwendet den Befehl `docker start`, um den Container zu starten, und verwendet dann den Befehl `docker ps`, um nur die laufenden Container anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="10356-200">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
docker start core-counter
core-counter

docker ps
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS          PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    2 minutes ago    Up 11 seconds            core-counter
```

<span data-ttu-id="10356-201">In ähnlicher Weise beendet der Befehl `docker stop` den Container.</span><span class="sxs-lookup"><span data-stu-id="10356-201">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="10356-202">Im folgenden Beispiel wird der Befehl `docker stop` verwendet, um den Container zu beenden, und dann der Befehl `docker ps`, um anzuzeigen, dass keine Container ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="10356-202">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running:</span></span>

```console
docker stop core-counter
core-counter

docker ps
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="10356-203">Herstellen einer Verbindung mit einem Container</span><span class="sxs-lookup"><span data-stu-id="10356-203">Connect to a container</span></span>

<span data-ttu-id="10356-204">Nachdem ein Container ausgeführt wird, können Sie sich mit ihm verbinden, um die Ausgabe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="10356-204">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="10356-205">Verwenden Sie die Befehle `docker start` und `docker attach`, um den Container zu starten und den Ausgabestream anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="10356-205">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="10356-206">In diesem Beispiel wird die Tastenkombination <kbd>STRG+C</kbd> verwendet, um die Trennung vom ausgeführten Container durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="10356-206">In this example, the <kbd>Ctrl+C</kbd> keystroke is used to detach from the running container.</span></span> <span data-ttu-id="10356-207">Diese Tastenkombination beendet den Prozess im Container, sofern nicht anders angegeben, was den Container anhalten würde.</span><span class="sxs-lookup"><span data-stu-id="10356-207">This keystroke will end the process in the container unless otherwise specified, which would stop the container.</span></span> <span data-ttu-id="10356-208">Der Parameter `--sig-proxy=false` stellt sicher, dass <kbd>STRG+C</kbd> den Prozess im Container nicht anhält.</span><span class="sxs-lookup"><span data-stu-id="10356-208">The `--sig-proxy=false` parameter ensures that <kbd>Ctrl+C</kbd> will not stop the process in the container.</span></span>

<span data-ttu-id="10356-209">Nachdem Sie den Container abgetrennt haben, fügen Sie ihn erneut an, um sicherzustellen, dass er noch läuft und zählt.</span><span class="sxs-lookup"><span data-stu-id="10356-209">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
docker start core-counter
core-counter

docker attach --sig-proxy=false core-counter
Counter: 7
Counter: 8
Counter: 9
^C

docker attach --sig-proxy=false core-counter
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="10356-210">Löschen eines Containers</span><span class="sxs-lookup"><span data-stu-id="10356-210">Delete a container</span></span>

<span data-ttu-id="10356-211">Für die Zwecke dieses Artikels wollen Sie nicht, dass Container einfach nur vorhanden sind und nichts tun.</span><span class="sxs-lookup"><span data-stu-id="10356-211">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="10356-212">Löschen Sie den zuvor erstellten Container.</span><span class="sxs-lookup"><span data-stu-id="10356-212">Delete the container you previously created.</span></span> <span data-ttu-id="10356-213">Wenn der Container ausgeführt wird, beenden Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="10356-213">If the container is running, stop it.</span></span>

```console
docker stop core-counter
```

<span data-ttu-id="10356-214">Das folgende Beispiel listet alle Container auf.</span><span class="sxs-lookup"><span data-stu-id="10356-214">The following example lists all containers.</span></span> <span data-ttu-id="10356-215">Anschließend wird der Container mit dem Befehl `docker rm` gelöscht und dann wird ein zweites Mal auf laufende Container überprüft.</span><span class="sxs-lookup"><span data-stu-id="10356-215">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS                        PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    7 minutes ago    Exited (143) 20 seconds ago            core-counter

docker rm core-counter
core-counter

docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="10356-216">Einzelausführung</span><span class="sxs-lookup"><span data-stu-id="10356-216">Single run</span></span>

<span data-ttu-id="10356-217">Docker bietet den Befehl `docker run`, um den Container als einen einzigen Befehl zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="10356-217">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="10356-218">Dieser Befehl erübrigt die Ausführung von `docker create` und dann `docker start`.</span><span class="sxs-lookup"><span data-stu-id="10356-218">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="10356-219">Sie können diesen Befehl auch so einstellen, dass der Container beim Beenden des Containers automatisch gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="10356-219">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="10356-220">Verwenden Sie beispielsweise `docker run -it --rm`, um zwei Dinge zu tun: 1) um sich automatisch über das aktuelle Terminal mit dem Container zu verbinden, und 2) wenn der Container fertig ist, um ihn zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="10356-220">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
docker run -it --rm counter-image
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="10356-221">Der Container übergibt auch Parameter an die Ausführung der .NET Core-App,</span><span class="sxs-lookup"><span data-stu-id="10356-221">The container also passes parameters into the execution of the .NET Core app.</span></span> <span data-ttu-id="10356-222">um diese anzuweisen, nur bis 3 zu zählen und dann 3 zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="10356-222">To instruct the .NET Core app to count only to 3 pass in 3.</span></span>

```console
docker run -it --rm counter-image 3
Counter: 1
Counter: 2
Counter: 3
```

<span data-ttu-id="10356-223">Bei `docker run -it` hält der Befehl <kbd>STRG + C</kbd> den Prozess an, der im Container ausgeführt wird, was wiederum den Container anhält.</span><span class="sxs-lookup"><span data-stu-id="10356-223">With `docker run -it`, the <kbd>Ctrl+C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="10356-224">Da der Parameter `--rm` angegeben wurde, wird der Container beim Anhalten des Prozesses automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="10356-224">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="10356-225">Stellen Sie sicher, dass er nicht vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="10356-225">Verify that it doesn't exist:</span></span>

```console
docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="10356-226">Ändern des EINSTIEGSPUNKTS</span><span class="sxs-lookup"><span data-stu-id="10356-226">Change the ENTRYPOINT</span></span>

<span data-ttu-id="10356-227">Mit dem Befehl `docker run` können Sie auch den Befehl `ENTRYPOINT` aus der *Dockerfile* ändern und etwas anderes ausführen, jedoch nur für diesen Container.</span><span class="sxs-lookup"><span data-stu-id="10356-227">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="10356-228">Verwenden Sie beispielsweise den folgenden Befehl, um `bash` oder `cmd.exe` auszuführen.</span><span class="sxs-lookup"><span data-stu-id="10356-228">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="10356-229">Bearbeiten Sie den Befehl nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="10356-229">Edit the command as necessary.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="10356-230">Windows</span><span class="sxs-lookup"><span data-stu-id="10356-230">Windows</span></span>](#tab/windows)

<span data-ttu-id="10356-231">In diesem Beispiel wird `ENTRYPOINT` in `cmd.exe` geändert.</span><span class="sxs-lookup"><span data-stu-id="10356-231">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="10356-232"><kbd>STRG+C</kbd> wird gedrückt, um den Prozess zu beenden und den Container anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="10356-232"><kbd>Ctrl+C</kbd> is pressed to end the process and stop the container.</span></span>

```console
docker run -it --rm --entrypoint "cmd.exe" counter-image

Microsoft Windows [Version 10.0.17763.379]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\>dir
 Volume in drive C has no label.
 Volume Serial Number is 3005-1E84

 Directory of C:\

04/09/2019  08:46 AM    <DIR>          app
03/07/2019  10:25 AM             5,510 License.txt
04/02/2019  01:35 PM    <DIR>          Program Files
04/09/2019  01:06 PM    <DIR>          Users
04/02/2019  01:35 PM    <DIR>          Windows
               1 File(s)          5,510 bytes
               4 Dir(s)  21,246,517,248 bytes free

C:\>^C
```

#### <a name="linux"></a>[<span data-ttu-id="10356-233">Linux</span><span class="sxs-lookup"><span data-stu-id="10356-233">Linux</span></span>](#tab/linux)

<span data-ttu-id="10356-234">In diesem Beispiel wird `ENTRYPOINT` in `bash` geändert.</span><span class="sxs-lookup"><span data-stu-id="10356-234">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="10356-235">Der Befehl `exit` wird ausgeführt, der den Prozess beendet und den Container stoppt.</span><span class="sxs-lookup"><span data-stu-id="10356-235">The `exit` command is run which ends the process and stop the container.</span></span>

```bash
docker run -it --rm --entrypoint "bash" counter-image
root@b735b9799abf:/App# ls
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.exe  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
root@b735b9799abf:/App# dotnet NetCore.Docker.dll 3
Counter: 1
Counter: 2
Counter: 3
root@b735b9799abf:/App# exit
exit
```

---

## <a name="essential-commands"></a><span data-ttu-id="10356-236">Grundlegende Befehle</span><span class="sxs-lookup"><span data-stu-id="10356-236">Essential commands</span></span>

<span data-ttu-id="10356-237">Docker bietet viele verschiedene Befehle für die Erstellung, Verwaltung und Interaktion mit Containern und Images.</span><span class="sxs-lookup"><span data-stu-id="10356-237">Docker has many different commands that create, manage, and interact with containers and images.</span></span> <span data-ttu-id="10356-238">Diese Docker-Befehle sind für die Verwaltung Ihrer Container unerlässlich:</span><span class="sxs-lookup"><span data-stu-id="10356-238">These Docker commands are essential to managing your containers:</span></span>

- [<span data-ttu-id="10356-239">docker build</span><span class="sxs-lookup"><span data-stu-id="10356-239">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
- [<span data-ttu-id="10356-240">docker run</span><span class="sxs-lookup"><span data-stu-id="10356-240">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
- [<span data-ttu-id="10356-241">docker ps</span><span class="sxs-lookup"><span data-stu-id="10356-241">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
- [<span data-ttu-id="10356-242">docker stop</span><span class="sxs-lookup"><span data-stu-id="10356-242">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
- [<span data-ttu-id="10356-243">docker rm</span><span class="sxs-lookup"><span data-stu-id="10356-243">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
- [<span data-ttu-id="10356-244">docker rmi</span><span class="sxs-lookup"><span data-stu-id="10356-244">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
- [<span data-ttu-id="10356-245">docker image</span><span class="sxs-lookup"><span data-stu-id="10356-245">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="10356-246">Bereinigen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="10356-246">Clean up resources</span></span>

<span data-ttu-id="10356-247">In diesem Tutorial haben Sie Container und Images erstellt.</span><span class="sxs-lookup"><span data-stu-id="10356-247">During this tutorial, you created containers and images.</span></span> <span data-ttu-id="10356-248">Wenn Sie möchten, können Sie diese Ressourcen löschen.</span><span class="sxs-lookup"><span data-stu-id="10356-248">If you want, delete these resources.</span></span> <span data-ttu-id="10356-249">Führen Sie die folgenden Befehle für diese Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="10356-249">Use the following commands to</span></span>

01. <span data-ttu-id="10356-250">Zum Anzeigen aller Container</span><span class="sxs-lookup"><span data-stu-id="10356-250">List all containers</span></span>

    ```console
    docker ps -a
    ```

02. <span data-ttu-id="10356-251">Zum Anhalten aller ausgeführten Container nach Namen</span><span class="sxs-lookup"><span data-stu-id="10356-251">Stop containers that are running by their name.</span></span>

    ```console
    docker stop counter-image
    ```

03. <span data-ttu-id="10356-252">Zum Löschen des Containers</span><span class="sxs-lookup"><span data-stu-id="10356-252">Delete the container</span></span>

    ```console
    docker rm counter-image
    ```

<span data-ttu-id="10356-253">Löschen Sie anschließend alle Images, die Sie nicht mehr auf Ihrem Computer benötigen.</span><span class="sxs-lookup"><span data-stu-id="10356-253">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="10356-254">Löschen Sie das von Ihrer *Dockerfile* erstellte Image und löschen Sie dann das .NET Core-Image, auf dem die *Dockerfile* basiert.</span><span class="sxs-lookup"><span data-stu-id="10356-254">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="10356-255">Sie können die **IMAGE ID** oder die mit **REPOSITORY:TAG** formatierte Zeichenfolge verwenden.</span><span class="sxs-lookup"><span data-stu-id="10356-255">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi counter-image:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

<span data-ttu-id="10356-256">Verwenden Sie den Befehl `docker images`, um eine Liste der installierten Images anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="10356-256">Use the `docker images` command to see a list of images installed.</span></span>

> [!TIP]
> <span data-ttu-id="10356-257">Imagedateien können groß sein.</span><span class="sxs-lookup"><span data-stu-id="10356-257">Image files can be large.</span></span> <span data-ttu-id="10356-258">Normalerweise würden Sie temporäre Container entfernen, die Sie während des Tests und der Entwicklung Ihrer App erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="10356-258">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="10356-259">In der Regel behalten Sie die Basisimages mit installierter Runtime, wenn Sie planen, andere Images auf Basis dieser Runtime zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="10356-259">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="10356-260">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="10356-260">Next steps</span></span>

- [<span data-ttu-id="10356-261">Bereitstellen einer ASP.NET Core-Anwendung im Container.</span><span class="sxs-lookup"><span data-stu-id="10356-261">Learn how to containerize an ASP.NET Core application.</span></span>](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [<span data-ttu-id="10356-262">Schauen Sie sich das Tutorial zu ASP.NET Core-Microservices an.</span><span class="sxs-lookup"><span data-stu-id="10356-262">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [<span data-ttu-id="10356-263">Überprüfen Sie die Azure-Dienste, die Container unterstützen.</span><span class="sxs-lookup"><span data-stu-id="10356-263">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/overview/containers/)
- [<span data-ttu-id="10356-264">Erfahren Sie mehr über Dockerfile-Befehle.</span><span class="sxs-lookup"><span data-stu-id="10356-264">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
- [<span data-ttu-id="10356-265">Containertools in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="10356-265">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
