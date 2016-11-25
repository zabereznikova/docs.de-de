---
title: Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile
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
ms.sourcegitcommit: 37e14d5cdf1593f6a8b1ecee9d9828647b023548
ms.openlocfilehash: 5493ccb77e62d20d5101728ef8ab1744ea697fb8

---

# <a name="getting-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a>Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile

In diesem Leitfaden erfahren Sie, wie Sie mit den Tools der .NET Core-Befehlszeilenschnittstelle einfache plattformübergreifende Konsolen-Apps erstellen können.

Wenn Sie mit dem Toolset der .NET Core-Befehlszeilenschnittstelle nicht vertraut sind, finden Sie entsprechende Informationen in der [Übersicht über das .NET Core SDK](../sdk.md).

## <a name="prerequisites"></a>Erforderliche Komponenten

Stellen Sie vor Beginn sicher, dass die [aktuellsten Tools der .NET Core-CLI](https://www.microsoft.com/net/core) installiert sind. Außerdem benötigen Sie einen Text-Editor.

## <a name="hello-console-app"></a>Hallo Konsolenanwendung!

Navigieren Sie zu einem Ordner mit einem beliebigen Namen, oder erstellen Sie diesen. Wir haben den Namen „Hello“ für den Beispielcode verwendet, der [hier](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/Hello) zu finden ist.

Öffnen Sie die Eingabeaufforderung, und geben Sie folgenden Befehl ein:

```
$ dotnet new
$ dotnet restore
$ dotnet run
```

Hier eine kurze Beschreibung der Schritte:

1. `$ dotnet new`

   Mit [`dotnet new`](../tools/dotnet-new.md) wird eine aktuelle `project.json`-Datei mit den NuGet-Abhängigkeiten erstellt, die zum Erstellen einer Konsolenanwendung benötigt werden.  Zudem wird `Program.cs` erstellt. Hierbei handelt es sich um eine einfache Datei, die den Einstiegspunkt für die Anwendung enthält.
   
   `project.json`:
   ```json
   {
        "version": "1.0.0-*",
        "buildOptions": {
            "emitEntryPoint": true
        },
        "dependencies": {
            "Microsoft.NETCore.App": {
                "type": "platform",
                "version": "1.0.0"
            }
        },   
       "frameworks": {
            "netcoreapp1.0": {
                "imports": "dnxcore50"
            }
        }
   }
   ```
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

2. `$ dotnet restore`

   [`dotnet restore`](../tools/dotnet-restore.md) führt einen Aufruf in NuGet aus, um die Struktur der Abhängigkeiten wiederherzustellen. NuGet analysiert die Datei `project.json`, lädt die in der Datei angegebenen Abhängigkeiten herunter (oder ruft diese aus einem Cache auf Ihrem Computer ab) und schreibt die Datei `project.lock.json`.  Die Datei `project.lock.json` ist zum Kompilieren und Ausführen erforderlich.
   
   Bei der Datei `project.lock.json` handelt es sich um eine persistente und umfassende Gruppe des Diagramms von NuGet-Abhängigkeiten und anderen Informationen, die eine Anwendung beschreiben.  Diese Datei wird von anderen Tools wie `dotnet build` und `dotnet run` gelesen, die dadurch in die Lage versetzt werden, den Quellcode mit einer vorschriftsmäßigen Menge von NuGet-Abhängigkeiten und Bindungsauflösungen zu verarbeiten.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) ruft `dotnet build` auf, um sicherzustellen, dass die Buildziele erstellt wurden, und ruft anschließend `dotnet <assembly.dll>` auf, um die Zielanwendung auszuführen.
   
```
$ dotnet run
Hello, World!
```

Sie können auch [`dotnet build`](../tools/dotnet-build.md) ausführen, um den Code zu kompilieren, ohne die Konsolenanwendungen des Builds auszuführen.

### <a name="building-a-self-contained-application"></a>Erstellen einer eigenständigen Anwendung

