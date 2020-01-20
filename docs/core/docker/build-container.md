---
title: 'Tutorial: Containerisieren einer .NET Core-App mit Docker'
description: In diesem Tutorial erfahren Sie, wie Sie eine .NET Core-Anwendung mit Docker containerisieren können.
ms.date: 01/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 17d3dfbe58770b19a75be1dad3ae03406584992c
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900115"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="19204-103">Tutorial: Containerisieren einer .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="19204-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="19204-104">In diesem Tutorial erfahren Sie, wie ein Docker-Image erstellt wird, das Ihre .NET Core-Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="19204-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="19204-105">Das Image kann zum Erstellen von Containern für Ihre lokale Entwicklungsumgebung, eine private Cloud oder eine öffentliche Cloud verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19204-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="19204-106">Es werden die folgenden Themen abgedeckt:</span><span class="sxs-lookup"><span data-stu-id="19204-106">You'll learn to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="19204-107">Erstellen und Veröffentlichen einer einfachen .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="19204-107">Create and publish a simple .NET Core app</span></span>
> - <span data-ttu-id="19204-108">Erstellen und Konfigurieren einer Dockerfile-Datei für .NET Core</span><span class="sxs-lookup"><span data-stu-id="19204-108">Create and configure a Dockerfile for .NET Core</span></span>
> - <span data-ttu-id="19204-109">Erstellen eines Docker-Images</span><span class="sxs-lookup"><span data-stu-id="19204-109">Build a Docker image</span></span>
> - <span data-ttu-id="19204-110">Erstellen und Ausführen eines Docker-Containers</span><span class="sxs-lookup"><span data-stu-id="19204-110">Create and run a Docker container</span></span>

<span data-ttu-id="19204-111">Hier erfahren Sie mehr über die Aufgaben für das Erstellen und Bereitstellen von Docker-Containern für eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="19204-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="19204-112">Die *Docker-Plattform* verwendet die *Docker-Engine*, um Pakete schnell als *Docker-Images* zu erstellen und zu packen.</span><span class="sxs-lookup"><span data-stu-id="19204-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="19204-113">Diese Images werden im *Dockerfile*-Format geschrieben, um in einem mehrstufigen Container bereitgestellt und ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="19204-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

> [!TIP]
> <span data-ttu-id="19204-114">Wenn Sie mit einer vorhandenen ASP.NET Core-Anwendung arbeiten, finden Sie weitere Informationen im Tutorial [Informationen zum Containerisieren einer ASP.NET Core-Anwendung](/aspnet/core/host-and-deploy/docker/building-net-docker-images).</span><span class="sxs-lookup"><span data-stu-id="19204-114">If you're working with an existing ASP.NET Core application, see the [Learn how to containerize an ASP.NET Core application](/aspnet/core/host-and-deploy/docker/building-net-docker-images) tutorial.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="19204-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="19204-115">Prerequisites</span></span>

<span data-ttu-id="19204-116">Die folgenden Komponenten müssen installiert sein:</span><span class="sxs-lookup"><span data-stu-id="19204-116">Install the following prerequisites:</span></span>

- <span data-ttu-id="19204-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="19204-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="19204-118">Wenn Sie .NET Core installiert haben, verwenden Sie den Befehl `dotnet --info`, um festzustellen, welches SDK Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="19204-118">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

