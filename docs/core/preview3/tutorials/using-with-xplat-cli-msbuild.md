---
title: Erste Schritte mit .NET Core unter Windows/Linux/macOS unter Verwendung der Befehlszeile (SDK Preview 3)
description: Erste Schritte mit .NET Core unter Windows, Linux oder Mac OS unter Verwendung der .NET Core-Befehlszeilenschnittstelle (CLI)
keywords: .NET, .NET Core
author: cartermp
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: be988f09-7349-43b0-97fb-3a703d4587ce
translationtype: Human Translation
ms.sourcegitcommit: ab71aab99505f211fe4adc86957eda4707761f1c
ms.openlocfilehash: 01b17021e79bcdb2dc69f97b709f4aa63dbab9aa

---

# <a name="getting-started-with-net-core-on-windowslinuxmacos-using-the-command-line-sdk-preview-3"></a>Erste Schritte mit .NET Core unter Windows/Linux/macOS unter Verwendung der Befehlszeile (SDK Preview 3)

In diesem Leitfaden erfahren Sie, wie Sie mit den Tools der .NET Core-Befehlszeilenschnittstelle plattformübergreifende Konsolen-Apps erstellen können.  Dabei wird mit einer ganz einfachen Konsolen-App begonnen, die immer mehr erweitert wird und sich über mehrere Projekte einschließlich Tests erstreckt. Die einzelnen Funktionen werden schrittweise hinzugefügt, wobei die einzelnen Schritte aufeinander aufbauen.

Wenn Sie mit dem Toolset der .NET Core-Befehlszeilenschnittstelle nicht vertraut sind, finden Sie entsprechende Informationen in der [Übersicht über das .NET Core SDK](../tools/dotnet.md).

## <a name="prerequisites"></a>Erforderliche Komponenten

