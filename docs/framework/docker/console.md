---
title: Ausführen von Konsolenanwendungen in Docker
description: Erfahren Sie, wie Sie eine vorhandene .NET Framework-Konsolenanwendung in einem Windows Docker-Container ausführen können.
author: spboyer
ms.date: 09/28/2016
ms.assetid: 85cca1d5-c9a4-4eb2-93e6-4f878de07fd7
ms.openlocfilehash: f5a38ac63db969a58e920ea79bf4bf10bcfcf64f
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581258"
---
# <a name="running-console-applications-in-windows-containers"></a><span data-ttu-id="91f09-103">Ausführen von Konsolenanwendungen in Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="91f09-103">Running console applications in Windows containers</span></span>

<span data-ttu-id="91f09-104">Konsolenanwendungen werden für verschiedene Zwecke verwendet – vom einfachen Abfragen eines Status bis hin zu Aufgaben zur Verarbeitung von Dokumentbildern mit langer Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="91f09-104">Console applications are used for many purposes; from simple querying of a status to long running document image processing tasks.</span></span> <span data-ttu-id="91f09-105">In allen Fällen wird die Möglichkeit, diese Anwendungen zu starten und zu skalieren, durch Hardwarekäufe, Startzeiten oder die Ausführung mehrerer Instanzen eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="91f09-105">In any case, the ability to start up and scale these applications are met with limitations of hardware acquisitions, startup times or running multiple instances.</span></span>

<span data-ttu-id="91f09-106">Indem Sie Ihre Konsolenanwendungen in Docker- und Windows Server-Container verlagern, können diese Anwendungen mit einem fehlerfreien Status gestartet werden, den Vorgang ausführen und dann ordnungsgemäß beendet werden.</span><span class="sxs-lookup"><span data-stu-id="91f09-106">Moving your console applications to use Docker and Windows Server containers allows for starting these applications from a clean state, enabling them to perform the operation and then shutdown cleanly.</span></span> <span data-ttu-id="91f09-107">Dieses Thema erläutert die Schritte, die erforderlich sind, um eine Konsolenanwendung in einen Windows-basierten Container zu verlagern und mithilfe eines PowerShell-Skripts zu starten.</span><span class="sxs-lookup"><span data-stu-id="91f09-107">This topic will show the steps needed to move a console application to a Windows based container and start it using a PowerShell script.</span></span>

<span data-ttu-id="91f09-108">Als Beispiel dient eine einfache Konsolenanwendung, die ein Argument akzeptiert – in diesem Fall eine Frage – und eine zufällige Antwort zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="91f09-108">The sample console application is a simple example which takes an argument, a question in this case, and returns a random answer.</span></span> <span data-ttu-id="91f09-109">Die Anwendung könnte auch eine `customer_id` akzeptieren und die entsprechenden Steuern berechnen oder eine Miniaturansicht für ein `image_url`-Argument erstellen.</span><span class="sxs-lookup"><span data-stu-id="91f09-109">This could take a `customer_id` and process their taxes, or create a thumbnail for an `image_url` argument.</span></span>

<span data-ttu-id="91f09-110">Zusätzlich zur Antwort wurde der Antwort auch der `Environment.MachineName` hinzugefügt, um den Unterschied zwischen der Ausführung der Anwendung im lokalen System oder in einem Windows-Container zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="91f09-110">In addition to the answer, the `Environment.MachineName` has been added to the response to show the difference between running the application locally and in a Windows container.</span></span> <span data-ttu-id="91f09-111">Wenn die Anwendung lokal ausgeführt wird, wird der Name des lokalen Computers zurückgegeben. Bei Ausführung in einem Windows-Container wird die ID der Containersitzung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="91f09-111">When running the application locally, your local machine name should be returned and when running in a Windows Container; the container session id is returned.</span></span>

