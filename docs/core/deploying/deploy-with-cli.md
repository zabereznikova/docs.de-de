---
title: Bereitstellung der .NET Core-App mit CLI-Tools
description: Erfahren Sie mehr zur .NET Core-App-Bereitstellung mit CLI-Tools
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.openlocfilehash: 7b009068422686442ebff83b9400c365f34a3154
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244750"
---
# <a name="deploying-net-core-apps-with-command-line-interface-cli-tools"></a>Bereitstellen von .NET Core-Apps mit CLI-Tools (command-line interface, Befehlszeilenschnittstelle)

Sie können eine .NET Core-Anwendung entweder als *Framework-abhängige Bereitstellung* bereitstellen, was die Binärdateien Ihrer Anwendung einschließt, jedoch von Präsenz von .NET Core auf dem Zielsystem abhängt, oder als *eigenständige Bereitstellung*,die jeweils Ihre Anwendung sowie die .NET Core-Binärdateien einschließt. Eine Übersicht finden Sie unter [.NET Core-Anwendungsbereitstellung](index.md).

Die folgenden Abschnitte zeigen, wie Sie [.NET Core-CLI-Tools](../tools/index.md) zum Erstellen der folgenden Bereitstellungen verwenden:

- Framework-abhängige Bereitstellung
- Framework-abhängige Bereitstellung mit Drittanbieterabhängigkeiten
- Eigenständige Bereitstellung
- Eigenständige Bereitstellung mit Drittanbieterabhängigkeiten

