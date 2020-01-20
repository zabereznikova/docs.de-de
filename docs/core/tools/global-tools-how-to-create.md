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
# <a name="create-a-net-core-global-tool-using-the-net-core-cli"></a>Erstellen eines globalen .NET Core-Tool mithilfe des .NET Core-CLIs

In diesem Artikel erfahren Sie, wie Sie ein globales .NET Core-Tool erstellen und verpacken. Das .NET Core-CLI ermöglicht es Ihnen, eine Konsolenanwendung als globales Tool zu erstellen, das leicht von anderen installiert und ausgeführt werden kann. Globale .NET Core-Tools sind NuGet-Pakete, die vom .NET Core-CLI aus installiert werden. Weitere Informationen über globale Tools finden Sie unter [Übersicht über globale .NET Core-Tools](global-tools.md).

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="create-a-project"></a>Erstellen eines Projekts

Dieser Artikel verwendet das .NET Core-CLI, um ein Projekt zu erstellen und zu verwalten.

Als Beispieltool verwenden wir eine Konsolenanwendung, die einen ASCII-Bot generiert und eine Meldung ausgibt. Erstellen Sie zunächst eine neue .NET Core-Konsolenanwendung.

```dotnetcli
dotnet new console -o botsay
```

Navigieren Sie zum `botsay`-Verzeichnis, das vom vorherigen Befehl erstellt wurde.

## <a name="add-the-code"></a>Hinzufügen des Codes

Öffnen Sie die Datei `Program.cs` in Ihrem bevorzugten Text-Editor, wie etwa `vim` oder [Visual Studio Code](https://code.visualstudio.com/).

Fügen Sie am Anfang der Datei die folgende `using`-Anweisung hinzu; dies hilft dabei, den Code zum Anzeigen der Versionsinformationen der Anwendung kurz zu halten.

```csharp
using System.Reflection;
```

Bewegen Sie sich als Nächstes nach unten zur Methode `Main`. Ersetzen Sie die Methode durch den folgenden Code, um die Befehlszeilenargumente für Ihre Anwendung zu verarbeiten. Wenn keine Argumente übergeben wurden, wird eine kurze Hilfemeldung angezeigt. Andernfalls werden alle diese Argumente in eine Zeichenfolge umgewandelt und zusammen mit dem Bot ausgegeben.

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

### <a name="create-the-bot"></a>Erstellen des Bots

Fügen Sie als Nächstes eine neue Methode mit dem Namen `ShowBot` hinzu, die einen Zeichenfolgenparameter akzeptiert. Diese Methode gibt die Meldung und den ASCII-Bot aus. Der Code des ASCII-Bots wurde aus dem [dotnetbot](https://github.com/dotnet/core/blob/master/samples/dotnetsay/Program.cs)-Beispiel entnommen.

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

### <a name="test-the-tool"></a>Testen des Tools

Führen Sie das Projekt aus, und sehen Sie sich die Ausgabe an. Probieren Sie diese Variationen in der Befehlszeile aus, um die verschiedenen Ergebnisse anzuzeigen:

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- hello from the bot
```

Alle Argumente hinter dem Trennzeichen `--` werden an Ihre Anwendung übergeben.

## <a name="set-up-the-global-tool"></a>Einrichten des globalen Tools

Bevor Sie die Anwendung als ein globales Tool verpacken und verteilen können, müssen Sie die Projektdatei ändern. Öffnen Sie die Datei `botsay.csproj`, und fügen Sie dem Knoten `<Project><PropertyGroup>` drei neue XML-Knoten hinzu:

- `<PackAsTool>`\
[ERFORDERLICH] Gibt an, dass die Anwendung für die Installation als globales Tool verpackt wird.

- `<ToolCommandName>`\
[OPTIONAL] Ein alternativer Name für das Tool, andernfalls wird der Befehlsname für das Tool nach der Projektdatei benannt. Sie können mehrere Tools in einem Paket verpacken, die Wahl eines eindeutigen und eingängigen Namens erleichtert die Unterscheidung von anderen Tools im gleichen Paket.

- `<PackageOutputPath>`\
[OPTIONAL] Ort, an dem das NuGet-Paket erzeugt werden soll. Das NuGet-Paket wird von .NET Core CLI Global Tools zur Installation Ihres Tools verwendet.

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

`<PackageOutputPath>` ist zwar optional, Sie sollten es aber in diesem Beispiel verwenden. Achten Sie darauf, es festzulegen: `<PackageOutputPath>./nupkg</PackageOutputPath>`.

Erstellen Sie als Nächstes ein NuGet-Paket für Ihre Anwendung.

```dotnetcli
dotnet pack
```

Die `botsay.1.0.0.nupkg`-Datei wird in dem Ordner erstellt, der durch den `<PackageOutputPath>`-XML-Wert aus der `botsay.csproj`-Datei angegeben wird, in diesem Beispiel ist das der Ordner `./nupkg`. Dies vereinfacht Installation und Testen. Wenn Sie ein Tool öffentlich herausbringen möchten, laden Sie es nach <https://www.nuget.org> hoch. Sobald das Tool unter NuGet verfügbar ist, können Entwickler eine Installation des Tools für alle Benutzer mit der `--global`-Option des [dotnet tool install](dotnet-tool-install.md)-Befehls durchführen.

Da Sie jetzt ein Paket besitzen, installieren Sie das Tool aus diesem Paket:

```dotnetcli
dotnet tool install --global --add-source ./nupkg botsay
```

Der Parameter `--add-source` weist das .NET Core-CLI an, vorübergehend den Ordner `./nupkg` (unseren `<PackageOutputPath>`-Ordner) als zusätzlichen Quellfeed für NuGet-Pakete zu verwenden. Weitere Informationen über das Installieren von globalen Tools finden Sie unter [Übersicht über globale .NET Core-Tools](global-tools.md).

Wenn die Installation erfolgreich abgeschlossen wurde, wird eine Meldung angezeigt, die den Befehl zum Aufrufen des Tools und die installierte Version ähnlich wie im folgenden Beispiel anzeigt:

```output
You can invoke the tool using the following command: botsay
Tool 'botsay' (version '1.0.0') was successfully installed.
```

Sie sollten jetzt in der Lage sein, `botsay` einzugeben und eine Reaktion vom Tool zu erhalten.

> [!NOTE]
> Wenn die Installation erfolgreich war, Sie den Befehl `botsay` aber nicht verwenden können, müssen Sie möglicherweise ein neues Terminal öffnen, um die PATH-Variable zu aktualisieren.

## <a name="remove-the-tool"></a>Entfernen des Tools

Wenn Sie Ihre Experimente mit dem Tool abgeschlossen haben, können Sie es mit dem folgenden Befehl entfernen:

```dotnetcli
dotnet tool uninstall -g botsay
```
