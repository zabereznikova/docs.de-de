---
title: Erstellen eines globalen .NET Core-Tools
description: Beschreibt das Erstellen eines globalen Tools. Das globale Tool ist eine Konsolenanwendung, die mithilfe des .NET Core-CLIs installiert wird.
author: Thraka
ms.author: adegeo
ms.date: 08/22/2018
ms.openlocfilehash: 1daecf7234f02a5fe0dcf25cf7edbb0af327b8c1
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75343521"
---
# <a name="create-a-net-core-global-tool-using-the-net-core-cli"></a><span data-ttu-id="bbb5a-104">Erstellen eines globalen .NET Core-Tool mithilfe des .NET Core-CLIs</span><span class="sxs-lookup"><span data-stu-id="bbb5a-104">Create a .NET Core Global Tool using the .NET Core CLI</span></span>

<span data-ttu-id="bbb5a-105">In diesem Artikel erfahren Sie, wie Sie ein globales .NET Core-Tool erstellen und verpacken.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-105">This article teaches you how to create and package a .NET Core Global Tool.</span></span> <span data-ttu-id="bbb5a-106">Das .NET Core-CLI ermöglicht es Ihnen, eine Konsolenanwendung als globales Tool zu erstellen, das leicht von anderen installiert und ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-106">The .NET Core CLI allows you to create a console application as a Global Tool, which others can easily install and run.</span></span> <span data-ttu-id="bbb5a-107">Globale .NET Core-Tools sind NuGet-Pakete, die vom .NET Core-CLI aus installiert werden.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-107">.NET Core Global Tools are NuGet packages that are installed from the .NET Core CLI.</span></span> <span data-ttu-id="bbb5a-108">Weitere Informationen über globale Tools finden Sie unter [Übersicht über globale .NET Core-Tools](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bbb5a-108">For more information about Global Tools, see [.NET Core Global Tools overview](global-tools.md).</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="create-a-project"></a><span data-ttu-id="bbb5a-109">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="bbb5a-109">Create a project</span></span>

<span data-ttu-id="bbb5a-110">Dieser Artikel verwendet das .NET Core-CLI, um ein Projekt zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-110">This article uses the .NET Core CLI to create and manage a project.</span></span>

<span data-ttu-id="bbb5a-111">Als Beispieltool verwenden wir eine Konsolenanwendung, die einen ASCII-Bot generiert und eine Meldung ausgibt.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-111">Our example tool will be a console application that generates an ASCII bot and prints a message.</span></span> <span data-ttu-id="bbb5a-112">Erstellen Sie zunächst eine neue .NET Core-Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-112">First, create a new .NET Core Console Application.</span></span>

```dotnetcli
dotnet new console -o botsay
```

<span data-ttu-id="bbb5a-113">Navigieren Sie zum `botsay`-Verzeichnis, das vom vorherigen Befehl erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-113">Navigate to the `botsay` directory created by the previous command.</span></span>

## <a name="add-the-code"></a><span data-ttu-id="bbb5a-114">Hinzufügen des Codes</span><span class="sxs-lookup"><span data-stu-id="bbb5a-114">Add the code</span></span>

