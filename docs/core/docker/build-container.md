---
title: 'Tutorial: Containerisieren einer .NET Core-App mit Docker'
description: In diesem Tutorial erfahren Sie, wie Sie eine .NET Core-Anwendung mit Docker containerisieren können.
ms.date: 04/10/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: fcbac0e0d17d2481d42e715a7f2790586e31d085
ms.sourcegitcommit: 8080271c246b57f4fb68c28369634bff46843424
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2019
ms.locfileid: "59553835"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="f7e93-103">Tutorial: Containerisieren einer .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="f7e93-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="f7e93-104">In diesem Tutorial erfahren Sie, wie ein Docker-Image erstellt wird, das Ihre .NET Core-Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="f7e93-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="f7e93-105">Das Image kann zum Erstellen von Containern für Ihre lokale Entwicklungsumgebung, eine private Cloud oder eine öffentliche Cloud verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f7e93-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="f7e93-106">Es werden die folgenden Themen abgedeckt:</span><span class="sxs-lookup"><span data-stu-id="f7e93-106">You'll learn to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="f7e93-107">Erstellen und Veröffentlichen einer einfachen .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="f7e93-107">Create and publish a simple .NET Core app</span></span>
> * <span data-ttu-id="f7e93-108">Erstellen und Konfigurieren einer Dockerfile-Datei für .NET Core</span><span class="sxs-lookup"><span data-stu-id="f7e93-108">Create and configure a Dockerfile for .NET Core</span></span>
> * <span data-ttu-id="f7e93-109">Erstellen eines Docker-Images</span><span class="sxs-lookup"><span data-stu-id="f7e93-109">Build a Docker image</span></span>
> * <span data-ttu-id="f7e93-110">Erstellen und Ausführen eines Docker-Containers</span><span class="sxs-lookup"><span data-stu-id="f7e93-110">Create and run a Docker container</span></span>

<span data-ttu-id="f7e93-111">Hier erfahren Sie mehr über die Aufgaben für das Erstellen und Bereitstellen von Docker-Containern für eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f7e93-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="f7e93-112">Die *Docker-Plattform* verwendet die *Docker-Engine*, um Pakete schnell als *Docker-Images* zu erstellen und zu packen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="f7e93-113">Diese Images werden im *Dockerfile*-Format geschrieben, um in einem mehrstufigen Container bereitgestellt und ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="f7e93-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f7e93-114">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="f7e93-114">Prerequisites</span></span>

<span data-ttu-id="f7e93-115">Die folgenden Komponenten müssen installiert sein:</span><span class="sxs-lookup"><span data-stu-id="f7e93-115">Install the following prerequisites:</span></span>

- <span data-ttu-id="f7e93-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)\\</span><span class="sxs-lookup"><span data-stu-id="f7e93-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)\\</span></span>
<span data-ttu-id="f7e93-117">Wenn Sie .NET Core installiert haben, verwenden Sie den Befehl `dotnet --info`, um festzustellen, welches SDK Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7e93-117">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

