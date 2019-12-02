---
title: Bereitstellen von .NET Core-Apps mit Visual Studio
description: Erfahren Sie, wie Sie eine .NET Core-App mit Visual Studio bereitstellen.
ms.date: 09/03/2018
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: f80b483fedc600a1e1a48d36ce9b7b95c6de9f27
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428895"
---
# <a name="deploy-net-core-apps-with-visual-studio"></a>Bereitstellen von .NET Core-Apps mit Visual Studio

Sie können eine .NET Core-Anwendung entweder als *Framework-abhängige Bereitstellung* bereitstellen, was die Binärdateien Ihrer Anwendung einschließt, jedoch von Präsenz von .NET Core auf dem Zielsystem abhängt, oder als *eigenständige Bereitstellung*,die jeweils Ihre Anwendung sowie .NET Core-Binärdateien einschließt. Einen Überblick über die Bereitstellung von .NET Core-Anwendungen finden Sie unter [.NET Core Anwendungsbereitstellung](index.md).

Die folgenden Abschnitte zeigen, wie Sie Microsoft Visual Studio zum Erstellen der folgenden Bereitstellungen verwenden:

- Framework-abhängige Bereitstellung
- Framework-abhängige Bereitstellung mit Drittanbieterabhängigkeiten
- Eigenständige Bereitstellung
- Eigenständige Bereitstellung mit Drittanbieterabhängigkeiten

Informationen zur Verwendung von Visual Studio für die Entwicklung von .NET Core-Anwendungen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](../install/dependencies.md?tabs=netcore30&pivots=os-windows).

## <a name="framework-dependent-deployment"></a>Framework-abhängige Bereitstellung

Die Bereitstellung einer Framework-abhängigen Bereitstellung ohne Drittanbieter-Abhängigkeiten umfasst nur das Erstellen, Testen und Veröffentlichen der Anwendung. Ein einfaches, in C# geschriebenes Beispiel veranschaulicht den Prozess.  

1. Erstellen eines Projekts

   Wählen Sie **Datei** > **Neu** > **Projekt** aus. Erweitern Sie im Dialogfeld **Neues Projekt** die Projektkategorien Ihrer Programmiersprache (C# oder Visual Basic) im Bereich **Installiert**, wählen Sie **.NET Core** aus, und wählen Sie dann im mittleren Bereich die Vorlage **Konsolenanwendung (.NET Core)** aus. Geben Sie im Textfeld **Name** einen Projektnamen ein, z.B. „FDD“. Klicken Sie auf die Schaltfläche **OK**.

1. Fügen Sie den Quellcode der Anwendung hinzu.

   Öffnen Sie die Datei *Program.cs* oder *Program.vb* im Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code. Der Benutzer wird zur Texteingabe aufgefordert, und die einzelnen Wörter, die vom Benutzer eingegeben wurden, werden angezeigt. Der reguläre Ausdruck `\w+` wird verwendet, um Wörter im Eingabetext zu trennen.

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]

1. Erstellen Sie ein Debugbuild Ihrer App.

   Wählen Sie **Erstellen** > **Projektmappe erstellen** aus. Sie können auch das Debugbuild Ihrer Anwendung erstellen und ausführen, indem Sie **Debuggen** > **Debugging starten** auswählen.