Wenn Sie über die Befehlszeile arbeiten, können Sie einen Programm-Editor Ihrer Wahl verwenden. Wenn Ihr Programm-Editor [Visual Studio Code](https://code.visualstudio.com) ist, können Sie eine Befehlskonsole in Ihrer Visual Studio Code-Umgebung öffnen, indem Sie **Ansicht** > **Integrierter Terminal** auswählen.

## <a name="framework-dependent-deployment"></a>Framework-abhängige Bereitstellung

Die Bereitstellung einer Framework-abhängigen Bereitstellung ohne Drittanbieter-Abhängigkeiten umfasst nur das Erstellen, Testen und Veröffentlichen der Anwendung. Ein einfaches, in C# geschriebenes Beispiel veranschaulicht den Prozess. 

1. Erstellen Sie ein Projektverzeichnis.

   Erstellen Sie ein Verzeichnis für Ihr Projekt, und machen Sie es zu Ihrem aktuellen Verzeichnis.

1. Erstellen eines Projekts

   Geben Sie über die Befehlszeile [dotnet new console](../tools/dotnet-new.md) ein, um ein neues C#-Konsolenprojekt in diesem Verzeichnis zu erstellen.

1. Überprüfen Sie den Quellcode der Anwendung.

   Öffnen Sie die *Program.cs*-Datei in Ihrem Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code. Der Benutzer wird zur Texteingabe aufgefordert, und die einzelnen Wörter, die vom Benutzer eingegeben wurden, werden angezeigt. Der reguläre Ausdruck `\w+` wird verwendet, um Wörter im Eingabetext zu trennen.

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. Aktualisieren Sie die Abhängigkeiten und Tools des Projekts.
 
   Führen Sie den Befehl [dotnet restore](../tools/dotnet-restore.md) aus ([siehe Hinweis](#dotnet-restore-note)), um die im Projekt angegebenen Abhängigkeiten wiederherzustellen.

1. Erstellen Sie ein Debugbuild Ihrer App.

   Verwenden Sie den Befehl [dotnet build](../tools/dotnet-build.md), um Ihre Anwendung zu erstellen, oder den Befehl [dotnet run](../tools/dotnet-run.md), um sie zu erstellen und auszuführen.

1. Stellen Sie Ihre App bereit.

   Nachdem Sie das Programm debuggt und getestet haben, erstellen Sie die Bereitstellung, indem Sie folgenden Befehl verwenden:

      ```console
      dotnet publish -f netcoreapp1.1 -c Release
      ```
   Dies erstellt eine Releaseversion (anstatt einer Debugversion) Ihrer Anwendung. Die resultierenden Dateien werden in ein Verzeichnis namens *publish* platziert, das sich in einem Unterverzeichnis des *bin*-Verzeichnisses Ihres Projekts befindet.

   Der Veröffentlichungsprozess gibt zusammen mit den Dateien Ihrer Anwendung eine Programmdatenbankdatei (.pdb) aus, die Debuginformationen über Ihre Anwendung enthält. Die Datei ist vornehmlich für das Debuggen von Ausnahmen nützlich. Sie können sich auch dazu entschließen, sie nicht mit den Dateien Ihrer Anwendung zu verteilen. Jedoch sollten Sie sie für den Fall speichern, dass Sie das Releasebuild Ihrer App debuggen möchten.

   Der vollständige Satz von Anwendungsdateien kann so bereitgestellt werden, wie Sie möchten. Sie können sie z.B. in einer ZIP-Datei verpacken, und einen einfachen `copy`-Befehl verwenden, oder sie mit jedem Installationspaket Ihrer Wahl bereitstellen.

1. Ausführen der App

   Sobald die Anwendung installiert ist, können Benutzer sie mithilfe des `dotnet`-Befehls ausführen und den Dateinamen der Anwendung bereitstellen, z.B. `dotnet fdd.dll`.

   Das Installationsprogramm sollte zusätzlich zu den Binärdateien der Anwendung das freigegebene Framework-Installationsprogramm bündeln, oder als erforderliche Komponente im Rahmen der Anwendungsinstallation überprüfen.  Die Installation des gemeinsam genutzten Frameworks erfordert Administrator-/Root-Zugriff.

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a>Framework-abhängige Bereitstellung mit Drittanbieterabhängigkeiten

Die Bereitstellung einer Framework-abhängigen Bereitstellung mit mindestens einer Drittanbieterabhängigkeit erfordert, dass diese Abhängigkeiten für Ihr Projekt verfügbar sind. Es sind noch zwei zusätzliche Schritte nötig, bevor Sie den `dotnet restore`-Befehl ausführen können ([siehe Hinweis](#dotnet-restore-note)):

1. Fügen Sie Verweise auf Drittanbieter-Bibliotheken zum `<ItemGroup>`-Teil Ihrer *CSPROJ*-Datei hinzu. Der folgende `<ItemGroup>`-Abschnitt verwendet [Json.NET](http://www.newtonsoft.com/json) als Drittanbieter-Bibliothek:

      ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
      ```

1. Wenn noch nicht geschehen, laden Sie das NuGet-Paket mit der Drittanbieter-Abhängigkeit herunter. Führen Sie den `dotnet restore`-Befehl ([siehe Hinweis](#dotnet-restore-note)) nach dem Hinzufügen der Abhängigkeit aus, um das Paket herunterzuladen. Da die Abhängigkeit zum Zeitpunkt der Veröffentlichung aus dem lokalen NuGet-Cache aufgelöst wurde, muss sie auf Ihrem System verfügbar sein.

Beachten Sie, dass eine Framework-abhängige Bereitstellung mit Drittanbieter-Abhängigkeiten nur so tragbar wie ihre Drittanbieter-Abhängigkeiten ist. Falls eine Drittanbieter-Bibliothek nur macOS unterstützen sollte, so wird die Anwendung nicht auf Windows-Systeme übertragbar sein. Dies kann geschehen, wenn die Drittanbieter-Abhängigkeit selbst vom nativen Code abhängt. Ein gutes Beispiel dafür ist der [Kestrel-Server](/aspnet/core/fundamentals/servers/kestrel), der eine native Abhängigkeit unter [libuv](https://github.com/libuv/libuv) erfordert. Wenn bei dieser Art von Drittanbieter-Abhängigkeit eine FDD für eine Anwendung erstellt wird, enthält die veröffentlichte Ausgabe einen Ordner für jede [Runtime-ID (RID)](../rid-catalog.md), die die native Abhängigkeit unterstützt (und im NuGet-Paket vorhanden ist).

## <a name="simpleSelf"></a> Eigenständige Bereitstellung ohne Drittanbieterabhängigkeiten

Das Bereitstellen einer eigenständigen Bereitstellung ohne Abhängigkeiten von Drittanbietern umfasst das Erstellen des Projekts, das Ändern der *CSPROJ*-Datei sowie das Erstellen, Testen und Veröffentlichen der Anwendung. Ein einfaches, in C# geschriebenes Beispiel veranschaulicht den Prozess. Dieses Beispiel zeigt, wie Sie eine eigenständige Bereitstellung mithilfe des [dotnet-Hilfsprogramms](../tools/dotnet.md) aus der Befehlszeile erstellen.

1. Erstellen Sie ein Verzeichnis für das Projekt.

   Erstellen Sie ein Verzeichnis für Ihr Projekt, und machen Sie es zu Ihrem aktuellen Verzeichnis.

1. Erstellen eines Projekts

   Geben Sie über die Befehlszeile [dotnet new console](../tools/dotnet-new.md) ein, um ein neues C#-Konsolenprojekt in diesem Verzeichnis zu erstellen.

1. Überprüfen Sie den Quellcode der Anwendung.

   Öffnen Sie die *Program.cs*-Datei in Ihrem Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code. Der Benutzer wird zur Texteingabe aufgefordert, und die einzelnen Wörter, die vom Benutzer eingegeben wurden, werden angezeigt. Der reguläre Ausdruck `\w+` wird verwendet, um Wörter im Eingabetext zu trennen.

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. Definieren Sie die Zielplattformen für Ihre App.

   Erstellen Sie das Tag `<RuntimeIdentifiers>` im Abschnitt `<PropertyGroup>` Ihrer Datei *CSPROJ*, der die Plattformen Ihrer Anwendungsziele definiert und die Runtime-ID für jede Zielplattform angibt. Beachten Sie, dass Sie auch ein Semikolon hinzufügen müssen, um die RIDs trennen. Sie finden eine RID-Liste im [RID-Katalog](../rid-catalog.md). 

   Der folgende Abschnitt `<PropertyGroup>` gibt z.B. an, dass die Anwendung unter den Betriebssystemen Windows 10 (64-Bit) und OS X 10.11 (64-Bit) ausgeführt wird.

     ```xml
     <PropertyGroup>
         <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
     </PropertyGroup>
     ```

   Beachten Sie, dass das Element `<RuntimeIdentifiers>` in jeder `<PropertyGroup>` in Ihrer *CSPROJ*-Datei erscheinen kann. Eine vollständige *CSPROJ*-Beispieldatei wird später in diesem Abschnitt angezeigt.

1. Aktualisieren Sie die Abhängigkeiten und Tools des Projekts.

   Führen Sie den Befehl [dotnet restore](../tools/dotnet-restore.md) aus ([siehe Hinweis](#dotnet-restore-note)), um die im Projekt angegebenen Abhängigkeiten wiederherzustellen.

1. Erstellen Sie ein Debugbuild Ihrer App.

   Verwenden Sie den Befehl [dotnet build](../tools/dotnet-build.md) aus der Befehlszeile.

1. Nachdem Sie das Programm debuggt und getestet haben, erstellen Sie die Dateien, die mit Ihrer App für jede Zielplattform bereitgestellt werden sollen.

   Verwenden Sie den `dotnet publish`-Befehl für beide Zielplattformen wie folgt:

      ```console
      dotnet publish -c Release -r win10-x64
      dotnet publish -c Release -r osx.10.11-x64
      ```

   Dies erstellt eine Releaseversion (anstatt einer Debugversion) Ihrer Anwendung für jede Zielplattform. Die resultierenden Dateien werden in ein Unterverzeichnis namens *publish* platziert, das sich in einem Unterverzeichnis des *\bin\Release\netcoreapp1.1\<runtime_identifier>*-Unterverzeichnis Ihres Projekts befindet. Beachten Sie, dass jedes Unterverzeichnis den vollständigen Dateisatz enthält (Dateien Ihrer Anwendung und alle .NET Core-Dateien), der zum Starten Ihrer Anwendung erforderlich ist.

Der Veröffentlichungsprozess gibt zusammen mit den Dateien Ihrer Anwendung eine Programmdatenbankdatei (.pdb) aus, die Debuginformationen über Ihre Anwendung enthält. Die Datei ist vornehmlich für das Debuggen von Ausnahmen nützlich. Sie können sich auch dazu entschließen, sie nicht mit den Dateien Ihrer Anwendung zu packen. Jedoch sollten Sie sie für den Fall speichern, dass Sie das Releasebuild Ihrer App debuggen möchten.

Stellen Sie die veröffentlichen Dateien in einer beliebigen Weise bereit. Sie können sie z.B. in einer ZIP-Datei verpacken, und einen einfachen `copy`-Befehl verwenden, oder sie mit jedem Installationspaket Ihrer Wahl bereitstellen.

Es folgt die vollständige *CSPROJ*-Datei dieses Projekts:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a>Eigenständige Bereitstellung mit Drittanbieterabhängigkeiten

Das Bereitstellen einer eigenständigen Bereitstellung mit einer oder mehreren Drittanbieter-Abhängigkeiten umfasst das Hinzufügen der Drittanbieter-Abhängigkeit: Es sind noch zwei zusätzliche Schritte nötig, bevor Sie den `dotnet restore`-Befehl ausführen können ([siehe Hinweis](#dotnet-restore-note)):

1. Fügen Sie Verweise auf Drittanbieter-Bibliotheken zum `<ItemGroup>`-Teil Ihrer *CSPROJ*-Datei hinzu. Der folgende `<ItemGroup>`-Abschnitt verwendet Json.NET als Drittanbieter-Bibliothek.

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
    ```

1. Wenn noch nicht geschehen, laden Sie das NuGet-Paket mit der Drittanbieter-Abhängigkeit auf Ihr System herunter. Führen Sie nach dem Hinzufügen der Abhängigkeit den `dotnet restore`-Befehl aus ([siehe Hinweis](#dotnet-restore-note)), um die Abhängigkeit für Ihre App zur Verfügung zu stellen. Da die Abhängigkeit zum Zeitpunkt der Veröffentlichung aus dem lokalen NuGet-Cache aufgelöst wurde, muss sie auf Ihrem System verfügbar sein.

Es folgt die vollständige *CSPROJ*-Datei dieses Projekts:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

Wenn Sie Ihre Anwendung bereitstellen, sind die Drittanbieter-Abhängigkeiten, die in Ihrer Anwendung verwendet werden, auch in Ihren Anwendungsdateien enthalten. Drittanbieter-Bibliotheken müssen nicht auf dem System vorhanden sein, auf dem die Anwendung ausgeführt wird.

Beachten Sie, dass Sie eine eigenständige Bereitstellung mit einer Drittanbieter-Bibliothek nur auf von dieser Bibliothek unterstützten Plattformen bereitstellen können. Dies ist ähnlich, als wenn Sie über Drittanbieter-Abhängigkeiten mit nativen Abhängigkeiten in einer Framework-abhängigen Bereitstellung verfügen, wobei die nativen Abhängigkeiten mit der Plattform kompatibel sein müssen, auf der die App bereitgestellt wird.

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

# <a name="see-also"></a>Siehe auch

[.NET Core Anwendungsbereitstellung](index.md)   
[.NET Core Runtime-ID (RID)-Katalog](../rid-catalog.md)   