- [<span data-ttu-id="19204-119">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="19204-119">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

- <span data-ttu-id="19204-120">Ein temporärer Arbeitsordner für das *Dockerfile* und eine .NET Core-Beispiel-App.</span><span class="sxs-lookup"><span data-stu-id="19204-120">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="19204-121">In diesem Tutorial trägt der Arbeitsordner den Namen *docker-working*.</span><span class="sxs-lookup"><span data-stu-id="19204-121">In this tutorial, the name *docker-working* is used as the working folder.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="19204-122">Erstellen der .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="19204-122">Create .NET Core app</span></span>

<span data-ttu-id="19204-123">Sie benötigen eine.NET Core-App, die der Docker-Container ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="19204-123">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="19204-124">Öffnen Sie Ihr Terminal, erstellen Sie einen Arbeitsordner, falls noch nicht geschehen, und geben Sie den Ordnernamen ein.</span><span class="sxs-lookup"><span data-stu-id="19204-124">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="19204-125">Führen Sie im Arbeitsordner den folgenden Befehl aus, um ein neues Projekt im Unterverzeichnis *app* zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="19204-125">In the working folder, run the following command to create a new project in a subdirectory named *app*:</span></span>

```dotnetcli
dotnet new console -o app -n myapp
```

<span data-ttu-id="19204-126">Ihre Ordnerstruktur sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="19204-126">Your folder tree will look like the following:</span></span>

```
docker-working
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.dgspec.json
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

<span data-ttu-id="19204-127">Über den Befehl `dotnet new` wird ein neuer Ordner namens *app* erstellt und eine „Hallo Welt“-App generiert.</span><span class="sxs-lookup"><span data-stu-id="19204-127">The `dotnet new` command creates a new folder named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="19204-128">Geben Sie den Ordner *app* ein, und führen Sie den Befehl `dotnet run` aus.</span><span class="sxs-lookup"><span data-stu-id="19204-128">Enter the *app* folder and run the command `dotnet run`.</span></span> <span data-ttu-id="19204-129">Die folgende Ausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="19204-129">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="19204-130">Die Standardvorlage erstellt eine App, die über das Terminal druckt und dann beendet wird.</span><span class="sxs-lookup"><span data-stu-id="19204-130">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="19204-131">Für dieses Tutorial verwenden Sie eine App, die auf unbestimmte Zeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="19204-131">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="19204-132">Öffnen Sie die Datei *Program.cs* in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="19204-132">Open the *Program.cs* file in a text editor.</span></span> <span data-ttu-id="19204-133">Diese sollte derzeit wie der folgende Code aussehen:</span><span class="sxs-lookup"><span data-stu-id="19204-133">It should currently look like the following code:</span></span>

```csharp
using System;

namespace myapp
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

<span data-ttu-id="19204-134">Ersetzen Sie die Datei durch den folgenden Code, der die Zahlen pro Sekunde zählt:</span><span class="sxs-lookup"><span data-stu-id="19204-134">Replace the file with the following code that counts numbers every second:</span></span>

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

<span data-ttu-id="19204-135">Speichern Sie die Datei, und testen Sie das Programm erneut mit `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="19204-135">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="19204-136">Denken Sie daran, dass diese App auf unbestimmte Zeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="19204-136">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="19204-137">Verwenden Sie zum Beenden den Abbruchbefehl <kbd>STRG</kbd>+<kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="19204-137">Use the cancel command <kbd>CTRL</kbd>+<kbd>C</kbd> to stop it.</span></span> <span data-ttu-id="19204-138">Die folgende Ausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="19204-138">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="19204-139">Wenn Sie eine Zahl auf der Kommandozeile an die App übergeben, zählt sie nur bis zu diesem Betrag und wird dann beendet.</span><span class="sxs-lookup"><span data-stu-id="19204-139">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="19204-140">Probieren Sie es mit`dotnet run -- 5`, um bis Fünf zu zählen.</span><span class="sxs-lookup"><span data-stu-id="19204-140">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="19204-141">Jegliche Parameter, die auf `--` folgen, werden nicht an den Befehl `dotnet run`, sondern an Ihre Anwendung übergeben.</span><span class="sxs-lookup"><span data-stu-id="19204-141">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="19204-142">Veröffentlichen der .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="19204-142">Publish .NET Core app</span></span>

<span data-ttu-id="19204-143">Bevor Sie Ihre .NET Core-App zum Docker-Image hinzufügen, veröffentlichen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="19204-143">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="19204-144">Sie sollten sich vergewissern, dass der Container die veröffentlichte Version der App ausführt, wenn er gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="19204-144">You want to make sure that the container runs the published version of the app when it's started.</span></span>

<span data-ttu-id="19204-145">Geben Sie im Arbeitsordner den Ordner *app* mit dem exemplarischen Quellcode ein, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="19204-145">From the working folder, enter the *app* folder with the example source code and run the following command:</span></span>

```dotnetcli
dotnet publish -c Release
```

<span data-ttu-id="19204-146">Dieser Befehl kompiliert Ihre App in den Ordner *publish*.</span><span class="sxs-lookup"><span data-stu-id="19204-146">This command compiles your app to the *publish* folder.</span></span> <span data-ttu-id="19204-147">Der Pfad zum Ordner *publish* aus dem Arbeitsordner sollte wie folgt lauten: `.\app\bin\Release\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="19204-147">The path to the *publish* folder from the working folder should be `.\app\bin\Release\netcoreapp3.1\publish\`</span></span>

<span data-ttu-id="19204-148">Rufen Sie aus dem Ordner *app* eine Verzeichnisliste des Veröffentlichungsordners ab, um sicherzustellen, dass die Datei *myapp.dll* erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="19204-148">From the *app* folder, get a directory listing of the publish folder to verify that the *myapp.dll* file was created.</span></span> 

```console
> dir bin\Release\netcoreapp3.1\publish

    Directory:  C:\docker-working\app\bin\Release\netcoreapp3.1\publish

01/09/2020  11:41 AM    <DIR>          .
01/09/2020  11:41 AM    <DIR>          ..
01/09/2020  11:41 AM               407 myapp.deps.json
01/09/2020  12:15 PM             4,608 myapp.dll
01/09/2020  12:15 PM           169,984 myapp.exe
01/09/2020  12:15 PM               736 myapp.pdb
01/09/2020  11:41 AM               154 myapp.runtimeconfig.json
```

<span data-ttu-id="19204-149">Wenn Sie Linux oder macOS verwenden, verwenden Sie den Befehl `ls`, um eine Verzeichnisauflistung abzurufen, und überprüfen Sie, ob die Datei *myapp.dll* erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="19204-149">If you're using Linux or macOS, use the `ls` command to get a directory listing and verify that the *myapp.dll* file was created.</span></span>

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a><span data-ttu-id="19204-150">Erstellen der Dockerfile</span><span class="sxs-lookup"><span data-stu-id="19204-150">Create the Dockerfile</span></span>

<span data-ttu-id="19204-151">Die *Dockerfile*-Datei wird vom Befehl `docker build` zum Erstellen des Containerimage verwendet.</span><span class="sxs-lookup"><span data-stu-id="19204-151">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="19204-152">Diese Datei ist eine Textdatei mit dem Namen *Dockerfile*, die keine Erweiterung besitzt.</span><span class="sxs-lookup"><span data-stu-id="19204-152">This file is a text file named *Dockerfile* that doesn't have an extension.</span></span>

<span data-ttu-id="19204-153">Navigieren Sie in Ihrem Terminal ein Verzeichnis nach oben zu dem Arbeitsordner, den Sie zu Beginn erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="19204-153">In your terminal, navigate up a directory to the working folder you created at the start.</span></span> <span data-ttu-id="19204-154">Erstellen Sie eine Datei namens *Dockerfile* in Ihrem Arbeitsordner, und öffnen Sie diese in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="19204-154">Create a file named *Dockerfile* in your working folder and open it in a text editor.</span></span> <span data-ttu-id="19204-155">Abhängig von der Art der Anwendung, die Sie containerisieren möchten, wählen Sie entweder die ASP.NET Core-Runtime oder die .NET Core-Runtime aus.</span><span class="sxs-lookup"><span data-stu-id="19204-155">Depending on the type of application you're going to containerize, you'll choose either the ASP.NET Core runtime or the .NET Core runtime.</span></span> <span data-ttu-id="19204-156">Wählen Sie im Zweifelsfall die ASP.NET Core-Runtime aus, die die .NET Core-Runtime enthält.</span><span class="sxs-lookup"><span data-stu-id="19204-156">When in doubt, choose the ASP.NET Core runtime, which includes the .NET Core runtime.</span></span> <span data-ttu-id="19204-157">In diesem Tutorial wird das ASP.NET Core-Runtimeimage verwendet, aber die in den vorherigen Abschnitten erstellte Anwendung ist eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="19204-157">This tutorial will use the ASP.NET Core runtime image, but the application created in the previous sections is an .NET Core application.</span></span>

- <span data-ttu-id="19204-158">ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="19204-158">ASP.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
  ```

- <span data-ttu-id="19204-159">.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="19204-159">.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/runtime:3.1
  ```

<span data-ttu-id="19204-160">Der Befehl `FROM` weist Docker an, das mit **3.1** gekennzeichnete Image aus dem angegebenen Repository herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="19204-160">The `FROM` command tells Docker to pull down the image tagged **3.1** from the specified repository.</span></span> <span data-ttu-id="19204-161">Stellen Sie sicher, dass Sie die .NET Core-Runtimeversion pullen, die der Runtime entspricht, die das Ziel Ihres SDK ist.</span><span class="sxs-lookup"><span data-stu-id="19204-161">Make sure that you pull the runtime version that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="19204-162">Beispielsweise verwendet die im vorherigen Abschnitt erstellte App das .NET Core 3.1 SDK, und das Basisimage, auf das in der *Dockerfile*-Datei verwiesen wird, ist mit **3.1** gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="19204-162">For example, the app created in the previous section used the .NET Core 3.1 SDK and the base image referred to in the *Dockerfile* is tagged with **3.1**.</span></span>

<span data-ttu-id="19204-163">Speichern Sie das *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="19204-163">Save the *Dockerfile* file.</span></span> <span data-ttu-id="19204-164">Die Verzeichnisstruktur des Arbeitsordners sollte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="19204-164">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="19204-165">Einige Dateien und Ordner, die sich auf tieferen Ebenen befinden, sind in diesem Beispiel nicht enthalten, um Platz zu sparen:</span><span class="sxs-lookup"><span data-stu-id="19204-165">Some of the deeper-level files and folders have been cut to save space in the article:</span></span>

```
docker-working
│   Dockerfile
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp3.1
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.exe
    │                   myapp.dll
    │                   myapp.pdb
    │                   myapp.runtimeconfig.json
    │
    └───obj
```

<span data-ttu-id="19204-166">Führen Sie in Ihrem Terminal den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="19204-166">From your terminal, run the following command:</span></span>

```console
docker build -t myimage -f Dockerfile .
```

<span data-ttu-id="19204-167">Docker verarbeitet die einzelnen Zeilen aus dem *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="19204-167">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="19204-168">Durch den Punkt `.` im Befehl `docker build` wird Docker angewiesen, im aktuellen Ordner nach einem *Dockerfile* zu suchen.</span><span class="sxs-lookup"><span data-stu-id="19204-168">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="19204-169">Dieser Befehl erstellt das Image und ein lokales Repository namens **myimage**, das auf dieses Image zeigt.</span><span class="sxs-lookup"><span data-stu-id="19204-169">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="19204-170">Nachdem dieser Befehl abgeschlossen ist, führen Sie `docker images` aus, um eine Liste der installierten Images anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="19204-170">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              38db0eb8f648        4 weeks ago         346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

<span data-ttu-id="19204-171">Beachten Sie, dass die beiden Images den gleichen **IMAGE ID**-Wert haben.</span><span class="sxs-lookup"><span data-stu-id="19204-171">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="19204-172">Der Wert ist zwischen beiden Images gleich, da der einzige Befehl in der *Dockerfile* war, das neue Image auf Basis eines vorhandenen Images zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="19204-172">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="19204-173">Fügen Sie zwei Befehle zur *Dockerfile* hinzu.</span><span class="sxs-lookup"><span data-stu-id="19204-173">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="19204-174">Jeder Befehl erstellt eine neue Imageebene, wobei der letzte Befehl das Image darstellt, auf das der Repositoryeintrag **myimage** verweist.</span><span class="sxs-lookup"><span data-stu-id="19204-174">Each command creates a new image layer with the final command representing the image the **myimage** repository entry points to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp3.1/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="19204-175">Der Befehl `COPY` weist Docker an, den angegebenen Ordner auf Ihrem Computer in einen Ordner im Container zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="19204-175">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="19204-176">In diesem Beispiel wird der Ordner *publish* in einen Ordner mit dem Namen *app* im Container kopiert.</span><span class="sxs-lookup"><span data-stu-id="19204-176">In this example, the *publish* folder is copied to a folder named *app* in the container.</span></span>

<span data-ttu-id="19204-177">Der nächste Befehl, `ENTRYPOINT`, weist Docker an, den Container so zu konfigurieren, dass er als ausführbare Datei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="19204-177">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="19204-178">Wenn der Container gestartet wird, wird die `ENTRYPOINT`-Befehl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="19204-178">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="19204-179">Wenn dieser Befehl beendet wird, wird der Container automatisch beendet.</span><span class="sxs-lookup"><span data-stu-id="19204-179">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="19204-180">Führen Sie von Ihrem Terminal aus `docker build -t myimage -f Dockerfile .` aus, und wenn dieser Befehl abgeschlossen ist, führen Sie `docker images` aus.</span><span class="sxs-lookup"><span data-stu-id="19204-180">From your terminal, run `docker build -t myimage -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  1.624MB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
 ---> 38db0eb8f648
Step 2/3 : COPY app/bin/Release/netcoreapp3.1/publish/ app/
 ---> 37873673e468
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in d8deb7b3aa9e
Removing intermediate container d8deb7b3aa9e
 ---> 0d602ca35c1d
Successfully built 0d602ca35c1d
Successfully tagged myimage:latest

> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              0d602ca35c1d        4 seconds ago       346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

<span data-ttu-id="19204-181">Jeder Befehl in der *Dockerfile* generierte eine Ebene und erstellte eine **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="19204-181">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="19204-182">Die endgültige **IMAGE ID** (Ihre wird anders sein) ist **ddcc6646461b**. Als nächstes werden Sie einen Container basierend auf diesem Image erstellen.</span><span class="sxs-lookup"><span data-stu-id="19204-182">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="19204-183">Erstellen eines Containers</span><span class="sxs-lookup"><span data-stu-id="19204-183">Create a container</span></span>

<span data-ttu-id="19204-184">Da Sie nun ein Image haben, das Ihre App enthält, können Sie einen Container erstellen.</span><span class="sxs-lookup"><span data-stu-id="19204-184">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="19204-185">Für die Erstellung eines Containers haben Sie zwei Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="19204-185">You can create a container in two ways.</span></span> <span data-ttu-id="19204-186">Erstellen Sie zunächst einen neuen Container, der beendet wird.</span><span class="sxs-lookup"><span data-stu-id="19204-186">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
ceda87b219a4e55e9ad5d833ee1a7ea4da21b5ea7ce5a7d08f3051152e784944
```

<span data-ttu-id="19204-187">Der Befehl `docker create` von oben erstellt einen Container basierend auf dem Image **myimage**.</span><span class="sxs-lookup"><span data-stu-id="19204-187">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="19204-188">Die Ausgabe dieses Befehls zeigt Ihnen die **CONTAINER ID** (Ihre wird anders sein) des erstellten Containers.</span><span class="sxs-lookup"><span data-stu-id="19204-188">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="19204-189">Um eine Liste *aller* Container zu erhalten, verwenden Sie den `docker ps -a`-Befehl:</span><span class="sxs-lookup"><span data-stu-id="19204-189">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               gallant_lehmann
```

### <a name="manage-the-container"></a><span data-ttu-id="19204-190">Verwalten des Containers</span><span class="sxs-lookup"><span data-stu-id="19204-190">Manage the container</span></span>

<span data-ttu-id="19204-191">Jedem Container ist ein Zufallsname zugeordnet, mit dem Sie auf diese Containerinstanz verweisen können.</span><span class="sxs-lookup"><span data-stu-id="19204-191">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="19204-192">Beispielsweise wurde für den automatisch erstellten Container der Name **gallant_lehmann** gewählt (Ihr Name wird anders lauten), und dieser Name kann zum Starten des Containers verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19204-192">For example, the container that was created automatically chose the name **gallant_lehmann** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="19204-193">Mit dem Parameter `docker create --name` überschreiben Sie den automatischen Namen durch einen bestimmten Namen.</span><span class="sxs-lookup"><span data-stu-id="19204-193">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="19204-194">Das folgende Beispiel verwendet den Befehl `docker start`, um den Container zu starten, und verwendet dann den Befehl `docker ps`, um nur die laufenden Container anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="19204-194">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           gallant_lehmann
```

<span data-ttu-id="19204-195">In ähnlicher Weise beendet der Befehl `docker stop` den Container.</span><span class="sxs-lookup"><span data-stu-id="19204-195">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="19204-196">Im folgenden Beispiel wird der Befehl `docker stop` verwendet, um den Container zu beenden, und dann der Befehl `docker ps`, um anzuzeigen, dass keine Container ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="19204-196">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running:</span></span>

```console
> docker stop gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="19204-197">Herstellen einer Verbindung mit einem Container</span><span class="sxs-lookup"><span data-stu-id="19204-197">Connect to a container</span></span>

<span data-ttu-id="19204-198">Nachdem ein Container ausgeführt wird, können Sie sich mit ihm verbinden, um die Ausgabe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="19204-198">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="19204-199">Verwenden Sie die Befehle `docker start` und `docker attach`, um den Container zu starten und den Ausgabestream anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="19204-199">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="19204-200">In diesem Beispiel wird die Tastenkombination <kbd>STRG+C</kbd> verwendet, um die Trennung vom ausgeführten Container auszuführen.</span><span class="sxs-lookup"><span data-stu-id="19204-200">In this example, the <kbd>CTRL + C</kbd> keystroke is used to detach from the running container.</span></span> <span data-ttu-id="19204-201">Durch diese Tastenkombination kann der Prozess im Container tatsächlich beendet werden, wodurch auch der Container beendet wird.</span><span class="sxs-lookup"><span data-stu-id="19204-201">This keystroke may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="19204-202">Der Parameter `--sig-proxy=false` stellt sicher, dass der Prozess im Container durch das Drücken von <kbd>STRG+C</kbd> nicht angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="19204-202">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> won't stop the process in the container.</span></span>

<span data-ttu-id="19204-203">Nachdem Sie den Container abgetrennt haben, fügen Sie ihn erneut an, um sicherzustellen, dass er noch läuft und zählt.</span><span class="sxs-lookup"><span data-stu-id="19204-203">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
> docker start gallant_lehmann
gallant_lehmann

> docker attach --sig-proxy=false gallant_lehmann
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false gallant_lehmann
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="19204-204">Löschen eines Containers</span><span class="sxs-lookup"><span data-stu-id="19204-204">Delete a container</span></span>

<span data-ttu-id="19204-205">Für die Zwecke dieses Artikels wollen Sie nicht, dass Container einfach nur vorhanden sind und nichts tun.</span><span class="sxs-lookup"><span data-stu-id="19204-205">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="19204-206">Löschen Sie den zuvor erstellten Container.</span><span class="sxs-lookup"><span data-stu-id="19204-206">Delete the container you previously created.</span></span> <span data-ttu-id="19204-207">Wenn der Container ausgeführt wird, beenden Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="19204-207">If the container is running, stop it.</span></span>

```console
> docker stop gallant_lehmann
```

<span data-ttu-id="19204-208">Das folgende Beispiel listet alle Container auf.</span><span class="sxs-lookup"><span data-stu-id="19204-208">The following example lists all containers.</span></span> <span data-ttu-id="19204-209">Anschließend wird der Container mit dem Befehl `docker rm` gelöscht und dann wird ein zweites Mal auf laufende Container überprüft.</span><span class="sxs-lookup"><span data-stu-id="19204-209">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             gallant_lehmann

> docker rm gallant_lehmann
gallant_lehmann

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="19204-210">Einzelausführung</span><span class="sxs-lookup"><span data-stu-id="19204-210">Single run</span></span>

<span data-ttu-id="19204-211">Docker bietet den Befehl `docker run`, um den Container als einen einzigen Befehl zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="19204-211">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="19204-212">Dieser Befehl erübrigt die Ausführung von `docker create` und dann `docker start`.</span><span class="sxs-lookup"><span data-stu-id="19204-212">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="19204-213">Sie können diesen Befehl auch so einstellen, dass der Container beim Beenden des Containers automatisch gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="19204-213">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="19204-214">Verwenden Sie beispielsweise `docker run -it --rm`, um zwei Dinge zu tun: 1) um sich automatisch über das aktuelle Terminal mit dem Container zu verbinden, und 2) wenn der Container fertig ist, um ihn zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="19204-214">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="19204-215">Bei `docker run -it` beendet der Befehl <kbd>STRG + C</kbd> den Prozess, der im Container ausgeführt wird, was wiederum den Container beendet.</span><span class="sxs-lookup"><span data-stu-id="19204-215">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="19204-216">Da der Parameter `--rm` angegeben wurde, wird der Container beim Anhalten des Prozesses automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="19204-216">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="19204-217">Stellen Sie sicher, dass er nicht vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="19204-217">Verify that it doesn't exist:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="19204-218">Ändern des EINSTIEGSPUNKTS</span><span class="sxs-lookup"><span data-stu-id="19204-218">Change the ENTRYPOINT</span></span>

