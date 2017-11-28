---
title: .NET Core-App-Bereitstellung mit Visual Studio
description: Erfahren Sie mehr zur .NET Core-App-Bereitstellung mit Visual Studio
keywords: .NET, .NET Core, .NET Core Bereitstellung
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 01049a21-fd50-4419-9ab2-0e4a2e091050
ms.openlocfilehash: 884ecb110b4168c6dc1e4c664de1dcb8db3734c5
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="deploying-net-core-apps-with-visual-studio"></a>Bereitstellen von .NET Core-Apps mit Visual Studio

Sie können eine .NET Core-Anwendung entweder als *Framework-abhängige Bereitstellung* bereitstellen, was die Binärdateien Ihrer Anwendung einschließt, jedoch von Präsenz von .NET Core auf dem Zielsystem abhängt, oder als *eigenständige Bereitstellung*,die jeweils Ihre Anwendung sowie .NET Core-Binärdateien einschließt. Einen Überblick über die Bereitstellung von .NET Core-Anwendungen finden Sie unter [.NET Core Anwendungsbereitstellung](index.md).

Die folgenden Abschnitte zeigen, wie Sie Microsoft Visual Studio zum Erstellen der folgenden Bereitstellungen verwenden:

- Framework-abhängige Bereitstellung
- Framework-abhängige Bereitstellung mit Drittanbieterabhängigkeiten
- Eigenständige Bereitstellung
- Eigenständige Bereitstellung mit Drittanbieterabhängigkeiten

