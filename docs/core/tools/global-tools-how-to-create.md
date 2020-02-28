---
title: 'Tutorial: Erstellen eines .NET Core-Tools'
description: Erfahren Sie, wie Sie ein .NET Core-Tool erstellen. Ein Tool ist eine Konsolenanwendung, die mithilfe der .NET Core-CLI installiert wird.
ms.date: 02/12/2020
ms.openlocfilehash: 558bf9e37efc8de68a61f1384fababe342ab7d66
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543403"
---
# <a name="tutorial-create-a-net-core-tool-using-the-net-core-cli"></a><span data-ttu-id="1d50a-104">Tutorial: Erstellen eines .NET Core-Tool mithilfe der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="1d50a-104">Tutorial: Create a .NET Core tool using the .NET Core CLI</span></span>

<span data-ttu-id="1d50a-105">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="1d50a-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="1d50a-106">In diesem Tutorial erfahren Sie, wie Sie ein .NET Core-Tool erstellen und packen.</span><span class="sxs-lookup"><span data-stu-id="1d50a-106">This tutorial teaches you how to create and package a .NET Core tool.</span></span> <span data-ttu-id="1d50a-107">Die .NET Core-CLI ermöglicht Ihnen, eine Konsolenanwendung als Tool zu erstellen, das von anderen installiert und ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1d50a-107">The .NET Core CLI lets you create a console application as a tool, which others can install and run.</span></span> <span data-ttu-id="1d50a-108">.NET Core-Tools sind NuGet-Pakete, die über die .NET Core-CLI installiert werden.</span><span class="sxs-lookup"><span data-stu-id="1d50a-108">.NET Core tools are NuGet packages that are installed from the .NET Core CLI.</span></span> <span data-ttu-id="1d50a-109">Weitere Informationen zu Tools finden Sie unter [Übersicht über .NET Core-Tools](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1d50a-109">For more information about tools, see [.NET Core tools overview](global-tools.md).</span></span>

<span data-ttu-id="1d50a-110">Das von Ihnen erstellte Tool ist eine Konsolenanwendung, die eine Nachricht als Eingabe verwendet und sie zusammen mit Textzeilen anzeigt, die das Bild eines Roboters erzeugen.</span><span class="sxs-lookup"><span data-stu-id="1d50a-110">The tool that you'll create is a console application that takes a message as input and displays the message along with lines of text that create the image of a robot.</span></span>

<span data-ttu-id="1d50a-111">Dies ist das erste in einer Reihe von drei Tutorials.</span><span class="sxs-lookup"><span data-stu-id="1d50a-111">This is the first in a series of three tutorials.</span></span> <span data-ttu-id="1d50a-112">In diesem Tutorial erstellen und packen Sie ein Tool.</span><span class="sxs-lookup"><span data-stu-id="1d50a-112">In this tutorial, you create and package a tool.</span></span> <span data-ttu-id="1d50a-113">In den nächsten beiden Tutorials verwenden Sie [das Tool als globales Tool](global-tools-how-to-use.md) und [das Tool als lokales Tool](local-tools-how-to-use.md).</span><span class="sxs-lookup"><span data-stu-id="1d50a-113">In the next two tutorials you [use the tool as a global tool](global-tools-how-to-use.md) and [use the tool as a local tool](local-tools-how-to-use.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1d50a-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1d50a-114">Prerequisites</span></span>

- <span data-ttu-id="1d50a-115">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) oder neuere Version.</span><span class="sxs-lookup"><span data-stu-id="1d50a-115">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or a later version.</span></span>

  <span data-ttu-id="1d50a-116">Dieses Tutorial und das folgende [Tutorial für globale Tools](global-tools-how-to-use.md) gelten für .NET Core SDK 2.1 und neuere Versionen, da globale Tools ab dieser Version verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1d50a-116">This tutorial and the following [tutorial for global tools](global-tools-how-to-use.md) apply to .NET Core SDK 2.1 and later versions because global tools are available starting in that version.</span></span> <span data-ttu-id="1d50a-117">Dieses Tutorial setzt jedoch voraus, dass Sie mindestens Version 3.1 installiert haben, sodass Sie die Möglichkeit haben, mit dem [Tutorial zu lokalen Tools](local-tools-how-to-use.md) fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="1d50a-117">But this tutorial assumes you have installed 3.1 or later so that you have the option of continuing on to the [local tools tutorial](local-tools-how-to-use.md).</span></span> <span data-ttu-id="1d50a-118">Lokale .NET Core-Tools sind ab .NET Core SDK 3.0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1d50a-118">Local tools are available starting in .NET Core SDK 3.0.</span></span> <span data-ttu-id="1d50a-119">Die Verfahren zum Erstellen eines Tools sind unabhängig davon identisch, ob es als globales oder lokales Tool verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1d50a-119">The procedures for creating a tool are the same whether you use it as a global tool or as a local tool.</span></span>
  
- <span data-ttu-id="1d50a-120">Ein Text-Editor oder Code-Editor Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="1d50a-120">A text editor or code editor of your choice.</span></span>

## <a name="create-a-project"></a><span data-ttu-id="1d50a-121">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="1d50a-121">Create a project</span></span>

1. <span data-ttu-id="1d50a-122">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *repository*.</span><span class="sxs-lookup"><span data-stu-id="1d50a-122">Open a command prompt and create a folder named *repository*.</span></span>

1. <span data-ttu-id="1d50a-123">Navigieren Sie zum Ordner *repository*, und geben Sie den folgenden Befehl ein, wobei `<name>` durch einen eindeutigen Wert ersetzt wird, um den Projektnamen eindeutig zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="1d50a-123">Navigate to the *repository* folder and enter the following command, replacing `<name>` with a unique value to make the project name unique.</span></span> 

   ```dotnetcli
   dotnet new console -n botsay-<name>
   ```

   <span data-ttu-id="1d50a-124">Sie können beispielsweise den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="1d50a-124">For example, you could run the following command:</span></span>

   ```dotnetcli
   dotnet new console -n botsay-nancydavolio
   ```

   <span data-ttu-id="1d50a-125">Der Befehl erstellt unter dem Ordner *repository* einen neuen Ordner namens *botsay-\<name>* .</span><span class="sxs-lookup"><span data-stu-id="1d50a-125">The command creates a new folder named *botsay-\<name>* under the *repository* folder.</span></span>

1. <span data-ttu-id="1d50a-126">Navigieren Sie zum Ordner *botsay-\<name>* .</span><span class="sxs-lookup"><span data-stu-id="1d50a-126">Navigate to the *botsay-\<name>* folder.</span></span>

   ```console
   cd botsay-<name>
   ```

## <a name="add-the-code"></a><span data-ttu-id="1d50a-127">Hinzufügen des Codes</span><span class="sxs-lookup"><span data-stu-id="1d50a-127">Add the code</span></span>

1. <span data-ttu-id="1d50a-128">Öffnen Sie die Datei `Program.cs` in einem Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="1d50a-128">Open the `Program.cs` file with your code editor.</span></span>

1. <span data-ttu-id="1d50a-129">Fügen Sie am Anfang der Datei die folgende `using`-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="1d50a-129">Add the following `using` directive to the top of the file:</span></span>

   ```csharp
   using System.Reflection;
   ```

1. <span data-ttu-id="1d50a-130">Ersetzen Sie die `Main`-Methode durch folgenden Code, um die Befehlszeilenargumente für die Anwendung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1d50a-130">Replace the `Main` method with the following code to process the command-line arguments for the application.</span></span>

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

   <span data-ttu-id="1d50a-131">Wenn keine Argumente übergeben werden, wird eine kurze Hilfemeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d50a-131">If no arguments are passed, a short help message is displayed.</span></span> <span data-ttu-id="1d50a-132">Andernfalls werden alle Argumente zu einer einzigen Zeichenfolge verkettet und durch den Aufruf der im nächsten Schritt erstellten `ShowBot`-Methode ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="1d50a-132">Otherwise, all of the arguments are concatenated into a single string and printed by calling the `ShowBot` method that you create in the next step.</span></span>

1. <span data-ttu-id="1d50a-133">Fügen Sie eine neue Methode namens `ShowBot` hinzu, die einen Zeichenfolgenparameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d50a-133">Add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="1d50a-134">Die Methode gibt die Meldung und mithilfe von Textzeilen ein Bild eines Roboters aus.</span><span class="sxs-lookup"><span data-stu-id="1d50a-134">The method prints out the message and an image of a robot using lines of text.</span></span>

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

1. <span data-ttu-id="1d50a-135">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="1d50a-135">Save your changes.</span></span>

## <a name="test-the-application"></a><span data-ttu-id="1d50a-136">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="1d50a-136">Test the application</span></span>

<span data-ttu-id="1d50a-137">Führen Sie das Projekt aus, und sehen Sie sich die Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="1d50a-137">Run the project and see the output.</span></span> <span data-ttu-id="1d50a-138">Probieren Sie diese Variationen in der Befehlszeile aus, um die verschiedenen Ergebnisse anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="1d50a-138">Try these variations at the command line to see different results:</span></span>

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

<span data-ttu-id="1d50a-139">Alle Argumente hinter dem Trennzeichen `--` werden an Ihre Anwendung übergeben.</span><span class="sxs-lookup"><span data-stu-id="1d50a-139">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="package-the-tool"></a><span data-ttu-id="1d50a-140">Packen des Tools</span><span class="sxs-lookup"><span data-stu-id="1d50a-140">Package the tool</span></span>

<span data-ttu-id="1d50a-141">Bevor Sie die Anwendung als Tool packen und verteilen können, müssen Sie die Projektdatei ändern.</span><span class="sxs-lookup"><span data-stu-id="1d50a-141">Before you can pack and distribute the application as a tool, you need to modify the project file.</span></span> 

1. <span data-ttu-id="1d50a-142">Öffnen Sie die Datei *botsay-\<name>.csproj*, und fügen Sie am Ende des Knotens `<PropertyGroup>` drei neue XML-Knoten hinzu:</span><span class="sxs-lookup"><span data-stu-id="1d50a-142">Open the *botsay-\<name>.csproj* file and add three new XML nodes to the end of the `<PropertyGroup>` node:</span></span>

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   <span data-ttu-id="1d50a-143">`<ToolCommandName>` ist ein optionales Element, das den Befehl angibt, der das Tool nach seiner Installation aufruft.</span><span class="sxs-lookup"><span data-stu-id="1d50a-143">`<ToolCommandName>` is an optional element that specifies the command that will invoke the tool after it's installed.</span></span> <span data-ttu-id="1d50a-144">Wenn dieses Element nicht angegeben wird, ist der Befehlsname für das Tool der Projektdateiname ohne die Erweiterung *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="1d50a-144">If this element isn't provided, the command name for the tool is the project file name without the *.csproj* extension.</span></span>

   <span data-ttu-id="1d50a-145">`<PackageOutputPath>` ist ein optionales Element, das bestimmt, wo das NuGet-Paket erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1d50a-145">`<PackageOutputPath>` is an optional element that determines where the NuGet package will be produced.</span></span> <span data-ttu-id="1d50a-146">Das NuGet-Paket wird von der .NET Core-CLI zur Installation Ihres Tools verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d50a-146">The NuGet package is what the .NET Core CLI uses to install your tool.</span></span>

   <span data-ttu-id="1d50a-147">Die Projektdatei sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="1d50a-147">The project file now looks like the following example:</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">
  
     <PropertyGroup>

       <OutputType>Exe</OutputType>
       <TargetFramework>netcoreapp3.1</TargetFramework>
  
       <PackAsTool>true</PackAsTool>
       <ToolCommandName>botsay</ToolCommandName>
       <PackageOutputPath>./nupkg</PackageOutputPath>
  
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="1d50a-148">Erstellen Sie ein NuGet-Paket, indem Sie den Befehl [dotnet pack](dotnet-pack.md) ausführen:</span><span class="sxs-lookup"><span data-stu-id="1d50a-148">Create a NuGet package by running the [dotnet pack](dotnet-pack.md) command:</span></span>

   ```dotnetcli
   dotnet pack
   ```

   <span data-ttu-id="1d50a-149">Die Datei *botsay-\<name>.1.0.0.nupkg* wird in dem Ordner erstellt, der mit dem Wert `<PackageOutputPath>` in der Datei *botsay-\<name>.csproj* angegeben wird. In diesem Beispiel ist das der Ordner *./nupkg*.</span><span class="sxs-lookup"><span data-stu-id="1d50a-149">The *botsay-\<name>.1.0.0.nupkg* file is created in the folder identified by the `<PackageOutputPath>` value from the *botsay-\<name>.csproj* file, which in this example is the *./nupkg* folder.</span></span>
  
   <span data-ttu-id="1d50a-150">Wenn Sie ein Tool veröffentlichen möchten, laden Sie es in `https://www.nuget.org` hoch.</span><span class="sxs-lookup"><span data-stu-id="1d50a-150">When you want to release a tool publicly, you can upload it to `https://www.nuget.org`.</span></span> <span data-ttu-id="1d50a-151">Sobald das Tool in NuGet verfügbar ist, können Entwickler es mit dem Befehl [dotnet tool install](dotnet-tool-install.md) installieren.</span><span class="sxs-lookup"><span data-stu-id="1d50a-151">Once the tool is available on NuGet, developers can install the tool by using the [dotnet tool install](dotnet-tool-install.md) command.</span></span> <span data-ttu-id="1d50a-152">Für dieses Tutorial installieren Sie das Paket direkt aus dem lokalen Ordner *nupkg*, sodass Sie das Paket nicht auf NuGet hochladen müssen.</span><span class="sxs-lookup"><span data-stu-id="1d50a-152">For this tutorial you install the package directly from the local *nupkg* folder, so there's no need to upload the package to NuGet.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="1d50a-153">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="1d50a-153">Troubleshoot</span></span>

<span data-ttu-id="1d50a-154">Falls im Verlauf des Tutorials eine Fehlermeldung angezeigt wird, finden Sie unter [Behandlung von Problemen bei der Nutzung von .NET Core-Tools](troubleshoot-usage-issues.md) weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="1d50a-154">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1d50a-155">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1d50a-155">Next steps</span></span>

<span data-ttu-id="1d50a-156">In diesem Tutorial haben Sie eine Konsolenanwendung erstellt und sie als Tool gepackt.</span><span class="sxs-lookup"><span data-stu-id="1d50a-156">In this tutorial, you created a console application and packaged it as a tool.</span></span> <span data-ttu-id="1d50a-157">Im nächsten Tutorial erfahren Sie, wie Sie das Tool als globales Tool verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1d50a-157">To learn how to use the tool as a global tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1d50a-158">Installieren und Verwenden eines globalen Tools</span><span class="sxs-lookup"><span data-stu-id="1d50a-158">Install and use a global tool</span></span>](global-tools-how-to-use.md)

<span data-ttu-id="1d50a-159">Auf Wunsch können Sie das Tutorial zu den globalen Tools überspringen und direkt zum Tutorial für lokale Tools übergehen.</span><span class="sxs-lookup"><span data-stu-id="1d50a-159">If you prefer, you can skip the global tools tutorial and go directly to the local tools tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1d50a-160">Installieren und Verwenden eines lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="1d50a-160">Install and use a local tool</span></span>](local-tools-how-to-use.md)