<span data-ttu-id="bbb5a-115">Öffnen Sie die Datei `Program.cs` in Ihrem bevorzugten Text-Editor, wie etwa `vim` oder [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="bbb5a-115">Open the `Program.cs` file with your favorite text editor, such as `vim` or [Visual Studio Code](https://code.visualstudio.com/).</span></span>

<span data-ttu-id="bbb5a-116">Fügen Sie am Anfang der Datei die folgende `using`-Anweisung hinzu; dies hilft dabei, den Code zum Anzeigen der Versionsinformationen der Anwendung kurz zu halten.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-116">Add the following `using` directive to the top of the file, this helps shorten the code to display the version information of the application.</span></span>

```csharp
using System.Reflection;
```

<span data-ttu-id="bbb5a-117">Bewegen Sie sich als Nächstes nach unten zur Methode `Main`.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-117">Next, move down to the `Main` method.</span></span> <span data-ttu-id="bbb5a-118">Ersetzen Sie die Methode durch den folgenden Code, um die Befehlszeilenargumente für Ihre Anwendung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-118">Replace the method with the following code to process the command-line arguments for your application.</span></span> <span data-ttu-id="bbb5a-119">Wenn keine Argumente übergeben wurden, wird eine kurze Hilfemeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-119">If no arguments were passed, a short help message is displayed.</span></span> <span data-ttu-id="bbb5a-120">Andernfalls werden alle diese Argumente in eine Zeichenfolge umgewandelt und zusammen mit dem Bot ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-120">Otherwise, all of those arguments are transformed into a string and printed with the bot.</span></span>

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

### <a name="create-the-bot"></a><span data-ttu-id="bbb5a-121">Erstellen des Bots</span><span class="sxs-lookup"><span data-stu-id="bbb5a-121">Create the bot</span></span>

<span data-ttu-id="bbb5a-122">Fügen Sie als Nächstes eine neue Methode mit dem Namen `ShowBot` hinzu, die einen Zeichenfolgenparameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-122">Next, add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="bbb5a-123">Diese Methode gibt die Meldung und den ASCII-Bot aus.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-123">This method prints out the message and the ASCII bot.</span></span> <span data-ttu-id="bbb5a-124">Der Code des ASCII-Bots wurde aus dem [dotnetbot](https://github.com/dotnet/core/blob/master/samples/dotnetsay/Program.cs)-Beispiel entnommen.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-124">The ASCII bot code was taken from the [dotnetbot](https://github.com/dotnet/core/blob/master/samples/dotnetsay/Program.cs) sample.</span></span>

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

### <a name="test-the-tool"></a><span data-ttu-id="bbb5a-125">Testen des Tools</span><span class="sxs-lookup"><span data-stu-id="bbb5a-125">Test the tool</span></span>

<span data-ttu-id="bbb5a-126">Führen Sie das Projekt aus, und sehen Sie sich die Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-126">Run the project and see the output.</span></span> <span data-ttu-id="bbb5a-127">Probieren Sie diese Variationen in der Befehlszeile aus, um die verschiedenen Ergebnisse anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="bbb5a-127">Try these variations at the command line to see different results:</span></span>

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- hello from the bot
```

<span data-ttu-id="bbb5a-128">Alle Argumente hinter dem Trennzeichen `--` werden an Ihre Anwendung übergeben.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-128">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="set-up-the-global-tool"></a><span data-ttu-id="bbb5a-129">Einrichten des globalen Tools</span><span class="sxs-lookup"><span data-stu-id="bbb5a-129">Set up the global tool</span></span>

<span data-ttu-id="bbb5a-130">Bevor Sie die Anwendung als ein globales Tool verpacken und verteilen können, müssen Sie die Projektdatei ändern.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-130">Before you can pack and distribute the application as a Global Tool, you need to modify the project file.</span></span> <span data-ttu-id="bbb5a-131">Öffnen Sie die Datei `botsay.csproj`, und fügen Sie dem Knoten `<Project><PropertyGroup>` drei neue XML-Knoten hinzu:</span><span class="sxs-lookup"><span data-stu-id="bbb5a-131">Open the `botsay.csproj` file and add three new XML nodes to the `<Project><PropertyGroup>` node:</span></span>

- `<PackAsTool>`\
<span data-ttu-id="bbb5a-132">[ERFORDERLICH] Gibt an, dass die Anwendung für die Installation als globales Tool verpackt wird.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-132">[REQUIRED] Indicates that the application will be packaged for install as a Global Tool.</span></span>

- `<ToolCommandName>`\
<span data-ttu-id="bbb5a-133">[OPTIONAL] Ein alternativer Name für das Tool, andernfalls wird der Befehlsname für das Tool nach der Projektdatei benannt.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-133">[OPTIONAL] An alternative name for the tool, otherwise the command name for the tool will be named after the project file.</span></span> <span data-ttu-id="bbb5a-134">Sie können mehrere Tools in einem Paket verpacken, die Wahl eines eindeutigen und eingängigen Namens erleichtert die Unterscheidung von anderen Tools im gleichen Paket.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-134">You can have multiple tools in a package, choosing a unique and friendly name helps differentiate from other tools in the same package.</span></span>

- `<PackageOutputPath>`\
<span data-ttu-id="bbb5a-135">[OPTIONAL] Ort, an dem das NuGet-Paket erzeugt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-135">[OPTIONAL] Where the NuGet package will be produced.</span></span> <span data-ttu-id="bbb5a-136">Das NuGet-Paket wird von .NET Core CLI Global Tools zur Installation Ihres Tools verwendet.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-136">The NuGet package is what the .NET Core CLI Global Tools uses to install your tool.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>

    <PackAsTool>true</PackAsTool>
    <ToolCommandName>botsay</ToolCommandName>
    <PackageOutputPath>./nupkg</PackageOutputPath>

  </PropertyGroup>

</Project>
```

<span data-ttu-id="bbb5a-137">`<PackageOutputPath>` ist zwar optional, Sie sollten es aber in diesem Beispiel verwenden.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-137">Even though `<PackageOutputPath>` is optional, use it in this example.</span></span> <span data-ttu-id="bbb5a-138">Achten Sie darauf, es festzulegen: `<PackageOutputPath>./nupkg</PackageOutputPath>`.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-138">Make sure you set it: `<PackageOutputPath>./nupkg</PackageOutputPath>`.</span></span>

<span data-ttu-id="bbb5a-139">Erstellen Sie als Nächstes ein NuGet-Paket für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-139">Next, create a NuGet package for your application.</span></span>

```dotnetcli
dotnet pack
```

<span data-ttu-id="bbb5a-140">Die `botsay.1.0.0.nupkg`-Datei wird in dem Ordner erstellt, der durch den `<PackageOutputPath>`-XML-Wert aus der `botsay.csproj`-Datei angegeben wird, in diesem Beispiel ist das der Ordner `./nupkg`.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-140">The `botsay.1.0.0.nupkg` file is created in the folder identified by the `<PackageOutputPath>` XML value from the `botsay.csproj` file, which in this example is the `./nupkg` folder.</span></span> <span data-ttu-id="bbb5a-141">Dies vereinfacht Installation und Testen.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-141">This makes it easy to install and test.</span></span> <span data-ttu-id="bbb5a-142">Wenn Sie ein Tool öffentlich herausbringen möchten, laden Sie es nach <https://www.nuget.org> hoch.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-142">When you want to release a tool publicly, upload it to <https://www.nuget.org>.</span></span> <span data-ttu-id="bbb5a-143">Sobald das Tool unter NuGet verfügbar ist, können Entwickler eine Installation des Tools für alle Benutzer mit der `--global`-Option des [dotnet tool install](dotnet-tool-install.md)-Befehls durchführen.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-143">Once the tool is available on NuGet, developers can perform a user-wide installation of the tool using the `--global` option of the [dotnet tool install](dotnet-tool-install.md) command.</span></span>

<span data-ttu-id="bbb5a-144">Da Sie jetzt ein Paket besitzen, installieren Sie das Tool aus diesem Paket:</span><span class="sxs-lookup"><span data-stu-id="bbb5a-144">Now that you have a package, install the tool from that package:</span></span>

```dotnetcli
dotnet tool install --global --add-source ./nupkg botsay
```

<span data-ttu-id="bbb5a-145">Der Parameter `--add-source` weist das .NET Core-CLI an, vorübergehend den Ordner `./nupkg` (unseren `<PackageOutputPath>`-Ordner) als zusätzlichen Quellfeed für NuGet-Pakete zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-145">The `--add-source` parameter tells the .NET Core CLI to temporarily use the `./nupkg` folder (our `<PackageOutputPath>` folder) as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="bbb5a-146">Weitere Informationen über das Installieren von globalen Tools finden Sie unter [Übersicht über globale .NET Core-Tools](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bbb5a-146">For more information about installing Global Tools, see [.NET Core Global Tools overview](global-tools.md).</span></span>

<span data-ttu-id="bbb5a-147">Wenn die Installation erfolgreich abgeschlossen wurde, wird eine Meldung angezeigt, die den Befehl zum Aufrufen des Tools und die installierte Version ähnlich wie im folgenden Beispiel anzeigt:</span><span class="sxs-lookup"><span data-stu-id="bbb5a-147">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: botsay
Tool 'botsay' (version '1.0.0') was successfully installed.
```

<span data-ttu-id="bbb5a-148">Sie sollten jetzt in der Lage sein, `botsay` einzugeben und eine Reaktion vom Tool zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-148">You should now be able to type `botsay` and get a response from the tool.</span></span>

> [!NOTE]
> <span data-ttu-id="bbb5a-149">Wenn die Installation erfolgreich war, Sie den Befehl `botsay` aber nicht verwenden können, müssen Sie möglicherweise ein neues Terminal öffnen, um die PATH-Variable zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="bbb5a-149">If the install was successful, but you cannot use the `botsay` command, you may need to open a new terminal to refresh the PATH.</span></span>

## <a name="remove-the-tool"></a><span data-ttu-id="bbb5a-150">Entfernen des Tools</span><span class="sxs-lookup"><span data-stu-id="bbb5a-150">Remove the tool</span></span>

<span data-ttu-id="bbb5a-151">Wenn Sie Ihre Experimente mit dem Tool abgeschlossen haben, können Sie es mit dem folgenden Befehl entfernen:</span><span class="sxs-lookup"><span data-stu-id="bbb5a-151">Once you're done experimenting with the tool, you can remove it with the following command:</span></span>

```dotnetcli
dotnet tool uninstall -g botsay
```