Informationen zur Verwendung von Visual Studio zur Entwicklung von .NET Core-Anwendungen finden Sie unter [Voraussetzungen für .NET Core unter Windows](../windows-prerequisites.md#prerequisites-with-visual-studio-2017).

## <a name="framework-dependent-deployment"></a>Framework-abhängige Bereitstellung

Die Bereitstellung einer Framework-abhängigen Bereitstellung ohne Drittanbieter-Abhängigkeiten umfasst nur das Erstellen, Testen und Veröffentlichen der Anwendung. Ein einfaches, in C# geschriebenes Beispiel veranschaulicht den Prozess.  

1. Erstellen eines Projekts

   Wählen Sie **Datei** > **Neu** > **Projekt** aus. Wählen Sie im Dialogfeld **Neues Projekt** **.NET Core** im Bereich „Projekttypen“ **Installiert** aus, und wählen Sie die Vorlage **Konsolen-App (.NET Core)** im mittleren Bereich aus. Geben Sie im Textfeld **Name** einen Projektnamen ein, z.B. „FDD“. Klicken Sie auf die Schaltfläche **OK**.

1. Fügen Sie den Quellcode der Anwendung hinzu.

   Öffnen Sie die *Program.cs*-Datei im Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code. Der Benutzer wird zur Texteingabe aufgefordert, und die einzelnen Wörter, die vom Benutzer eingegeben wurden, werden angezeigt. Der reguläre Ausdruck `\w+` wird verwendet, um Wörter im Eingabetext zu trennen.

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. Erstellen Sie ein Debugbuild Ihrer App.

   Wählen Sie **Erstellen** > **Projektmappe erstellen** aus. Sie können auch das Debugbuild Ihrer Anwendung erstellen und ausführen, indem Sie **Debuggen** > **Debugging starten** auswählen.

1. Stellen Sie Ihre App bereit.

   Nachdem Sie die Anwendung debuggt und getestet haben, erstellen Sie die Dateien, die mit Ihrer Anwendung bereitgestellt werden. Um eine Veröffentlichung über Visual Studio durchzuführen, tun Sie Folgendes:

      1. Ändern Sie die Projektmappenkonfiguration von **Debuggen** zu **Freigabe** auf der Symbolleiste, um eine Releaseversion (anstatt eine Debugversion) Ihrer App zu erstellen.

      1. Führen Sie auf dem Projekt (nicht in der Projektmappe) im **Projektmappen-Explorer** einen Rechtsklick aus, und wählen Sie **Veröffentlichen** aus.

      1. Wählen Sie auf der Registerkarte **Veröffentlichen** **Veröffentlichen** aus. Visual Studio schreibt die Dateien, die Ihre Anwendung enthalten, in das lokale Dateisystem.

      1. Die Registerkarte **Veröffentlichen** zeigt nun ein einzelnes Profil an: **FolderProfile**. Die Konfigurationseinstellungen des Profils werden im Abschnitt **Zusammenfassung** der Registerkarte gezeigt.

   Die resultierenden Dateien werden in ein Verzeichnis namens `PublishOutput` platziert, das sich in einem Unterverzeichnis des *\bin\release*-Unterverzeichnis Ihres Projekts befindet.

Der Veröffentlichungsprozess gibt zusammen mit den Dateien Ihrer Anwendung eine Programmdatenbankdatei (.pdb) aus, die Debuginformationen über Ihre Anwendung enthält. Die Datei ist vornehmlich für das Debuggen von Ausnahmen nützlich. Sie können sich auch dazu entschließen, sie nicht mit den Dateien Ihrer Anwendung zu packen. Jedoch sollten Sie sie für den Fall speichern, dass Sie das Releasebuild Ihrer App debuggen möchten.

Stellen Sie den vollständige Satz von Anwendungsdateien so bereit, wie Sie möchten. Sie können sie z.B. in einer ZIP-Datei verpacken, und einen einfachen `copy`-Befehl verwenden, oder sie mit jedem Installationspaket Ihrer Wahl bereitstellen. Sobald die Anwendung installiert ist, können Benutzer sie mithilfe des `dotnet`-Befehls ausführen und den Dateinamen der Anwendung bereitstellen, z.B. `dotnet fdd.dll`.

Das Installationsprogramm sollte zusätzlich zu den Binärdateien der Anwendung das freigegebene Framework-Installationsprogramm bündeln, oder als erforderliche Komponente im Rahmen der Anwendungsinstallation überprüfen.  Die Installation des gemeinsam genutzten Frameworks erfordert Administrator-/Root-Zugriff, da es sich um eine computerweite Installation handelt.

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a>Framework-abhängige Bereitstellung mit Drittanbieterabhängigkeiten

Die Bereitstellung einer Framework-abhängigen Bereitstellung mit mindestens einer Drittanbieterabhängigkeit erfordert, dass Abhängigkeiten für Ihr Projekt verfügbar sind. Die folgenden Schritte müssen noch durchgeführt werden, bevor Sie Ihre App erstellen können:

1. Verwenden Sie den **NuGet-Paket-Manager**, um einem NuGet-Paket einen Verweis für Ihr Projekt hinzuzufügen. Falls das Paket noch nicht auf Ihrem System verfügbar ist, installieren Sie es. Wählen Sie zum Öffnen des Paket-Managers **Tools** > **NuGet-Paket-Manager** > **NuGet-Pakete für Projektmappe verwalten** aus.

1. Bestätigen Sie, dass `Newtonsoft.Json` auf Ihrem System installiert ist. Falls nicht, installieren Sie es. Die Registerkarte **Installiert** listet NuGet-Pakete auf, die auf Ihrem System installiert sind. Wenn `Newtonsoft.Json` hier nicht aufgelistet ist, wählen Sie die Registerkarte **Durchsuchen** aus, und geben Sie „Newtonsoft.Json“ in das Suchfeld ein. Wählen Sie `Newtonsoft.Json` aus, und wählen Sie im rechten Bereich Ihre Projekt, bevor Sie auf **Installieren** klicken.

1. Wenn `Newtonsoft.Json` bereits auf Ihrem System installiert ist, fügen Sie es Ihrem Projekt hinzu, indem Sie Ihr Projekt im rechten Bereich der Registerkarte **Pakete für Projektmappe verwalten** auswählen.

Beachten Sie, dass eine Framework-abhängige Bereitstellung mit Drittanbieter-Abhängigkeiten nur so tragbar wie ihre Drittanbieter-Abhängigkeiten ist. Falls eine Drittanbieter-Bibliothek nur macOS unterstützen sollte, so wird die Anwendung nicht auf Windows-Systeme übertragbar sein. Dies kann geschehen, wenn die Drittanbieter-Abhängigkeit selbst vom nativen Code abhängt. Ein gutes Beispiel dafür ist der [Kestrel-Server](http://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), der eine native Abhängigkeit unter [libuv](https://github.com/libuv/libuv) erfordert. Wenn bei dieser Art von Drittanbieter-Abhängigkeit eine FDD für eine Anwendung erstellt wird, enthält die veröffentlichte Ausgabe einen Ordner für jede [Runtime-ID (RID)](../rid-catalog.md), die die native Abhängigkeit unterstützt (und im NuGet-Paket vorhanden ist).

## <a name="simpleSelf"></a> Eigenständige Bereitstellung mit Drittanbieterabhängigkeiten

Das Bereitstellen einer eigenständigen Bereitstellung ohne Abhängigkeiten von Drittanbietern umfasst das Erstellen des Projekts, das Ändern der *CSPROJ*-Datei sowie das Erstellen, Testen und Veröffentlichen der Anwendung. Ein einfaches, in C# geschriebenes Beispiel veranschaulicht den Prozess. 

1. Erstellen eines Projekts

   Wählen Sie **Datei** > **Neu** > **Projekt** aus. Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** **.NET Core** im Bereich „Projekttypen“ **Installiert** aus, und wählen Sie die Vorlage **Konsolen-App (.NET Core)** im mittleren Bereich aus. Geben Sie im Textfeld **Name** einen Projektnamen ein, z.B. „SCD“, und klicken Sie auf die Schaltfläche **OK**.

1. Fügen Sie den Quellcode der Anwendung hinzu.

   Öffnen Sie die *Program.cs*-Datei in einem Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code. Der Benutzer wird zur Texteingabe aufgefordert, und die einzelnen Wörter, die vom Benutzer eingegeben wurden, werden angezeigt. Der reguläre Ausdruck `\w+` wird verwendet, um Wörter im Eingabetext zu trennen.

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. Definieren Sie die Zielplattformen für Ihre App.

   1. Führen Sie auf Ihrem Projekt (nicht in der Projektmappe) im **Projektmappen-Explorer** einen Rechtsklick aus, und wählen Sie **Edit SCD.csproj** (SCD.csproj bearbeiten) aus.

   1. Erstellen Sie das Tag `<RuntimeIdentifiers>` im Abschnitt `<PropertyGroup>` Ihrer Datei *csproj*, der die Plattformen Ihrer Anwendungsziele definiert und die Runtime-ID jeder Zielplattform angibt. Beachten Sie, dass Sie auch ein Semikolon hinzufügen müssen, um die RIDs trennen. Sie finden eine RID-Liste im [RID-Katalog](../rid-catalog.md). 

   Das folgende Beispiel gibt an, dass die Anwendung unter den Betriebssystemen Windows 10 (64-Bit) und OS X 10.11 (64-Bit) ausgeführt wird.

```xml
<PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
</PropertyGroup>
```
   Beachten Sie, dass das Element `<RuntimeIdentifiers>` jedem `<PropertyGroup>`-Element in Ihrer Datei *CSPROJ* hinzugefügt werden kann. Eine vollständige *CSPROJ*-Beispieldatei wird später in diesem Abschnitt angezeigt.

1. Erstellen Sie ein Debugbuild Ihrer App.

   Wählen Sie **Erstellen** > **Projektmappe erstellen** aus. Sie können auch das Debugbuild Ihrer Anwendung erstellen und ausführen, indem Sie **Debuggen** > **Debugging starten** auswählen.

1. Veröffentlichen Sie die App.

   Nachdem Sie das Programm debuggt und getestet haben, erstellen Sie die Dateien, die mit Ihrer App für jede Zielplattform bereitgestellt werden sollen.

   Um eine Veröffentlichung Ihrer App über Visual Studio durchzuführen, tun Sie Folgendes:

      1. Ändern Sie die Projektmappenkonfiguration von **Debuggen** zu **Freigabe** auf der Symbolleiste, um eine Releaseversion (anstatt eine Debugversion) Ihrer App zu erstellen.

      1. Führen Sie auf dem Projekt (nicht in der Projektmappe) im **Projektmappen-Explorer** einen Rechtsklick aus, und wählen Sie **Veröffentlichen** aus. 

      1. Wählen Sie auf der Registerkarte **Veröffentlichen** **Veröffentlichen** aus. Visual Studio schreibt die Dateien, die Ihre Anwendung enthalten, in das lokale Dateisystem.

      1. Die Registerkarte **Veröffentlichen** zeigt nun ein einzelnes Profil an: **FolderProfile**. Die Konfigurationseinstellungen des Profils werden im Abschnitt **Zusammenfassung** der Registerkarte gezeigt. **Ziellaufzeit** identifiziert, welche Laufzeit veröffentlicht wurde; **Zielort** identifiziert, wo die Dateien für die eigenständige Bereitstellung geschrieben wurden.

      1. Visual Studio schreibt standardmäßig alle veröffentlichten Dateien in ein einzelnes Verzeichnis. Der Einfachheit halber ist es am besten, separate Profile für jede Ziellaufzeit zu erstellen und veröffentlichte Dateien in einem plattformspezifischen Verzeichnis zu platzieren. Dafür muss ein separates Veröffentlichungsprofil für jede Zielplattform erstellt werden. Erstellen Sie nun die Anwendung für jede Plattform neu, indem Sie Folgendes tun:

         1. Wählen Sie **Neues Profil erstellen** im Dialogfeld **Veröffentlichen** aus.

         1. Ändern Sie im Dialogfeld **Veröffentlichungsziel auswählen** den Speicherort **Ordner auswählen** in *bin\Release\PublishOutput\win10-x64*. Klicken Sie auf **OK**.

         1. Wählen Sie das neue Profil (**FolderProfile1**) in der Liste der Profile aus, und stellen Sie sicher, dass die **Ziellaufzeit** `win10-x64` ist. Falls nicht, wählen Sie **Einstellungen** aus. Ändern Sie im Dialogfeld **Profileinstellungen** die **Ziellaufzeit** in `win10-x64`, und klicken Sie auf **Speichern**. Wählen Sie andernfalls **Abbrechen** aus.

         1. Wählen Sie **Veröffentlichen** aus, um Ihre App für 64-Bit-Windows 10-Plattformen zu veröffentlichen.

         1. Arbeiten Sie erneut die vorherigen Schritte durch, um ein Profil für die `osx.10.11-x64`-Plattform zu erstellen. Der **Zielort** ist *bin\Release\PublishOutput\osx.10.11-x64*, und die **Ziellaufzeit** ist `osx.10.11-x64`. Der Name, den Visual Studio diesem Profil zuweist, ist **FolderProfile2**.

      Beachten Sie, dass jeder Zielort den vollständigen Dateisatz enthält (Dateien Ihrer Anwendung und alle .NET Core-Dateien), der zum Starten Ihrer Anwendung erforderlich ist.

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

Das Bereitstellen einer eigenständigen Bereitstellung mit einer oder mehreren Drittanbieter-Abhängigkeiten umfasst das Hinzufügen der Drittanbieter-Abhängigkeit: Die folgenden Schritte müssen noch durchgeführt werden, bevor Sie Ihre App erstellen können:

1. Verwenden Sie den **NuGet-Paket-Manager**, um einem NuGet-Paket einen Verweis für Ihr Projekt hinzuzufügen. Falls das Paket noch nicht auf Ihrem System verfügbar ist, installieren Sie es. Wählen Sie zum Öffnen des Paket-Managers **Tools** > **NuGet-Paket-Manager** > **NuGet-Pakete für Projektmappe verwalten** aus.

1. Bestätigen Sie, dass `Newtonsoft.Json` auf Ihrem System installiert ist. Falls nicht, installieren Sie es. Die Registerkarte **Installiert** listet NuGet-Pakete auf, die auf Ihrem System installiert sind. Wenn `Newtonsoft.Json` hier nicht aufgelistet ist, wählen Sie die Registerkarte **Durchsuchen** aus, und geben Sie „Newtonsoft.Json“ in das Suchfeld ein. Wählen Sie `Newtonsoft.Json` aus, und wählen Sie im rechten Bereich Ihre Projekt, bevor Sie auf **Installieren** klicken.

1. Wenn `Newtonsoft.Json` bereits auf Ihrem System installiert ist, fügen Sie es Ihrem Projekt hinzu, indem Sie Ihr Projekt im rechten Bereich der Registerkarte **Pakete für Projektmappe verwalten** auswählen.

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

Beachten Sie, dass Sie eine eigenständige Bereitstellung mit einer Drittanbieter-Bibliothek nur auf von dieser Bibliothek unterstützten Plattformen bereitstellen können. Dies ist ähnlich, als wenn Sie über Drittanbieter-Abhängigkeiten mit nativen Abhängigkeiten in Ihrer Framework-abhängigen Bereitstellung verfügen, wobei die nativen Abhängigkeiten nicht auf der Zielplattform vorhanden sind, es sei denn, sie wurden dort zuvor installiert.

# <a name="see-also"></a>Siehe auch
[.NET Core Anwendungsbereitstellung](index.md)   
[.NET Core Runtime-ID (RID)-Katalog](../rid-catalog.md)   
