---
title: Beispiel für die Migration zu .NET Core 3.1
description: Es wird gezeigt, wie Sie eine Beispielanwendung, die .NET Framework, auf .net Core 3,1 migrieren.
ms.date: 05/12/2020
ms.openlocfilehash: 6a0311e9aaeb25ac39f3394d3a62e17046fe03d8
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "97866532"
---
# <a name="example-of-migrating-to-net-core-31"></a>Beispiel für die Migration zu .NET Core 3.1

In diesem Kapitel werden praktische Richtlinien vorgestellt, die Ihnen bei der Migration Ihrer vorhandenen Anwendung von .NET Framework zu .net Core helfen.

Wir präsentieren einen gut strukturierten Prozess, den Sie befolgen können, und die wichtigsten Punkte, die bei jedem Schritt berücksichtigt werden müssen.

Anschließend wird ein schrittweises Migrationsverfahren für eine Beispiel-Desktop Anwendung, beides aus WinForms-und WPF-Versionen, dokumentiert.

## <a name="migration-process-overview"></a>Übersicht über den Migrationsprozess

Der Migrations Vorgang besteht aus vier aufeinander folgenden Schritten:

1. **Vorbereitung**: verstehen Sie die Abhängigkeiten des Projekts, um eine Vorstellung davon zu erhalten, was vorausgeht. In diesem Schritt nehmen Sie das aktuelle Projekt in einen Zustand, der den Startpunkt für die Migration vereinfacht.

2. **Projektdatei migrieren:** für .net Core-Projekte wird das neue Projekt Format im SDK-Format verwendet. Erstellen Sie eine neue Projektdatei mit diesem Format, oder aktualisieren Sie die Datei, für die Sie den SDK-Stil verwenden möchten.

3. **Korrigieren Sie den Code und den Build:** Erstellen Sie den Code in .net Core, der die Unterschiede auf API-Ebene zwischen .NET Framework und .net Core adressiert. Aktualisieren Sie bei Bedarf Pakete von Drittanbietern auf diejenigen, die .net Core unterstützen.

4. **Ausführen und testen:** Möglicherweise gibt es Unterschiede, die bis zur Laufzeit nicht angezeigt werden. Vergessen Sie daher nicht, die Anwendung auszuführen und zu testen, ob alles erwartungsgemäß funktioniert.

### <a name="preparation"></a>Vorbereitung

#### <a name="migrate-packagesconfig-file"></a>Migrieren packages.config Datei