1. Stellen Sie Ihre App bereit.

   Nachdem Sie die Anwendung debuggt und getestet haben, erstellen Sie die Dateien, die mit Ihrer Anwendung bereitgestellt werden. Um eine Veröffentlichung über Visual Studio durchzuführen, tun Sie Folgendes:

      1. Ändern Sie die Projektmappenkonfiguration von **Debuggen** zu **Freigabe** auf der Symbolleiste, um eine Releaseversion (anstatt eine Debugversion) Ihrer App zu erstellen.

      1. Führen Sie auf dem Projekt (nicht in der Projektmappe) im **Projektmappen-Explorer** einen Rechtsklick aus, und wählen Sie **Veröffentlichen** aus.

      1. Wählen Sie auf der Registerkarte **Veröffentlichen** **Veröffentlichen** aus. Visual Studio schreibt die Dateien, die Ihre Anwendung enthalten, in das lokale Dateisystem.

      1. Die Registerkarte **Veröffentlichen** zeigt nun ein einzelnes Profil an: **FolderProfile**. Die Konfigurationseinstellungen des Profils werden im Abschnitt **Zusammenfassung** der Registerkarte gezeigt.

   Die resultierenden Dateien werden unter Windows und `publish` auf Unix-Systemen in ein Verzeichnis namens `Publish` platziert, das sich in einem Unterverzeichnis des Unterverzeichnisses *.\bin\release\netcoreapp2.1* Ihres Projekts befindet.

Der Veröffentlichungsprozess gibt zusammen mit den Dateien Ihrer Anwendung eine Programmdatenbankdatei (.pdb) aus, die Debuginformationen über Ihre Anwendung enthält. Die Datei ist vornehmlich für das Debuggen von Ausnahmen nützlich. Sie können sich auch dazu entschließen, sie nicht mit den Dateien Ihrer Anwendung zu packen. Jedoch sollten Sie sie für den Fall speichern, dass Sie das Releasebuild Ihrer App debuggen möchten.

Stellen Sie den vollständige Satz von Anwendungsdateien so bereit, wie Sie möchten. Sie können sie z.B. in einer ZIP-Datei verpacken, und einen einfachen `copy`-Befehl verwenden, oder sie mit jedem Installationspaket Ihrer Wahl bereitstellen. Sobald die Anwendung installiert ist, können Benutzer sie mithilfe des `dotnet`-Befehls ausführen und den Dateinamen der Anwendung bereitstellen, z.B. `dotnet fdd.dll`.

Das Installationsprogramm sollte zusätzlich zu den Binärdateien der Anwendung das freigegebene Framework-Installationsprogramm bündeln, oder als erforderliche Komponente im Rahmen der Anwendungsinstallation überprüfen.  Die Installation des gemeinsam genutzten Frameworks erfordert Administrator-/Root-Zugriff, da es sich um eine computerweite Installation handelt.

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a>Framework-abhängige Bereitstellung mit Drittanbieterabhängigkeiten

Die Bereitstellung einer Framework-abhängigen Bereitstellung mit mindestens einer Drittanbieterabhängigkeit erfordert, dass Abhängigkeiten für Ihr Projekt verfügbar sind. Die folgenden Schritte müssen noch durchgeführt werden, bevor Sie Ihre App erstellen können:

1. Verwenden Sie den **NuGet-Paket-Manager**, um einem NuGet-Paket einen Verweis für Ihr Projekt hinzuzufügen. Falls das Paket noch nicht auf Ihrem System verfügbar ist, installieren Sie es. Wählen Sie zum Öffnen des Paket-Managers **Tools** > **NuGet-Paket-Manager** > **NuGet-Pakete für Projektmappe verwalten** aus.

1. Bestätigen Sie, dass Ihre Drittanbieterabhängigkeiten (z. B. `Newtonsoft.Json`) auf Ihrem System installiert sind. Falls dies nicht der Fall ist, installieren Sie sie. Die Registerkarte **Installiert** listet NuGet-Pakete auf, die auf Ihrem System installiert sind. Wenn `Newtonsoft.Json` hier nicht aufgelistet ist, wählen Sie die Registerkarte **Durchsuchen** aus, und geben Sie „Newtonsoft.Json“ in das Suchfeld ein. Wählen Sie `Newtonsoft.Json` aus, und wählen Sie im rechten Bereich Ihre Projekt, bevor Sie auf **Installieren** klicken.

1. Wenn `Newtonsoft.Json` bereits auf Ihrem System installiert ist, fügen Sie es Ihrem Projekt hinzu, indem Sie Ihr Projekt im rechten Bereich der Registerkarte **Pakete für Projektmappe verwalten** auswählen.

