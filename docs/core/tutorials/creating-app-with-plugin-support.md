---
title: Erstellen einer .NET Core-Anwendung mit Plug-Ins
description: Erfahren Sie, wie Sie eine .NET Core-Anwendung erstellen, die Plug-Ins unterstützt.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/28/2019
ms.openlocfilehash: a9431ee28c7df21a8688f845be20e062eca21887
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773427"
---
# <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="fc9ee-103">Erstellen einer .NET Core-Anwendung mit Plug-Ins</span><span class="sxs-lookup"><span data-stu-id="fc9ee-103">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="fc9ee-104">In diesem Tutorial lernen Sie:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-104">This tutorial shows you how to:</span></span>

- <span data-ttu-id="fc9ee-105">Strukturieren eines Projekts zur Unterstützung von Plug-Ins</span><span class="sxs-lookup"><span data-stu-id="fc9ee-105">Structure a project to support plugins.</span></span>
- <span data-ttu-id="fc9ee-106">Erstellen einer benutzerdefinierten <xref:System.Runtime.Loader.AssemblyLoadContext>-Klasse zum Laden jedes Plug-Ins</span><span class="sxs-lookup"><span data-stu-id="fc9ee-106">Create a custom <xref:System.Runtime.Loader.AssemblyLoadContext> to load each plugin.</span></span>
- <span data-ttu-id="fc9ee-107">Verwenden des Typs `System.Runtime.Loader.AssemblyDependencyResolver` zum Ermöglichen von Abhängigkeiten für Plug-Ins</span><span class="sxs-lookup"><span data-stu-id="fc9ee-107">Use the `System.Runtime.Loader.AssemblyDependencyResolver` type to allow plugins to have dependencies.</span></span>
- <span data-ttu-id="fc9ee-108">Schreiben von Plug-Ins, die mühelos durch Kopieren der Buildartefakte bereitgestellt werden können</span><span class="sxs-lookup"><span data-stu-id="fc9ee-108">Author plugins that can be easily deployed by just copying the build artifacts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fc9ee-109">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="fc9ee-109">Prerequisites</span></span>

