---
title: Erstellen einer .NET Core-Anwendung mit Plug-Ins
description: Erfahren Sie, wie Sie eine .NET Core-Anwendung erstellen, die Plug-Ins unterstützt.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 10/16/2019
ms.openlocfilehash: d3b532ae72a80eef9603fc6f3ada8c11cae966dd
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98187898"
---
# <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="94110-103">Erstellen einer .NET Core-Anwendung mit Plug-Ins</span><span class="sxs-lookup"><span data-stu-id="94110-103">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="94110-104">In diesem Tutorial erfahren Sie, wie Sie einen benutzerdefinierten <xref:System.Runtime.Loader.AssemblyLoadContext> zum Laden von Plug-Ins erstellen.</span><span class="sxs-lookup"><span data-stu-id="94110-104">This tutorial shows you how to create a custom <xref:System.Runtime.Loader.AssemblyLoadContext> to load plugins.</span></span> <span data-ttu-id="94110-105">Ein <xref:System.Runtime.Loader.AssemblyDependencyResolver> wird verwendet, um die Abhängigkeiten des Plug-Ins aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="94110-105">An <xref:System.Runtime.Loader.AssemblyDependencyResolver> is used to resolve the dependencies of the plugin.</span></span> <span data-ttu-id="94110-106">Das Tutorial isoliert die Plug-In-Abhängigkeiten ordnungsgemäß von der Hostanwendung.</span><span class="sxs-lookup"><span data-stu-id="94110-106">The tutorial correctly isolates the plugin's dependencies from the hosting application.</span></span> <span data-ttu-id="94110-107">Sie lernen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="94110-107">You'll learn how to:</span></span>

- <span data-ttu-id="94110-108">Strukturieren eines Projekts zur Unterstützung von Plug-Ins</span><span class="sxs-lookup"><span data-stu-id="94110-108">Structure a project to support plugins.</span></span>
- <span data-ttu-id="94110-109">Erstellen einer benutzerdefinierten <xref:System.Runtime.Loader.AssemblyLoadContext>-Klasse zum Laden jedes Plug-Ins</span><span class="sxs-lookup"><span data-stu-id="94110-109">Create a custom <xref:System.Runtime.Loader.AssemblyLoadContext> to load each plugin.</span></span>
- <span data-ttu-id="94110-110">Verwenden des Typs <xref:System.Runtime.Loader.AssemblyDependencyResolver?displayProperty=fullName> zum Ermöglichen von Abhängigkeiten für Plug-Ins</span><span class="sxs-lookup"><span data-stu-id="94110-110">Use the <xref:System.Runtime.Loader.AssemblyDependencyResolver?displayProperty=fullName> type to allow plugins to have dependencies.</span></span>
- <span data-ttu-id="94110-111">Schreiben von Plug-Ins, die mühelos durch Kopieren der Buildartefakte bereitgestellt werden können</span><span class="sxs-lookup"><span data-stu-id="94110-111">Author plugins that can be easily deployed by just copying the build artifacts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94110-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="94110-112">Prerequisites</span></span>