Stellen Sie vor Beginn sicher, dass die [Tools der .NET Core-CLI der Preview 3-Version](https://github.com/dotnet/core/blob/master/release-notes/preview3-download.md) installiert sind.  Außerdem benötigen Sie einen Text-Editor.

## <a name="hello-console-app"></a>Hallo Konsolenanwendung!

Erstellen Sie zunächst einen Ordner mit einem beliebigen Namen.  Wir haben den Namen „Hello“ für den Beispielcode verwendet, der [hier](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloMsBuild) zu finden ist.

Öffnen Sie die Eingabeaufforderung, und geben Sie folgenden Befehl ein:

```
$ dotnet new
$ dotnet restore
$ dotnet run
```

Hier eine kurze Beschreibung der Schritte:

1. `$ dotnet new`

   Mit [`dotnet new`](../tools/dotnet-new.md) wird eine aktuelle Projektdatei `Hello.csproj` mit den Abhängigkeiten erstellt, die zum Erstellen einer Konsolen-App benötigt werden.  Zudem wird `Program.cs` erstellt. Hierbei handelt es sich um eine einfache Datei, die den Einstiegspunkt für die Anwendung enthält.
   
   `Hello.csproj`:
   ```xml
    <Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
        <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
        
        <PropertyGroup>
            <OutputType>Exe</OutputType>
            <TargetFramework>netcoreapp1.0</TargetFramework>
        </PropertyGroup>

        <ItemGroup>
            <Compile Include="**\*.cs" />
            <EmbeddedResource Include="**\*.resx" />
        </ItemGroup>

        <ItemGroup>
            <PackageReference Include="Microsoft.NETCore.App">
                <Version>1.0.1</Version>
            </PackageReference>
            <PackageReference Include="Microsoft.NET.Sdk">
                <Version>1.0.0-alpha-20161104-2</Version>
                <PrivateAssets>All</PrivateAssets>
            </PackageReference>
        </ItemGroup>
        
        <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
    </Project>
   ```

   Die Projektdatei gibt alle Elemente an, die zum Wiederherstellen von Abhängigkeiten und erstellen des Programms erforderlich sind.

   * Das Tag `Import` fügt einige Eigenschaften hinzu, die alle .NET Core-Projekte gemeinsam haben.
   * Das Tag `OutputType` gibt an, dass wir eine ausführbare Datei, also eine Konsolenanwendung, erstellen.
   * Das Tag `TargetFramework` gibt an, welche .NET Runtime wir als Ziel haben. In einem komplexen Szenario können Sie mehrere Zielframeworks angeben und die Erstellung für diese in einem einzigen Vorgang vornehmen. In diesem Tutorial beschränken wir uns auf Builds für .NET Core 1.0.
   * Das Tag `Compile` weist den Compiler an, alle Dateien im aktuellen Verzeichnis und allen seinen Unterverzeichnisse mit der Erweiterung `.cs` zu erstellen, also alle C#-Dateien im Projekt. In komplexen Szenarien ist es möglich, Dateien auszuschließen. Doch in diesem Tutorial und in den meisten einfachen Szenarien kann diese Zeile unverändert bleiben.
   * Das Tag `EmbeddedResource` weist das Buildsystem an, Lokalisierungsdateien mit der Erweiterung `.resx` in die kompilierte ausführbare Datei einzubetten. Dieses Feature verwenden wird in diesem Tutorial nicht.
   * Die `PackageReference`-Tags geben an, welche Abhängigkeitspakete beim Erstellen der Anwendung wiederhergestellt werden müssen. Jeder Paketverweis gibt den Namen des Pakets unter dem `Include`-Attribut und eine Versionsnummer an. In den meisten komplexen Szenarien fügen Sie weitere Paketverweise hinzu. Es ist auch möglich, auf andere Projekte auf dem Datenträger zu verweisen.

   `Program.cs`:
   ```csharp
   using System;

   namespace ConsoleApplication
   {
       public class Program
       {
           public static void Main(string[] args)
           {
               Console.WriteLine("Hello World!");
           }
       }
   }
   ```

   Das Programm startet mithilfe von `using System`, was bedeutet, dass alles im Namespace `System` in den Geltungsbereich für diese Datei gebracht wird. Der Namespace `System` enthält grundlegende Konstrukte, wie z.B. `string`, oder numerische Typen.

   Wir definieren dann einen Namespace mit dem Namen „ConsoleApplication“. Sie können diesen Namen nach Wunsch ändern. Eine Klasse namens „Program“ wird in diesem Namespace definiert, die über eine `Main`-Methode verfügt, welche ein Array von Zeichenfolgen als Argument verwendet. Dieses Array enthält die Liste mit Argumenten, die übergeben werden, wenn das kompilierte Programm aufgerufen wird. Dieses Array wird allerdings nicht verwendet. Die Anwendung gibt lediglich „Hello World!“ auf der Konsole aus. Wir können die Dinge ein wenig interessanter gestalten, indem wir `Console.WriteLine` in den folgenden Code ändern.

   ```csharp
   if (args.Length > 0)
   {
       Console.WriteLine($"Hello {args[0]}!");
   }
   else
   {
       Console.WriteLine("Hello World!");
   }
   ```

2. `$ dotnet restore`

   [`dotnet restore`](../tools/dotnet-restore.md) führt einen Aufruf in [NuGet](http://nuget.org) (dem Paket-Manager von .NET) aus, um die Struktur der Abhängigkeiten wiederherzustellen. NuGet analysiert die Datei `Hello.csproj`, lädt die in der Datei angegebenen Abhängigkeiten herunter (oder ruft diese aus einem Cache auf Ihrem Computer ab) und schreibt die Datei `obj/project.assets.json`.  Die Datei `project.assets.json` ist zum Kompilieren und Ausführen erforderlich.
   
   Bei der Datei `project.assets.json` handelt es sich um eine persistente und umfassende Gruppe des Diagramms von NuGet-Abhängigkeiten und anderen Informationen, die eine Anwendung beschreiben.  Diese Datei wird von anderen Tools wie `dotnet build` und `dotnet run` gelesen, die dadurch in die Lage versetzt werden, den Quellcode mit einer vorschriftsmäßigen Menge von NuGet-Abhängigkeiten und Bindungsauflösungen zu verarbeiten.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) ruft `dotnet build` auf, um sicherzustellen, dass die Buildziele erstellt wurden, und ruft anschließend `dotnet <assembly.dll>` auf, um die Zielanwendung auszuführen.
   
    ```
    $ dotnet run
    Hello World!
    ```

    Sie können alternativ [`dotnet build`](../tools/dotnet-build.md) ausführen, um den Code zu kompilieren, ohne die Konsolenanwendungen des Builds auszuführen. Dies führt zur kompilierten Anwendung `bin/Debug/netcoreapp1.0/Hello.dll`, die mit `dotnet bin\Debug\netcoreapp1.0\Hello.dll` unter Windows und mit `dotnet bin/Debug/netcoreapp1.0/Hello.dll` auf anderen Systemen ausgeführt werden kann. Sie können in der Befehlszeile einen zusätzlichen Parameter angeben (vorausgesetzt, Sie arbeiten unter Windows):

    ```
    $ dotnet bin\Debug\netcoreapp1.0\Hello.dll .NET
    Hello .NET!
    ```

    In einem komplexen Szenario ist es möglich, die Anwendung als eigenständigen Satz plattformspezifischer Dateien zu erstellen, die auf einen Computer bereitgestellt und ausgeführt werden können, auf dem nicht notwendigerweise .NET Core installiert ist. Details finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).

### <a name="augmenting-the-program"></a>Erweitern des Programms

