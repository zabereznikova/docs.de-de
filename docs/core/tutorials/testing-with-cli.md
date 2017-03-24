---
title: Organisieren und Testen von Projekten mit der .NET Core-Befehlszeile | Microsoft-Dokumentation
description: "In diesem Tutorial wird das Organisieren und Testen von .NET Core-Projekten von der Befehlszeile aus erläutert."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 03/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 52ff1be3-d92e-4477-9c84-8c1771e87ab5
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 3f401907a59d5427cbcfaa0b785931a7ed82110f
ms.lasthandoff: 03/07/2017

---

# <a name="organizing-and-testing-projects-with-the-net-core-command-line"></a>Organisieren und Testen von Projekten mit der .NET Core-Befehlszeile

Dieses Lernprogramm folgt auf [Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile](./using-with-xplat-cli.md), um zu zeigen, wie Sie über einfache „hello world“-Szenarios hinaus anspruchsvolleren und überlegt organisierten Anwendungen den Weg ebnen.

## <a name="using-folders-to-organize-code"></a>Verwenden von Ordnern zum Strukturieren von Code

Angenommen, Sie möchten einige neue Typen einführen, die Sie bearbeiten möchten. In diesem Fall können Sie weitere Dateien hinzufügen und ihnen Namespaces zuordnen, die Sie in Ihrer Datei *Program.cs* einbinden können.

```
/MyProject
|__Program.cs
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
```

Das funktioniert bei relativ kleinen Projekten recht gut. Wenn Sie jedoch eine größere Anwendung mit vielen verschiedenen Datentypen und womöglich mehreren Schichten haben, sollten Sie die Dinge logisch strukturieren. Hier kommen nun Ordner ins Spiel. Sie können entweder [das Beispielprojekt „NewTypes“](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypesMsBuild) in diesem Leitfaden befolgen oder eigene Dateien und Ordner erstellen.

Erstellen Sie zunächst im Stammverzeichnis des Projekts einen neuen Ordner. In diesem Fall wird `/Model` ausgewählt.

```
/NewTypes
|__/Model
|__Program.cs
|__NewTypes.csproj
```

Fügen Sie nun einige neue Typen zum Ordner hinzu:

```
/NewTypes
|__/Model
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__Program.cs
|__NewTypes.csproj
```

Ordnen Sie die Dateien demselben Namespace zu, als würden sie sich in einem Verzeichnis befinden, sodass Sie sie in die Datei `Program.cs` einbinden können.

### <a name="example-pet-types"></a>Beispiel: Pet-Typen

In diesem Beispiel werden die beiden neuen Typen `Dog` und `Cat` erstellt, mit deren Hilfe die allgemeine Schnittstelle `IPet` implementiert wird.

Ordnerstruktur:

```
/NewTypes
|__/Pets
   |__Dog.cs
   |__Cat.cs
   |__IPet.cs
|__Program.cs
|__NewTypes.csproj
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

`NewTypes.csproj`:
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

Ergebnis bei der Ausführung:

```
$ dotnet restore
$ dotnet run
Woof!
Meow!
```

Das Projekt kann durch Hinzufügen neuer Pet-Typen (wie etwa `Bird`) erweitert werden.

## <a name="testing-your-console-app"></a>Testen der Konsolenanwendung

Irgendwann müssen Sie Ihre Projekte testen. Im Folgenden wird ein recht gute Methode dafür beschrieben:

1. Verschieben Sie alle Quelldateien Ihres vorhandenen Projekts in einen neuen `src`-Ordner.

   ```
   /Project
   |__/src
   ```

2. Erstellen Sie das Verzeichnis `/test`, zu dem Sie anschließend über `cd` wechseln.

   ```
   /Project
   |__/src
   |__/test
   ```

3. Initialisieren Sie das Verzeichnis mit dem Befehl `dotnet new xunit`. Hierbei wird von xUnit ausgegangen. Sie können aber auch MSTest nutzen, indem Sie `xunit` durch `mstest` ersetzen.
   
### <a name="example-extending-the-newtypes-project"></a>Beispiel: Erweitern des Projekts „NewTypes“

Nachdem Sie das Projektsystem eingerichtet haben, können Sie das Testprojekt erstellen und mit dem Schreiben von Tests beginnen. Ab hier wird in diesem Leitfaden [das Beispielprojekt „Types“](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypesMsBuild) verwendet und erweitert. Darüber hinaus wird das [Xunit](https://xunit.github.io/)-Testframework verwendet. Sie können diesem Beispiel folgen oder ein eigenes System mit mehreren Projekten und Tests erstellen.

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
      |__NewTypes.csproj
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__NewTypesTests.csproj
```

Stellen Sie sicher, dass sich zwei neue Dinge in Ihrem Testprojekt befinden:

1. Eine korrekte *NewTypesTests.csproj*-Datei mit Folgendem:

   * Einen Verweis auf `xunit`
   * Einen Verweis auf `dotnet-test-xunit`
   * Einen Verweis auf den Namespace für den zu testenden Code

   Dies kann erstellt werden, indem Sie im Verzeichnis *NewTypesTests* einfach `dotnet new xunit` an der Befehlszeile ausführen und dann einen Projektverweis zum Projekt `NewTypes` hinzufügen.

    `NewTypesTests/NewTypesTests.csproj`:
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
        <PackageReference Include="Microsoft.NET.Test.Sdk">
          <Version>15.0.0-preview-20161024-02</Version>
        </PackageReference>
        <PackageReference Include="xunit">
          <Version>2.2.0-beta3-build3402</Version>
        </PackageReference>
        <PackageReference Include="xunit.runner.visualstudio">
          <Version>2.2.0-beta4-build1188</Version>
        </PackageReference>
        <ProjectReference Include="../../src/NewTypes/NewTypes.csproj"/>
      </ItemGroup>

      <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
    </Project>
    ```

2. Eine xUnit-Testklasse.

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
   
Nun können Sie Tests durchführen. Mit dem Befehl [`dotnet test`](../tools/dotnet-test.md) wird der in Ihrem Projekt angegebene Test Runner ausgeführt. Stellen Sie sicher, dass Sie mit dem Verzeichnis der obersten Ebene beginnen.
 
```
$ cd test/NewTypesTests
$ dotnet restore
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