<span data-ttu-id="19204-219">Mit dem Befehl `docker run` können Sie auch den Befehl `ENTRYPOINT` aus der *Dockerfile* ändern und etwas anderes ausführen, jedoch nur für diesen Container.</span><span class="sxs-lookup"><span data-stu-id="19204-219">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="19204-220">Verwenden Sie beispielsweise den folgenden Befehl, um `bash` oder `cmd.exe` auszuführen.</span><span class="sxs-lookup"><span data-stu-id="19204-220">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="19204-221">Bearbeiten Sie den Befehl nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="19204-221">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="19204-222">Windows</span><span class="sxs-lookup"><span data-stu-id="19204-222">Windows</span></span>

<span data-ttu-id="19204-223">In diesem Beispiel wird `ENTRYPOINT` in `cmd.exe` geändert.</span><span class="sxs-lookup"><span data-stu-id="19204-223">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="19204-224"><kbd>STRG</kbd>+<kbd>C</kbd> wird gedrückt, um den Prozess zu beenden und den Container anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="19204-224"><kbd>CTRL</kbd>+<kbd>C</kbd> is pressed to end the process and stop the container.</span></span>

```console
> docker run -it --rm --entrypoint "cmd.exe" myimage

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

#### <a name="linux"></a><span data-ttu-id="19204-225">Linux</span><span class="sxs-lookup"><span data-stu-id="19204-225">Linux</span></span>

<span data-ttu-id="19204-226">In diesem Beispiel wird `ENTRYPOINT` in `bash` geändert.</span><span class="sxs-lookup"><span data-stu-id="19204-226">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="19204-227">Der Befehl `quit` wird ausgeführt, der den Prozess beendet und den Container stoppt.</span><span class="sxs-lookup"><span data-stu-id="19204-227">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="19204-228">Grundlegende Befehle</span><span class="sxs-lookup"><span data-stu-id="19204-228">Essential commands</span></span>

<span data-ttu-id="19204-229">Docker hat viele verschiedene Befehle, die behandeln, was Sie mit Ihrem Container und Ihren Images machen wollen.</span><span class="sxs-lookup"><span data-stu-id="19204-229">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="19204-230">Diese Docker-Befehle sind für die Verwaltung Ihrer Container unerlässlich:</span><span class="sxs-lookup"><span data-stu-id="19204-230">These Docker commands are essential to managing your containers:</span></span>

- [<span data-ttu-id="19204-231">docker build</span><span class="sxs-lookup"><span data-stu-id="19204-231">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
- [<span data-ttu-id="19204-232">docker run</span><span class="sxs-lookup"><span data-stu-id="19204-232">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
- [<span data-ttu-id="19204-233">docker ps</span><span class="sxs-lookup"><span data-stu-id="19204-233">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
- [<span data-ttu-id="19204-234">docker stop</span><span class="sxs-lookup"><span data-stu-id="19204-234">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
- [<span data-ttu-id="19204-235">docker rm</span><span class="sxs-lookup"><span data-stu-id="19204-235">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
- [<span data-ttu-id="19204-236">docker rmi</span><span class="sxs-lookup"><span data-stu-id="19204-236">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
- [<span data-ttu-id="19204-237">docker image</span><span class="sxs-lookup"><span data-stu-id="19204-237">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="19204-238">Bereinigen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="19204-238">Clean up resources</span></span>

<span data-ttu-id="19204-239">In diesem Tutorial haben Sie Container und Images erstellt.</span><span class="sxs-lookup"><span data-stu-id="19204-239">During this tutorial, you created containers and images.</span></span> <span data-ttu-id="19204-240">Wenn Sie möchten, können Sie diese Ressourcen löschen.</span><span class="sxs-lookup"><span data-stu-id="19204-240">If you want, delete these resources.</span></span> <span data-ttu-id="19204-241">Führen Sie die folgenden Befehle für diese Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="19204-241">Use the following commands to</span></span>

01. <span data-ttu-id="19204-242">Zum Anzeigen aller Container</span><span class="sxs-lookup"><span data-stu-id="19204-242">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="19204-243">Zum Anhalten aller ausgeführten Container.</span><span class="sxs-lookup"><span data-stu-id="19204-243">Stop containers that are running.</span></span> <span data-ttu-id="19204-244">`CONTAINER_NAME` steht für automatisch dem Container zugewiesenen Namen.</span><span class="sxs-lookup"><span data-stu-id="19204-244">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="19204-245">Zum Löschen des Containers</span><span class="sxs-lookup"><span data-stu-id="19204-245">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="19204-246">Löschen Sie anschließend alle Images, die Sie nicht mehr auf Ihrem Computer benötigen.</span><span class="sxs-lookup"><span data-stu-id="19204-246">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="19204-247">Löschen Sie das von Ihrer *Dockerfile* erstellte Image und löschen Sie dann das .NET Core-Image, auf dem die *Dockerfile* basiert.</span><span class="sxs-lookup"><span data-stu-id="19204-247">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="19204-248">Sie können die **IMAGE ID** oder die mit **REPOSITORY:TAG** formatierte Zeichenfolge verwenden.</span><span class="sxs-lookup"><span data-stu-id="19204-248">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

<span data-ttu-id="19204-249">Verwenden Sie den Befehl `docker images`, um eine Liste der installierten Images anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="19204-249">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="19204-250">Imagedateien können groß sein.</span><span class="sxs-lookup"><span data-stu-id="19204-250">Image files can be large.</span></span> <span data-ttu-id="19204-251">Normalerweise würden Sie temporäre Container entfernen, die Sie während des Tests und der Entwicklung Ihrer App erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="19204-251">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="19204-252">In der Regel behalten Sie die Basisimages mit installierter Runtime, wenn Sie planen, andere Images auf Basis dieser Runtime zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="19204-252">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="19204-253">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="19204-253">Next steps</span></span>

- [<span data-ttu-id="19204-254">Bereitstellen einer ASP.NET Core-Anwendung im Container.</span><span class="sxs-lookup"><span data-stu-id="19204-254">Learn how to containerize an ASP.NET Core application.</span></span>](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [<span data-ttu-id="19204-255">Schauen Sie sich das Tutorial zu ASP.NET Core-Microservices an.</span><span class="sxs-lookup"><span data-stu-id="19204-255">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [<span data-ttu-id="19204-256">Überprüfen Sie die Azure-Dienste, die Container unterstützen.</span><span class="sxs-lookup"><span data-stu-id="19204-256">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/overview/containers/)
- [<span data-ttu-id="19204-257">Erfahren Sie mehr über Dockerfile-Befehle.</span><span class="sxs-lookup"><span data-stu-id="19204-257">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
- [<span data-ttu-id="19204-258">Containertools in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="19204-258">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
