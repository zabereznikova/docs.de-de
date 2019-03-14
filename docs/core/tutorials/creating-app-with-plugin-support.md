---
title: Erstellen einer .NET Core-Anwendung mit Plug-Ins
description: Erfahren Sie, wie Sie eine .NET Core-Anwendung erstellen, die Plug-Ins unterstützt.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/28/2019
ms.openlocfilehash: 85ea06d56ed1c3312a010c5e575dd193c00b93e9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363903"
---
# <a name="create-a-net-core-application-with-plugins"></a>Erstellen einer .NET Core-Anwendung mit Plug-Ins

In diesem Tutorial lernen Sie:

- Strukturieren eines Projekts zur Unterstützung von Plug-Ins
- Erstellen einer benutzerdefinierten <xref:System.Runtime.Loader.AssemblyLoadContext>-Klasse zum Laden jedes Plug-Ins
- Verwenden des Typs `System.Runtime.Loader.AssemblyDependencyResolver` zum Ermöglichen von Abhängigkeiten für Plug-Ins
- Schreiben von Plug-Ins, die mühelos durch Kopieren der Buildartefakte bereitgestellt werden können

## <a name="prerequisites"></a>Erforderliche Komponenten

- Installieren Sie das [.NET Core 3.0 Preview 2 SDK](https://www.microsoft.com/net/core) oder eine neuere Version.

## <a name="create-the-application"></a>Erstellen der Anwendung

Im ersten Schritt erstellen Sie die Anwendung:

1. Erstellen Sie einen neuen Ordner, und führen Sie `dotnet new console -o AppWithPlugin` in diesem Ordner aus. 
2. Erstellen Sie eine Visual Studio-Projektmappendatei, um das Erstellen des Projekts zu vereinfachen. Führen Sie `dotnet new sln` im gleichen Ordner aus. 
3. Führen Sie `dotnet sln add AppWithPlugin/AppWithPlugin.csproj` aus, um das App-Projekt zur Projektmappe hinzuzufügen.

Das Gerüst der Anwendung kann nun aufgefüllt werden. Ersetzen Sie den Code der Datei *AppWithPlugin/Program.cs* durch folgenden Code:

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

## <a name="create-the-plugin-interfaces"></a>Erstellen der Plug-In-Schnittstellen

Der nächste Schritt zum Erstellen einer App mit Plug-Ins besteht im Definieren der Schnittstelle, die die Plug-Ins implementieren müssen. Es wird empfohlen, dass Sie eine Klassenbibliothek erstellen, die alle Typen enthält, die Sie für die Kommunikation zwischen Ihrer App und den Plug-Ins verwenden möchten. Diese Trennung ermöglicht Ihnen das Veröffentlichen Ihrer Plug-In-Schnittstelle als Paket, ohne die vollständige Anwendung senden zu müssen.

Führen Sie `dotnet new classlib -o PluginBase` im Stammverzeichnis des Projekts aus. Führen Sie außerdem `dotnet sln add PluginBase/PluginBase.csproj` aus, um das Projekt zur Projektmappendatei hinzuzufügen. Löschen Sie die Datei `PluginBase/Class1.cs`, und erstellen Sie eine neue Datei im `PluginBase`-Ordner namens `ICommand.cs` mit der folgenden Schnittstellendefinition:

[!code-csharp[the-plugin-interface](~/samples/core/extensions/AppWithPlugin/PluginBase/ICommand.cs)]

Diese `ICommand`-Schnittstelle ist die, die von allen Plug-Ins implementiert wird.

Nachdem die `ICommand`-Schnittstelle definiert wurde, kann das Anwendungsprojekt ein wenig mehr aufgefüllt werden. Fügen Sie einen Verweis vom `AppWithPlugin`-Projekt auf das `PluginBase`-Projekt mit dem Befehl `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj` aus dem Stammverzeichnis hinzu.

Ersetzen Sie den Kommentar `// Load commands from plugins` durch den folgenden Codeausschnitt, um das Laden von Plug-Ins aus den angegebenen Dateipfaden zu ermöglichen:

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



Ersetzen Sie dann den Kommentar `// Output the loaded commands` durch folgenden Codeausschnitt:

```csharp
foreach (ICommand command in commands)
{
    Console.WriteLine($"{command.Name}\t - {command.Description}");
}
```

Ersetzen Sie den Kommentar `// Execute the command with the name passed as an argument` durch folgenden Codeausschnitt:

```csharp
ICommand command = commands.FirstOrDefault(c => c.Name == commandName);
if (command == null)
{
    Console.WriteLine("No such command is known.");
    return;
}

command.Execute();
```

Fügen Sie schließlich die statischen Methoden namens `LoadPlugin` und `CreateCommands` wie folgt zur `Program`-Klasse hinzu.

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

## <a name="load-plugins"></a>Laden der Plug-Ins

Die Anwendung kann jetzt ordnungsgemäß geladen werden und Befehle aus geladenen Plug-In-Assemblys instanziieren, jedoch kann sie die Plug-In-Assemblys noch nicht laden. Erstellen Sie eine Datei namens *PluginLoadContext.cs* mit den folgenden Inhalten im Ordner *AppWithPlugin*:

[!code-csharp[loading-plugins](~/samples/core/extensions/AppWithPlugin/AppWithPlugin/PluginLoadContext.cs)]

Der Typ `PluginLoadContext` wird von <xref:System.Runtime.Loader.AssemblyLoadContext> abgeleitet. Der Typ `AssemblyLoadContext` ist ein spezieller Typ in der Runtime, der Entwicklern ermöglicht, geladene Assemblys in verschiedenen Gruppen zu isolieren, um sicherzustellen, dass die Assemblyversionen nicht im Konflikt stehen. Darüber hinaus kann eine benutzerdefinierte `AssemblyLoadContext`-Klasse verschiedene Pfade zum Laden von Assemblys und zum Überschreiben des Standardverhaltens verwenden. `PluginLoadContext` verwendet eine Instanz vom Typ `AssemblyDependencyResolver`, die in .NET Core 3.0 eingeführt wurde, um Assemblynamen in Pfade aufzulösen. Das `AssemblyDependencyResolver`-Objekt wird mit dem Pfad zu einer .NET-Klassenbibliothek erstellt. Es löst Assemblys und native Bibliotheken basierend auf der *deps.json* in ihre relativen Pfade für die Klassenbibliothek auf, deren Pfad an den Konstruktor `AssemblyDependencyResolver` übergeben wurde. Das benutzerdefinierte Objekt `AssemblyLoadContext` ermöglicht eigene Abhängigkeiten für Plug-Ins, und `AssemblyDependencyResolver` erleichtert das richtige Laden der Abhängigkeiten.

Da das `AppWithPlugin`-Projekt nun über den Typ `PluginLoadContext` verfügt, aktualisieren Sie die `Program.LoadPlugin`-Methode mit folgendem Text:

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

Aufgrund der verschiedenen `PluginLoadContext`-Instanzen für jedes Plug-In können die Plug-Ins problemlos verschiedene oder sogar in Konflikt stehende Abhängigkeiten aufweisen.

## <a name="create-a-simple-plugin-with-no-dependencies"></a>Erstellen eines einfachen Plug-Ins ohne Abhängigkeiten

Führen Sie folgende Schritte im Stammverzeichnis aus:

1. Führen Sie `dotnet new classlib -o HelloPlugin` aus, um ein neues Klassenbibliotheksprojekt namens `HelloPlugin` zu erstellen.
2. Führen Sie `dotnet sln add HelloPlugin/HelloPlugin.csproj` aus, um das Projekt zur `AppWithPlugin`-Projektmappe hinzuzufügen. 
3. Ersetzen Sie die Datei *HelloPlugin/Class1.cs* durch eine Datei namens *HelloCommand.cs* mit folgendem Inhalt:

[!code-csharp[the-hello-plugin](~/samples/core/extensions/AppWithPlugin/HelloPlugin/HelloCommand.cs)]

Öffnen Sie jetzt die Datei *HelloPlugin.csproj*. Der Inhalt sollte Folgendem ähnlich sehen:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>

```

Fügen Sie die folgenden Elemente zwischen den `<Project>`-Tags ein:

```xml
<ItemGroup>
<ProjectReference Include="..\PluginBase\PluginBase.csproj">
    <Private>false</Private>
</ProjectReference>
</ItemGroup>
```

Das Element `<Private>false</Private>` ist sehr wichtig. Es weist MSBuild dazu an, die *PluginBase.dll* nicht in das Ausgabeverzeichnis für „HelloPlugin“ zu kopieren. Wenn die Assembly *PluginBase.dll* im Ausgabeverzeichnis enthalten ist, findet `PluginLoadContext` die Assembly dort und lädt sie, wenn die Assembly *HelloPlugin.dll* geladen wird. An diesem Punkt implementiert der Typ `HelloPlugin.HelloCommand` die `ICommand`-Schnittstelle aus der *PluginBase.dll* in das Ausgabeverzeichnis des `HelloPlugin`-Projekts und nicht die `ICommand`-Schnittstelle, die in den Standardladekontext geladen wurde. Da die Runtime die beiden Typen als verschiedene Typen aus verschiedenen Assemblys erkennt, findet die Methode `AppWithPlugin.Program.CreateCommands` die Befehle nicht. Daher sind die `<Private>false</Private>`-Metadaten für den Verweis auf die Assembly erforderlich, die die Plug-In-Schnittstellen enthält.

Nach Fertigstellung des `HelloPlugin`-Projekts sollten Sie das `AppWithPlugin`-Projekt aktualisieren, um in Erfahrung zu bringen, wo sich das `HelloPlugin`-Plug-In befindet. Fügen Sie `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` als ein Element des `pluginPaths`-Arrays nach dem Kommentar `// Paths to plugins to load` hinzu.

## <a name="create-a-plugin-with-library-dependencies"></a>Erstellen eines Plug-Ins mit Bibliotheksabhängigkeiten

Fast alle Plug-Ins sind komplexer als eine einfaches „Hallo Welt“-Programm, und viele Plug-Ins weisen Abhängigkeiten von anderen Bibliotheken auf. Im Beispiel veranschaulichen die Plug-In-Projekte `JsonPlugin` und `OldJson` zwei verschiedene Plug-Ins mit NuGet-Paketabhängigkeiten von `Newtonsoft.Json`. Die Projektdateien selbst enthalten keine speziellen Informationen für die Projektverweise, und die Plug-Ins werden (nachdem die Plug-In-Pfade zum `pluginPaths`-Array hinzugefügt wurden) problemlos ausgeführt, auch wenn sie in derselben Ausführung der AppWithPlugin-App ausgeführt werden. Diese Projekte kopieren die Assemblys, auf die verwiesen wird, jedoch nicht in ihr Ausgabeverzeichnis, weshalb die Assemblys auf dem Computer der Benutzers vorhanden sein müssen, damit die Plug-Ins funktionieren. Es gibt zwei Möglichkeiten, dieses Problem zu umgehen. Die erste Option ist die Verwendung des Befehls `dotnet publish`, um die Klassenbibliothek zu veröffentlichen. Wenn Sie die Ausgabe von `dotnet build` für Ihr Plug-In verwenden möchten, können Sie alternativ die Eigenschaft `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` zwischen den `<PropertyGroup>`-Tags in der Projektdatei des Plug-Ins einfügen. Ein Beispiel hierfür ist das Plug-In-Projekt `XcopyablePlugin`.

## <a name="other-plugin-examples-in-the-sample"></a>Andere-Plug-In-Beispiele in diesem Beispiel

Den vollständigen Quellcode für dieses Tutorial finden Sie im [Repository dotnet/samples](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin). Das vollständige Beispiel enthält einige weitere Beispiele für das `AssemblyDependencyResolver`-Verhalten. Zum Beispiel kann das `AssemblyDependencyResolver`-Objekt auch in NuGet-Paketen enthaltene native Bibliotheken und lokalisierte Satellitenassemblys auflösen. Das `UVPlugin` und `FrenchPlugin` im Beispielrepository veranschaulichen diese Szenarios.

## <a name="how-to-reference-a-plugin-interface-assembly-defined-in-a-nuget-package"></a>Verweisen auf eine in einem NuGet-Paket definierte Assembly für Plug-In-Schnittstellen

Angenommen, die App „A“ verfügt über eine Plug-In-Schnittstelle, die in einem NuGet-Paket mit dem Namen `A.PluginBase` definiert ist. Wie verweisen Sie in Ihrem Plug-In-Projekt ordnungsgemäß auf das Paket? Für Projektverweise verhindern die `<Private>false</Private>`-Metadaten im `ProjectReference`-Element in der Projektdatei, dass die DLL-Datei in die Ausgabe kopiert wird.

Um ordnungsgemäß auf das `A.PluginBase`-Paket zu verweisen, sollten Sie das `<PackageReference>`-Element in der Projektdatei in folgendes ändern:

```xml
<PackageReference Include="A.PluginBase" Version="1.0.0">
    <ExcludeAssets>runtime</ExcludeAssets>
</PackageReference>
```

Damit wird verhindert, dass die `A.PluginBase`-Assemblys in das Ausgabeverzeichnis Ihres Plug-Ins kopiert werden, und es wird sichergestellt, dass Ihr Plug-In die Version von `A.PluginBase` der App „A“ verwendet.

## <a name="plugin-target-framework-recommendations"></a>Empfehlungen für das Plug-In-Zielframework

Da beim Laden der Plug-In-Abhängigkeit die Datei *deps.json* verwendet wird, gibt es ein Problem im Zusammenhang mit dem Zielframework des Plug-Ins. Genauer gesagt müssen Ihre Plug-Ins für eine Runtime ausgelegt sein, z.B. .NET Core 3.0, anstatt für eine Version von .NET Standard. Die Datei `deps.json` wird anhand des Zielframeworks des Projekts generiert, und da viele Pakete, die mit .NET Standard kompatibel sind, Verweisassemblys für die Erstellung für .NET Standard und Implementierungsassemblys für spezifische Runtimes enthalten, werden Implementierungsassemblys möglicherweise nicht ordnungsgemäß von `deps.json` erkannt, oder die .NET Standard-Version kann anstelle der erwarteten .NET Core-Version abgerufen werden.
