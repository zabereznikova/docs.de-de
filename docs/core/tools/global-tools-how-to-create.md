---
title: 'Tutorial: Erstellen eines .NET Core-Tools'
description: Erfahren Sie, wie Sie ein .NET Core-Tool erstellen. Ein Tool ist eine Konsolenanwendung, die mithilfe der .NET Core-CLI installiert wird.
ms.date: 02/12/2020
ms.openlocfilehash: 88cc3be7b149834ace0c5f3ba8ac8c039199908f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156724"
---
# <a name="tutorial-create-a-net-core-tool-using-the-net-core-cli"></a>Tutorial: Erstellen eines .NET Core-Tool mithilfe der .NET Core-CLI

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

In diesem Tutorial erfahren Sie, wie Sie ein .NET Core-Tool erstellen und packen. Die .NET Core-CLI ermöglicht Ihnen, eine Konsolenanwendung als Tool zu erstellen, das von anderen installiert und ausgeführt werden kann. .NET Core-Tools sind NuGet-Pakete, die über die .NET Core-CLI installiert werden. Weitere Informationen zu Tools finden Sie unter [Übersicht über .NET Core-Tools](global-tools.md).

Das von Ihnen erstellte Tool ist eine Konsolenanwendung, die eine Nachricht als Eingabe verwendet und sie zusammen mit Textzeilen anzeigt, die das Bild eines Roboters erzeugen.

Dies ist das erste in einer Reihe von drei Tutorials. In diesem Tutorial erstellen und packen Sie ein Tool. In den nächsten beiden Tutorials verwenden Sie [das Tool als globales Tool](global-tools-how-to-use.md) und [das Tool als lokales Tool](local-tools-how-to-use.md).

## <a name="prerequisites"></a>Voraussetzungen

- [.NET Core SDK 3.1](https://dotnet.microsoft.com/download) oder neuere Version.

  Dieses Tutorial und das folgende [Tutorial für globale Tools](global-tools-how-to-use.md) gelten für .NET Core SDK 2.1 und neuere Versionen, da globale Tools ab dieser Version verfügbar sind. Dieses Tutorial setzt jedoch voraus, dass Sie mindestens Version 3.1 installiert haben, sodass Sie die Möglichkeit haben, mit dem [Tutorial zu lokalen Tools](local-tools-how-to-use.md) fortzufahren. Lokale .NET Core-Tools sind ab .NET Core SDK 3.0 verfügbar. Die Verfahren zum Erstellen eines Tools sind unabhängig davon identisch, ob es als globales oder lokales Tool verwendet wird.
  
- Ein Text-Editor oder Code-Editor Ihrer Wahl.

## <a name="create-a-project"></a>Erstellen eines Projekts

1. Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *repository*.

1. Navigieren Sie zum Ordner *Repository*, und geben Sie den folgenden Befehl ein:

   ```dotnetcli
   dotnet new console -n microsoft.botsay
   ```

   Der Befehl erstellt einen neuen Ordner namens *microsoft.botsay* im Ordner *Repository*.

1. Navigieren Sie zum Ordner *microsoft.botsay*.

   ```console
   cd microsoft.botsay
   ```

## <a name="add-the-code"></a>Hinzufügen des Codes

1. Öffnen Sie die Datei `Program.cs` in einem Code-Editor.

1. Fügen Sie am Anfang der Datei die folgende `using`-Anweisung hinzu:

   ```csharp
   using System.Reflection;
   ```

1. Ersetzen Sie die `Main`-Methode durch folgenden Code, um die Befehlszeilenargumente für die Anwendung zu verarbeiten.

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

   Wenn keine Argumente übergeben werden, wird eine kurze Hilfemeldung angezeigt. Andernfalls werden alle Argumente zu einer einzigen Zeichenfolge verkettet und durch den Aufruf der im nächsten Schritt erstellten `ShowBot`-Methode ausgegeben.

1. Fügen Sie eine neue Methode namens `ShowBot` hinzu, die einen Zeichenfolgenparameter verwendet. Die Methode gibt die Meldung und mithilfe von Textzeilen ein Bild eines Roboters aus.

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

1. Speichern Sie die Änderungen.

## <a name="test-the-application"></a>Testen der Anwendung

Führen Sie das Projekt aus, und sehen Sie sich die Ausgabe an. Probieren Sie diese Variationen in der Befehlszeile aus, um die verschiedenen Ergebnisse anzuzeigen:

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

Alle Argumente hinter dem Trennzeichen `--` werden an Ihre Anwendung übergeben.

## <a name="package-the-tool"></a>Packen des Tools

Bevor Sie die Anwendung als Tool packen und verteilen können, müssen Sie die Projektdatei ändern.

1. Öffnen Sie die Datei *microsoft.botsay.csproj*, und fügen Sie drei neue XML-Knoten zum Ende des `<PropertyGroup>`-Knotens hinzu:

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   `<ToolCommandName>` ist ein optionales Element, das den Befehl angibt, der das Tool nach seiner Installation aufruft. Wenn dieses Element nicht angegeben wird, ist der Befehlsname für das Tool der Projektdateiname ohne die Erweiterung *.csproj*.

   `<PackageOutputPath>` ist ein optionales Element, das bestimmt, wo das NuGet-Paket erstellt wird. Das NuGet-Paket wird von der .NET Core-CLI zur Installation Ihres Tools verwendet.

   Die Projektdatei sieht wie im folgenden Beispiel aus:

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

1. Erstellen Sie ein NuGet-Paket, indem Sie den Befehl [dotnet pack](dotnet-pack.md) ausführen:

   ```dotnetcli
   dotnet pack
   ```

   Die Datei *microsoft.botsay.1.0.0.nupkg* wird in dem Ordner erstellt, der mit dem `<PackageOutputPath>`-Wert der Datei *microsoft.botsay.csproj* angegeben wird. In diesem Beispiel handelt es sich dabei um den Ordner *./nupkg*.
  
   Wenn Sie ein Tool veröffentlichen möchten, laden Sie es in `https://www.nuget.org` hoch. Sobald das Tool in NuGet verfügbar ist, können Entwickler es mit dem Befehl [dotnet tool install](dotnet-tool-install.md) installieren. Für dieses Tutorial installieren Sie das Paket direkt aus dem lokalen Ordner *nupkg*, sodass Sie das Paket nicht auf NuGet hochladen müssen.

## <a name="troubleshoot"></a>Problembehandlung

Falls im Verlauf des Tutorials eine Fehlermeldung angezeigt wird, finden Sie unter [Behandlung von Problemen bei der Nutzung von .NET Core-Tools](troubleshoot-usage-issues.md) weitere Informationen.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine Konsolenanwendung erstellt und sie als Tool gepackt. Im nächsten Tutorial erfahren Sie, wie Sie das Tool als globales Tool verwenden können.

> [!div class="nextstepaction"]
> [Installieren und Verwenden eines globalen Tools](global-tools-how-to-use.md)

Auf Wunsch können Sie das Tutorial zu den globalen Tools überspringen und direkt zum Tutorial für lokale Tools übergehen.

> [!div class="nextstepaction"]
> [Installieren und Verwenden eines lokalen Tools](local-tools-how-to-use.md)
