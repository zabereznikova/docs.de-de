---
title: 'Tutorial: Erstellen eines .NET-Tools'
description: In diesem Artikel erfahren Sie, wie Sie ein .NET-Tool erstellen. Ein Tool ist eine Konsolenanwendung, die über die .NET-CLI installiert wird.
ms.topic: tutorial
ms.date: 12/14/2020
ms.openlocfilehash: dc5cf014336848ff1a3035647a386419653a083b
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633896"
---
# <a name="tutorial-create-a-net-tool-using-the-net-cli"></a><span data-ttu-id="f751a-104">Tutorial: Erstellen eines .NET-Tools mithilfe der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="f751a-104">Tutorial: Create a .NET tool using the .NET CLI</span></span>

<span data-ttu-id="f751a-105">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="f751a-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="f751a-106">In diesem Tutorial erfahren Sie, wie Sie ein .NET-Tool erstellen und packen.</span><span class="sxs-lookup"><span data-stu-id="f751a-106">This tutorial teaches you how to create and package a .NET tool.</span></span> <span data-ttu-id="f751a-107">Die .NET-CLI ermöglicht es Ihnen, eine Konsolenanwendung als Tool zu erstellen, das von anderen installiert und ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f751a-107">The .NET CLI lets you create a console application as a tool, which others can install and run.</span></span> <span data-ttu-id="f751a-108">.NET-Tools sind NuGet-Pakete, die über die .NET-CLI installiert werden.</span><span class="sxs-lookup"><span data-stu-id="f751a-108">.NET tools are NuGet packages that are installed from the .NET CLI.</span></span> <span data-ttu-id="f751a-109">Weitere Informationen zu Tools finden Sie unter [Übersicht über die .NET-Tools](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f751a-109">For more information about tools, see [.NET tools overview](global-tools.md).</span></span>

<span data-ttu-id="f751a-110">Das von Ihnen erstellte Tool ist eine Konsolenanwendung, die eine Nachricht als Eingabe verwendet und sie zusammen mit Textzeilen anzeigt, die das Bild eines Roboters erzeugen.</span><span class="sxs-lookup"><span data-stu-id="f751a-110">The tool that you'll create is a console application that takes a message as input and displays the message along with lines of text that create the image of a robot.</span></span>

<span data-ttu-id="f751a-111">Dies ist das erste in einer Reihe von drei Tutorials.</span><span class="sxs-lookup"><span data-stu-id="f751a-111">This is the first in a series of three tutorials.</span></span> <span data-ttu-id="f751a-112">In diesem Tutorial erstellen und packen Sie ein Tool.</span><span class="sxs-lookup"><span data-stu-id="f751a-112">In this tutorial, you create and package a tool.</span></span> <span data-ttu-id="f751a-113">In den nächsten beiden Tutorials verwenden Sie [das Tool als globales Tool](global-tools-how-to-use.md) und [das Tool als lokales Tool](local-tools-how-to-use.md).</span><span class="sxs-lookup"><span data-stu-id="f751a-113">In the next two tutorials you [use the tool as a global tool](global-tools-how-to-use.md) and [use the tool as a local tool](local-tools-how-to-use.md).</span></span> <span data-ttu-id="f751a-114">Die Verfahren zum Erstellen eines Tools sind unabhängig davon identisch, ob es als globales oder lokales Tool verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f751a-114">The procedures for creating a tool are the same whether you use it as a global tool or as a local tool.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f751a-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f751a-115">Prerequisites</span></span>

- <span data-ttu-id="f751a-116">[.NET SDK 5.0.100](https://dotnet.microsoft.com/download) oder höhere Versionen.</span><span class="sxs-lookup"><span data-stu-id="f751a-116">[.NET SDK 5.0.100](https://dotnet.microsoft.com/download) or a later version.</span></span>

  <span data-ttu-id="f751a-117">In diesem Tutorial wird .NET SDK 5.0 verwendet, aber die globalen Tools sind ab .NET Core SDK 2.1 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f751a-117">This tutorial uses .NET SDK 5.0, but global tools are available starting in .NET Core SDK 2.1.</span></span> <span data-ttu-id="f751a-118">Lokale .NET Core-Tools sind ab .NET Core SDK 3.0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f751a-118">Local tools are available starting in .NET Core SDK 3.0.</span></span>

- <span data-ttu-id="f751a-119">Ein Text-Editor oder Code-Editor Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="f751a-119">A text editor or code editor of your choice.</span></span>

## <a name="create-a-project"></a><span data-ttu-id="f751a-120">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="f751a-120">Create a project</span></span>

1. <span data-ttu-id="f751a-121">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *repository*.</span><span class="sxs-lookup"><span data-stu-id="f751a-121">Open a command prompt and create a folder named *repository*.</span></span>

1. <span data-ttu-id="f751a-122">Navigieren Sie zum Ordner *Repository*, und geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="f751a-122">Navigate to the *repository* folder and enter the following command:</span></span>

   ```dotnetcli
   dotnet new console -n microsoft.botsay -f net5.0
   ```

   <span data-ttu-id="f751a-123">Der Befehl erstellt einen neuen Ordner namens *microsoft.botsay* im Ordner *Repository*.</span><span class="sxs-lookup"><span data-stu-id="f751a-123">The command creates a new folder named *microsoft.botsay* under the *repository* folder.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f751a-124">In diesem Tutorial erfahren Sie, wie Sie ein Tool erstellen, das auf .NET 5.0 ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="f751a-124">For this tutorial you create a tool that targets .NET 5.0.</span></span> <span data-ttu-id="f751a-125">Wenn Sie ein anderes Framework als Ziel verwenden möchten, ändern Sie die Option `-f|--framework`.</span><span class="sxs-lookup"><span data-stu-id="f751a-125">To target a different framework, change the `-f|--framework` option.</span></span> <span data-ttu-id="f751a-126">Wenn Sie mehrere Frameworks als Ziel verwenden möchten, ändern Sie das Element `TargetFramework` wie im folgenden Beispiel gezeigt in ein `TargetFrameworks`-Element in der Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="f751a-126">To target multiple frameworks, change the `TargetFramework` element to a `TargetFrameworks` element in the project file, as shown in the following example:</span></span>
   >
   > ```xml
   > <Project Sdk="Microsoft.NET.Sdk">
   >   <PropertyGroup>
   >     <OutputType>Exe</OutputType>
   >     <TargetFrameworks>netcoreapp3.1;net5.0</TargetFrameworks>
   >   </PropertyGroup>
   > </Project>
   > ```

1. <span data-ttu-id="f751a-127">Navigieren Sie zum Ordner *microsoft.botsay*.</span><span class="sxs-lookup"><span data-stu-id="f751a-127">Navigate to the *microsoft.botsay* folder.</span></span>

   ```console
   cd microsoft.botsay
   ```

## <a name="add-the-code"></a><span data-ttu-id="f751a-128">Hinzufügen des Codes</span><span class="sxs-lookup"><span data-stu-id="f751a-128">Add the code</span></span>

1. <span data-ttu-id="f751a-129">Öffnen Sie die Datei `Program.cs` in einem Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="f751a-129">Open the `Program.cs` file with your code editor.</span></span>

1. <span data-ttu-id="f751a-130">Fügen Sie am Anfang der Datei die folgende `using`-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="f751a-130">Add the following `using` directive to the top of the file:</span></span>

   ```csharp
   using System.Reflection;
   ```

1. <span data-ttu-id="f751a-131">Ersetzen Sie die `Main`-Methode durch folgenden Code, um die Befehlszeilenargumente für die Anwendung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f751a-131">Replace the `Main` method with the following code to process the command-line arguments for the application.</span></span>

   ```csharp
   static void Main(string[] args)
   {
       if (args.Length == 0)
       {
           var versionString = Assembly.GetEntryAssembly()
                                   .GetCustomAttribute<AssemblyInformationalVersionAttribute>()
                                   .InformationalVersion
                                   .ToString();

           Console.WriteLine($"botsay v{versionString}");
           Console.WriteLine("-------------");
           Console.WriteLine("\nUsage:");
           Console.WriteLine("  botsay <message>");
           return;
       }

       ShowBot(string.Join(' ', args));
   }
   ```

   <span data-ttu-id="f751a-132">Wenn keine Argumente übergeben werden, wird eine kurze Hilfemeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f751a-132">If no arguments are passed, a short help message is displayed.</span></span> <span data-ttu-id="f751a-133">Andernfalls werden alle Argumente zu einer einzigen Zeichenfolge verkettet und durch den Aufruf der im nächsten Schritt erstellten `ShowBot`-Methode ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f751a-133">Otherwise, all of the arguments are concatenated into a single string and printed by calling the `ShowBot` method that you create in the next step.</span></span>

1. <span data-ttu-id="f751a-134">Fügen Sie eine neue Methode namens `ShowBot` hinzu, die einen Zeichenfolgenparameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="f751a-134">Add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="f751a-135">Die Methode gibt die Meldung und mithilfe von Textzeilen ein Bild eines Roboters aus.</span><span class="sxs-lookup"><span data-stu-id="f751a-135">The method prints out the message and an image of a robot using lines of text.</span></span>

   ```csharp
   static void ShowBot(string message)
   {
       string bot = $"\n        {message}";
       bot += @"
       __________________
                         \
                          \
                             ....
                             ....'
                              ....
                           ..........
                       .............'..'..
                    ................'..'.....
                  .......'..........'..'..'....
                 ........'..........'..'..'.....
                .'....'..'..........'..'.......'.
                .'..................'...   ......
                .  ......'.........         .....
                .    _            __        ......
               ..    #            ##        ......
              ....       .                 .......
              ......  .......          ............
               ................  ......................
               ........................'................
              ......................'..'......    .......
           .........................'..'.....       .......
        ........    ..'.............'..'....      ..........
      ..'..'...      ...............'.......      ..........
     ...'......     ...... ..........  ......         .......
    ...........   .......              ........        ......
   .......        '...'.'.              '.'.'.'         ....
   .......       .....'..               ..'.....
      ..       ..........               ..'........
             ............               ..............
            .............               '..............
           ...........'..              .'.'............
          ...............              .'.'.............
         .............'..               ..'..'...........
         ...............                 .'..............
          .........                        ..............
           .....
   ";
       Console.WriteLine(bot);
   }
   ```

1. <span data-ttu-id="f751a-136">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="f751a-136">Save your changes.</span></span>

## <a name="test-the-application"></a><span data-ttu-id="f751a-137">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="f751a-137">Test the application</span></span>

<span data-ttu-id="f751a-138">Führen Sie das Projekt aus, und sehen Sie sich die Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="f751a-138">Run the project and see the output.</span></span> <span data-ttu-id="f751a-139">Probieren Sie diese Variationen in der Befehlszeile aus, um die verschiedenen Ergebnisse anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="f751a-139">Try these variations at the command line to see different results:</span></span>

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

<span data-ttu-id="f751a-140">Alle Argumente hinter dem Trennzeichen `--` werden an Ihre Anwendung übergeben.</span><span class="sxs-lookup"><span data-stu-id="f751a-140">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="package-the-tool"></a><span data-ttu-id="f751a-141">Packen des Tools</span><span class="sxs-lookup"><span data-stu-id="f751a-141">Package the tool</span></span>

<span data-ttu-id="f751a-142">Bevor Sie die Anwendung als Tool packen und verteilen können, müssen Sie die Projektdatei ändern.</span><span class="sxs-lookup"><span data-stu-id="f751a-142">Before you can pack and distribute the application as a tool, you need to modify the project file.</span></span>

1. <span data-ttu-id="f751a-143">Öffnen Sie die Datei *microsoft.botsay.csproj*, und fügen Sie drei neue XML-Knoten zum Ende des `<PropertyGroup>`-Knotens hinzu:</span><span class="sxs-lookup"><span data-stu-id="f751a-143">Open the *microsoft.botsay.csproj* file and add three new XML nodes to the end of the `<PropertyGroup>` node:</span></span>

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   <span data-ttu-id="f751a-144">`<ToolCommandName>` ist ein optionales Element, das den Befehl angibt, der das Tool nach seiner Installation aufruft.</span><span class="sxs-lookup"><span data-stu-id="f751a-144">`<ToolCommandName>` is an optional element that specifies the command that will invoke the tool after it's installed.</span></span> <span data-ttu-id="f751a-145">Wenn dieses Element nicht angegeben wird, ist der Befehlsname für das Tool der Projektdateiname ohne die Erweiterung *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="f751a-145">If this element isn't provided, the command name for the tool is the project file name without the *.csproj* extension.</span></span>

   <span data-ttu-id="f751a-146">`<PackageOutputPath>` ist ein optionales Element, das bestimmt, wo das NuGet-Paket erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f751a-146">`<PackageOutputPath>` is an optional element that determines where the NuGet package will be produced.</span></span> <span data-ttu-id="f751a-147">Das NuGet-Paket wird von der .NET-CLI zur Installation Ihres Tools verwendet.</span><span class="sxs-lookup"><span data-stu-id="f751a-147">The NuGet package is what the .NET CLI uses to install your tool.</span></span>

   <span data-ttu-id="f751a-148">Die Projektdatei sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="f751a-148">The project file now looks like the following example:</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>

       <OutputType>Exe</OutputType>
       <TargetFramework>net5.0</TargetFramework>

       <PackAsTool>true</PackAsTool>
       <ToolCommandName>botsay</ToolCommandName>
       <PackageOutputPath>./nupkg</PackageOutputPath>

     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="f751a-149">Erstellen Sie ein NuGet-Paket, indem Sie den Befehl [dotnet pack](dotnet-pack.md) ausführen:</span><span class="sxs-lookup"><span data-stu-id="f751a-149">Create a NuGet package by running the [dotnet pack](dotnet-pack.md) command:</span></span>

   ```dotnetcli
   dotnet pack
   ```

   <span data-ttu-id="f751a-150">Die Datei *microsoft.botsay.1.0.0.nupkg* wird in dem Ordner erstellt, der mit dem `<PackageOutputPath>`-Wert der Datei *microsoft.botsay.csproj* angegeben wird. In diesem Beispiel handelt es sich dabei um den Ordner *./nupkg*.</span><span class="sxs-lookup"><span data-stu-id="f751a-150">The *microsoft.botsay.1.0.0.nupkg* file is created in the folder identified by the `<PackageOutputPath>` value from the *microsoft.botsay.csproj* file, which in this example is the *./nupkg* folder.</span></span>

   <span data-ttu-id="f751a-151">Wenn Sie ein Tool veröffentlichen möchten, laden Sie es in `https://www.nuget.org` hoch.</span><span class="sxs-lookup"><span data-stu-id="f751a-151">When you want to release a tool publicly, you can upload it to `https://www.nuget.org`.</span></span> <span data-ttu-id="f751a-152">Sobald das Tool in NuGet verfügbar ist, können Entwickler es mit dem Befehl [dotnet tool install](dotnet-tool-install.md) installieren.</span><span class="sxs-lookup"><span data-stu-id="f751a-152">Once the tool is available on NuGet, developers can install the tool by using the [dotnet tool install](dotnet-tool-install.md) command.</span></span> <span data-ttu-id="f751a-153">Für dieses Tutorial installieren Sie das Paket direkt aus dem lokalen Ordner *nupkg*, sodass Sie das Paket nicht auf NuGet hochladen müssen.</span><span class="sxs-lookup"><span data-stu-id="f751a-153">For this tutorial you install the package directly from the local *nupkg* folder, so there's no need to upload the package to NuGet.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="f751a-154">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="f751a-154">Troubleshoot</span></span>

<span data-ttu-id="f751a-155">Falls im Verlauf des Tutorials eine Fehlermeldung angezeigt wird, finden Sie unter [Behandlung von Problemen bei der Nutzung von .NET-Tools](troubleshoot-usage-issues.md) weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="f751a-155">If you get an error message while following the tutorial, see [Troubleshoot .NET tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f751a-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f751a-156">Next steps</span></span>

<span data-ttu-id="f751a-157">In diesem Tutorial haben Sie eine Konsolenanwendung erstellt und sie als Tool gepackt.</span><span class="sxs-lookup"><span data-stu-id="f751a-157">In this tutorial, you created a console application and packaged it as a tool.</span></span> <span data-ttu-id="f751a-158">Im nächsten Tutorial erfahren Sie, wie Sie das Tool als globales Tool verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f751a-158">To learn how to use the tool as a global tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f751a-159">Installieren und Verwenden eines globalen Tools</span><span class="sxs-lookup"><span data-stu-id="f751a-159">Install and use a global tool</span></span>](global-tools-how-to-use.md)

<span data-ttu-id="f751a-160">Auf Wunsch können Sie das Tutorial zu den globalen Tools überspringen und direkt zum Tutorial für lokale Tools übergehen.</span><span class="sxs-lookup"><span data-stu-id="f751a-160">If you prefer, you can skip the global tools tutorial and go directly to the local tools tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f751a-161">Installieren und Verwenden eines lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="f751a-161">Install and use a local tool</span></span>](local-tools-how-to-use.md)