<span data-ttu-id="91f09-112">Das [vollständige Beispiel](https://github.com/dotnet/samples/tree/master/framework/docker/ConsoleRandomAnswerGenerator) finden Sie im „dotnet/samples“-Repository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="91f09-112">The [complete example](https://github.com/dotnet/samples/tree/master/framework/docker/ConsoleRandomAnswerGenerator) is available in the dotnet/samples repository on GitHub.</span></span> <span data-ttu-id="91f09-113">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="91f09-113">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="91f09-114">Sie müssen sich mit einigen Docker-Begriffen vertraut machen, bevor Sie damit beginnen, Ihre Anwendung in einen Container zu verlagern.</span><span class="sxs-lookup"><span data-stu-id="91f09-114">You need to be familiar with some Docker terms before you begin working on moving your application to a container.</span></span>

> <span data-ttu-id="91f09-115">Ein *Docker-Image* ist eine schreibgeschützte Vorlage, die die Umgebung für einen ausgeführten Container definiert, einschließlich Betriebssystem, Systemkomponenten und Anwendung(en).</span><span class="sxs-lookup"><span data-stu-id="91f09-115">A *Docker image* is a read-only template that defines the environment for a running container, including the operating system (OS), system components, and application(s).</span></span>

<span data-ttu-id="91f09-116">Ein wichtiges Merkmal der Docker-Images ist es, dass Images aus einem Basisimage zusammengestellt werden.</span><span class="sxs-lookup"><span data-stu-id="91f09-116">One important feature of Docker images is that images are composed from a base image.</span></span> <span data-ttu-id="91f09-117">Jedes neue Image fügt einen kleinen Satz an Funktionen zu einem vorhandenen Image hinzu.</span><span class="sxs-lookup"><span data-stu-id="91f09-117">Each new image adds a small set of features to an existing image.</span></span> 

> <span data-ttu-id="91f09-118">Ein *Docker-Container* ist eine ausgeführte Instanz eines Images.</span><span class="sxs-lookup"><span data-stu-id="91f09-118">A *Docker container* is a running instance of an image.</span></span> 

<span data-ttu-id="91f09-119">Sie skalieren eine Anwendung, indem Sie das gleiche Image in mehreren Containern ausführen.</span><span class="sxs-lookup"><span data-stu-id="91f09-119">You scale an application by running the same image in many containers.</span></span>
<span data-ttu-id="91f09-120">Vom Konzept her ähnelt dieses Vorgehen der Ausführung der gleichen Anwendung auf mehreren Hosts.</span><span class="sxs-lookup"><span data-stu-id="91f09-120">Conceptually, this is similar to running the same application in multiple hosts.</span></span>

<span data-ttu-id="91f09-121">Weitere Informationen zur Docker-Architektur finden Sie auf der Docker-Website unter [Docker Overview](https://docs.docker.com/engine/understanding-docker/) (Übersicht über Docker).</span><span class="sxs-lookup"><span data-stu-id="91f09-121">You can learn more about the Docker architecture by reading the [Docker Overview](https://docs.docker.com/engine/understanding-docker/) on the Docker site.</span></span> 

<span data-ttu-id="91f09-122">Die Verlagerung Ihrer Konsolenanwendung erfordert nur einige wenige Schritte.</span><span class="sxs-lookup"><span data-stu-id="91f09-122">Moving your console application is a matter of a few steps.</span></span>

1. [<span data-ttu-id="91f09-123">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="91f09-123">Build the application</span></span>](#building-the-application)
1. [<span data-ttu-id="91f09-124">Erstellen einer Dockerfile-Datei für das Image</span><span class="sxs-lookup"><span data-stu-id="91f09-124">Creating a Dockerfile for the image</span></span>](#creating-the-dockerfile)
1. [<span data-ttu-id="91f09-125">Erstellen und Ausführen des Docker-Containers</span><span class="sxs-lookup"><span data-stu-id="91f09-125">Process to build and run the Docker container</span></span>](#creating-the-image)

## <a name="prerequisites"></a><span data-ttu-id="91f09-126">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="91f09-126">Prerequisites</span></span>
<span data-ttu-id="91f09-127">Windows-Container werden unter [Windows 10 Anniversary Update](https://www.microsoft.com/en-us/software-download/windows10/) oder [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="91f09-127">Windows containers are supported on [Windows 10 Anniversary Update](https://www.microsoft.com/en-us/software-download/windows10/) or [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server).</span></span>

> [!NOTE]
><span data-ttu-id="91f09-128">Wenn Sie Windows Server 2016 verwenden, müssen Sie Container manuell aktivieren, da das Installationsprogramm für Docker für Windows die Funktion nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="91f09-128">If you are using Windows Server 2016, you must enable containers manually since the Docker for Windows installer will not enable the feature.</span></span> <span data-ttu-id="91f09-129">Stellen Sie sicher, dass alle Updates für das Betriebssystem ausgeführt wurden, und folgen Sie dann den Anweisungen des Artikels [Containerhostbereitstellung](https://msdn.microsoft.com/virtualization/windowscontainers/deployment/deployment), um die Container und Docker-Funktionen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="91f09-129">Make sure all updates have run for the OS and then follow the instructions from the [Container Host Deployment](https://msdn.microsoft.com/virtualization/windowscontainers/deployment/deployment) article to install the containers and Docker features.</span></span>

<span data-ttu-id="91f09-130">Sie müssen über Docker für Windows, Version 1.12 Beta 26 oder höher, verfügen, um Windows-Container zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="91f09-130">You need to have Docker for Windows, version 1.12 Beta 26 or higher to support Windows containers.</span></span> <span data-ttu-id="91f09-131">Standardmäßig arbeitet Docker mit Linux-basierten Containern. Wechseln Sie zu Windows-Containern, indem Sie in der Taskleiste mit der rechten Maustaste auf das Docker-Symbol klicken und **Zu Windows-Containern wechseln** auswählen.</span><span class="sxs-lookup"><span data-stu-id="91f09-131">By default, Docker enables Linux based containers; switch to Windows containers by right clicking the Docker icon in the system tray and select **Switch to Windows containers**.</span></span> <span data-ttu-id="91f09-132">Docker führt den Änderungsprozess aus. Möglicherweise ist ein Neustart erforderlich.</span><span class="sxs-lookup"><span data-stu-id="91f09-132">Docker will run the process to change and a restart may be required.</span></span>

![Windows-Container](./media/console/SwitchContainer.png)

## <a name="building-the-application"></a><span data-ttu-id="91f09-134">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="91f09-134">Building the application</span></span>
<span data-ttu-id="91f09-135">Konsolenanwendungen werden üblicherweise über ein Installationsprogramm, einen FTP-Speicherort oder eine Dateifreigabe verteilt.</span><span class="sxs-lookup"><span data-stu-id="91f09-135">Typically console applications are distributed through an installer, FTP, or File Share deployment.</span></span> <span data-ttu-id="91f09-136">Wenn Sie eine Anwendung in einem Container bereitstellen, müssen die Assets kompiliert und an einem Speicherort bereitgestellt werden, der beim Erstellen des Docker-Images verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="91f09-136">When deploying to a container, the assets need to be compiled and staged to a location that can be used when the Docker image is created.</span></span>

<span data-ttu-id="91f09-137">In *build.ps1* verwendet das Skript [MSBuild](/visualstudio/msbuild/msbuild), um die Anwendung zu kompilieren und so die Erstellung der Assets abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="91f09-137">In *build.ps1*, the script uses [MSBuild](/visualstudio/msbuild/msbuild) to compile the application to complete the task of building the assets.</span></span> <span data-ttu-id="91f09-138">Es werden einige Parameter an MSBuild übergeben, um die benötigten Assets zu finalisieren.</span><span class="sxs-lookup"><span data-stu-id="91f09-138">There are a few parameters passed to MSBuild to finalize the needed assets.</span></span> <span data-ttu-id="91f09-139">Der Name der Projektdatei oder Projektmappe, die kompiliert werden soll, der Speicherort der Ausgabe und schließlich die Konfiguration („Release“ oder „Debug“).</span><span class="sxs-lookup"><span data-stu-id="91f09-139">The name of the project file or solution to be compiled, the location for the output and finally the configuration (Release or Debug).</span></span>

<span data-ttu-id="91f09-140">Im Aufruf von `Invoke-MSBuild` ist der `OutputPath` auf **publish** festgelegt und die `Configuration` auf **Release**.</span><span class="sxs-lookup"><span data-stu-id="91f09-140">In the call to `Invoke-MSBuild` the `OutputPath` is set to **publish** and  `Configuration` set to **Release**.</span></span> 

```
function Invoke-MSBuild ([string]$MSBuildPath, [string]$MSBuildParameters) {
    Invoke-Expression "$MSBuildPath $MSBuildParameters"
}

Invoke-MSBuild -MSBuildPath "MSBuild.exe" -MSBuildParameters ".\ConsoleRandomAnswerGenerator.csproj -p:OutputPath=.\publish -p:Configuration=Release"
```

## <a name="creating-the-dockerfile"></a><span data-ttu-id="91f09-141">Erstellen der Dockerfile-Datei</span><span class="sxs-lookup"><span data-stu-id="91f09-141">Creating the Dockerfile</span></span>
<span data-ttu-id="91f09-142">Das für eine .NET Framework-Konsolenanwendung verwendete Basisimage ist `microsoft/windowsservercore`, öffentlich verfügbar im [Docker-Hub](https://hub.docker.com/r/microsoft/windowsservercore/).</span><span class="sxs-lookup"><span data-stu-id="91f09-142">The base image used for a console .NET Framework application is `microsoft/windowsservercore`, publicly available on [Docker Hub](https://hub.docker.com/r/microsoft/windowsservercore/).</span></span> <span data-ttu-id="91f09-143">Das Basisimage umfasst eine Minimalinstallation mit Windows Server 2016 und .NET Framework 4.6.2 und dient als grundlegendes Betriebssystemimage für Windows-Container.</span><span class="sxs-lookup"><span data-stu-id="91f09-143">The base image contains a minimal installation of Windows Server 2016, .NET Framework 4.6.2 and serves as the base OS image for Windows Containers.</span></span>

```
FROM microsoft/windowsservercore
ADD publish/ /
ENTRYPOINT ConsoleRandomAnswerGenerator.exe
```
<span data-ttu-id="91f09-144">Die erste Zeile der Dockerfile-Datei gibt mithilfe der [`FROM`](https://docs.docker.com/engine/reference/builder/#/from)-Anweisung das Basisimage an.</span><span class="sxs-lookup"><span data-stu-id="91f09-144">The first line in the Dockerfile designates the base image using the [`FROM`](https://docs.docker.com/engine/reference/builder/#/from) instruction.</span></span> <span data-ttu-id="91f09-145">Danach kopiert [`ADD`](https://docs.docker.com/engine/reference/builder/#/add) in der Datei die Anwendungsassets aus dem Ordner **publish** in den Stammordner des Containers, und zum Schluss wird mit [`ENTRYPOINT`](https://docs.docker.com/engine/reference/builder/#/entrypoint) der Befehl oder die Anwendung festgelegt, der bzw. die beim Starten des Containers ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="91f09-145">Next, [`ADD`](https://docs.docker.com/engine/reference/builder/#/add) in the file copies the application assets from the **publish** folder to root folder of the container and last; setting the [`ENTRYPOINT`](https://docs.docker.com/engine/reference/builder/#/entrypoint) of the image states that this is the command or application that will run when the container starts.</span></span> 

## <a name="creating-the-image"></a><span data-ttu-id="91f09-146">Erstellen des Images</span><span class="sxs-lookup"><span data-stu-id="91f09-146">Creating the image</span></span>
<span data-ttu-id="91f09-147">Um das Docker-Image zu erstellen, wird dem Skript *build.ps1* folgender Code hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="91f09-147">In order to create the Docker image, the following code is added to the *build.ps1* script.</span></span> <span data-ttu-id="91f09-148">Wenn das Skript ausgeführt wird, wird das `console-random-answer-generator`-Image mithilfe der Assets erstellt, die aus dem im Abschnitt [Erstellen der Anwendung](#building-the-application) definierten MSBuild kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="91f09-148">When the script is run, the `console-random-answer-generator` image is created using the assets compiled from MSBuild defined in the [Building the application](#building-the-application) section.</span></span>

```powershell
$ImageName="console-random-answer-generator"

function Invoke-Docker-Build ([string]$ImageName, [string]$ImagePath, [string]$DockerBuildArgs = "") {
    echo "docker build -t $ImageName $ImagePath $DockerBuildArgs"
    Invoke-Expression "docker build -t $ImageName $ImagePath $DockerBuildArgs"
}

Invoke-Docker-Build -ImageName $ImageName -ImagePath "."
```

<span data-ttu-id="91f09-149">Führen Sie das Skript unter Verwendung von `.\build.ps1` in der PowerShell-Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="91f09-149">Run the script using `.\build.ps1` from the PowerShell command prompt.</span></span>

<span data-ttu-id="91f09-150">Wenn der Build abgeschlossen ist, verwenden Sie den Befehl `docker images` in einer Befehlszeile oder PowerShell-Eingabeaufforderung. Damit wird das Image erstellt und ist bereit zur Ausführung.</span><span class="sxs-lookup"><span data-stu-id="91f09-150">When the build is complete, using the `docker images` command from a command line or PowerShell prompt; you'll see that the image is created and ready to be run.</span></span>

```
REPOSITORY                        TAG                 IMAGE ID            CREATED             SIZE
console-random-answer-generator   latest              8f7c807db1b5        8 seconds ago       7.33 GB
```

## <a name="running-the-container"></a><span data-ttu-id="91f09-151">Ausführen des Containers</span><span class="sxs-lookup"><span data-stu-id="91f09-151">Running the container</span></span>
<span data-ttu-id="91f09-152">Sie können den Container mithilfe der Docker-Befehle in der Befehlszeile starten.</span><span class="sxs-lookup"><span data-stu-id="91f09-152">You can start the container from the command line using the Docker commands.</span></span>

```
docker run console-random-answer-generator "Are you a square container?"
```

<span data-ttu-id="91f09-153">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="91f09-153">The output is</span></span>

```
The answer to your question: 'Are you a square container?' is Concentrate and ask again on (70C3D48F4343)
```

<span data-ttu-id="91f09-154">Wenn Sie den `docker ps -a`-Befehl in PowerShell ausführen, können Sie sehen, dass der Container immer noch vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="91f09-154">If you run the `docker ps -a` command from PowerShell, you can see that the container still exists.</span></span>

```
CONTAINER ID        IMAGE                             COMMAND                  CREATED             STATUS                          
70c3d48f4343        console-random-answer-generator   "cmd /S /C ConsoleRan"   2 minutes ago       Exited (0) About a minute ago      
```

<span data-ttu-id="91f09-155">Die Statusspalte zeigt bei „About a minute ago“, dass die Anwendung vor ungefähr einer Minute abgeschlossen wurde und beendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="91f09-155">The STATUS column shows at "About a minute ago", the application was complete and could be shut down.</span></span> <span data-ttu-id="91f09-156">Wenn der Befehl hundert Mal ausgeführt wurde, würden hundert Container in statischem Zustand ohne Aufgabe zurückbleiben.</span><span class="sxs-lookup"><span data-stu-id="91f09-156">If the command was run a hundred times, there would be a hundred containers left static with no work to do.</span></span> <span data-ttu-id="91f09-157">Im Anfangsszenario bestand der ideale Vorgang darin, die erforderlichen Funktionen auszuführen und dann zu beenden oder zu bereinigen.</span><span class="sxs-lookup"><span data-stu-id="91f09-157">In the beginning scenario the ideal operation was to do the work and shutdown or cleanup.</span></span> <span data-ttu-id="91f09-158">Um diesen Workflow vollständig durchzuführen, fügen Sie die Option `--rm` zum `docker run`-Befehl hinzu, um den Container zu entfernen, sobald das Signal `Exited` empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="91f09-158">To accomplish that workflow, adding the `--rm` option to the `docker run` command will remove the container as soon as the `Exited` signal is received.</span></span>

```
docker run --rm console-random-answer-generator "Are you a square container?"
```

<span data-ttu-id="91f09-159">Führen Sie den Befehl mit dieser Option aus, und betrachten Sie dann die Ausgabe des `docker ps -a`-Befehls. Sie werden feststellen, dass sich die Container-ID (`Environment.MachineName`) nicht mehr in der Liste befindet.</span><span class="sxs-lookup"><span data-stu-id="91f09-159">Running the command with this option and then looking at the output of `docker ps -a` command; notice that the container id (the `Environment.MachineName`) is not in the list.</span></span>

### <a name="running-the-container-using-powershell"></a><span data-ttu-id="91f09-160">Ausführen des Container mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="91f09-160">Running the container using PowerShell</span></span>
<span data-ttu-id="91f09-161">In den Beispielprojektdateien befindet sich auch die Datei *run.ps1*. Diese ist ein Beispiel dafür, wie Sie PowerShell verwenden, um die Anwendung auszuführen, wobei die Argumente akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="91f09-161">In the sample project files there is also a *run.ps1* which is an example of how to use PowerShell to run the application accepting the arguments.</span></span>

<span data-ttu-id="91f09-162">Um die Datei auszuführen, öffnen Sie PowerShell, und verwenden Sie folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="91f09-162">To run, open PowerShell and use the following command:</span></span>

```
.\run.ps1 "Is this easy or what?"
```

## <a name="summary"></a><span data-ttu-id="91f09-163">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="91f09-163">Summary</span></span>
<span data-ttu-id="91f09-164">Sie können Ihre .NET Framework-Konsolenanwendungen in Containern ausführen, indem Sie einfach eine Dockerfile-Datei hinzufügen und die Anwendung veröffentlichen. So können Sie mehrere Instanzen ausführen, sauber starten und beenden und von mehr Windows Server 2016-Funktionen profitieren, ohne den Anwendungscode selbst in irgendeiner Weise zu ändern.</span><span class="sxs-lookup"><span data-stu-id="91f09-164">Just by adding a Dockerfile and publishing the application, you can containerize your .NET Framework console applications and now take the advantage of running multiple instances, clean start and stop and more Windows Server 2016 capabilities without making any changes to the application code at all.</span></span>
