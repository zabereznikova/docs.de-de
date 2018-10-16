---
title: Bereitstellung der .NET Core-App mit CLI-Tools
description: Erfahren Sie mehr zur .NET Core-App-Bereitstellung mit CLI-Tools
author: rpetrusha
ms.author: ronpet
ms.date: 09/05/2018
dev_langs:
- csharp
- vb
ms.openlocfilehash: a7e810372d831699eae777186385e45fe65cdf45
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47208249"
---
# <a name="deploying-net-core-apps-with-command-line-interface-cli-tools"></a><span data-ttu-id="78cc4-103">Bereitstellen von .NET Core-Apps mit CLI-Tools (command-line interface, Befehlszeilenschnittstelle)</span><span class="sxs-lookup"><span data-stu-id="78cc4-103">Deploying .NET Core apps with command-line interface (CLI) tools</span></span>

<span data-ttu-id="78cc4-104">Sie können eine .NET Core-Anwendung entweder als *Framework-abhängige Bereitstellung* bereitstellen, was die Binärdateien Ihrer Anwendung einschließt, jedoch von Präsenz von .NET Core auf dem Zielsystem abhängt, oder als *eigenständige Bereitstellung*,die jeweils Ihre Anwendung sowie die .NET Core-Binärdateien einschließt.</span><span class="sxs-lookup"><span data-stu-id="78cc4-104">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and the .NET Core binaries.</span></span> <span data-ttu-id="78cc4-105">Eine Übersicht finden Sie unter [.NET Core-Anwendungsbereitstellung](index.md).</span><span class="sxs-lookup"><span data-stu-id="78cc4-105">For an overview, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="78cc4-106">Die folgenden Abschnitte zeigen, wie Sie [.NET Core-CLI-Tools](../tools/index.md) zum Erstellen der folgenden Bereitstellungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="78cc4-106">The following sections show how to use [.NET Core command-line interface tools](../tools/index.md) to create the following kinds of deployments:</span></span>

- <span data-ttu-id="78cc4-107">Framework-abhängige Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="78cc4-107">Framework-dependent deployment</span></span>
- <span data-ttu-id="78cc4-108">Framework-abhängige Bereitstellung mit Drittanbieterabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="78cc4-108">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="78cc4-109">Eigenständige Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="78cc4-109">Self-contained deployment</span></span>
- <span data-ttu-id="78cc4-110">Eigenständige Bereitstellung mit Drittanbieterabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="78cc4-110">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="78cc4-111">Wenn Sie über die Befehlszeile arbeiten, können Sie einen Programm-Editor Ihrer Wahl verwenden.</span><span class="sxs-lookup"><span data-stu-id="78cc4-111">When working from the command line, you can use a program editor of your choice.</span></span> <span data-ttu-id="78cc4-112">Wenn Ihr Programm-Editor [Visual Studio Code](https://code.visualstudio.com) ist, können Sie eine Befehlskonsole in Ihrer Visual Studio Code-Umgebung öffnen, indem Sie **Ansicht** > **Integrierter Terminal** auswählen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-112">If your program editor is [Visual Studio Code](https://code.visualstudio.com), you can open a command console inside your Visual Studio Code environment by selecting **View** > **Integrated Terminal**.</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="78cc4-113">Framework-abhängige Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="78cc4-113">Framework-dependent deployment</span></span>

<span data-ttu-id="78cc4-114">Die Bereitstellung einer Framework-abhängigen Bereitstellung ohne Drittanbieter-Abhängigkeiten umfasst nur das Erstellen, Testen und Veröffentlichen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="78cc4-114">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="78cc4-115">Ein einfaches, in C# geschriebenes Beispiel veranschaulicht den Prozess.</span><span class="sxs-lookup"><span data-stu-id="78cc4-115">A simple example written in C# illustrates the process.</span></span>

1. <span data-ttu-id="78cc4-116">Erstellen Sie ein Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="78cc4-116">Create a project directory.</span></span>

   <span data-ttu-id="78cc4-117">Erstellen Sie ein Verzeichnis für Ihr Projekt, und machen Sie es zu Ihrem aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="78cc4-117">Create a directory for your project and make it your current directory.</span></span>

1. <span data-ttu-id="78cc4-118">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="78cc4-118">Create the project.</span></span>

   <span data-ttu-id="78cc4-119">Geben Sie [dotnet new console](../tools/dotnet-new.md) über die Befehlszeile ein, um ein neues C#-Konsolenprojekt zu erstellen. Geben Sie alternativ [dotnet new console -lang vb](../tools/dotnet-new.md) ein, um ein neues Visual Basic-Konsolenprojekt in diesem Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-119">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project or [dotnet new console -lang vb](../tools/dotnet-new.md) to create a new Visual Basic console project in that directory.</span></span>

1. <span data-ttu-id="78cc4-120">Fügen Sie den Quellcode der Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="78cc4-120">Add the application's source code.</span></span>

   <span data-ttu-id="78cc4-121">Öffnen Sie die Datei *Program.cs* oder *Program.vb* in Ihrem Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="78cc4-121">Open the *Program.cs* or *Program.vb* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="78cc4-122">Der Benutzer wird zur Texteingabe aufgefordert, und die einzelnen Wörter, die vom Benutzer eingegeben wurden, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78cc4-122">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="78cc4-123">Der reguläre Ausdruck `\w+` wird verwendet, um Wörter im Eingabetext zu trennen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-123">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]