Versuchen wir, anstelle einer portierbaren Anwendung eine eigenständige Anwendung zu kompilieren. Weitere Informationen zu den Arten der Portierbarkeit in .NET Core sowie zu deren Bereitstellung finden Sie [hier](../deploying/index.md).

Sie müssen einige Änderungen an Ihrer `project.json`-Datei vornehmen, um die Tools so anzuweisen, dass eine eigenständige Anwendung erstellt wird. Diese sind im Projekt [HelloNative](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloNative) im Beispielverzeichnis zu sehen.

Die erste Änderung besteht darin, das Element `"type": "platform"` aus allen Abhängigkeiten zu entfernen. Dieses Projekt enthält bis jetzt nur die Abhängigkeit `"Microsoft.NETCore.App"`. Der Abschnitt `dependencies` sollte wie folgt aussehen:

```json
"dependencies": {
    "Microsoft.NETCore.App": {
        "version": "1.0.0"
    }
},
```

Als Nächstes müssen Sie einen `runtimes`-Knoten hinzufügen, um alle Zielausführungsumgebungen anzugeben. Der folgende `runtimes`-Knoten weist das Buildsystem beispielsweise an, die ausführbaren Dateien für die 64-Bit-Version von Windows 10 und der 64-Bit-Version von Mac OS X Version 10.11 zu erstellen.
Das Buildsystem generiert native ausführbare Dateien für die aktuelle Umgebung. Wenn Sie diese Schritte auf einem Windows-Computer befolgen, erstellen Sie eine ausführbare Windows-Datei. Wenn Sie diese Schritte auf einem Mac-Computer befolgen, erstellen Sie eine ausführbare OS X-Datei.

```json 
"runtimes": {
  "win10-x64": {},
  "osx.10.11-x64": {}
}
```

Die Liste mit allen unterstützten Runtimes finden Sie im [RID-Katalog](../rid-catalog.md). 
 
Nachdem Sie diese beiden Änderungen vorgenommen haben, führen Sie zuerst `dotnet restore` und dann `dotnet build` aus, um die native ausführbare Datei zu erstellen. Anschließend können Sie die generierte native ausführbare Datei ausführen. 

Das folgende Beispiel enthält die Befehle für Windows. Im Beispiel wird gezeigt, an welcher Stelle die native ausführbare Datei erstellt wird. Dabei wird davon ausgegangen, dass der Name des Projektverzeichnisses „HelloNative“ lautet.

```
$ dotnet restore 
$ dotnet build 
$ .\bin\Debug\netcoreapp1.0\win10-x64\HelloNative.exe
Hello World!
```

Sie werden feststellen, dass es etwas länger dauert, bis die native Anwendung erstellt ist. Dafür wird sie jedoch etwas schneller ausgeführt. Dieses Verhalten wird umso deutlicher, wenn die Anwendung größer wird.

Während des Buildprozesses werden einige Dateien mehr erstellt, wenn die Datei `project.json` einen nativen Build erstellt. Diese Dateien werden in `bin\Debug\netcoreapp1.0\<platform>` erstellt, wobei `<platform>` die ausgewählte RID ist. Neben der Datei `HelloNative.dll` des Projekts gibt es die Datei `HelloNative.exe`, mit der die Runtime geladen und die Anwendung gestartet wird.
Beachten Sie, dass der Name der generierten Anwendung geändert wurde, da der Name des Projektverzeichnisses geändert wurde.  

Packen Sie diese Anwendung, um sie auf einem Computer auszuführen, auf dem die .NET-Laufzeit nicht installiert ist.
Verwenden Sie hierzu den Befehl `dotnet publish`. Mit dem Befehl `dotnet publish` wird ein Unterverzeichnis im Verzeichnis `./bin/Debug/netcoreapp1.0/<platform>` mit dem Namen `publish` erstellt. Damit werden die ausführbare Datei, alle abhängigen DLL-Dateien und das Framework in dieses Unterverzeichnis kopiert. Sie können dieses Verzeichnis auf einem anderen Computer (oder Container) packen und die Anwendung dort ausführen. 