Beachten Sie, dass eine Framework-abhängige Bereitstellung mit Drittanbieter-Abhängigkeiten nur so tragbar wie ihre Drittanbieter-Abhängigkeiten ist. Falls eine Drittanbieter-Bibliothek nur macOS unterstützen sollte, so wird die Anwendung nicht auf Windows-Systeme übertragbar sein. Dies kann geschehen, wenn die Drittanbieter-Abhängigkeit selbst vom nativen Code abhängt. Ein gutes Beispiel dafür ist der [Kestrel-Server](https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), der eine native Abhängigkeit unter [libuv](https://github.com/libuv/libuv) erfordert. Wenn bei dieser Art von Drittanbieter-Abhängigkeit eine FDD für eine Anwendung erstellt wird, enthält die veröffentlichte Ausgabe einen Ordner für jede [Runtime-ID (RID)](../rid-catalog.md), die die native Abhängigkeit unterstützt (und im NuGet-Paket vorhanden ist).

## <a name="simpleSelf"></a> Eigenständige Bereitstellung mit Drittanbieterabhängigkeiten

Das Bereitstellen einer eigenständigen Bereitstellung ohne Abhängigkeiten von Drittanbietern umfasst das Erstellen des Projekts, das Ändern der *CSPROJ*-Datei sowie das Erstellen, Testen und Veröffentlichen der Anwendung. Ein einfaches, in C# geschriebenes Beispiel veranschaulicht den Prozess. Zunächst erstellen, codieren und testen Sie Ihr Projekt wie eine Framework-abhängige Bereitstellung:

1. Erstellen eines Projekts

   Wählen Sie **Datei** > **Neu** > **Projekt** aus. Erweitern Sie im Dialogfeld **Neues Projekt** die Projektkategorien Ihrer Programmiersprache (C# oder Visual Basic) im Bereich **Installiert**, wählen Sie **.NET Core** aus, und wählen Sie dann im mittleren Bereich die Vorlage **Konsolenanwendung (.NET Core)** aus. Geben Sie im Textfeld **Name** einen Projektnamen ein, z.B. „SCD“, und klicken Sie auf die Schaltfläche **OK**.

1. Fügen Sie den Quellcode der Anwendung hinzu.

   Öffnen Sie die Datei *Program.cs* oder *Program.vb* in Ihrem Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code. Der Benutzer wird zur Texteingabe aufgefordert, und die einzelnen Wörter, die vom Benutzer eingegeben wurden, werden angezeigt. Der reguläre Ausdruck `\w+` wird verwendet, um Wörter im Eingabetext zu trennen.

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]

1. Bestimmen Sie, ob Sie den invarianten Globalisierungsmodus verwenden möchten.

   Insbesondere, wenn Ihre Anwendung für Linux konzipiert ist, können Sie die Gesamtgröße Ihrer Bereitstellung reduzieren, indem Sie den [invarianten Globalisierungsmodus](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md) verwenden. Der invariante Globalisierungsmodus eignet sich für Anwendungen, die nicht für den globalen Einsatz ausgelegt sind, und Formatierungskonventionen, Groß-/Kleinschreibungskonventionen, Zeichenfolgenvergleiche und Sortierreihenfolgen der [invarianten Kultur](xref:System.Globalization.CultureInfo.InvariantCulture) verwenden können.

   Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf Ihr Projekt (nicht auf die Projektmappe), und klicken Sie auf **SCD.csproj bearbeiten** oder **SCD.vbproj bearbeiten**. Fügen Sie der Datei dann die folgenden hervorgehobenen Zeilen hinzu:

   [!code-xml[globalization-invariant-mode](~/samples/snippets/core/deploying/xml/invariant.csproj?highlight=6-8)]

1. Erstellen Sie einen Debugbuild Ihrer Anwendung.

   Wählen Sie **Erstellen** > **Projektmappe erstellen** aus. Sie können auch das Debugbuild Ihrer Anwendung erstellen und ausführen, indem Sie **Debuggen** > **Debugging starten** auswählen. Mit diesem Schritt können Sie beim Debuggen Probleme mit Ihrer Anwendung identifizieren, die auftreten, wenn sie auf Ihrer Hostplattform ausgeführt wird. Sie müssen dies dennoch auf jeder Zielplattform testen.

   Wenn Sie den invarianten Globalisierungsmodus aktiviert haben, stellen Sie unbedingt sicher, ob das Fehlen von kulturabhängigen Daten für die Anwendung geeignet ist.

Sobald Sie das Debuggen abgeschlossen haben, können Sie Ihre eigenständige Bereitstellung veröffentlichen:

<!-- markdownlint-disable MD025 -->

# <a name="visual-studio-156-and-earliertabvs156"></a>[Visual Studio 15.6 und frühere Versionen](#tab/vs156)

Nachdem Sie das Programm debuggt und getestet haben, erstellen Sie die Dateien, die mit Ihrer App für jede Zielplattform bereitgestellt werden sollen.

Um eine Veröffentlichung Ihrer App über Visual Studio durchzuführen, tun Sie Folgendes:

1. Definieren Sie die Zielplattformen für Ihre App.

   1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf Ihr Projekt (nicht auf die Projektmappe), und wählen Sie **SCD.csproj bearbeiten** aus.

   1. Erstellen Sie das Tag `<RuntimeIdentifiers>` im Abschnitt `<PropertyGroup>` Ihrer Datei *csproj*, der die Plattformen Ihrer Anwendungsziele definiert und die Runtime-ID jeder Zielplattform angibt. Beachten Sie, dass Sie auch ein Semikolon hinzufügen müssen, um die RIDs trennen. Sie finden eine RID-Liste im [RID-Katalog](../rid-catalog.md).

   Das folgende Beispiel gibt an, dass die Anwendung unter den Betriebssystemen Windows 10 (64-Bit) und OS X 10.11 (64-Bit) ausgeführt wird.

   ```xml
   <PropertyGroup>
      <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
   </PropertyGroup>
   ```

   Beachten Sie, dass das Element `<RuntimeIdentifiers>` jedem `<PropertyGroup>`-Element in Ihrer Datei *CSPROJ* hinzugefügt werden kann. Eine vollständige *CSPROJ*-Beispieldatei wird später in diesem Abschnitt angezeigt.

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
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

# <a name="visual-studio-157-and-latertabvs157"></a>[Visual Studio 15.7 und höhere Versionen](#tab/vs157)

Nachdem Sie das Programm debuggt und getestet haben, erstellen Sie die Dateien, die mit Ihrer App für jede Zielplattform bereitgestellt werden sollen. Dafür muss ein separates Profil für jede Zielplattform erstellt werden.

Führen Sie die folgenden Schritte für jede Zielplattform der Anwendung durch:

1. Erstellen Sie ein Profil für Ihre Zielplattform.

   Wenn dies das erste Profil ist, das Sie erstellen, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt (nicht auf die Projektmappe), und wählen Sie **Veröffentlichen** aus.

   Wenn Sie bereits ein Profil erstellt haben, klicken Sie mit der rechten Maustaste auf das Projekt, um das Dialogfeld **Veröffentlichen** zu öffnen, sofern dies noch nicht geöffnet ist. Klicken Sie dann auf **Neues Profil**.

   Das Dialogfeld **Veröffentlichungsziel auswählen** wird geöffnet.
  
1. Wählen Sie aus, wo Ihre Anwendung von Visual Studio veröffentlicht werden soll.

   Wenn Sie die Anwendung auf einer einzigen Plattform veröffentlichen, können Sie den Standardwert im Textfeld **Ordner auswählen** bestätigen. Die frameworkabhängige Bereitstellung Ihrer Anwendung wird dann im Verzeichnis *\<Projektverzeichnis>\bin\Release\netcoreapp2.1\publish* veröffentlicht.

   Wenn Sie die Anwendung auf mehreren Plattformen veröffentlichen, fügen Sie eine Zeichenfolge an, mit der die Zielplattform identifiziert wird. Wenn Sie beispielsweise die Zeichenfolge „linux“ an den Dateipfad anfügen, veröffentlicht Visual Studio die Framework-abhängige Bereitstellung Ihrer Anwendung im Verzeichnis *\<Projektverzeichnis>\bin\Release\netcoreapp2.1\publish\linux*.

1. Erstellen Sie das Profil, indem Sie auf das Symbol für die Dropdownliste neben der Schaltfläche **Veröffentlichen** klicken und die Option **Profil erstellen** auswählen. Klicken Sie anschließend auf **Profil erstellen**, um das Profil zu erstellen.

1. Geben Sie an, dass Sie eine eigenständige Bereitstellung veröffentlichen, und definieren Sie eine Zielplattform für die Anwendung.

   1. Klicken Sie im Dialogfeld **Veröffentlichen** auf den Link **Konfigurieren**, um das Dialogfeld **Profileinstellungen** zu öffnen.

   1. Wählen Sie **Eigenständig** im Listenfeld **Bereitstellungsmodus** aus.

   1. Wählen Sie im Listenfeld **Ziellaufzeit** eine der Zielplattformen Ihrer Anwendung aus.

   1. Klicken Sie auf **Speichern**, um die Änderungen zu bestätigen und das Dialogfeld zu schließen.

1. Benennen Sie Ihr Profil.

   1. Klicken Sie auf **Aktionen** > **Profil umbenennen**, um das Profil zu benennen.

   2. Geben Sie dem Profil einen Namen, mit dem die Zielplattform identifiziert werden kann, und klicken Sie dann auf \**Speichern*.

Wiederholen Sie diese Schritte, um die zusätzlichen Zielplattformen Ihrer Anwendung zu definieren.

Da Sie die Profile nun konfiguriert haben, können Sie Ihre Anwendung nun veröffentlichen. Gehen Sie dazu wie folgt vor:

   1. Wenn das Fenster **Veröffentlichen** nicht geöffnet ist, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt (nicht auf die Projektmappe), und wählen Sie **Veröffentlichen** aus.

   2. Wählen Sie das Profil aus, das Sie veröffentlichen möchten, und klicken Sie dann auf **Veröffentlichen**. Wiederholen Sie diese Schritte für alle zu veröffentlichenden Profile.

   Beachten Sie, dass jeder Zielort (für das Beispiel bin\release\netcoreapp2.1\publish\\*Profilname*) alle Dateien enthält (Dateien Ihrer Anwendung und alle .NET Core-Dateien), die zum Starten Ihrer Anwendung erforderlich sind.

Der Veröffentlichungsprozess gibt zusammen mit den Dateien Ihrer Anwendung eine Programmdatenbankdatei (.pdb) aus, die Debuginformationen über Ihre Anwendung enthält. Die Datei ist vornehmlich für das Debuggen von Ausnahmen nützlich. Sie können sich auch dazu entschließen, sie nicht mit den Dateien Ihrer Anwendung zu packen. Jedoch sollten Sie sie für den Fall speichern, dass Sie das Releasebuild Ihrer App debuggen möchten.

Stellen Sie die veröffentlichen Dateien in einer beliebigen Weise bereit. Sie können sie z.B. in einer ZIP-Datei verpacken, und einen einfachen `copy`-Befehl verwenden, oder sie mit jedem Installationspaket Ihrer Wahl bereitstellen.

Es folgt die vollständige *CSPROJ*-Datei dieses Projekts:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
</Project>
```

Darüber hinaus erstellt Visual Studio ein separates Veröffentlichungsprofil („\*.pubxml“) für jede Zielplattform. Zum Beispiel wird die Datei für das Linux-Profil („linux.pubxml“) wie folgt angezeigt:

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--
https://go.microsoft.com/fwlink/?LinkID=208121. 
-->
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <PublishProtocol>FileSystem</PublishProtocol>
    <Configuration>Release</Configuration>
    <Platform>Any CPU</Platform>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <PublishDir>bin\Release\netcoreapp2.1\publish\linux</PublishDir>
    <RuntimeIdentifier>win-x86</RuntimeIdentifier>
    <SelfContained>true</SelfContained>
    <_IsPortable>false</_IsPortable>
  </PropertyGroup>
</Project>
```

---

## <a name="self-contained-deployment-with-third-party-dependencies"></a>Eigenständige Bereitstellung mit Drittanbieterabhängigkeiten

Das Bereitstellen einer eigenständigen Bereitstellung mit einer oder mehreren Drittanbieter-Abhängigkeiten umfasst das Hinzufügen der Drittanbieter-Abhängigkeit: Die folgenden Schritte müssen noch durchgeführt werden, bevor Sie Ihre App erstellen können:

1. Verwenden Sie den **NuGet-Paket-Manager**, um einem NuGet-Paket einen Verweis für Ihr Projekt hinzuzufügen. Falls das Paket noch nicht auf Ihrem System verfügbar ist, installieren Sie es. Wählen Sie zum Öffnen des Paket-Managers **Tools** > **NuGet-Paket-Manager** > **NuGet-Pakete für Projektmappe verwalten** aus.

1. Bestätigen Sie, dass Ihre Drittanbieterabhängigkeiten (z. B. `Newtonsoft.Json`) auf Ihrem System installiert sind. Falls dies nicht der Fall ist, installieren Sie sie. Die Registerkarte **Installiert** listet NuGet-Pakete auf, die auf Ihrem System installiert sind. Wenn `Newtonsoft.Json` hier nicht aufgelistet ist, wählen Sie die Registerkarte **Durchsuchen** aus, und geben Sie „Newtonsoft.Json“ in das Suchfeld ein. Wählen Sie `Newtonsoft.Json` aus, und wählen Sie im rechten Bereich Ihre Projekt, bevor Sie auf **Installieren** klicken.

1. Wenn `Newtonsoft.Json` bereits auf Ihrem System installiert ist, fügen Sie es Ihrem Projekt hinzu, indem Sie Ihr Projekt im rechten Bereich der Registerkarte **Pakete für Projektmappe verwalten** auswählen.

Es folgt die vollständige *CSPROJ*-Datei dieses Projekts:

# <a name="visual-studio-156-and-earliertabvs156"></a>[Visual Studio 15.6 und frühere Versionen](#tab/vs156)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

# <a name="visual-studio-157-and-latertabvs157"></a>[Visual Studio 15.7 und höhere Versionen](#tab/vs157)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

---

Wenn Sie Ihre Anwendung bereitstellen, sind die Drittanbieter-Abhängigkeiten, die in Ihrer Anwendung verwendet werden, auch in Ihren Anwendungsdateien enthalten. Drittanbieter-Bibliotheken müssen nicht auf dem System vorhanden sein, auf dem die Anwendung ausgeführt wird.

Beachten Sie, dass Sie eine eigenständige Bereitstellung mit einer Drittanbieter-Bibliothek nur auf von dieser Bibliothek unterstützten Plattformen bereitstellen können. Dies ist ähnlich, als wenn Sie über Drittanbieter-Abhängigkeiten mit nativen Abhängigkeiten in Ihrer Framework-abhängigen Bereitstellung verfügen, wobei die nativen Abhängigkeiten nicht auf der Zielplattform vorhanden sind, es sei denn, sie wurden dort zuvor installiert.

## <a name="see-also"></a>Siehe auch

- [.NET Core-Anwendungsbereitstellung](index.md)
- [.NET Core Runtime-ID (RID)-Katalog](../rid-catalog.md)