1. <span data-ttu-id="78cc4-124">Aktualisieren Sie die Abhängigkeiten und Tools des Projekts.</span><span class="sxs-lookup"><span data-stu-id="78cc4-124">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="78cc4-125">Führen Sie den Befehl [dotnet restore](../tools/dotnet-restore.md) aus ([siehe Hinweis](#dotnet-restore-note)), um die im Projekt angegebenen Abhängigkeiten wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-125">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="78cc4-126">Erstellen Sie ein Debugbuild Ihrer App.</span><span class="sxs-lookup"><span data-stu-id="78cc4-126">Create a Debug build of your app.</span></span>

   <span data-ttu-id="78cc4-127">Verwenden Sie den Befehl [dotnet build](../tools/dotnet-build.md), um Ihre Anwendung zu erstellen, oder den Befehl [dotnet run](../tools/dotnet-run.md), um sie zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-127">Use the [dotnet build](../tools/dotnet-build.md) command to build your application or the [dotnet run](../tools/dotnet-run.md) command to build and run it.</span></span>

1. <span data-ttu-id="78cc4-128">Stellen Sie Ihre App bereit.</span><span class="sxs-lookup"><span data-stu-id="78cc4-128">Deploy your app.</span></span>

   <span data-ttu-id="78cc4-129">Nachdem Sie das Programm debuggt und getestet haben, erstellen Sie die Bereitstellung, indem Sie folgenden Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="78cc4-129">After you've debugged and tested the program, create the deployment by using the following command:</span></span>

      ```console
      dotnet publish -f netcoreapp2.1 -c Release
      ```
   <span data-ttu-id="78cc4-130">Dies erstellt eine Releaseversion (anstatt einer Debugversion) Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="78cc4-130">This creates a Release (rather than a Debug) version of your app.</span></span> <span data-ttu-id="78cc4-131">Die resultierenden Dateien werden in ein Verzeichnis namens *publish* platziert, das sich in einem Unterverzeichnis des *bin*-Verzeichnisses Ihres Projekts befindet.</span><span class="sxs-lookup"><span data-stu-id="78cc4-131">The resulting files are placed in a directory named *publish*      that's in a subdirectory of your project's *bin* directory.</span></span>

   <span data-ttu-id="78cc4-132">Der Veröffentlichungsprozess gibt zusammen mit den Dateien Ihrer Anwendung eine Programmdatenbankdatei (.pdb) aus, die Debuginformationen über Ihre Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="78cc4-132">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="78cc4-133">Die Datei ist vornehmlich für das Debuggen von Ausnahmen nützlich.</span><span class="sxs-lookup"><span data-stu-id="78cc4-133">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="78cc4-134">Sie können sich auch dazu entschließen, sie nicht mit den Dateien Ihrer Anwendung zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-134">You can choose not to distribute it with your application's files.</span></span> <span data-ttu-id="78cc4-135">Jedoch sollten Sie sie für den Fall speichern, dass Sie das Releasebuild Ihrer App debuggen möchten.</span><span class="sxs-lookup"><span data-stu-id="78cc4-135">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

   <span data-ttu-id="78cc4-136">Der vollständige Satz von Anwendungsdateien kann so bereitgestellt werden, wie Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="78cc4-136">You can deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="78cc4-137">Sie können sie z.B. in einer ZIP-Datei verpacken, und einen einfachen `copy`-Befehl verwenden, oder sie mit jedem Installationspaket Ihrer Wahl bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-137">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

1. <span data-ttu-id="78cc4-138">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="78cc4-138">Run your app</span></span>

   <span data-ttu-id="78cc4-139">Sobald die Anwendung installiert ist, können Benutzer sie mithilfe des `dotnet`-Befehls ausführen und den Dateinamen der Anwendung bereitstellen, z.B. `dotnet fdd.dll`.</span><span class="sxs-lookup"><span data-stu-id="78cc4-139">Once installed, users can execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

   <span data-ttu-id="78cc4-140">Das Installationsprogramm sollte zusätzlich zu den Binärdateien der Anwendung das freigegebene Framework-Installationsprogramm bündeln, oder als erforderliche Komponente im Rahmen der Anwendungsinstallation überprüfen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-140">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="78cc4-141">Die Installation des gemeinsam genutzten Frameworks erfordert Administrator-/Root-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="78cc4-141">Installation of the shared framework requires Administrator/root access.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="78cc4-142">Framework-abhängige Bereitstellung mit Drittanbieterabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="78cc4-142">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="78cc4-143">Die Bereitstellung einer Framework-abhängigen Bereitstellung mit mindestens einer Drittanbieterabhängigkeit erfordert, dass diese Abhängigkeiten für Ihr Projekt verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="78cc4-143">Deploying a framework-dependent deployment with one or more third-party dependencies requires that those dependencies be available to your project.</span></span> <span data-ttu-id="78cc4-144">Es sind noch zwei zusätzliche Schritte nötig, bevor Sie den `dotnet restore`-Befehl ausführen können ([siehe Hinweis](#dotnet-restore-note)):</span><span class="sxs-lookup"><span data-stu-id="78cc4-144">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="78cc4-145">Fügen Sie Verweise auf Drittanbieter-Bibliotheken zum `<ItemGroup>`-Teil Ihrer *CSPROJ*-Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="78cc4-145">Add references to required third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="78cc4-146">Der folgende `<ItemGroup>`-Abschnitt verwendet [Json.NET](http://www.newtonsoft.com/json) als Drittanbieter-Bibliothek:</span><span class="sxs-lookup"><span data-stu-id="78cc4-146">The following `<ItemGroup>` section contains a dependency on [Json.NET](http://www.newtonsoft.com/json) as a third-party library:</span></span>

      ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
      ```

1. <span data-ttu-id="78cc4-147">Wenn noch nicht geschehen, laden Sie das NuGet-Paket mit der Drittanbieter-Abhängigkeit herunter.</span><span class="sxs-lookup"><span data-stu-id="78cc4-147">If you haven't already, download the NuGet package containing the third-party dependency.</span></span> <span data-ttu-id="78cc4-148">Führen Sie den `dotnet restore`-Befehl ([siehe Hinweis](#dotnet-restore-note)) nach dem Hinzufügen der Abhängigkeit aus, um das Paket herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-148">To download the package, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="78cc4-149">Da die Abhängigkeit zum Zeitpunkt der Veröffentlichung aus dem lokalen NuGet-Cache aufgelöst wurde, muss sie auf Ihrem System verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="78cc4-149">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="78cc4-150">Beachten Sie, dass eine Framework-abhängige Bereitstellung mit Drittanbieter-Abhängigkeiten nur so tragbar wie ihre Drittanbieter-Abhängigkeiten ist.</span><span class="sxs-lookup"><span data-stu-id="78cc4-150">Note that a framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="78cc4-151">Falls eine Drittanbieter-Bibliothek nur macOS unterstützen sollte, so wird die Anwendung nicht auf Windows-Systeme übertragbar sein.</span><span class="sxs-lookup"><span data-stu-id="78cc4-151">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="78cc4-152">Dies kann geschehen, wenn die Drittanbieter-Abhängigkeit selbst vom nativen Code abhängt.</span><span class="sxs-lookup"><span data-stu-id="78cc4-152">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="78cc4-153">Ein gutes Beispiel dafür ist der [Kestrel-Server](/aspnet/core/fundamentals/servers/kestrel), der eine native Abhängigkeit unter [libuv](https://github.com/libuv/libuv) erfordert.</span><span class="sxs-lookup"><span data-stu-id="78cc4-153">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="78cc4-154">Wenn bei dieser Art von Drittanbieter-Abhängigkeit eine FDD für eine Anwendung erstellt wird, enthält die veröffentlichte Ausgabe einen Ordner für jede [Runtime-ID (RID)](../rid-catalog.md), die die native Abhängigkeit unterstützt (und im NuGet-Paket vorhanden ist).</span><span class="sxs-lookup"><span data-stu-id="78cc4-154">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <a name="simpleSelf"></a> <span data-ttu-id="78cc4-155">Eigenständige Bereitstellung ohne Drittanbieterabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="78cc4-155">Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="78cc4-156">Das Bereitstellen einer eigenständigen Bereitstellung ohne Abhängigkeiten von Drittanbietern umfasst das Erstellen des Projekts, das Ändern der *CSPROJ*-Datei sowie das Erstellen, Testen und Veröffentlichen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="78cc4-156">Deploying a self-contained deployment without third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="78cc4-157">Ein einfaches, in C# geschriebenes Beispiel veranschaulicht den Prozess.</span><span class="sxs-lookup"><span data-stu-id="78cc4-157">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="78cc4-158">Dieses Beispiel zeigt, wie Sie eine eigenständige Bereitstellung mithilfe des [dotnet-Hilfsprogramms](../tools/dotnet.md) aus der Befehlszeile erstellen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-158">The example shows how to create a self-contained deployment using the [dotnet utility](../tools/dotnet.md) from the command line.</span></span>

1. <span data-ttu-id="78cc4-159">Erstellen Sie ein Verzeichnis für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="78cc4-159">Create a directory for the project.</span></span>

   <span data-ttu-id="78cc4-160">Erstellen Sie ein Verzeichnis für Ihr Projekt, und machen Sie es zu Ihrem aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="78cc4-160">Create a directory for your project, and make it your current directory.</span></span>

1. <span data-ttu-id="78cc4-161">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="78cc4-161">Create the project.</span></span>

   <span data-ttu-id="78cc4-162">Geben Sie über die Befehlszeile [dotnet new console](../tools/dotnet-new.md) ein, um ein neues C#-Konsolenprojekt in diesem Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-162">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="78cc4-163">Überprüfen Sie den Quellcode der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="78cc4-163">Add the application's source code.</span></span>

   <span data-ttu-id="78cc4-164">Öffnen Sie die *Program.cs*-Datei in Ihrem Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="78cc4-164">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="78cc4-165">Der Benutzer wird zur Texteingabe aufgefordert, und die einzelnen Wörter, die vom Benutzer eingegeben wurden, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78cc4-165">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="78cc4-166">Der reguläre Ausdruck `\w+` wird verwendet, um Wörter im Eingabetext zu trennen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-166">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]
1. <span data-ttu-id="78cc4-167">Definieren Sie die Zielplattformen für Ihre App.</span><span class="sxs-lookup"><span data-stu-id="78cc4-167">Define the platforms that your app will target.</span></span>

   <span data-ttu-id="78cc4-168">Erstellen Sie das Tag `<RuntimeIdentifiers>` im Abschnitt `<PropertyGroup>` Ihrer Datei *CSPROJ*, der die Plattformen Ihrer Anwendungsziele definiert und die Runtime-ID für jede Zielplattform angibt.</span><span class="sxs-lookup"><span data-stu-id="78cc4-168">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets and specify the runtime identifier (RID) for each platform that you target.</span></span> <span data-ttu-id="78cc4-169">Beachten Sie, dass Sie auch ein Semikolon hinzufügen müssen, um die RIDs trennen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-169">Note that you also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="78cc4-170">Sie finden eine RID-Liste im [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="78cc4-170">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span>

   <span data-ttu-id="78cc4-171">Der folgende Abschnitt `<PropertyGroup>` gibt z.B. an, dass die Anwendung unter den Betriebssystemen Windows 10 (64-Bit) und OS X 10.11 (64-Bit) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="78cc4-171">For example, the following `<PropertyGroup>` section indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

     ```xml
     <PropertyGroup>
         <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
     </PropertyGroup>
     ```

   <span data-ttu-id="78cc4-172">Beachten Sie, dass das Element `<RuntimeIdentifiers>` in jeder `<PropertyGroup>` in Ihrer *CSPROJ*-Datei erscheinen kann.</span><span class="sxs-lookup"><span data-stu-id="78cc4-172">Note that the `<RuntimeIdentifiers>` element can appear in any `<PropertyGroup>` in your *csproj* file.</span></span> <span data-ttu-id="78cc4-173">Eine vollständige *CSPROJ*-Beispieldatei wird später in diesem Abschnitt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78cc4-173">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="78cc4-174">Aktualisieren Sie die Abhängigkeiten und Tools des Projekts.</span><span class="sxs-lookup"><span data-stu-id="78cc4-174">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="78cc4-175">Führen Sie den Befehl [dotnet restore](../tools/dotnet-restore.md) aus ([siehe Hinweis](#dotnet-restore-note)), um die im Projekt angegebenen Abhängigkeiten wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-175">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="78cc4-176">Bestimmen Sie, ob Sie den invarianten Globalisierungsmodus verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="78cc4-176">Determine whether you want to use globalization invariant mode.</span></span>

   <span data-ttu-id="78cc4-177">Insbesondere, wenn Ihre Anwendung für Linux konzipiert ist, können Sie die Gesamtgröße Ihrer Bereitstellung reduzieren, indem Sie den [invarianten Globalisierungsmodus](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="78cc4-177">Particularly if your app targets Linux, you can reduce the total size of your deployment by taking advantage of [globalization invariant mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span></span> <span data-ttu-id="78cc4-178">Der invariante Globalisierungsmodus eignet sich für Anwendungen, die nicht für den globalen Einsatz ausgelegt sind, und Formatierungskonventionen, Groß-/Kleinschreibungskonventionen, Zeichenfolgenvergleiche und Sortierreihenfolgen der [invarianten Kultur](xref:System.Globalization.CultureInfo.InvariantCulture) verwenden können.</span><span class="sxs-lookup"><span data-stu-id="78cc4-178">Globalization invariant mode is useful for applications that are not globally aware and that can use the formatting conventions, casing conventions, and string comparison and sort order of the [invariant culture](xref:System.Globalization.CultureInfo.InvariantCulture).</span></span>

   <span data-ttu-id="78cc4-179">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf Ihr Projekt (nicht auf die Projektmappe), und klicken Sie auf **SCD.csproj bearbeiten** oder **SCD.vbproj bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="78cc4-179">To enable invariant mode, right-click on your project (not the solution) in **Solution Explorer**, and select **Edit SCD.csproj** or **Edit SCD.vbproj**.</span></span> <span data-ttu-id="78cc4-180">Fügen Sie der Datei dann die folgenden hervorgehobenen Zeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="78cc4-180">Then add the following highlighted lines to the file:</span></span>

 [!code-xml[globalization-invariant-mode](~/samples/snippets/core/deploying/xml/invariant.csproj)]

1. <span data-ttu-id="78cc4-181">Erstellen Sie ein Debugbuild Ihrer App.</span><span class="sxs-lookup"><span data-stu-id="78cc4-181">Create a Debug build of your app.</span></span>

   <span data-ttu-id="78cc4-182">Verwenden Sie den Befehl [dotnet build](../tools/dotnet-build.md) aus der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="78cc4-182">From the command line, use the [dotnet build](../tools/dotnet-build.md) command.</span></span>

1. <span data-ttu-id="78cc4-183">Nachdem Sie das Programm debuggt und getestet haben, erstellen Sie die Dateien, die mit Ihrer App für jede Zielplattform bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-183">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="78cc4-184">Verwenden Sie den `dotnet publish`-Befehl für beide Zielplattformen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="78cc4-184">Use the `dotnet publish` command for both target platforms as follows:</span></span>

      ```console
      dotnet publish -c Release -r win10-x64
      dotnet publish -c Release -r osx.10.11-x64
      ```

   <span data-ttu-id="78cc4-185">Dies erstellt eine Releaseversion (anstatt einer Debugversion) Ihrer Anwendung für jede Zielplattform.</span><span class="sxs-lookup"><span data-stu-id="78cc4-185">This creates a Release (rather than a Debug) version of your app for each target platform.</span></span> <span data-ttu-id="78cc4-186">Die resultierenden Dateien werden in ein Unterverzeichnis namens *publish* platziert, das sich in einem Unterverzeichnis des *.\bin\Release\netcoreapp2.1\<runtime_identifier>*-Unterverzeichnisses Ihres Projekts befindet.</span><span class="sxs-lookup"><span data-stu-id="78cc4-186">The resulting files are placed in a subdirectory named *publish* that's in a subdirectory of your project's *.\bin\Release\netcoreapp2.1\<runtime_identifier>* subdirectory.</span></span> <span data-ttu-id="78cc4-187">Beachten Sie, dass jedes Unterverzeichnis den vollständigen Dateisatz enthält (Dateien Ihrer Anwendung und alle .NET Core-Dateien), der zum Starten Ihrer Anwendung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="78cc4-187">Note that each subdirectory contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="78cc4-188">Der Veröffentlichungsprozess gibt zusammen mit den Dateien Ihrer Anwendung eine Programmdatenbankdatei (.pdb) aus, die Debuginformationen über Ihre Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="78cc4-188">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="78cc4-189">Die Datei ist vornehmlich für das Debuggen von Ausnahmen nützlich.</span><span class="sxs-lookup"><span data-stu-id="78cc4-189">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="78cc4-190">Sie können sich auch dazu entschließen, sie nicht mit den Dateien Ihrer Anwendung zu packen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-190">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="78cc4-191">Jedoch sollten Sie sie für den Fall speichern, dass Sie das Releasebuild Ihrer App debuggen möchten.</span><span class="sxs-lookup"><span data-stu-id="78cc4-191">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="78cc4-192">Stellen Sie die veröffentlichen Dateien in einer beliebigen Weise bereit.</span><span class="sxs-lookup"><span data-stu-id="78cc4-192">Deploy the published files in any way you like.</span></span> <span data-ttu-id="78cc4-193">Sie können sie z.B. in einer ZIP-Datei verpacken, und einen einfachen `copy`-Befehl verwenden, oder sie mit jedem Installationspaket Ihrer Wahl bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-193">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="78cc4-194">Es folgt die vollständige *CSPROJ*-Datei dieses Projekts:</span><span class="sxs-lookup"><span data-stu-id="78cc4-194">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="78cc4-195">Eigenständige Bereitstellung mit Drittanbieterabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="78cc4-195">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="78cc4-196">Das Bereitstellen einer eigenständigen Bereitstellung mit einer oder mehreren Drittanbieter-Abhängigkeiten umfasst das Hinzufügen der Drittanbieter-Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="78cc4-196">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="78cc4-197">Es sind noch zwei zusätzliche Schritte nötig, bevor Sie den `dotnet restore`-Befehl ausführen können ([siehe Hinweis](#dotnet-restore-note)):</span><span class="sxs-lookup"><span data-stu-id="78cc4-197">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="78cc4-198">Fügen Sie Verweise auf Drittanbieter-Bibliotheken zum `<ItemGroup>`-Teil Ihrer *CSPROJ*-Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="78cc4-198">Add references to any third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="78cc4-199">Der folgende `<ItemGroup>`-Abschnitt verwendet Json.NET als Drittanbieter-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="78cc4-199">The following `<ItemGroup>` section uses Json.NET as a third-party library.</span></span>

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
    ```

1. <span data-ttu-id="78cc4-200">Wenn noch nicht geschehen, laden Sie das NuGet-Paket mit der Drittanbieter-Abhängigkeit auf Ihr System herunter.</span><span class="sxs-lookup"><span data-stu-id="78cc4-200">If you haven't already, download the NuGet package containing the third-party dependency to your system.</span></span> <span data-ttu-id="78cc4-201">Führen Sie nach dem Hinzufügen der Abhängigkeit den `dotnet restore`-Befehl aus ([siehe Hinweis](#dotnet-restore-note)), um die Abhängigkeit für Ihre App zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="78cc4-201">To make the dependency available to your app, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="78cc4-202">Da die Abhängigkeit zum Zeitpunkt der Veröffentlichung aus dem lokalen NuGet-Cache aufgelöst wurde, muss sie auf Ihrem System verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="78cc4-202">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="78cc4-203">Es folgt die vollständige *CSPROJ*-Datei dieses Projekts:</span><span class="sxs-lookup"><span data-stu-id="78cc4-203">The following is the complete *csproj* file for this project:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="78cc4-204">Wenn Sie Ihre Anwendung bereitstellen, sind die Drittanbieter-Abhängigkeiten, die in Ihrer Anwendung verwendet werden, auch in Ihren Anwendungsdateien enthalten.</span><span class="sxs-lookup"><span data-stu-id="78cc4-204">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="78cc4-205">Drittanbieter-Bibliotheken müssen nicht auf dem System vorhanden sein, auf dem die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="78cc4-205">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="78cc4-206">Beachten Sie, dass Sie eine eigenständige Bereitstellung mit einer Drittanbieter-Bibliothek nur auf von dieser Bibliothek unterstützten Plattformen bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="78cc4-206">Note that you can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="78cc4-207">Dies ist ähnlich, als wenn Sie über Drittanbieter-Abhängigkeiten mit nativen Abhängigkeiten in einer Framework-abhängigen Bereitstellung verfügen, wobei die nativen Abhängigkeiten mit der Plattform kompatibel sein müssen, auf der die App bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="78cc4-207">This is similar to having third-party dependencies with native dependencies in a framework-dependent deployment, where the native dependencies must be compatible with the platform to which the app is deployed.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

## <a name="see-also"></a><span data-ttu-id="78cc4-208">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78cc4-208">See also</span></span>

* [<span data-ttu-id="78cc4-209">.NET Core-Anwendungsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="78cc4-209">.NET Core Application Deployment</span></span>](index.md)
* [<span data-ttu-id="78cc4-210">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="78cc4-210">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