In einer .NET Framework Anwendung werden alle Verweise auf externe Pakete in der *packages.config* -Datei deklariert. In .net Core ist es nicht mehr erforderlich, die *packages.config* -Datei zu verwenden. Verwenden Sie stattdessen die [packagereferenzierungseigenschaft](../../core/project-sdk/msbuild-props.md#packagereference) in der Projektdatei, um die nuget-Pakete für Ihre APP anzugeben.

Daher müssen Sie von einem Format in ein anderes wechseln. Sie können das Update manuell ausführen, indem Sie die in der *packages.config* -Datei enthaltenen Abhängigkeiten übernehmen und Sie in die Projektdatei mit dem `PackageReference` Format migrieren. Alternativ können Sie Visual Studio für Sie ausführen lassen: Klicken Sie mit der rechten Maustaste auf die Datei *packages.config* , und wählen Sie die Option **packages.config zu packagereferenzierung migrieren** aus.

#### <a name="verify-every-dependency-compatibility-in-net-core"></a>Überprüfen aller Abhängigkeits Kompatibilität in .net Core

Nachdem Sie die Paket Verweise migriert haben, müssen Sie jeden Verweis auf Kompatibilität überprüfen. Sie können die Abhängigkeiten der einzelnen nuget-Pakete untersuchen, die Ihre Anwendung auf [nuget.org](https://www.nuget.org/)verwendet. Wenn das Paket .NET Standard Abhängigkeiten aufweist, wird es auf .net Core funktionieren, da .net Core 3,1 alle Versionen von .NET Standard [unterstützt](../../standard/net-standard.md#net-implementation-support) . Die folgende Abbildung zeigt die Abhängigkeiten für das `Castle.Windsor` Paket:

![Screenshot der nuget-Abhängigkeiten für das Castle. Windsor-Paket](./media/example-migration-core/nuget-dependencies.png)

Zum Überprüfen der Paket Kompatibilität können Sie das Tool verwenden <https://fuget.org> , das ausführlichere Informationen zu Versionen und Abhängigkeiten bietet.

Möglicherweise verweist das Projekt auf ältere Paketversionen, die .net Core nicht unterstützen, aber Sie finden neuere Versionen, die diese unterstützen. Das Aktualisieren von Paketen auf neuere Versionen ist im Allgemeinen eine gute Empfehlung. Sie sollten jedoch berücksichtigen, dass durch die Aktualisierung der Paketversion einige wichtige Änderungen eingeführt werden, die das Aktualisieren Ihres Codes erzwingen würden.

Was geschieht, wenn Sie keine kompatible Version finden? Was geschieht, wenn Sie die Version eines Pakets aufgrund dieser wichtigen Änderungen nicht aktualisieren möchten? Keine Sorge, da es möglich ist, von einer .net Core-Anwendung aus .NET Framework Paketen zu abhängen. Vergessen Sie nicht, Sie ausgiebig zu testen, da Sie Laufzeitfehler verursachen kann, wenn das externe Paket eine API aufruft, die in .net Core nicht verfügbar ist. Dies eignet sich hervorragend für den Fall, dass Sie ein altes Paket verwenden, das nicht aktualisiert wird, und Sie können einfach neu zuweisen, um auf .net Core zu arbeiten.

#### <a name="check-for-api-compatibility"></a>Auf API-Kompatibilität überprüfen

Da die API-Oberfläche in .NET Framework und .net Core ähnlich, aber nicht identisch ist, müssen Sie überprüfen, welche APIs in .net Core verfügbar sind und welche nicht. Sie können das Tool .net-Portabilitäts Analyse verwenden, um APIs zu verwenden, die nicht in .net Core vorhanden sind. Sie untersucht die binäre Ebene Ihrer APP, extrahiert alle APIs, die aufgerufen werden, und listet dann auf, welche APIs in Ihrem Ziel Framework nicht verfügbar sind (in diesem Fall .net Core 3,1).

Weitere Informationen zu diesem Tool finden Sie unter:

<https://docs.microsoft.com/dotnet/standard/analyzers/portability-analyzer>

Ein interessanter Aspekt dieses Tools besteht darin, dass nur die Unterschiede von Ihrem eigenen Code und nicht von Code aus externen Paketen, die Sie nicht ändern können, angezeigt werden. Denken Sie daran, dass Sie die meisten dieser Pakete aktualisiert haben müssen, damit Sie mit .net Core funktionieren.

### <a name="migrate-project-file"></a>Projektdatei migrieren

#### <a name="create-the-new-net-core-project"></a>Erstellen des neuen .net Core-Projekts

In den meisten Fällen sollten Sie Ihr vorhandenes Projekt auf das neue .net Core-Format aktualisieren. Sie können jedoch auch ein neues Projekt erstellen, während Sie das alte Projekt beibehalten. Der Hauptnachteil beim Aktualisieren des alten Projekts ist, dass Sie die Designer Unterstützung verlieren, was für Sie wichtig ist. Wenn Sie den Designer weiterhin verwenden möchten, müssen Sie ein neues .net Core-Projekt parallel zum alten erstellen und Assets freigeben. Wenn Sie Benutzeroberflächen Elemente im Designer ändern müssen, können Sie dazu zum alten Projekt wechseln. Und da Assets verknüpft sind, werden Sie ebenfalls im .net Core-Projekt aktualisiert.

Das [SDK-Stil Projekt](../../core/project-sdk/msbuild-props.md) für .net Core ist viel einfacher als das Projekt Format .NET Framework. Und abgesehen von den zuvor erwähnten `PackageReference` Einträgen müssen Sie nicht viel mehr tun. Das neue Projekt Format schließt [standardmäßig](../../core/tools/csproj.md#default-compilation-includes-in-net-core-projects)bestimmte Dateierweiterungen ein, z `.cs` . b.-und- `.xaml` Dateien, ohne dass diese explizit in die Projektdatei eingeschlossen werden müssen.

#### <a name="assemblyinfo-considerations"></a>Überlegungen zu Assembly.info

Attribute werden für .net Core-Projekte automatisch generiert. Wenn das Projekt eine *AssemblyInfo.cs* -Datei enthält, werden die Definitionen dupliziert, was zu Kompilierungs Konflikten führt. Sie können die ältere *AssemblyInfo.cs* -Datei löschen oder die automatische Generierung deaktivieren, indem Sie den folgenden Eintrag der .net Core-Projektdatei hinzufügen:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

#### <a name="resources"></a>Ressourcen

Eingebettete Ressourcen werden automatisch eingeschlossen, aber Ressourcen sind nicht vorhanden, sodass Sie die Ressourcen in die neue Projektdatei migrieren müssen.

#### <a name="package-references"></a>Paketverweise

Mit der Option **packages.config zu packagerereferences migrieren** können Sie Ihre externen Paket Verweise problemlos in das neue Format verschieben, wie bereits erwähnt.

#### <a name="update-package-references"></a>Aktualisieren von Paketverweisen

Aktualisieren Sie die Versionen der Pakete, die Sie als kompatibel befunden haben, wie im vorherigen Abschnitt gezeigt.

### <a name="fix-the-code-and-build"></a>Korrigieren Sie den Code und den Build

#### <a name="microsoftwindowscompatibility"></a>Microsoft. Windows. Compatibility

Wenn Ihre Anwendung von APIs abhängig ist, die in .net Core nicht verfügbar sind, wie z. b. Registrierung, ACLs oder WCF, müssen Sie einen Verweis auf das Paket einschließen, `Microsoft.Windows.Compatibility` um diese Windows-spezifischen APIs hinzuzufügen. Sie funktionieren unter .net Core, sind aber nicht enthalten, da Sie nicht plattformübergreifend sind.

Es gibt ein Tool namens API Analyzer ( <https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer> ), das Ihnen hilft, APIs zu identifizieren, die nicht mit Ihrem Code kompatibel sind.

#### <a name="use-if-directives"></a>\#If-Direktiven verwenden

Wenn Sie unterschiedliche Ausführungs Pfade benötigen, wenn Sie auf .NET Framework und .net Core abzielen, sollten Sie Kompilierungs Konstanten verwenden. Fügen Sie \# dem Code einige if-Direktiven hinzu, um die gleiche Codebasis für beide Ziele beizubehalten.

#### <a name="technologies-not-available-on-net-core"></a>Technologien, die in .net Core nicht verfügbar sind

Einige Technologien sind in .net Core nicht verfügbar, wie z. b.:

* AppDomains
* Remoting
* Codezugriffssicherheit
* WCF-Server
* Windows-Workflow

Daher müssen Sie einen Ersatz für diese Technologien finden, wenn Sie Sie in Ihrer Anwendung verwenden. Weitere Informationen finden Sie im Artikel [.NET Framework-Technologien, die für .net Core nicht verfügbar](../../core/porting/net-framework-tech-unavailable.md) sind.

#### <a name="regenerate-autogenerated-clients"></a>Automatisch generierte Clients neu generieren

Wenn Ihre Anwendung automatisch generierten Code (z. b. einen WCF-Client) verwendet, müssen Sie diesen Code ggf. erneut generieren, um .net Core als Ziel zu verwenden Manchmal können Sie einige fehlende Verweise finden, da Sie möglicherweise nicht als Bestandteil des standardmäßigen Satzes von .net Core-Assemblys enthalten sind. Mithilfe eines Tools wie <https://apisof.net/> können Sie die Assembly, in der sich der fehlende Verweis befindet, leicht finden und aus nuget hinzufügen.

#### <a name="rolling-back-package-versions"></a>Rollback von Paketversionen

Als allgemeine Regel haben wir bereits festgelegt, dass Sie jede einzelne Paketversion so aktualisieren, dass Sie mit .net Core kompatibel ist. Allerdings können Sie feststellen, dass das Ziel einer aktualisierten und kompatiblen Version einer Assembly nicht zahlt. Wenn die Kosten für die Änderung nicht akzeptabel sind, können Sie ein Rollback der Paketversionen in Erwägung gezogen, wobei Sie die in .NET Framework verwendeten. Obwohl Sie möglicherweise nicht auf .net Core abzielen, sollten Sie gut funktionieren, es sei denn, Sie wenden einige nicht unterstützte APIs an.

### <a name="run-and-test"></a>Ausführen und Testen

Wenn Sie die Anwendungs Erstellung ohne Fehler durchlaufen haben, können Sie den letzten Schritt der Migration starten, indem Sie jede Funktionalität testen.

In diesem letzten Schritt finden Sie verschiedene verschiedene Probleme, abhängig von der Komplexität Ihrer Anwendung und den von Ihnen verwendeten Abhängigkeiten und APIs.

Wenn Sie z. b. Konfigurationsdateien (*app.config*) verwenden, finden Sie möglicherweise einige Fehler zur Laufzeit, z. b. Konfigurations Abschnitte nicht vorhanden. Wenn Sie das `Microsoft.Extensions.Configuration` nuget-Paket verwenden, sollte dieser Fehler behoben werden.

Ein weiterer Grund für Fehler ist die Verwendung der `BeginInvoke` -Methode und der- `EndInvoke` Methode, da Sie von .net Core nicht unterstützt werden. Sie werden von .net Core nicht unterstützt, da Sie eine Abhängigkeit von Remoting haben, das in .net Core nicht vorhanden ist. Um dieses Problem zu beheben, versuchen Sie, das- `await` Schlüsselwort (falls verfügbar) oder die-Methode zu verwenden <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> .

Mithilfe von Kompatibilitäts Analysen können Sie APIs und Code muster in Ihrem Code identifizieren, die zur Laufzeit möglicherweise Probleme mit .net Core verursachen können. Wechseln Sie zu, <https://github.com/dotnet/platform-compat> und verwenden Sie den .NET API Analyzer für Ihr Projekt.

## <a name="migrating-a-windows-forms-application"></a>Migrieren einer Windows Forms Anwendung

Um einen kompletten Migrationsprozess einer Windows Forms Anwendung vorzustellen, haben wir uns für die Migration der in verfügbaren eShop-Beispielanwendung entschieden <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms> . Das gesamte Ergebnis der Migration finden Sie unter <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms> .

Diese Anwendung zeigt einen Produktkatalog und ermöglicht dem Benutzer das Navigieren, Filtern und suchen nach Produkten. Aus Sicht der Architektur basiert die APP auf einem externen WCF-Dienst, der als Fassade für eine Back-End-Datenbank fungiert.

Das Hauptanwendungsfenster wird in der folgenden Abbildung angezeigt:

![Hauptanwendungsfenster](./media/example-migration-core/main-application-window.png)

Wenn Sie die *csproj* -Projektdatei öffnen, sehen Sie Folgendes:

![Screenshot der Inhalte der CSPROJ-Datei](./media/example-migration-core/csproj-file.png)

Wie bereits erwähnt, hat das .net Core-Projekt einen kompakteren Stil, und Sie müssen die Projektstruktur zum neuen .net Core SDK-Stil migrieren.

Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt Windows Forms, und wählen Sie **Projekt**  >  **Bearbeiten**.

Nun können Sie die CSPROJ-Datei aktualisieren. Löschen Sie den gesamten Inhalt, und ersetzen Sie ihn durch den folgenden Code:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

Speichern und laden Sie das Projekt erneut. Nun haben Sie die Projektdatei aktualisiert, und das Projekt zielt auf .net Core ab.

Wenn Sie das Projekt zu diesem Zeitpunkt kompilieren, finden Sie einige Fehler im Zusammenhang mit der WCF-Client Referenz. Da dieser Code automatisch generiert wird, müssen Sie ihn neu generieren, um .net Core als Ziel zu erhalten.

![Screenshot der Kompilierungsfehler in Visual Studio](./media/example-migration-core/winforms-compilation-errors.png)

Löschen Sie die Datei *Reference.cs* , und generieren Sie einen neuen Dienst Client.

Klicken Sie mit der rechten Maustaste auf **verbundene Dienste** und wählen Sie die Option **verbundenen Dienst hinzufügen** aus.

![Screenshot des Menüs "verbundene Dienste" mit ausgewählter Option "verbundenen Dienst hinzufügen"](./media/example-migration-core/add-connected-service.png)

Das verbundene Dienste Fenster wird geöffnet. Wählen Sie die Option **Microsoft WCF-Webdienst** aus.

![Screenshot des Fensters "verbundene Dienste"](./media/example-migration-core/connected-services-window.png)

Wenn Sie den WCF-Dienst in derselben Projekt Mappe wie in diesem Beispiel verwenden, können Sie die **Ermittlungs Option auswählen** , anstatt eine Dienst-URL anzugeben.

![Screenshot des Fensters "WCF-Webdienst Verweis konfigurieren"](./media/example-migration-core/configure-wcf-reference.png)

Sobald der Dienst gefunden wurde, reflektiert das Tool den API-Vertrag, der vom Dienst implementiert wird. Ändern Sie den Namen des Namespace in, `eShopServiceReference` wie in der folgenden Abbildung dargestellt:

![Screenshot: der API-Vertrag und der Namespace wurden geändert.](./media/example-migration-core/api-contract-namespace.png)

Wählen Sie die Schaltfläche **Fertig** stellen. Nach einer Weile sehen Sie den generierten Code.

Es sollten drei automatisch generierte Dateien angezeigt werden:

1. *Getting Started*: ein Link zu GitHub, um einige Informationen zu WCF bereitzustellen.
2. *ConnectedService.js*: Konfigurationsparameter zum Herstellen einer Verbindung mit dem Dienst.
3. *Reference.cs*: der tatsächliche WCF-Client Code.

![Screenshot des Fensters "Projektmappen-Explorer" mit den drei automatisch generierten Dateien](./media/example-migration-core/autogenerated-files.png)

Wenn Sie die Kompilierung erneut ausführen, werden viele Fehler aus *CS* - *Dateien im* hilfsprogrammordner angezeigt. Dieser Ordner war in der .NET Framework-Version vorhanden, jedoch nicht in der alten *csproj*-Datei enthalten. Mit dem neuen SDK-Stil-Projekt ist jedoch jede Codedatei, die unterhalb des Projektdatei Speicher Orts vorhanden ist, standardmäßig enthalten. Das heißt, das neue .net Core-Projekt versucht, die *Dateien im hilfsprogrammordner zu* kompilieren. Da dieser Ordner nicht benötigt wird, können Sie ihn problemlos löschen.

Wenn Sie das Projekt erneut kompilieren und ausführen, werden die Produkt Images nicht angezeigt. Das Problem ist, dass sich der Pfad zu den Dateien nun etwas geändert hat. Um dieses Problem zu beheben, müssen Sie eine weitere Tiefe des Pfads hinzufügen und in der Datei `CatalogView.cs` die Zeile aktualisieren:

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

zu

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

Nachdem Sie diese Änderung vorgenommen haben, können Sie überprüfen, ob die Anwendung in .net Core erwartungsgemäß gestartet und ausgeführt wird.

## <a name="migrating-a-wpf-application"></a>Migrieren einer WPF-Anwendung

Wir verwenden die `Shop.ClassicWPF` Beispielanwendung, um die Migration durchzuführen. Die folgende Abbildung zeigt einen Screenshot der APP vor der Migration:

![Beispiel-APP vor der Migration](./media/example-migration-core/app-before-migration.png)

Diese Anwendung verwendet eine lokale SQL Server Express Datenbank, um die Produktkatalog Informationen zu speichern. Der Zugriff auf diese Datenbank erfolgt direkt über die WPF-Anwendung.

Zunächst müssen Sie die *csproj* -Datei auf den neuen SDK-Stil aktualisieren, der von .net Core-Anwendungen verwendet wird. Befolgen Sie dieselben Schritte, die in der Windows Forms Migration beschrieben werden: Sie entladen das Projekt, öffnen die *csproj* -Datei, aktualisieren den Inhalt und laden das Projekt erneut.

Löschen Sie in diesem Fall den gesamten Inhalt der *csproj* -Datei, und ersetzen Sie ihn durch den folgenden Code:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWpf>true</UseWpf>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

Wenn Sie das Projekt erneut laden und kompilieren, erhalten Sie die folgende Fehlermeldung:

![Screenshot der Kompilierungsfehler in Visual Studio](./media/example-migration-core/wpf-compilation-error.png)

Da Sie alle *csproj* -Inhalte gelöscht haben, haben Sie eine Projekt Verweis Spezifikation verloren, die im alten Projekt vorhanden ist. Sie müssen diese Zeile lediglich der *csproj* -Datei hinzufügen, um den Projekt Verweis einzuschließen:

```xml
<ItemGroup>
    <ProjectReference Include="..\\eShop.SqlProvider\\eShop.SqlProvider.csproj" />
<ItemGroup>
```

Sie können Visual Studio auch helfen, indem Sie mit der rechten Maustaste auf den Knoten **Abhängigkeiten** klicken und **Projekt Verweis hinzufügen** auswählen. Wählen Sie das Projekt aus der Projekt Mappe, und klicken Sie auf **OK**:

![Screenshot des Dialog Felds "Verweis-Manager" mit ausgewähltem "eShop. SqlProvider"-Projekt](./media/example-migration-core/reference-manager.png)

Nachdem Sie den fehlenden Projekt Verweis hinzugefügt haben, wird die Anwendung in .net Core wie erwartet kompiliert und ausgeführt.

>[!div class="step-by-step"]
>[Zurück](windows-migration.md)
>[Weiter](deploy-modern-applications.md)