- <span data-ttu-id="94110-113">Installieren Sie das [.NET 5 SDK](https://dotnet.microsoft.com/download) oder eine neuere Version.</span><span class="sxs-lookup"><span data-stu-id="94110-113">Install the [.NET 5 SDK](https://dotnet.microsoft.com/download) or a newer version.</span></span>

> [!NOTE]
> <span data-ttu-id="94110-114">Der Beispielcode ist auf .NET 5 ausgelegt. Alle verwendeten Features wurden jedoch in .NET Core 3.0 eingeführt und sind seitdem in allen höheren .NET-Releases verfügbar.</span><span class="sxs-lookup"><span data-stu-id="94110-114">The sample code targets .NET 5, but all the features it uses were introduced in .NET Core 3.0 and are available in all .NET releases since then.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="94110-115">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="94110-115">Create the application</span></span>

<span data-ttu-id="94110-116">Im ersten Schritt erstellen Sie die Anwendung:</span><span class="sxs-lookup"><span data-stu-id="94110-116">The first step is to create the application:</span></span>

1. <span data-ttu-id="94110-117">Erstellen Sie einen neuen Ordner, und führen Sie in diesem Ordner den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="94110-117">Create a new folder, and in that folder run the following command:</span></span>

    ```dotnetcli
    dotnet new console -o AppWithPlugin
    ```

2. <span data-ttu-id="94110-118">Erstellen Sie eine Visual Studio-Projektmappendatei im gleichen Ordner, um das Erstellen des Projekts zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="94110-118">To make building the project easier, create a Visual Studio solution file in the same folder.</span></span> <span data-ttu-id="94110-119">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="94110-119">Run the following command:</span></span>

    ```dotnetcli
    dotnet new sln
    ```

3. <span data-ttu-id="94110-120">Führen Sie den folgenden Befehl aus, um das Anwendungsprojekt zur Projektmappe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="94110-120">Run the following command to add the app project to the solution:</span></span>

    ```dotnetcli
    dotnet sln add AppWithPlugin/AppWithPlugin.csproj
    ```

<span data-ttu-id="94110-121">Das Gerüst der Anwendung kann nun aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="94110-121">Now we can fill in the skeleton of our application.</span></span> <span data-ttu-id="94110-122">Ersetzen Sie den Code der Datei *AppWithPlugin/Program.cs* durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="94110-122">Replace the code in the *AppWithPlugin/Program.cs* file with the following code:</span></span>

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

## <a name="create-the-plugin-interfaces"></a><span data-ttu-id="94110-123">Erstellen der Plug-In-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="94110-123">Create the plugin interfaces</span></span>

<span data-ttu-id="94110-124">Der nächste Schritt zum Erstellen einer App mit Plug-Ins besteht im Definieren der Schnittstelle, die die Plug-Ins implementieren müssen.</span><span class="sxs-lookup"><span data-stu-id="94110-124">The next step in building an app with plugins is defining the interface the plugins need to implement.</span></span> <span data-ttu-id="94110-125">Es wird empfohlen, dass Sie eine Klassenbibliothek erstellen, die alle Typen enthält, die Sie für die Kommunikation zwischen Ihrer App und den Plug-Ins verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="94110-125">We suggest that you make a class library that contains any types that you plan to use for communicating between your app and plugins.</span></span> <span data-ttu-id="94110-126">Diese Trennung ermöglicht Ihnen das Veröffentlichen Ihrer Plug-In-Schnittstelle als Paket, ohne die vollständige Anwendung senden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="94110-126">This division allows you to publish your plugin interface as a package without having to ship your full application.</span></span>

<span data-ttu-id="94110-127">Führen Sie `dotnet new classlib -o PluginBase` im Stammverzeichnis des Projekts aus.</span><span class="sxs-lookup"><span data-stu-id="94110-127">In the root folder of the project, run `dotnet new classlib -o PluginBase`.</span></span> <span data-ttu-id="94110-128">Führen Sie außerdem `dotnet sln add PluginBase/PluginBase.csproj` aus, um das Projekt zur Projektmappendatei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="94110-128">Also, run `dotnet sln add PluginBase/PluginBase.csproj` to add the project to the solution file.</span></span> <span data-ttu-id="94110-129">Löschen Sie die Datei `PluginBase/Class1.cs`, und erstellen Sie eine neue Datei im `PluginBase`-Ordner namens `ICommand.cs` mit der folgenden Schnittstellendefinition:</span><span class="sxs-lookup"><span data-stu-id="94110-129">Delete the `PluginBase/Class1.cs` file, and create a new file in the `PluginBase` folder named `ICommand.cs` with the following interface definition:</span></span>

[!code-csharp[the-plugin-interface](~/samples/snippets/core/tutorials/creating-app-with-plugin-support/csharp/PluginBase/ICommand.cs)]

<span data-ttu-id="94110-130">Diese `ICommand`-Schnittstelle ist die, die von allen Plug-Ins implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="94110-130">This `ICommand` interface is the interface that all of the plugins will implement.</span></span>

<span data-ttu-id="94110-131">Nachdem die `ICommand`-Schnittstelle definiert wurde, kann das Anwendungsprojekt ein wenig mehr aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="94110-131">Now that the `ICommand` interface is defined, the application project can be filled in a little more.</span></span> <span data-ttu-id="94110-132">Fügen Sie einen Verweis vom `AppWithPlugin`-Projekt auf das `PluginBase`-Projekt mit dem Befehl `dotnet add AppWithPlugin/AppWithPlugin.csproj reference PluginBase/PluginBase.csproj` aus dem Stammverzeichnis hinzu.</span><span class="sxs-lookup"><span data-stu-id="94110-132">Add a reference from the `AppWithPlugin` project to the `PluginBase` project with the `dotnet add AppWithPlugin/AppWithPlugin.csproj reference PluginBase/PluginBase.csproj`  command from the root folder.</span></span>

<span data-ttu-id="94110-133">Ersetzen Sie den Kommentar `// Load commands from plugins` durch den folgenden Codeausschnitt, um das Laden von Plug-Ins aus den angegebenen Dateipfaden zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="94110-133">Replace the `// Load commands from plugins` comment with the following code snippet to enable it to load plugins from given file paths:</span></span>

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

<span data-ttu-id="94110-134">Ersetzen Sie dann den Kommentar `// Output the loaded commands` durch folgenden Codeausschnitt:</span><span class="sxs-lookup"><span data-stu-id="94110-134">Then replace the `// Output the loaded commands` comment with the following code snippet:</span></span>

```csharp
foreach (ICommand command in commands)
{
    Console.WriteLine($"{command.Name}\t - {command.Description}");
}
```

<span data-ttu-id="94110-135">Ersetzen Sie den Kommentar `// Execute the command with the name passed as an argument` durch folgenden Codeausschnitt:</span><span class="sxs-lookup"><span data-stu-id="94110-135">Replace the `// Execute the command with the name passed as an argument` comment with the following snippet:</span></span>

```csharp
ICommand command = commands.FirstOrDefault(c => c.Name == commandName);
if (command == null)
{
    Console.WriteLine("No such command is known.");
    return;
}

command.Execute();
```

<span data-ttu-id="94110-136">Fügen Sie schließlich die statischen Methoden namens `LoadPlugin` und `CreateCommands` wie folgt zur `Program`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="94110-136">And finally, add static methods to the `Program` class named `LoadPlugin` and `CreateCommands`, as shown here:</span></span>

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

## <a name="load-plugins"></a><span data-ttu-id="94110-137">Laden der Plug-Ins</span><span class="sxs-lookup"><span data-stu-id="94110-137">Load plugins</span></span>

<span data-ttu-id="94110-138">Die Anwendung kann jetzt ordnungsgemäß geladen werden und Befehle aus geladenen Plug-In-Assemblys instanziieren, jedoch kann sie die Plug-In-Assemblys noch nicht laden.</span><span class="sxs-lookup"><span data-stu-id="94110-138">Now the application can correctly load and instantiate commands from loaded plugin assemblies, but it's still unable to load the plugin assemblies.</span></span> <span data-ttu-id="94110-139">Erstellen Sie eine Datei namens *PluginLoadContext.cs* mit den folgenden Inhalten im Ordner *AppWithPlugin*:</span><span class="sxs-lookup"><span data-stu-id="94110-139">Create a file named *PluginLoadContext.cs* in the *AppWithPlugin* folder with the following contents:</span></span>

[!code-csharp[loading-plugins](~/samples/snippets/core/tutorials/creating-app-with-plugin-support/csharp/AppWithPlugin/PluginLoadContext.cs)]

<span data-ttu-id="94110-140">Der Typ `PluginLoadContext` wird von <xref:System.Runtime.Loader.AssemblyLoadContext> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="94110-140">The `PluginLoadContext` type derives from <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="94110-141">Der Typ `AssemblyLoadContext` ist ein spezieller Typ in der Runtime, der Entwicklern ermöglicht, geladene Assemblys in verschiedenen Gruppen zu isolieren, um sicherzustellen, dass die Assemblyversionen nicht im Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="94110-141">The `AssemblyLoadContext` type is a special type in the runtime that allows developers to isolate loaded assemblies into different groups to ensure that assembly versions don't conflict.</span></span> <span data-ttu-id="94110-142">Darüber hinaus kann eine benutzerdefinierte `AssemblyLoadContext`-Klasse verschiedene Pfade zum Laden von Assemblys und zum Überschreiben des Standardverhaltens verwenden.</span><span class="sxs-lookup"><span data-stu-id="94110-142">Additionally, a custom `AssemblyLoadContext` can choose different paths to load assemblies from and override the default behavior.</span></span> <span data-ttu-id="94110-143">`PluginLoadContext` verwendet eine Instanz vom Typ `AssemblyDependencyResolver`, die in .NET Core 3.0 eingeführt wurde, um Assemblynamen in Pfade aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="94110-143">The `PluginLoadContext` uses an instance of the `AssemblyDependencyResolver` type introduced in .NET Core 3.0 to resolve assembly names to paths.</span></span> <span data-ttu-id="94110-144">Das `AssemblyDependencyResolver`-Objekt wird mit dem Pfad zu einer .NET-Klassenbibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="94110-144">The `AssemblyDependencyResolver` object is constructed with the path to a .NET class library.</span></span> <span data-ttu-id="94110-145">Es löst Assemblys und native Bibliotheken basierend auf der Datei *.deps.json* in ihre relativen Pfade für die Klassenbibliothek auf, deren Pfad an den Konstruktor `AssemblyDependencyResolver` übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="94110-145">It resolves assemblies and native libraries to their relative paths based on the *.deps.json* file for the class library whose path was passed to the `AssemblyDependencyResolver` constructor.</span></span> <span data-ttu-id="94110-146">Das benutzerdefinierte Objekt `AssemblyLoadContext` ermöglicht eigene Abhängigkeiten für Plug-Ins, und `AssemblyDependencyResolver` erleichtert das richtige Laden der Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="94110-146">The custom `AssemblyLoadContext` enables plugins to have their own dependencies, and the `AssemblyDependencyResolver` makes it easy to correctly load the dependencies.</span></span>

<span data-ttu-id="94110-147">Da das `AppWithPlugin`-Projekt nun über den Typ `PluginLoadContext` verfügt, aktualisieren Sie die `Program.LoadPlugin`-Methode mit folgendem Text:</span><span class="sxs-lookup"><span data-stu-id="94110-147">Now that the `AppWithPlugin` project has the `PluginLoadContext` type, update the `Program.LoadPlugin` method with the following body:</span></span>

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

<span data-ttu-id="94110-148">Aufgrund der verschiedenen `PluginLoadContext`-Instanzen für jedes Plug-In können die Plug-Ins problemlos verschiedene oder sogar in Konflikt stehende Abhängigkeiten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="94110-148">By using a different `PluginLoadContext` instance for each plugin, the plugins can have different or even conflicting dependencies without issue.</span></span>

## <a name="simple-plugin-with-no-dependencies"></a><span data-ttu-id="94110-149">Einfaches Plug-In ohne Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="94110-149">Simple plugin with no dependencies</span></span>

<span data-ttu-id="94110-150">Führen Sie folgende Schritte im Stammverzeichnis aus:</span><span class="sxs-lookup"><span data-stu-id="94110-150">Back in the root folder, do the following:</span></span>

1. <span data-ttu-id="94110-151">Führen Sie den folgenden Befehl aus, um ein neues Klassenbibliotheksprojekt namens `HelloPlugin` zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="94110-151">Run the following command to create a new class library project named `HelloPlugin`:</span></span>

    ```dotnetcli
    dotnet new classlib -o HelloPlugin
    ```

2. <span data-ttu-id="94110-152">Führen Sie den folgenden Befehl aus, um das Projekt zur Projektmappe `AppWithPlugin` hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="94110-152">Run the following command to add the project to the `AppWithPlugin` solution:</span></span>

    ```dotnetcli
    dotnet sln add HelloPlugin/HelloPlugin.csproj
    ```

3. <span data-ttu-id="94110-153">Ersetzen Sie die Datei *HelloPlugin/Class1.cs* durch eine Datei namens *HelloCommand.cs* mit folgendem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="94110-153">Replace the *HelloPlugin/Class1.cs* file with a file named *HelloCommand.cs* with the following contents:</span></span>

[!code-csharp[the-hello-plugin](~/samples/snippets/core/tutorials/creating-app-with-plugin-support/csharp/HelloPlugin/HelloCommand.cs)]

<span data-ttu-id="94110-154">Öffnen Sie jetzt die Datei *HelloPlugin.csproj*.</span><span class="sxs-lookup"><span data-stu-id="94110-154">Now, open the *HelloPlugin.csproj* file.</span></span> <span data-ttu-id="94110-155">Der Inhalt sollte Folgendem ähnlich sehen:</span><span class="sxs-lookup"><span data-stu-id="94110-155">It should look similar to the following:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>net5</TargetFramework>
  </PropertyGroup>

</Project>

```

<span data-ttu-id="94110-156">Fügen Sie die folgenden Elemente zwischen den `<Project>`-Tags ein:</span><span class="sxs-lookup"><span data-stu-id="94110-156">In between the `<Project>` tags, add the following elements:</span></span>

```xml
<ItemGroup>
    <ProjectReference Include="..\PluginBase\PluginBase.csproj">
        <Private>false</Private>
        <ExcludeAssets>runtime</ExcludeAssets>
    </ProjectReference>
</ItemGroup>
```

<span data-ttu-id="94110-157">Das Element `<Private>false</Private>` ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="94110-157">The `<Private>false</Private>` element is important.</span></span> <span data-ttu-id="94110-158">Es weist MSBuild dazu an, die *PluginBase.dll* nicht in das Ausgabeverzeichnis für „HelloPlugin“ zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="94110-158">This tells MSBuild to not copy *PluginBase.dll* to the output directory for HelloPlugin.</span></span> <span data-ttu-id="94110-159">Wenn die Assembly *PluginBase.dll* im Ausgabeverzeichnis enthalten ist, findet `PluginLoadContext` die Assembly dort und lädt sie, wenn die Assembly *HelloPlugin.dll* geladen wird.</span><span class="sxs-lookup"><span data-stu-id="94110-159">If the *PluginBase.dll* assembly is present in the output directory, `PluginLoadContext` will find the assembly there and load it when it loads the *HelloPlugin.dll* assembly.</span></span> <span data-ttu-id="94110-160">An diesem Punkt implementiert der Typ `HelloPlugin.HelloCommand` die `ICommand`-Schnittstelle aus der *PluginBase.dll* in das Ausgabeverzeichnis des `HelloPlugin`-Projekts und nicht die `ICommand`-Schnittstelle, die in den Standardladekontext geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="94110-160">At this point, the `HelloPlugin.HelloCommand` type will implement the `ICommand` interface from the *PluginBase.dll* in the output directory of the `HelloPlugin` project, not the `ICommand` interface that is loaded into the default load context.</span></span> <span data-ttu-id="94110-161">Da die Runtime die beiden Typen als verschiedene Typen aus verschiedenen Assemblys erkennt, findet die `AppWithPlugin.Program.CreateCommands`-Methode die Befehle nicht.</span><span class="sxs-lookup"><span data-stu-id="94110-161">Since the runtime sees these two types as different types from different assemblies, the `AppWithPlugin.Program.CreateCommands` method won't find the commands.</span></span> <span data-ttu-id="94110-162">Daher sind die `<Private>false</Private>`-Metadaten für den Verweis auf die Assembly erforderlich, die die Plug-In-Schnittstellen enthält.</span><span class="sxs-lookup"><span data-stu-id="94110-162">As a result, the `<Private>false</Private>` metadata is required for the reference to the assembly containing the plugin interfaces.</span></span>

<span data-ttu-id="94110-163">Ebenso ist das Element `<ExcludeAssets>runtime</ExcludeAssets>` wichtig, wenn `PluginBase` auf andere Paket verweist.</span><span class="sxs-lookup"><span data-stu-id="94110-163">Similarly, the `<ExcludeAssets>runtime</ExcludeAssets>` element is also important if the `PluginBase` references other packages.</span></span> <span data-ttu-id="94110-164">Diese Einstellung hat denselben Effekt wie `<Private>false</Private>`, funktioniert aber in Paketverweisen, die im `PluginBase`-Projekt oder einer der zugehörigen Abhängigkeiten enthalten sein können.</span><span class="sxs-lookup"><span data-stu-id="94110-164">This setting has the same effect as `<Private>false</Private>` but works on package references that the `PluginBase` project or one of its dependencies may include.</span></span>

<span data-ttu-id="94110-165">Nach Fertigstellung des `HelloPlugin`-Projekts sollten Sie das `AppWithPlugin`-Projekt aktualisieren, um in Erfahrung zu bringen, wo sich das `HelloPlugin` befindet.</span><span class="sxs-lookup"><span data-stu-id="94110-165">Now that the `HelloPlugin` project is complete, you should update the `AppWithPlugin` project to know where the `HelloPlugin` plugin can be found.</span></span> <span data-ttu-id="94110-166">Fügen Sie nach dem Kommentar `// Paths to plugins to load` `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` (dieser Pfad kann je nach .NET Core-Version anders sein) als Element das Array `pluginPaths` hinzu.</span><span class="sxs-lookup"><span data-stu-id="94110-166">After the `// Paths to plugins to load` comment, add `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` (this path could be different based on the .NET Core version you use) as an element of the `pluginPaths` array.</span></span>

## <a name="plugin-with-library-dependencies"></a><span data-ttu-id="94110-167">Plug-In mit Bibliotheksabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="94110-167">Plugin with library dependencies</span></span>

<span data-ttu-id="94110-168">Fast alle Plug-Ins sind komplexer als eine einfaches „Hallo Welt“-Programm, und viele Plug-Ins weisen Abhängigkeiten von anderen Bibliotheken auf.</span><span class="sxs-lookup"><span data-stu-id="94110-168">Almost all plugins are more complex than a simple "Hello World", and many plugins have dependencies on other libraries.</span></span> <span data-ttu-id="94110-169">Im Beispiel veranschaulichen die Plug-In-Projekte `JsonPlugin` und `OldJson` zwei verschiedene Plug-Ins mit NuGet-Paketabhängigkeiten von `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="94110-169">The `JsonPlugin` and `OldJson` plugin projects in the sample show two examples of plugins with NuGet package dependencies on `Newtonsoft.Json`.</span></span> <span data-ttu-id="94110-170">Die Projektdateien selbst enthalten keine speziellen Informationen für die Projektverweise, und die Plug-Ins werden (nachdem die Plug-In-Pfade dem `pluginPaths`-Array hinzugefügt wurden) problemlos ausgeführt, auch wenn sie in derselben Ausführung der AppWithPlugin-App ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="94110-170">The project files themselves don't have any special information for the project references, and (after adding the plugin paths to the `pluginPaths` array) the plugins run perfectly, even if run in the same execution of the AppWithPlugin app.</span></span> <span data-ttu-id="94110-171">Diese Projekte kopieren die Assemblys, auf die verwiesen wird, jedoch nicht in ihr Ausgabeverzeichnis. Daher müssen die Assemblys auf dem Computer der Benutzers vorhanden sein, damit die Plug-Ins funktionieren.</span><span class="sxs-lookup"><span data-stu-id="94110-171">However, these projects don't copy the referenced assemblies to their output directory, so the assemblies need to be present on the user's machine for the plugins to work.</span></span> <span data-ttu-id="94110-172">Es gibt zwei Möglichkeiten, dieses Problem zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="94110-172">There are two ways to work around this problem.</span></span> <span data-ttu-id="94110-173">Die erste Option ist die Verwendung des Befehls `dotnet publish`, um die Klassenbibliothek zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="94110-173">The first option is to use the `dotnet publish` command to publish the class library.</span></span> <span data-ttu-id="94110-174">Wenn Sie die Ausgabe von `dotnet build` für Ihr Plug-In verwenden möchten, können Sie alternativ die Eigenschaft `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` zwischen den `<PropertyGroup>`-Tags in der Projektdatei des Plug-Ins einfügen.</span><span class="sxs-lookup"><span data-stu-id="94110-174">Alternatively, if you want to be able to use the output of `dotnet build` for your plugin, you can add the `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` property between the `<PropertyGroup>` tags in the plugin's project file.</span></span> <span data-ttu-id="94110-175">Ein Beispiel hierfür ist das Plug-In-Projekt `XcopyablePlugin`.</span><span class="sxs-lookup"><span data-stu-id="94110-175">See the `XcopyablePlugin` plugin project for an example.</span></span>

## <a name="other-examples-in-the-sample"></a><span data-ttu-id="94110-176">Andere Beispiele in diesem Beispiel</span><span class="sxs-lookup"><span data-stu-id="94110-176">Other examples in the sample</span></span>

<span data-ttu-id="94110-177">Den vollständigen Quellcode für dieses Tutorial finden Sie im [Repository dotnet/samples](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span><span class="sxs-lookup"><span data-stu-id="94110-177">The complete source code for this tutorial can be found in [the dotnet/samples repository](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span></span> <span data-ttu-id="94110-178">Das vollständige Beispiel enthält einige weitere Beispiele für das `AssemblyDependencyResolver`-Verhalten.</span><span class="sxs-lookup"><span data-stu-id="94110-178">The completed sample includes a few other examples of `AssemblyDependencyResolver` behavior.</span></span> <span data-ttu-id="94110-179">Zum Beispiel kann das `AssemblyDependencyResolver`-Objekt auch in NuGet-Paketen enthaltene native Bibliotheken und lokalisierte Satellitenassemblys auflösen.</span><span class="sxs-lookup"><span data-stu-id="94110-179">For example, the `AssemblyDependencyResolver` object can also resolve native libraries as well as localized satellite assemblies included in NuGet packages.</span></span> <span data-ttu-id="94110-180">Das `UVPlugin` und `FrenchPlugin` im Beispielrepository veranschaulichen diese Szenarios.</span><span class="sxs-lookup"><span data-stu-id="94110-180">The `UVPlugin` and `FrenchPlugin` in the samples repository demonstrate these scenarios.</span></span>

## <a name="reference-a-plugin-interface-from-a-nuget-package"></a><span data-ttu-id="94110-181">Verweisen auf eine Plug-In-Schnittstelle aus einem NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="94110-181">Reference a plugin interface from a NuGet package</span></span>

<span data-ttu-id="94110-182">Angenommen, die App „A“ verfügt über eine Plug-In-Schnittstelle, die in einem NuGet-Paket mit dem Namen `A.PluginBase` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="94110-182">Let's say that there is an app A that has a plugin interface defined in the NuGet package named `A.PluginBase`.</span></span> <span data-ttu-id="94110-183">Wie verweisen Sie in Ihrem Plug-In-Projekt ordnungsgemäß auf das Paket?</span><span class="sxs-lookup"><span data-stu-id="94110-183">How do you reference the package correctly in your plugin project?</span></span> <span data-ttu-id="94110-184">Für Projektverweise verhindern die `<Private>false</Private>`-Metadaten im `ProjectReference`-Element in der Projektdatei, dass die DLL-Datei in die Ausgabe kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="94110-184">For project references, using the `<Private>false</Private>` metadata on the `ProjectReference` element in the project file prevented the dll from being copied to the output.</span></span>

<span data-ttu-id="94110-185">Um ordnungsgemäß auf das `A.PluginBase`-Paket zu verweisen, sollten Sie das `<PackageReference>`-Element in der Projektdatei in folgendes ändern:</span><span class="sxs-lookup"><span data-stu-id="94110-185">To correctly reference the `A.PluginBase` package, you want to change the `<PackageReference>` element in the project file to the following:</span></span>

```xml
<PackageReference Include="A.PluginBase" Version="1.0.0">
    <ExcludeAssets>runtime</ExcludeAssets>
</PackageReference>
```

<span data-ttu-id="94110-186">Damit wird verhindert, dass die `A.PluginBase`-Assemblys in das Ausgabeverzeichnis Ihres Plug-Ins kopiert werden, und es wird sichergestellt, dass Ihr Plug-In die Version von `A.PluginBase` der App „A“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="94110-186">This prevents the `A.PluginBase` assemblies from being copied to the output directory of your plugin and ensures that your plugin will use A's version of `A.PluginBase`.</span></span>

## <a name="plugin-target-framework-recommendations"></a><span data-ttu-id="94110-187">Empfehlungen für das Plug-In-Zielframework</span><span class="sxs-lookup"><span data-stu-id="94110-187">Plugin target framework recommendations</span></span>

<span data-ttu-id="94110-188">Da beim Laden der Plug-In-Abhängigkeit die Datei *.deps.json* verwendet wird, gibt es ein Problem im Zusammenhang mit dem Zielframework des Plug-Ins.</span><span class="sxs-lookup"><span data-stu-id="94110-188">Because plugin dependency loading uses the *.deps.json* file, there is a gotcha related to the plugin's target framework.</span></span> <span data-ttu-id="94110-189">Genauer gesagt müssen Ihre Plug-Ins für eine Runtime wie .NET 5 ausgelegt sein, nicht auf eine Version von .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="94110-189">Specifically, your plugins should target a runtime, such as .NET 5, instead of a version of .NET Standard.</span></span> <span data-ttu-id="94110-190">Die Datei *.deps.json* wird anhand des Zielframeworks des Projekts generiert, und da viele Pakete, die mit .NET Standard kompatibel sind, Verweisassemblys für die Erstellung für .NET Standard und Implementierungsassemblys für spezifische Runtimes enthalten, werden Implementierungsassemblys möglicherweise nicht ordnungsgemäß von *.deps.json* erkannt, oder die .NET Standard-Version kann anstelle der erwarteten .NET Core-Version abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="94110-190">The *.deps.json* file is generated based on which framework the project targets, and since many .NET Standard-compatible packages ship reference assemblies for building against .NET Standard and implementation assemblies for specific runtimes, the *.deps.json* may not correctly see implementation assemblies, or it may grab the .NET Standard version of an assembly instead of the .NET Core version you expect.</span></span>

## <a name="plugin-framework-references"></a><span data-ttu-id="94110-191">Plug-In-Frameworkverweise</span><span class="sxs-lookup"><span data-stu-id="94110-191">Plugin framework references</span></span>

<span data-ttu-id="94110-192">Plug-Ins können derzeit keine neuen Frameworks in den Prozess einbringen.</span><span class="sxs-lookup"><span data-stu-id="94110-192">Currently, plugins can't introduce new frameworks into the process.</span></span> <span data-ttu-id="94110-193">Beispielsweise können Sie ein Plug-in, das das Framework `Microsoft.AspNetCore.App` verwendet, nicht in eine Anwendung laden, die nur das Stammframework `Microsoft.NETCore.App` verwendet.</span><span class="sxs-lookup"><span data-stu-id="94110-193">For example, you can't load a plugin that uses the `Microsoft.AspNetCore.App` framework into an application that only uses the root `Microsoft.NETCore.App` framework.</span></span> <span data-ttu-id="94110-194">Die Hostanwendung muss Verweise auf alle von Plug-Ins benötigten Frameworks deklarieren.</span><span class="sxs-lookup"><span data-stu-id="94110-194">The host application must declare references to all frameworks needed by plugins.</span></span>