- [<span data-ttu-id="f7e93-118">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="f7e93-118">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

- <span data-ttu-id="f7e93-119">Eine temporäre Arbeitsverzeichnis für die *Dockerfile-Datei* und .NET Core-Beispiel-App.</span><span class="sxs-lookup"><span data-stu-id="f7e93-119">A temporary working directory for the *Dockerfile* and .NET Core example app.</span></span>

### <a name="use-sdk-version-22"></a><span data-ttu-id="f7e93-120">Verwenden der SDK-Version 2.2</span><span class="sxs-lookup"><span data-stu-id="f7e93-120">Use SDK version 2.2</span></span>

<span data-ttu-id="f7e93-121">Wenn Sie ein neueres SDK als 3.0 verwenden, stellen Sie sicher, dass Ihre App gezwungen ist, das SDK 2.2 zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7e93-121">If you're using an SDK that is newer, like 3.0, make sure that your app is forced to use the 2.2 SDK.</span></span> <span data-ttu-id="f7e93-122">Erstellen Sie eine Datei namens `global.json` in Ihrem Arbeitsverzeichnis und fügen Sie den folgenden JSON-Code ein:</span><span class="sxs-lookup"><span data-stu-id="f7e93-122">Create a file named `global.json` in your working directory and paste in the following json code:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

<span data-ttu-id="f7e93-123">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="f7e93-123">Save this file.</span></span> <span data-ttu-id="f7e93-124">Das Vorhandensein einer Datei zwingt .NET Core, Version 2.2 für jeden `dotnet`-Befehl zu verwenden, der aus diesem Verzeichnis und darunter aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f7e93-124">The presence of file will force .NET Core to use version 2.2 for any `dotnet` command called from this directory and below.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="f7e93-125">Erstellen der .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="f7e93-125">Create .NET Core app</span></span>

<span data-ttu-id="f7e93-126">Sie benötigen eine.NET Core-App, die der Docker-Container ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="f7e93-126">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="f7e93-127">Öffnen Sie Ihr Terminal, erstellen Sie ein Arbeitsverzeichnis und geben Sie es ein.</span><span class="sxs-lookup"><span data-stu-id="f7e93-127">Open your terminal, create a working directory, and enter it.</span></span> <span data-ttu-id="f7e93-128">Führen Sie im Arbeitsverzeichnis den folgenden Befehl aus, um ein neues Projekt in einem Unterverzeichnis namens „app“ zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f7e93-128">In the working directory, run the following command to create a new project in a subdirectory named app:</span></span>

```console
dotnet new console -o app -n myapp
```

<span data-ttu-id="f7e93-129">Dieser Befehl erstellt ein neues Verzeichnis namens *app* und generiert eine „Hallo Welt“-App.</span><span class="sxs-lookup"><span data-stu-id="f7e93-129">That command creates a new directory named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="f7e93-130">Sie können diese App testen, um zu sehen, wie sie funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f7e93-130">You can test this app to see what it does.</span></span> <span data-ttu-id="f7e93-131">Geben Sie das *app*-Verzeichnis ein, und führen Sie den Befehl `dotnet run` aus.</span><span class="sxs-lookup"><span data-stu-id="f7e93-131">Enter the *app* directory and execute the command `dotnet run`.</span></span> <span data-ttu-id="f7e93-132">Die folgende Ausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f7e93-132">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="f7e93-133">Die Standardvorlage erstellt eine App, die über das Terminal druckt und dann beendet wird.</span><span class="sxs-lookup"><span data-stu-id="f7e93-133">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="f7e93-134">Für dieses Tutorial verwenden Sie eine App, die auf unbestimmte Zeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7e93-134">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="f7e93-135">Öffnen Sie die Datei **Program.cs** in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="f7e93-135">Open the **Program.cs** file in a text editor.</span></span> <span data-ttu-id="f7e93-136">Diese sollte derzeit wie der folgende Code aussehen:</span><span class="sxs-lookup"><span data-stu-id="f7e93-136">It should currently look like the following code:</span></span>

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

<span data-ttu-id="f7e93-137">Ersetzen Sie die Datei durch den folgenden Code, der die Zahlen pro Sekunde zählt:</span><span class="sxs-lookup"><span data-stu-id="f7e93-137">Replace the file with the following code that counts numbers every second:</span></span>

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
            while(max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

<span data-ttu-id="f7e93-138">Speichern Sie die Datei, und testen Sie das Programm erneut mit `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="f7e93-138">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="f7e93-139">Denken Sie daran, dass diese App auf unbestimmte Zeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7e93-139">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="f7e93-140">Verwenden Sie zum Beenden den Befehl „Abbrechen“ <kbd>STRG + C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="f7e93-140">Use the cancel command <kbd>CTRL + C</kbd> to stop it.</span></span> <span data-ttu-id="f7e93-141">Die folgende Ausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f7e93-141">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="f7e93-142">Wenn Sie eine Zahl auf der Kommandozeile an die App übergeben, zählt sie nur bis zu diesem Betrag und wird dann beendet.</span><span class="sxs-lookup"><span data-stu-id="f7e93-142">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="f7e93-143">Probieren Sie es mit`dotnet run -- 5`, um bis Fünf zu zählen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-143">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="f7e93-144">Alle Parameter nach `--` werden an Ihre Anwendung übergeben.</span><span class="sxs-lookup"><span data-stu-id="f7e93-144">Any parameters after `--` are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="f7e93-145">Veröffentlichen der .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="f7e93-145">Publish .NET Core app</span></span>

<span data-ttu-id="f7e93-146">Bevor Sie Ihre .NET Core-App zum Docker-Image hinzufügen, veröffentlichen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="f7e93-146">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="f7e93-147">Der Container führt die veröffentlichte Version der App aus, wenn er gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f7e93-147">The container will execute the published version of the app when it's started.</span></span>

<span data-ttu-id="f7e93-148">Geben Sie im Arbeitsverzeichnis das Verzeichnis **app** mit dem exemplarischen Quellcode ein, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f7e93-148">From the working directory, enter the **app** directory with the example source code and run the following command:</span></span>

```console
dotnet publish -c Release
```

<span data-ttu-id="f7e93-149">Dieser Befehl kompiliert Ihre App in den Ordner **publish** im Ausgabeordner Ihrer App.</span><span class="sxs-lookup"><span data-stu-id="f7e93-149">This command compiles your app to the **publish** folder in the output folder of your app.</span></span> <span data-ttu-id="f7e93-150">Der Pfad zum Ordner **publish** aus dem Arbeitsverzeichnis sollte `.\app\bin\Release\netcoreapp2.2\publish\` sein.</span><span class="sxs-lookup"><span data-stu-id="f7e93-150">The path to the **publish** folder from the working directory should be `.\app\bin\Release\netcoreapp2.2\publish\`</span></span>

<span data-ttu-id="f7e93-151">Rufen Sie eine Verzeichnisliste des Veröffentlichungsordners ab, um sicherzustellen, dass die Datei **myapp.dll** erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f7e93-151">Get a directory listing of the publish folder to verify that the **myapp.dll** was created.</span></span> <span data-ttu-id="f7e93-152">Führen Sie im Verzeichnis **app** einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="f7e93-152">From the **app** directory, run one of the following commands:</span></span>

```console
> dir bin\Release\netcoreapp2.2\publish
 Directory of C:\path-to-working-dir\app\bin\Release\netcoreapp2.2\publish

04/05/2019  11:00 AM    <DIR>          .
04/05/2019  11:00 AM    <DIR>          ..
04/05/2019  11:00 AM               447 myapp.deps.json
04/05/2019  11:00 AM             4,608 myapp.dll
04/05/2019  11:00 AM               448 myapp.pdb
04/05/2019  11:00 AM               154 myapp.runtimeconfig.json
```

```bash
me@DESKTOP:/path-to-working-dir/app$ ls bin/Release/netcoreapp2.2/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

<span data-ttu-id="f7e93-153">Wechseln Sie in Ihrem Terminal ein Verzeichnis nach oben zum Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f7e93-153">In your terminal, go up a directory to the working directory.</span></span>

## <a name="create-the-dockerfile"></a><span data-ttu-id="f7e93-154">Erstellen der Dockerfile</span><span class="sxs-lookup"><span data-stu-id="f7e93-154">Create the Dockerfile</span></span>

<span data-ttu-id="f7e93-155">Die *Dockerfile*-Datei wird vom Befehl `docker build` zum Erstellen des Containerimage verwendet.</span><span class="sxs-lookup"><span data-stu-id="f7e93-155">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="f7e93-156">Diese Datei ist eine Klartextdatei mit dem Namen *Dockerfile*, die keine Erweiterung hat.</span><span class="sxs-lookup"><span data-stu-id="f7e93-156">This file is a plaintext file named *Dockerfile* that does not have an extension.</span></span> <span data-ttu-id="f7e93-157">Erstellen Sie eine Datei namens *Dockerfile* in Ihrem Arbeitsverzeichnis, und öffnen Sie sie in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="f7e93-157">Create a file named *Dockerfile* in your working directory and open it in a text editor.</span></span> <span data-ttu-id="f7e93-158">Fügen Sie den folgenden Befehl als erste Zeile der Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="f7e93-158">Add the following command as the first line of the file:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="f7e93-159">Der Befehl `FROM` weist Docker an, das mit **2.2** gekennzeichnete Image aus dem Repository **mcr.microsoft.com/dotnet/core/runtime** herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-159">The `FROM` command tells Docker to pull down the image tagged **2.2** from the **mcr.microsoft.com/dotnet/core/runtime** repository.</span></span> <span data-ttu-id="f7e93-160">Stellen Sie sicher, dass Sie die .NET Core-Runtime pullen, die der von Ihrem SDK angestrebten Runtime entspricht.</span><span class="sxs-lookup"><span data-stu-id="f7e93-160">Make sure that you pull the .NET Core runtime that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="f7e93-161">So verwendete beispielsweise die im vorherigen Abschnitt erstellte App das .NET Core 2.2 SDK und erstellte eine App, die auf.NET Core 2.2 ausgerichtet war.</span><span class="sxs-lookup"><span data-stu-id="f7e93-161">For example, the app created in the previous section used the .NET Core 2.2 SDK and created an app that targeted .NET Core 2.2.</span></span> <span data-ttu-id="f7e93-162">So wird das in der *Dockerfile* genannte Basisimage mit **2.2** gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f7e93-162">So the base image referred to in the *Dockerfile* is tagged with **2.2**.</span></span>

<span data-ttu-id="f7e93-163">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="f7e93-163">Save the file.</span></span> <span data-ttu-id="f7e93-164">Führen Sie von Ihrem Terminal aus `docker build -t myimage .` aus, und Docker verarbeitet jede Zeile in der *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="f7e93-164">From your terminal, run `docker build -t myimage .` and Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="f7e93-165">Der Befehl `.` im Befehl `docker build` weist Docker an, das aktuelle Verzeichnis zu verwenden, um eine *Dockerfile* zu finden.</span><span class="sxs-lookup"><span data-stu-id="f7e93-165">The `.` in the `docker build` command tells docker to use the current directory to find a *Dockerfile*.</span></span> <span data-ttu-id="f7e93-166">Dieser Befehl erstellt das Image und ein lokales Repository namens **myimage**, das auf dieses Image zeigt.</span><span class="sxs-lookup"><span data-stu-id="f7e93-166">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="f7e93-167">Nachdem dieser Befehl abgeschlossen ist, führen Sie `docker images` aus, um eine Liste der installierten Images anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="f7e93-167">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="f7e93-168">Beachten Sie, dass die beiden Images den gleichen **IMAGE ID**-Wert haben.</span><span class="sxs-lookup"><span data-stu-id="f7e93-168">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="f7e93-169">Der Wert ist zwischen beiden Images gleich, da der einzige Befehl in der *Dockerfile* war, das neue Image auf Basis eines vorhandenen Images zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-169">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="f7e93-170">Fügen Sie zwei Befehle zur *Dockerfile* hinzu.</span><span class="sxs-lookup"><span data-stu-id="f7e93-170">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="f7e93-171">Jeder Befehl erstellt eine neue Imageebene, wobei der letzte Befehl das Image repräsentiert, auf das das Repository **myimage** zeigen wird.</span><span class="sxs-lookup"><span data-stu-id="f7e93-171">Each command creates a new image layer with the final command representing the image the **myimage** repository will point to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="f7e93-172">Der Befehl `COPY` weist Docker an, den angegebenen Ordner auf Ihrem Computer in einen Ordner im Container zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="f7e93-172">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="f7e93-173">In diesem Beispiel wird der Ordner **publish** in einen Ordner mit dem Namen **app** im Container kopiert.</span><span class="sxs-lookup"><span data-stu-id="f7e93-173">In this example, the **publish** folder is copied to a folder named **app** in the container.</span></span>

<span data-ttu-id="f7e93-174">Der nächste Befehl, `ENTRYPOINT`, weist den Docker an, den Container so zu konfigurieren, dass er als ausführbare Datei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7e93-174">The next command, `ENTRYPOINT`, tells docker to configure the container to run as an executable.</span></span> <span data-ttu-id="f7e93-175">Wenn der Container gestartet wird, wird die `ENTRYPOINT`-Befehl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f7e93-175">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="f7e93-176">Wenn dieser Befehl beendet wird, wird der Container automatisch beendet.</span><span class="sxs-lookup"><span data-stu-id="f7e93-176">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="f7e93-177">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="f7e93-177">Save the file.</span></span> <span data-ttu-id="f7e93-178">Führen Sie von Ihrem Terminal aus `docker build -t myimage .` aus, und wenn dieser Befehl abgeschlossen ist, führen Sie `docker images` aus.</span><span class="sxs-lookup"><span data-stu-id="f7e93-178">From your terminal, run `docker build -t myimage .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage .
Sending build context to Docker daemon  819.7kB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/runtime:2.2
 ---> d51bb4452469
Step 2/3 : COPY app/bin/Release/netcoreapp2.2/publish/ app/
 ---> a1e98ac62017
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in f34da5c18e7c
Removing intermediate container f34da5c18e7c
 ---> ddcc6646461b
Successfully built ddcc6646461b
Successfully tagged myimage:latest


> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              ddcc6646461b        10 seconds ago      314MB
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="f7e93-179">Jeder Befehl in der *Dockerfile* generierte eine Ebene und erstellte eine **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="f7e93-179">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="f7e93-180">Die endgültige **IMAGE ID** (Ihre wird anders sein) ist **ddcc6646461b**. Als nächstes werden Sie einen Container basierend auf diesem Image erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-180">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="f7e93-181">Erstellen eines Containers</span><span class="sxs-lookup"><span data-stu-id="f7e93-181">Create a container</span></span>

<span data-ttu-id="f7e93-182">Da Sie nun ein Image haben, das Ihre App enthält, können Sie einen Container erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-182">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="f7e93-183">Für die Erstellung eines Containers haben Sie zwei Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="f7e93-183">You can create a container in two ways.</span></span> <span data-ttu-id="f7e93-184">Erstellen Sie zunächst einen neuen Container, der beendet wird.</span><span class="sxs-lookup"><span data-stu-id="f7e93-184">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

<span data-ttu-id="f7e93-185">Der Befehl `docker create` von oben erstellt einen Container basierend auf dem Image **myimage**.</span><span class="sxs-lookup"><span data-stu-id="f7e93-185">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="f7e93-186">Die Ausgabe dieses Befehls zeigt Ihnen die **CONTAINER ID** (Ihre wird anders sein) des erstellten Containers.</span><span class="sxs-lookup"><span data-stu-id="f7e93-186">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="f7e93-187">Um eine Liste *aller* Container zu erhalten, verwenden Sie den `docker ps -a`-Befehl:</span><span class="sxs-lookup"><span data-stu-id="f7e93-187">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a><span data-ttu-id="f7e93-188">Verwalten des Containers</span><span class="sxs-lookup"><span data-stu-id="f7e93-188">Manage the container</span></span>

<span data-ttu-id="f7e93-189">Jedem Container ist ein Zufallsname zugeordnet, mit dem Sie auf diese Containerinstanz verweisen können.</span><span class="sxs-lookup"><span data-stu-id="f7e93-189">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="f7e93-190">Beispielsweise wurde für den automatisch erstellten Container der Name **boring_matsumoto** gewählt (Ihrer wird anders sein), und dieser Name kann zum Starten des Containers verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f7e93-190">For example, the container that was created automatically chose the name **boring_matsumoto** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="f7e93-191">Mit dem Parameter `docker create --name` überschreiben Sie den automatischen Namen durch einen bestimmten Namen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-191">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="f7e93-192">Das folgende Beispiel verwendet den Befehl `docker start`, um den Container zu starten, und verwendet dann den Befehl `docker ps`, um nur die laufenden Container anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="f7e93-192">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

<span data-ttu-id="f7e93-193">In ähnlicher Weise beendet der Befehl `docker stop` den Container.</span><span class="sxs-lookup"><span data-stu-id="f7e93-193">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="f7e93-194">Das folgende Beispiel verwendet den Befehl `docker stop`, um den Container zu beenden, und verwendet dann den Befehl `docker ps`, um anzuzeigen, dass keine Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f7e93-194">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running.</span></span>

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="f7e93-195">Herstellen einer Verbindung mit einem Container</span><span class="sxs-lookup"><span data-stu-id="f7e93-195">Connect to a container</span></span>

<span data-ttu-id="f7e93-196">Nachdem ein Container ausgeführt wird, können Sie sich mit ihm verbinden, um die Ausgabe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-196">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="f7e93-197">Verwenden Sie die Befehle `docker start` und `docker attach`, um den Container zu starten und den Ausgabestream anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-197">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="f7e93-198">In diesem Beispiel wird der Befehl <kbd>STRG + C</kbd> verwendet, um sich vom ausgeführten Container zu trennen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-198">In this example, the <kbd>CTRL + C</kbd> command is used to detach from the running container.</span></span> <span data-ttu-id="f7e93-199">Dadurch kann der Prozess im Container tatsächlich beendet werden, wodurch der Container gestoppt wird.</span><span class="sxs-lookup"><span data-stu-id="f7e93-199">This may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="f7e93-200">Der Parameter `--sig-proxy=false` stellt sicher, dass <kbd>STRG + C</kbd> den Prozess im Container nicht anhält.</span><span class="sxs-lookup"><span data-stu-id="f7e93-200">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> will not stop the process in the container.</span></span>

<span data-ttu-id="f7e93-201">Nachdem Sie den Container abgetrennt haben, fügen Sie ihn erneut an, um sicherzustellen, dass er noch läuft und zählt.</span><span class="sxs-lookup"><span data-stu-id="f7e93-201">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker attach --sig-proxy=false boring_matsumoto
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false boring_matsumoto
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="f7e93-202">Löschen eines Containers</span><span class="sxs-lookup"><span data-stu-id="f7e93-202">Delete a container</span></span>

<span data-ttu-id="f7e93-203">Für die Zwecke dieses Artikels wollen Sie nicht, dass Container einfach nur vorhanden sind und nichts tun.</span><span class="sxs-lookup"><span data-stu-id="f7e93-203">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="f7e93-204">Löschen Sie den zuvor erstellten Container.</span><span class="sxs-lookup"><span data-stu-id="f7e93-204">Delete the container you previously created.</span></span> <span data-ttu-id="f7e93-205">Wenn der Container ausgeführt wird, beenden Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="f7e93-205">If the container is running, stop it.</span></span>

```console
> docker stop boring_matsumoto
```

<span data-ttu-id="f7e93-206">Das folgende Beispiel listet alle Container auf.</span><span class="sxs-lookup"><span data-stu-id="f7e93-206">The following example lists all containers.</span></span> <span data-ttu-id="f7e93-207">Anschließend wird der Container mit dem Befehl `docker rm` gelöscht und dann wird ein zweites Mal auf laufende Container überprüft.</span><span class="sxs-lookup"><span data-stu-id="f7e93-207">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="f7e93-208">Einzelausführung</span><span class="sxs-lookup"><span data-stu-id="f7e93-208">Single run</span></span>

<span data-ttu-id="f7e93-209">Docker bietet den Befehl `docker run`, um den Container als einen einzigen Befehl zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-209">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="f7e93-210">Dieser Befehl erübrigt die Ausführung von `docker create` und dann `docker start`.</span><span class="sxs-lookup"><span data-stu-id="f7e93-210">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="f7e93-211">Sie können diesen Befehl auch so einstellen, dass der Container beim Beenden des Containers automatisch gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="f7e93-211">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="f7e93-212">Verwenden Sie beispielsweise `docker run -it --rm`, um zwei Dinge zu tun: 1) um sich automatisch über das aktuelle Terminal mit dem Container zu verbinden, und 2) wenn der Container fertig ist, um ihn zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="f7e93-212">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="f7e93-213">Bei `docker run -it` beendet der Befehl <kbd>STRG + C</kbd> den Prozess, der im Container ausgeführt wird, was wiederum den Container beendet.</span><span class="sxs-lookup"><span data-stu-id="f7e93-213">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="f7e93-214">Da der Parameter `--rm` angegeben wurde, wird der Container beim Anhalten des Prozesses automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f7e93-214">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="f7e93-215">Stellen Sie sicher, dass Folgendes nicht beendet wird:</span><span class="sxs-lookup"><span data-stu-id="f7e93-215">Verify that it does not exist:</span></span>

```
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="f7e93-216">Ändern des EINSTIEGSPUNKTS</span><span class="sxs-lookup"><span data-stu-id="f7e93-216">Change the ENTRYPOINT</span></span>

<span data-ttu-id="f7e93-217">Mit dem Befehl `docker run` können Sie auch den Befehl `ENTRYPOINT` aus der *Dockerfile* ändern und etwas anderes ausführen, jedoch nur für diesen Container.</span><span class="sxs-lookup"><span data-stu-id="f7e93-217">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="f7e93-218">Verwenden Sie beispielsweise den folgenden Befehl, um `bash` oder `cmd.exe` auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-218">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="f7e93-219">Bearbeiten Sie den Befehl nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="f7e93-219">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="f7e93-220">Windows</span><span class="sxs-lookup"><span data-stu-id="f7e93-220">Windows</span></span>
<span data-ttu-id="f7e93-221">In diesem Beispiel wird `ENTRYPOINT` in `cmd.exe` geändert.</span><span class="sxs-lookup"><span data-stu-id="f7e93-221">In this example the `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="f7e93-222"><kbd>STRG + C</kbd> wird gedrückt, um den Prozess, zu beenden und den Container anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="f7e93-222"><kbd>CTRL + C</kbd> is pressed to end the process and stop the container.</span></span>

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

#### <a name="linux"></a><span data-ttu-id="f7e93-223">Linux</span><span class="sxs-lookup"><span data-stu-id="f7e93-223">Linux</span></span>

<span data-ttu-id="f7e93-224">In diesem Beispiel wird `ENTRYPOINT` in `bash` geändert.</span><span class="sxs-lookup"><span data-stu-id="f7e93-224">In this example the `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="f7e93-225">Der Befehl `quit` wird ausgeführt, der den Prozess beendet und den Container stoppt.</span><span class="sxs-lookup"><span data-stu-id="f7e93-225">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="f7e93-226">Grundlegende Befehle</span><span class="sxs-lookup"><span data-stu-id="f7e93-226">Essential commands</span></span>

<span data-ttu-id="f7e93-227">Docker hat viele verschiedene Befehle, die behandeln, was Sie mit Ihrem Container und Ihren Images machen wollen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-227">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="f7e93-228">Diese Docker-Befehle sind für die Verwaltung Ihrer Container unerlässlich:</span><span class="sxs-lookup"><span data-stu-id="f7e93-228">These Docker commands are essential to managing your containers:</span></span>

* [<span data-ttu-id="f7e93-229">docker build</span><span class="sxs-lookup"><span data-stu-id="f7e93-229">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="f7e93-230">docker run</span><span class="sxs-lookup"><span data-stu-id="f7e93-230">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="f7e93-231">docker ps</span><span class="sxs-lookup"><span data-stu-id="f7e93-231">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="f7e93-232">docker stop</span><span class="sxs-lookup"><span data-stu-id="f7e93-232">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="f7e93-233">docker rm</span><span class="sxs-lookup"><span data-stu-id="f7e93-233">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="f7e93-234">docker rmi</span><span class="sxs-lookup"><span data-stu-id="f7e93-234">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="f7e93-235">docker image</span><span class="sxs-lookup"><span data-stu-id="f7e93-235">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="f7e93-236">Bereinigen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f7e93-236">Clean up resources</span></span>

<span data-ttu-id="f7e93-237">In diesem Tutorial haben Sie Container und Images erstellt.</span><span class="sxs-lookup"><span data-stu-id="f7e93-237">During this tutorial you created containers and images.</span></span> <span data-ttu-id="f7e93-238">Wenn Sie möchten, können Sie diese Ressourcen löschen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-238">If you want, delete these resources.</span></span> <span data-ttu-id="f7e93-239">Führen Sie die folgenden Befehle für diese Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="f7e93-239">Use the following commands to</span></span>

01. <span data-ttu-id="f7e93-240">Zum Anzeigen aller Container</span><span class="sxs-lookup"><span data-stu-id="f7e93-240">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="f7e93-241">Zum Anhalten aller ausgeführten Container.</span><span class="sxs-lookup"><span data-stu-id="f7e93-241">Stop containers that are running.</span></span> <span data-ttu-id="f7e93-242">`CONTAINER_NAME` steht für automatisch dem Container zugewiesenen Namen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-242">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="f7e93-243">Zum Löschen des Containers</span><span class="sxs-lookup"><span data-stu-id="f7e93-243">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="f7e93-244">Löschen Sie anschließend alle Images, die Sie nicht mehr auf Ihrem Computer benötigen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-244">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="f7e93-245">Löschen Sie das von Ihrer *Dockerfile* erstellte Image und löschen Sie dann das .NET Core-Image, auf dem die *Dockerfile* basiert.</span><span class="sxs-lookup"><span data-stu-id="f7e93-245">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="f7e93-246">Sie können die **IMAGE ID** oder die mit **REPOSITORY:TAG** formatierte Zeichenfolge verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7e93-246">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="f7e93-247">Verwenden Sie den Befehl `docker images`, um eine Liste der installierten Images anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-247">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="f7e93-248">Imagedateien können groß sein.</span><span class="sxs-lookup"><span data-stu-id="f7e93-248">Image files can be large.</span></span> <span data-ttu-id="f7e93-249">Normalerweise würden Sie temporäre Container entfernen, die Sie während des Tests und der Entwicklung Ihrer App erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f7e93-249">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="f7e93-250">In der Regel behalten Sie die Basisimages mit installierter Runtime, wenn Sie planen, andere Images auf Basis dieser Runtime zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-250">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f7e93-251">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f7e93-251">Next steps</span></span>

* [<span data-ttu-id="f7e93-252">Schauen Sie sich das Tutorial zu ASP.NET Core-Microservices an.</span><span class="sxs-lookup"><span data-stu-id="f7e93-252">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
* [<span data-ttu-id="f7e93-253">Überprüfen Sie die Azure-Dienste, die Container unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f7e93-253">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/en-us/overview/containers/)
* [<span data-ttu-id="f7e93-254">Erfahren Sie mehr über Dockerfile-Befehle.</span><span class="sxs-lookup"><span data-stu-id="f7e93-254">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