Vergleichen wir dies mit dem Verhalten von `dotnet publish` im ersten „Hello World“-Beispiel. Diese Anwendung ist eine *portierbare Anwendung*, also der Standardanwendungstyp für .NET Core. Für eine portierbare Anwendung muss .NET Core auf dem Zielcomputer installiert sein. Portierbare Anwendungen können auf einem Computer erstellt und auf einem beliebigen Computer ausgeführt werden. Native Anwendung müssen für jeden Zielcomputer separat erstellt werden. `dotnet publish` erstellt ein Verzeichnis, das die DLL der Anwendung sowie alle abhängigen DLLs enthält, die nicht Teil der Plattforminstallation sind.

### <a name="augmenting-the-program"></a>Erweitern des Programms

Verändern wir nun die Datei ein wenig.  Fibonacci-Zahlen machen Spaß, also probieren wir das aus (mit der nativen Version):

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
$ .\bin\Debug\netcoreapp1.0\win10-x64\Fibonacci.exe
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
using static System.Console;
using NumberFun;
```

Und schließlich können Sie sie erstellen:

`$ dotnet build`

Nun kommt der unterhaltsame Teil: Sorgen Sie dafür, dass die neue Datei etwas tut.

### <a name="example-a-fibonacci-sequence-generator"></a>Beispiel: Generator für Fibonacci-Folgen

Angenommen, Sie möchten das vorherige [Fibonacci-Beispiel](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/Fibonacci) weiterentwickeln, indem Sie einige Fibonacci-Werte zwischenspeichern und einige rekursive Funktionen hinzufügen.  Ihr Code für ein [verbessertes Fibonacci-Beispiel](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/FibonacciBetter) kann beispielsweise wie folgt aussehen:

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

Beachten Sie, dass die Verwendung von `Dictionary<int, int>` und `IEnumerable<int>` bedeutet, dass der Namespace `System.Collections` eingebunden wird.
Beim `Microsoft.NetCore.App`-Paket handelt es sich um ein *Metapaket*, das zahlreiche Basisassemblys aus dem .NET Framework enthält. Durch das Einbinden dieses Metapakets haben Sie die `System.Collections.dll`-Assembly bereits als Teil Ihres Projekts eingebunden. Sie können dies überprüfen, indem Sie `dotnet publish` ausführen und die Dateien überprüfen, die Teil des installierten Pakets sind. `System.Collections.dll` wird in der Liste angezeigt. 

```json
{ 
  "version": "1.0.0-*", 
  "buildOptions": { 
    "debugType": "portable", 
    "emitEntryPoint": true 
  }, 
  "dependencies": {}, 
  "frameworks": { 
    "netcoreapp1.0": { 
      "dependencies": { 
        "Microsoft.NETCore.App": { 
          "version": "1.0.0" 
        } 
      }, 
      "imports": "dnxcore50" 
    } 
  },
  "runtimes": {
    "win10-x64": {},
    "osx.10.11-x64": {}
  }
}
```

Passen Sie nun die `Main()`-Methode in der Datei `Program.cs` wie folgt an. Im Beispiel wird vorausgesetzt, dass `Program.cs` eine `using System;`-Anweisung enthält. Wenn eine `using static System.Console;`-Anweisung vorhanden ist, entfernen Sie `Console.` aus `Console.WriteLine`.  

```csharp
public static void Main(string[] args)
{
    var generator = new FibonacciGenerator();
    foreach (var digit in generator.Generate(15))
    {
        WriteLine(digit);
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

## <a name="using-folders-to-organize-code"></a>Verwenden von Ordnern zum Strukturieren von Code

Angenommen, Sie möchten einige neue Typen einführen, die Sie bearbeiten möchten.  In diesem Fall können Sie weitere Dateien hinzufügen und ihnen Namespaces zuordnen, die Sie in die Datei `Program.cs` einbinden können.

```
/MyProject
|__Program.cs
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__project.json
```

Das funktioniert bei relativ kleinen Projekten recht gut.  Wenn Sie jedoch eine größere Anwendung mit vielen verschiedenen Datentypen und womöglich mehreren Schichten haben, sollten Sie die Dinge logisch strukturieren.  Hier kommen nun Ordner ins Spiel.  Sie können entweder [das Beispielprojekt „NewTypes“](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypes) in diesem Leitfaden befolgen oder eigene Dateien und Ordner erstellen.

Erstellen Sie zunächst im Stammverzeichnis des Projekts einen neuen Ordner.  In diesem Fall wird `/Model` ausgewählt.

```
/NewTypes
|__/Model
|__Program.cs
|__project.json
```

Fügen Sie nun einige neue Typen zum Ordner hinzu:

```
/NewTypes
|__/Model
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__Program.cs
|__project.json
```

Ordnen Sie die Dateien demselben Namespace zu, als würden sie sich in einem Verzeichnis befinden, sodass Sie sie in die Datei `Program.cs` einbinden können.

### <a name="example-pet-types"></a>Beispiel: Pet-Typen

In diesem Beispiel werden die beiden neuen Typen `Dog` und `Cat` erstellt, mit deren Hilfe die Schnittstelle `IPet` implementiert wird.

Ordnerstruktur:

```
/NewTypes
|__/Pets
   |__Dog.cs
   |__Cat.cs
   |__IPet.cs
|__Program.cs
|__project.json
```

`IPet.cs`:
```csharp
using System;

namespace Pets
{
    public interface IPet
    {
        string TalkToOwner();
    }
}
```

`Dog.cs`:
```csharp
using System;

namespace Pets
{
    public class Dog : IPet
    {
        public string TalkToOwner() => "Woof!";
    }
}
```

`Cat.cs`:
```csharp
using System;

namespace Pets
{
    public class Cat : IPet
    {
        public string TalkToOwner() => "Meow!";
    }
}
```

`Program.cs`:
```csharp
using System;
using Pets;
using System.Collections.Generic;

namespace ConsoleApplication
{
    public class Program
    {
        public static void Main(string[] args)
        {
            List<IPet> pets = new List<IPet>
            {
                new Dog(),
                new Cat()  
            };
            
            foreach (var pet in pets)
            {
                Console.WriteLine(pet.TalkToOwner());
            }
        }
    }
}
```

`project.json`:
```json
{
  "version": "1.0.0-*",
  "buildOptions": {
    "emitEntryPoint": true
  },
  "dependencies": {
    "Microsoft.NETCore.App": {
      "type": "platform",
      "version": "1.0.0"
    }
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": "dnxcore50"
    }
  }
}
```

Ergebnis bei der Ausführung:

```
$ dotnet restore
$ dotnet run
Woof!
Meow!
```

Das Projekt kann durch Hinzufügen neuer Pet-Typen (wie etwa `Bird`) erweitert werden.

## <a name="testing-your-console-app"></a>Testen der Konsolenanwendung

Irgendwann müssen Sie Ihre Projekte testen.  Im Folgenden wird ein recht gute Methode dafür beschrieben:

1. Verschieben Sie alle Quelldateien Ihres vorhandenen Projekts in einen neuen `src`-Ordner.

   ```
   /Project
   |__/src
   ```

2. Erstellen Sie das Verzeichnis `/test`.

   ```
   /Project
   |__/src
   |__/test
   ```

3. Erstellen Sie eine neue `global.json`-Datei:

   ```
   /Project
   |__/src
   |__/test
   |__global.json
   ```

   `global.json`:
   ```json
   {
      "projects": [
         "src", "test"
      ]
   }
   ```

   Diese Datei teilt dem Buildsystem mit, dass es sich hierbei um ein System mit mehreren Projekten handelt, das die Suche nach Abhängigkeiten nicht nur in dem Ordner ermöglicht, indem es aktuell ausgeführt wird.  Dies ist wichtig, weil Sie dadurch eine Abhängigkeit in den zu testenden Code in Ihrem Testprojekt einfügen können.
   
### <a name="example-extending-the-newtypes-project"></a>Beispiel: Erweitern des Projekts „NewTypes“

Nachdem Sie das Projektsystem eingerichtet haben, können Sie das Testprojekt erstellen und mit dem Schreiben von Tests beginnen.  Ab hier wird in diesem Leitfaden [das Beispielprojekt „Types“](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypes) verwendet und erweitert.  Darüber hinaus wird das [Xunit](https://xunit.github.io/)-Testframework verwendet.  Sie können diesem Beispiel folgen oder ein eigenes System mit mehreren Projekten und Tests erstellen.


Die gesamte Projektstruktur sollte wie folgt aussehen:

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__project.json
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__project.json
|__global.json
```

Stellen Sie sicher, dass sich zwei neue Dinge in Ihrem Testprojekt befinden:

1. Eine korrekte `project.json`-Datei, die Folgendes enthält:

   * Einen Verweis auf `xunit`
   * Einen Verweis auf `dotnet-test-xunit`
   * Einen Verweis auf den Namespace für den zu testenden Code

2. Eine Xunit-Testklasse.

`NewTypesTests/project.json`:
```json
{
  "version": "1.0.0-*",
  "testRunner": "xunit",

  "dependencies": {
    "Microsoft.NETCore.App": {
      "type":"platform",
      "version": "1.0.0"
    },
    "xunit":"2.2.0-beta2-build3300",
    "dotnet-test-xunit": "2.2.0-preview2-build1029",
    "NewTypes": "1.0.0"
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dnxcore50",
        "portable-net45+win8" 
      ]
    }
  }
}
```

`PetTests.cs`: 
```csharp
using System;
using Xunit;
using Pets;
public class PetTests
{
    [Fact]
    public void DogTalkToOwnerTest()
    {
        string expected = "Woof!";
        string actual = new Dog().TalkToOwner();
        
        Assert.Equal(expected, actual);
    }
    
    [Fact]
    public void CatTalkToOwnerTest()
    {
        string expected = "Meow!";
        string actual = new Cat().TalkToOwner();
        
        Assert.Equal(expected, actual);
    }
}
```
   
Nun können Sie Tests durchführen.  Mit dem Befehl [`dotnet test`](../tools/dotnet-test.md) wird der in Ihrem Projekt angegebene Test Runner ausgeführt. Stellen Sie sicher, dass Sie mit dem Verzeichnis der obersten Ebene beginnen.
 
```
$ dotnet restore
$ cd test/NewTypesTests
$ dotnet test
```
 
Das Ergebnis sollte wie folgt aussehen:
 
```
xUnit.net .NET CLI test runner (64-bit win10-x64)
  Discovering: NewTypesTests
  Discovered:  NewTypesTests
  Starting:    NewTypesTests
  Finished:    NewTypesTests
=== TEST EXECUTION SUMMARY ===
   NewTypesTests  Total: 2, Errors: 0, Failed: 0, Skipped: 0, Time: 0.144s
SUMMARY: Total: 1 targets, Passed: 1, Failed: 0.
```
 
## <a name="conclusion"></a>Schlussfolgerung
 
In dieser Anleitung wurde beschrieben, wie eine .NET Core-Konsolenanwendung erstellt wird. Dabei wurde mit einer einfachen Konsolenanwendung begonnen, die schrittweise zu einem System mit mehreren Projekten und Unittests erweitert wurde.  Im nächsten Schritt erstellen Sie eigene beeindruckende Konsolenanwendungen.
 
Wenn Sie Interesse an einem komplexeren Beispiel für eine Konsolenanwendung haben, lesen Sie das nächste Tutorial: [Using the CLI tools to write console apps: An advanced step-by-step guide (Schreiben von Konsolenanwendungen mithilfe der CLI-Tools: ein ausführlicher Schritt-für-Schritt-Leitfaden)](cli-console-app-tutorial-advanced.md).



<!--HONumber=Nov16_HO3-->