Verändern wir nun die Datei ein wenig.  Fibonacci-Zahlen machen Spaß, also probieren wir das aus:

`Program.cs`:

```csharp
using static System.Console;

namespace ConsoleApplication
{
    public class Program
    {
        public static int FibonacciNumber(int n)
        {
            int a = 0;
            int b = 1;
            int tmp;
            
            for (int i = 0; i < n; i++)
            {
                tmp = a;
                a = b;
                b += tmp;
            }
            
            return a;   
        }
        
        public static void Main(string[] args)
        {
            WriteLine("Hello World!");
            WriteLine("Fibonacci Numbers 1-15:");
            
            for (int i = 0; i < 15; i++)
            {
                WriteLine($"{i+1}: {FibonacciNumber(i)}");
            }
        }
    }
}
```

Führen wir das Programm aus (dabei gehen wir davon aus, dass Sie mit Windows arbeiten und das Projektverzeichnis in „Fibonacci“ umbenannt haben):

```
$ dotnet build
$ dotnet bin\Debug\netcoreapp1.0\win10-x64\Fibonacci.exe
1: 0
2: 1
3: 1
4: 2
5: 3
6: 5
7: 8
8: 13
9: 21
10: 34
11: 55
12: 89
13: 144
14: 233
15: 377
```

Und das ist schon alles!  Sie können `Program.cs` beliebig erweitern.

## <a name="adding-some-new-files"></a>Hinzufügen neuer Dateien

Einzelne Dateien können problemlos zu einfachen Einmalprogrammen hinzugefügt werden. Wenn Sie jedoch ein Programm mit mehreren Komponenten erstellen, werden Sie die Dinge wahrscheinlich in mehreren Dateien ausgliedern wollen.  Eine Möglichkeit, dies zu tun, ist die Verwendung mehrerer Dateien.

Erstellen Sie eine neue Datei, und geben Sie ihr einen eindeutigen Namespace:

```csharp
using System;

namespace NumberFun
{
    // code can go here
} 
```

Als Nächstes fügen Sie sie in die Datei `Program.cs` ein:

```csharp
using NumberFun;
```

Und schließlich können Sie sie erstellen:

`$ dotnet build`

Nun kommt der unterhaltsame Teil: Sorgen Sie dafür, dass die neue Datei etwas tut.

### <a name="example-a-fibonacci-sequence-generator"></a>Beispiel: Generator für Fibonacci-Folgen

Angenommen, Sie möchten das vorherige Fibonacci-Beispiel weiterentwickeln, indem Sie einige Fibonacci-Werte zwischenspeichern und einige rekursive Funktionen hinzufügen.  Der Code für ein [besseres Fibonacci-Beispiel](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/FibonacciBetterMsBuild) kann eine neue Datei `FibonacciGenerator.cs` mit dem folgenden Code verwenden.

```csharp
using System;
using System.Collections.Generic;

namespace NumberFun
{
    public class FibonacciGenerator
    {
        private Dictionary<int, int> _cache = new Dictionary<int, int>();
        
        private int Fib(int n) => n < 2 ? n : FibValue(n - 1) + FibValue(n - 2);
        
        private int FibValue(int n)
        {
            if (!_cache.ContainsKey(n))
            {
                _cache.Add(n, Fib(n));
            }
            
            return _cache[n];
        }
        
        public IEnumerable<int> Generate(int n)
        {
            for (int i = 0; i < n; i++)
            {
                yield return FibValue(i);
            }
        }
    }
}
```

Passen Sie nun die `Main()`-Methode in der Datei `Program.cs` wie folgt an.

```csharp
using System;
using NumberFun;

class Program
{
    static void Main(string[] args)
    {
        var generator = new FibonacciGenerator();
        foreach (var digit in generator.Generate(15))
        {
            Console.WriteLine(digit);
        }
    }
}
```

Führen Sie die Datei anschließend aus.

```
$ dotnet run
0
1
1
2
3
5
8
13
21
34
55
89
144
233
377
```

Und das ist schon alles!

## <a name="conclusion"></a>Schlussfolgerung
 
In dieser Anleitung wurde beschrieben, wie eine .NET Core-Konsolenanwendung erstellt wird. Dabei wurde mit einer einfachen Konsolenanwendung begonnen, die schrittweise zu einem System mit mehreren Projekten und Unittests erweitert wurde.  Im nächsten Schritt erstellen Sie eigene beeindruckende Konsolenanwendungen.
 
Wenn Sie an einem komplexeres Beispiel der Konsolen-App interessiert sind, sehen Sie sich das nächste Tutorial über das [Organisieren und Testen von Projekten mit der .NET Core-Befehlszeile (SDK Preview 3)](using-with-xplat-cli-msbuild-folders.md) an.



<!--HONumber=Nov16_HO3-->