- <span data-ttu-id="fc9ee-110">Installieren Sie das [.NET Core 3.0 Preview 2 SDK](https://www.microsoft.com/net/core) oder eine neuere Version.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-110">Install the [.NET Core 3.0 Preview 2 SDK](https://www.microsoft.com/net/core) or a newer version.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="fc9ee-111">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="fc9ee-111">Create the application</span></span>

<span data-ttu-id="fc9ee-112">Im ersten Schritt erstellen Sie die Anwendung:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-112">The first step is to create the application:</span></span>

1. <span data-ttu-id="fc9ee-113">Erstellen Sie einen neuen Ordner, und führen Sie `dotnet new console -o AppWithPlugin` in diesem Ordner aus.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-113">Create a new folder, and in that folder run `dotnet new console -o AppWithPlugin`.</span></span> 
2. <span data-ttu-id="fc9ee-114">Erstellen Sie eine Visual Studio-Projektmappendatei, um das Erstellen des Projekts zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-114">To make building the project easier, create a Visual Studio solution file.</span></span> <span data-ttu-id="fc9ee-115">Führen Sie `dotnet new sln` im gleichen Ordner aus.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-115">Run `dotnet new sln` in the same folder.</span></span> 
3. <span data-ttu-id="fc9ee-116">Führen Sie `dotnet sln add AppWithPlugin/AppWithPlugin.csproj` aus, um das App-Projekt zur Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-116">Run `dotnet sln add AppWithPlugin/AppWithPlugin.csproj` to add the app project to the solution.</span></span>

<span data-ttu-id="fc9ee-117">Das Gerüst der Anwendung kann nun aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-117">Now we can fill in the skeleton of our application.</span></span> <span data-ttu-id="fc9ee-118">Ersetzen Sie den Code der Datei *AppWithPlugin/Program.cs* durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-118">Replace the code in the *AppWithPlugin/Program.cs* file with the following code:</span></span>

```csharp
using PluginBase;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Reflection;

namespace AppWithPlugin
{
    class Program
    {
        static void Main(string[] args)
        {
            try
            {
                if (args.Length == 1 && args[0] == "/d")
                {
                    Console.WriteLine("Waiting for any key...");
                    Console.ReadLine();
                }

                // Load commands from plugins.

                if (args.Length == 0)
                {
                    Console.WriteLine("Commands: ");
                    // Output the loaded commands.
                }
                else
                {
                    foreach (string commandName in args)
                    {
                        Console.WriteLine($"-- {commandName} --");

                        // Execute the command with the name passed as an argument.

                        Console.WriteLine();
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex);
            }
        }
    }
}

```

## <a name="create-the-plugin-interfaces"></a><span data-ttu-id="fc9ee-119">Erstellen der Plug-In-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fc9ee-119">Create the plugin interfaces</span></span>

<span data-ttu-id="fc9ee-120">Der nächste Schritt zum Erstellen einer App mit Plug-Ins besteht im Definieren der Schnittstelle, die die Plug-Ins implementieren müssen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-120">The next step in building an app with plugins is defining the interface the plugins need to implement.</span></span> <span data-ttu-id="fc9ee-121">Es wird empfohlen, dass Sie eine Klassenbibliothek erstellen, die alle Typen enthält, die Sie für die Kommunikation zwischen Ihrer App und den Plug-Ins verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-121">We suggest that you make a class library that contains any types that you plan to use for communicating between your app and plugins.</span></span> <span data-ttu-id="fc9ee-122">Diese Trennung ermöglicht Ihnen das Veröffentlichen Ihrer Plug-In-Schnittstelle als Paket, ohne die vollständige Anwendung senden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-122">This division allows you to publish your plugin interface as a package without having to ship your full application.</span></span>

<span data-ttu-id="fc9ee-123">Führen Sie `dotnet new classlib -o PluginBase` im Stammverzeichnis des Projekts aus.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-123">In the root folder of the project, run `dotnet new classlib -o PluginBase`.</span></span> <span data-ttu-id="fc9ee-124">Führen Sie außerdem `dotnet sln add PluginBase/PluginBase.csproj` aus, um das Projekt zur Projektmappendatei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-124">Also, run `dotnet sln add PluginBase/PluginBase.csproj` to add the project to the solution file.</span></span> <span data-ttu-id="fc9ee-125">Löschen Sie die Datei `PluginBase/Class1.cs`, und erstellen Sie eine neue Datei im `PluginBase`-Ordner namens `ICommand.cs` mit der folgenden Schnittstellendefinition:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-125">Delete the `PluginBase/Class1.cs` file, and create a new file in the `PluginBase` folder named `ICommand.cs` with the following interface definition:</span></span>

[!code-csharp[the-plugin-interface](~/samples/core/extensions/AppWithPlugin/PluginBase/ICommand.cs)]

<span data-ttu-id="fc9ee-126">Diese `ICommand`-Schnittstelle ist die, die von allen Plug-Ins implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-126">This `ICommand` interface is the interface that all of the plugins will implement.</span></span>

<span data-ttu-id="fc9ee-127">Nachdem die `ICommand`-Schnittstelle definiert wurde, kann das Anwendungsprojekt ein wenig mehr aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-127">Now that the `ICommand` interface is defined, the application project can be filled in a little more.</span></span> <span data-ttu-id="fc9ee-128">Fügen Sie einen Verweis vom `AppWithPlugin`-Projekt auf das `PluginBase`-Projekt mit dem Befehl `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj` aus dem Stammverzeichnis hinzu.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-128">Add a reference from the `AppWithPlugin` project to the `PluginBase` project with the `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj`  command from the root folder.</span></span>

<span data-ttu-id="fc9ee-129">Ersetzen Sie den Kommentar `// Load commands from plugins` durch den folgenden Codeausschnitt, um das Laden von Plug-Ins aus den angegebenen Dateipfaden zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-129">Replace the `// Load commands from plugins` comment with the following code snippet to enable it to load plugins from given file paths:</span></span>

```csharp
string[] pluginPaths = new string[]
{
    // Paths to plugins to load.
};

IEnumerable<ICommand> commands = pluginPaths.SelectMany(pluginPath =>
{
    Assembly pluginAssembly = LoadPlugin(pluginPath);
    return CreateCommands(pluginAssembly);
}).ToList();
```

<span data-ttu-id="fc9ee-130">Ersetzen Sie dann den Kommentar `// Output the loaded commands` durch folgenden Codeausschnitt:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-130">Then replace the `// Output the loaded commands` comment with the following code snippet:</span></span>

```csharp
foreach (ICommand command in commands)
{
    Console.WriteLine($"{command.Name}\t - {command.Description}");
}
```

<span data-ttu-id="fc9ee-131">Ersetzen Sie den Kommentar `// Execute the command with the name passed as an argument` durch folgenden Codeausschnitt:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-131">Replace the `// Execute the command with the name passed as an argument` comment with the following snippet:</span></span>

```csharp
ICommand command = commands.FirstOrDefault(c => c.Name == commandName);
if (command == null)
{
    Console.WriteLine("No such command is known.");
    return;
}

command.Execute();
```

<span data-ttu-id="fc9ee-132">Fügen Sie schließlich die statischen Methoden namens `LoadPlugin` und `CreateCommands` wie folgt zur `Program`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-132">And finally, add static methods to the `Program` class named `LoadPlugin` and `CreateCommands`, as shown here:</span></span>

```csharp
static Assembly LoadPlugin(string relativePath)
{
    throw new NotImplementedException();
}

static IEnumerable<ICommand> CreateCommands(Assembly assembly)
{
    int count = 0;

    foreach (Type type in assembly.GetTypes())
    {
        if (typeof(ICommand).IsAssignableFrom(type))
        {
            ICommand result = Activator.CreateInstance(type) as ICommand;
            if (result != null)
            {
                count++;
                yield return result;
            }
        }
    }

    if (count == 0)
    {
        string availableTypes = string.Join(",", assembly.GetTypes().Select(t => t.FullName));
        throw new ApplicationException(
            $"Can't find any type which implements ICommand in {assembly} from {assembly.Location}.\n" +
            $"Available types: {availableTypes}");
    }
}
```

## <a name="load-plugins"></a><span data-ttu-id="fc9ee-133">Laden der Plug-Ins</span><span class="sxs-lookup"><span data-stu-id="fc9ee-133">Load plugins</span></span>

<span data-ttu-id="fc9ee-134">Die Anwendung kann jetzt ordnungsgemäß geladen werden und Befehle aus geladenen Plug-In-Assemblys instanziieren, jedoch kann sie die Plug-In-Assemblys noch nicht laden.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-134">Now the application can correctly load and instantiate commands from loaded plugin assemblies, but it is still unable to load the plugin assemblies.</span></span> <span data-ttu-id="fc9ee-135">Erstellen Sie eine Datei namens *PluginLoadContext.cs* mit den folgenden Inhalten im Ordner *AppWithPlugin*:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-135">Create a file named *PluginLoadContext.cs* in the *AppWithPlugin* folder with the following contents:</span></span>

[!code-csharp[loading-plugins](~/samples/core/extensions/AppWithPlugin/AppWithPlugin/PluginLoadContext.cs)]

<span data-ttu-id="fc9ee-136">Der Typ `PluginLoadContext` wird von <xref:System.Runtime.Loader.AssemblyLoadContext> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-136">The `PluginLoadContext` type derives from <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="fc9ee-137">Der Typ `AssemblyLoadContext` ist ein spezieller Typ in der Runtime, der Entwicklern ermöglicht, geladene Assemblys in verschiedenen Gruppen zu isolieren, um sicherzustellen, dass die Assemblyversionen nicht im Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-137">The `AssemblyLoadContext` type is a special type in the runtime that allows developers to isolate loaded assemblies into different groups to ensure that assembly versions do not conflict.</span></span> <span data-ttu-id="fc9ee-138">Darüber hinaus kann eine benutzerdefinierte `AssemblyLoadContext`-Klasse verschiedene Pfade zum Laden von Assemblys und zum Überschreiben des Standardverhaltens verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-138">Additionally, a custom `AssemblyLoadContext` can choose different paths to load assemblies from and override the default behavior.</span></span> <span data-ttu-id="fc9ee-139">`PluginLoadContext` verwendet eine Instanz vom Typ `AssemblyDependencyResolver`, die in .NET Core 3.0 eingeführt wurde, um Assemblynamen in Pfade aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-139">The `PluginLoadContext` uses an instance of the `AssemblyDependencyResolver` type introduced in .NET Core 3.0 to resolve assembly names to paths.</span></span> <span data-ttu-id="fc9ee-140">Das `AssemblyDependencyResolver`-Objekt wird mit dem Pfad zu einer .NET-Klassenbibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-140">The `AssemblyDependencyResolver` object is constructed with the path to a .NET class library.</span></span> <span data-ttu-id="fc9ee-141">Es löst Assemblys und native Bibliotheken basierend auf der *deps.json* in ihre relativen Pfade für die Klassenbibliothek auf, deren Pfad an den Konstruktor `AssemblyDependencyResolver` übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-141">It resolves assemblies and native libraries to their relative paths based on the *deps.json* file for the class library whose path was passed to the `AssemblyDependencyResolver` constructor.</span></span> <span data-ttu-id="fc9ee-142">Das benutzerdefinierte Objekt `AssemblyLoadContext` ermöglicht eigene Abhängigkeiten für Plug-Ins, und `AssemblyDependencyResolver` erleichtert das richtige Laden der Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-142">The custom `AssemblyLoadContext` enables plugins to have their own dependencies, and the `AssemblyDependencyResolver` makes it easy to correctly load the dependencies.</span></span>

<span data-ttu-id="fc9ee-143">Da das `AppWithPlugin`-Projekt nun über den Typ `PluginLoadContext` verfügt, aktualisieren Sie die `Program.LoadPlugin`-Methode mit folgendem Text:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-143">Now that the `AppWithPlugin` project has the `PluginLoadContext` type, update the `Program.LoadPlugin` method with the following body:</span></span>

```csharp
static Assembly LoadPlugin(string relativePath)
{
    // Navigate up to the solution root
    string root = Path.GetFullPath(Path.Combine(
        Path.GetDirectoryName(
            Path.GetDirectoryName(
                Path.GetDirectoryName(
                    Path.GetDirectoryName(
                        Path.GetDirectoryName(typeof(Program).Assembly.Location)))))));

    string pluginLocation = Path.GetFullPath(Path.Combine(root, relativePath.Replace('\\', Path.DirectorySeparatorChar)));
    Console.WriteLine($"Loading commands from: {pluginLocation}");
    PluginLoadContext loadContext = new PluginLoadContext(pluginLocation);
    return loadContext.LoadFromAssemblyName(new AssemblyName(Path.GetFileNameWithoutExtension(pluginLocation)));
}
```

<span data-ttu-id="fc9ee-144">Aufgrund der verschiedenen `PluginLoadContext`-Instanzen für jedes Plug-In können die Plug-Ins problemlos verschiedene oder sogar in Konflikt stehende Abhängigkeiten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-144">By using a different `PluginLoadContext` instance for each plugin, the plugins can have different or even conflicting dependencies without issue.</span></span>

## <a name="create-a-simple-plugin-with-no-dependencies"></a><span data-ttu-id="fc9ee-145">Erstellen eines einfachen Plug-Ins ohne Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="fc9ee-145">Create a simple plugin with no dependencies</span></span>

<span data-ttu-id="fc9ee-146">Führen Sie folgende Schritte im Stammverzeichnis aus:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-146">Back in the root folder, do the following:</span></span>

1. <span data-ttu-id="fc9ee-147">Führen Sie `dotnet new classlib -o HelloPlugin` aus, um ein neues Klassenbibliotheksprojekt namens `HelloPlugin` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-147">Run `dotnet new classlib -o HelloPlugin` to create a new class library project named `HelloPlugin`.</span></span>
2. <span data-ttu-id="fc9ee-148">Führen Sie `dotnet sln add HelloPlugin/HelloPlugin.csproj` aus, um das Projekt zur `AppWithPlugin`-Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-148">Run `dotnet sln add HelloPlugin/HelloPlugin.csproj` to add the project to the `AppWithPlugin` solution.</span></span> 
3. <span data-ttu-id="fc9ee-149">Ersetzen Sie die Datei *HelloPlugin/Class1.cs* durch eine Datei namens *HelloCommand.cs* mit folgendem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-149">Replace the *HelloPlugin/Class1.cs* file with a file named *HelloCommand.cs* with the following contents:</span></span>

[!code-csharp[the-hello-plugin](~/samples/core/extensions/AppWithPlugin/HelloPlugin/HelloCommand.cs)]

<span data-ttu-id="fc9ee-150">Öffnen Sie jetzt die Datei *HelloPlugin.csproj*.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-150">Now, open the *HelloPlugin.csproj* file.</span></span> <span data-ttu-id="fc9ee-151">Der Inhalt sollte Folgendem ähnlich sehen:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-151">It should look similar to the following:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>

```

<span data-ttu-id="fc9ee-152">Fügen Sie die folgenden Elemente zwischen den `<Project>`-Tags ein:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-152">In between the `<Project>` tags, add the following elements:</span></span>

```xml
<ItemGroup>
<ProjectReference Include="..\PluginBase\PluginBase.csproj">
    <Private>false</Private>
</ProjectReference>
</ItemGroup>
```

<span data-ttu-id="fc9ee-153">Das Element `<Private>false</Private>` ist sehr wichtig.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-153">The `<Private>false</Private>` element is very important.</span></span> <span data-ttu-id="fc9ee-154">Es weist MSBuild dazu an, die *PluginBase.dll* nicht in das Ausgabeverzeichnis für „HelloPlugin“ zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-154">This tells MSBuild to not copy *PluginBase.dll* to the output directory for HelloPlugin.</span></span> <span data-ttu-id="fc9ee-155">Wenn die Assembly *PluginBase.dll* im Ausgabeverzeichnis enthalten ist, findet `PluginLoadContext` die Assembly dort und lädt sie, wenn die Assembly *HelloPlugin.dll* geladen wird.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-155">If the *PluginBase.dll* assembly is present in the output directory, `PluginLoadContext` will find the assembly there and load it when it loads the *HelloPlugin.dll* assembly.</span></span> <span data-ttu-id="fc9ee-156">An diesem Punkt implementiert der Typ `HelloPlugin.HelloCommand` die `ICommand`-Schnittstelle aus der *PluginBase.dll* in das Ausgabeverzeichnis des `HelloPlugin`-Projekts und nicht die `ICommand`-Schnittstelle, die in den Standardladekontext geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-156">At this point, the `HelloPlugin.HelloCommand` type will implement the `ICommand` interface from the *PluginBase.dll* in the output directory of the `HelloPlugin` project, not the `ICommand` interface that is loaded into the default load context.</span></span> <span data-ttu-id="fc9ee-157">Da die Runtime die beiden Typen als verschiedene Typen aus verschiedenen Assemblys erkennt, findet die Methode `AppWithPlugin.Program.CreateCommands` die Befehle nicht.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-157">Since the runtime sees these two types as different types from different assemblies, the `AppWithPlugin.Program.CreateCommands` method will not find the commands.</span></span> <span data-ttu-id="fc9ee-158">Daher sind die `<Private>false</Private>`-Metadaten für den Verweis auf die Assembly erforderlich, die die Plug-In-Schnittstellen enthält.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-158">As a result, the `<Private>false</Private>` metadata is required for the reference to the assembly containing the plugin interfaces.</span></span>

<span data-ttu-id="fc9ee-159">Nach Fertigstellung des `HelloPlugin`-Projekts sollten Sie das `AppWithPlugin`-Projekt aktualisieren, um in Erfahrung zu bringen, wo sich das `HelloPlugin`-Plug-In befindet.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-159">Now that the `HelloPlugin` project is complete, we should update the `AppWithPlugin` project to know where the `HelloPlugin` plugin can be found.</span></span> <span data-ttu-id="fc9ee-160">Fügen Sie `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` als ein Element des `pluginPaths`-Arrays nach dem Kommentar `// Paths to plugins to load` hinzu.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-160">After the `// Paths to plugins to load` comment, add `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` as an element of the `pluginPaths` array.</span></span>

## <a name="create-a-plugin-with-library-dependencies"></a><span data-ttu-id="fc9ee-161">Erstellen eines Plug-Ins mit Bibliotheksabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="fc9ee-161">Create a plugin with library dependencies</span></span>

<span data-ttu-id="fc9ee-162">Fast alle Plug-Ins sind komplexer als eine einfaches „Hallo Welt“-Programm, und viele Plug-Ins weisen Abhängigkeiten von anderen Bibliotheken auf.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-162">Almost all plugins are more complex than a simple "Hello World", and many plugins have dependencies on other libraries.</span></span> <span data-ttu-id="fc9ee-163">Im Beispiel veranschaulichen die Plug-In-Projekte `JsonPlugin` und `OldJson` zwei verschiedene Plug-Ins mit NuGet-Paketabhängigkeiten von `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-163">The `JsonPlugin` and `OldJson` plugin projects in the sample show two examples of plugins with NuGet package dependencies on `Newtonsoft.Json`.</span></span> <span data-ttu-id="fc9ee-164">Die Projektdateien selbst enthalten keine speziellen Informationen für die Projektverweise, und die Plug-Ins werden (nachdem die Plug-In-Pfade zum `pluginPaths`-Array hinzugefügt wurden) problemlos ausgeführt, auch wenn sie in derselben Ausführung der AppWithPlugin-App ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-164">The project files themselves do not have any special information for the project references, and (after adding the plugin paths to the `pluginPaths` array) the plugins run perfectly, even if run in the same execution of the AppWithPlugin app.</span></span> <span data-ttu-id="fc9ee-165">Diese Projekte kopieren die Assemblys, auf die verwiesen wird, jedoch nicht in ihr Ausgabeverzeichnis, weshalb die Assemblys auf dem Computer der Benutzers vorhanden sein müssen, damit die Plug-Ins funktionieren.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-165">However, these projects do not copy the referenced assemblies to their output directory, so the assemblies need to be present on the user's machine for the plugins to work.</span></span> <span data-ttu-id="fc9ee-166">Es gibt zwei Möglichkeiten, dieses Problem zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-166">There are two ways to work around this problem.</span></span> <span data-ttu-id="fc9ee-167">Die erste Option ist die Verwendung des Befehls `dotnet publish`, um die Klassenbibliothek zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-167">The first option is to use the `dotnet publish` command to publish the class library.</span></span> <span data-ttu-id="fc9ee-168">Wenn Sie die Ausgabe von `dotnet build` für Ihr Plug-In verwenden möchten, können Sie alternativ die Eigenschaft `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` zwischen den `<PropertyGroup>`-Tags in der Projektdatei des Plug-Ins einfügen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-168">Alternatively, if you want to be able to use the output of `dotnet build` for your plugin, you can add the `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` property between the `<PropertyGroup>` tags in the plugin's project file.</span></span> <span data-ttu-id="fc9ee-169">Ein Beispiel hierfür ist das Plug-In-Projekt `XcopyablePlugin`.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-169">See the `XcopyablePlugin` plugin project for an example.</span></span>

## <a name="other-plugin-examples-in-the-sample"></a><span data-ttu-id="fc9ee-170">Andere-Plug-In-Beispiele in diesem Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc9ee-170">Other plugin examples in the sample</span></span>

<span data-ttu-id="fc9ee-171">Den vollständigen Quellcode für dieses Tutorial finden Sie im [Repository dotnet/samples](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span><span class="sxs-lookup"><span data-stu-id="fc9ee-171">The complete source code for this tutorial can be found in [the dotnet/samples repository](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span></span> <span data-ttu-id="fc9ee-172">Das vollständige Beispiel enthält einige weitere Beispiele für das `AssemblyDependencyResolver`-Verhalten.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-172">The completed sample includes a few other examples of `AssemblyDependencyResolver` behavior.</span></span> <span data-ttu-id="fc9ee-173">Zum Beispiel kann das `AssemblyDependencyResolver`-Objekt auch in NuGet-Paketen enthaltene native Bibliotheken und lokalisierte Satellitenassemblys auflösen.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-173">For example, the `AssemblyDependencyResolver` object can also resolve native libraries as well as localized satellite assemblies included in NuGet packages.</span></span> <span data-ttu-id="fc9ee-174">Das `UVPlugin` und `FrenchPlugin` im Beispielrepository veranschaulichen diese Szenarios.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-174">The `UVPlugin` and `FrenchPlugin` in the samples repository demonstrate these scenarios.</span></span>

## <a name="how-to-reference-a-plugin-interface-assembly-defined-in-a-nuget-package"></a><span data-ttu-id="fc9ee-175">Verweisen auf eine in einem NuGet-Paket definierte Assembly für Plug-In-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fc9ee-175">How to reference a plugin interface assembly defined in a NuGet package</span></span>

<span data-ttu-id="fc9ee-176">Angenommen, die App „A“ verfügt über eine Plug-In-Schnittstelle, die in einem NuGet-Paket mit dem Namen `A.PluginBase` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-176">Let's say that there is an app A that has a plugin interface defined in the NuGet package named `A.PluginBase`.</span></span> <span data-ttu-id="fc9ee-177">Wie verweisen Sie in Ihrem Plug-In-Projekt ordnungsgemäß auf das Paket?</span><span class="sxs-lookup"><span data-stu-id="fc9ee-177">How do you reference the package correctly in your plugin project?</span></span> <span data-ttu-id="fc9ee-178">Für Projektverweise verhindern die `<Private>false</Private>`-Metadaten im `ProjectReference`-Element in der Projektdatei, dass die DLL-Datei in die Ausgabe kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-178">For project references, using the `<Private>false</Private>` metadata on the `ProjectReference` element in the project file prevented the dll from being copied to the output.</span></span>

<span data-ttu-id="fc9ee-179">Um ordnungsgemäß auf das `A.PluginBase`-Paket zu verweisen, sollten Sie das `<PackageReference>`-Element in der Projektdatei in folgendes ändern:</span><span class="sxs-lookup"><span data-stu-id="fc9ee-179">To correctly reference the `A.PluginBase` package, you want to change the `<PackageReference>` element in the project file to the following:</span></span>

```xml
<PackageReference Include="A.PluginBase" Version="1.0.0">
    <ExcludeAssets>runtime</ExcludeAssets>
</PackageReference>
```

<span data-ttu-id="fc9ee-180">Damit wird verhindert, dass die `A.PluginBase`-Assemblys in das Ausgabeverzeichnis Ihres Plug-Ins kopiert werden, und es wird sichergestellt, dass Ihr Plug-In die Version von `A.PluginBase` der App „A“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-180">This prevents the `A.PluginBase` assemblies from being copied to the output directory of your plugin and ensures that your plugin will use A's version of `A.PluginBase`.</span></span>

## <a name="plugin-target-framework-recommendations"></a><span data-ttu-id="fc9ee-181">Empfehlungen für das Plug-In-Zielframework</span><span class="sxs-lookup"><span data-stu-id="fc9ee-181">Plugin target framework recommendations</span></span>

<span data-ttu-id="fc9ee-182">Da beim Laden der Plug-In-Abhängigkeit die Datei *deps.json* verwendet wird, gibt es ein Problem im Zusammenhang mit dem Zielframework des Plug-Ins.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-182">Because plugin dependency loading uses the *deps.json* file, there is a gotcha related to the plugin's target framework.</span></span> <span data-ttu-id="fc9ee-183">Genauer gesagt müssen Ihre Plug-Ins für eine Runtime ausgelegt sein, z.B. .NET Core 3.0, anstatt für eine Version von .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-183">Specifically, your plugins should target a runtime, such as .NET Core 3.0, instead of a version of .NET Standard.</span></span> <span data-ttu-id="fc9ee-184">Die Datei `deps.json` wird anhand des Zielframeworks des Projekts generiert, und da viele Pakete, die mit .NET Standard kompatibel sind, Verweisassemblys für die Erstellung für .NET Standard und Implementierungsassemblys für spezifische Runtimes enthalten, werden Implementierungsassemblys möglicherweise nicht ordnungsgemäß von `deps.json` erkannt, oder die .NET Standard-Version kann anstelle der erwarteten .NET Core-Version abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fc9ee-184">The `deps.json` file is generated based on which framework the project targets, and since many .NET Standard-compatible packages ship reference assemblies for building against .NET Standard and implementation assemblies for specific runtimes, the `deps.json` may not correctly see implementation assemblies, or it may grab the .NET Standard version of an assembly instead of the .NET Core version you expect.</span></span>
