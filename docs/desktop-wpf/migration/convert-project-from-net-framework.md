---
title: Migrieren von WPF-Apps zu .NET Core 3.0
description: Erfahren Sie, wie Sie eine Windows Presentation Foundation-App (WPF) zu .NET Core 3.0 migrieren.
author: mjrousos
ms.date: 09/12/2019
ms.author: mikerou
ms.openlocfilehash: fda4f618ddb4a3edbe6f2dd9fba0b10bc618e88d
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201560"
---
# <a name="migrating-wpf-apps-to-net-core"></a>Migrieren von WPF-Apps zu .NET Core

In diesem Artikel werden die erforderlichen Schritte zum Migrieren einer Windows Presentation Foundation-App (WPF) von .NET Framework zu .NET Core 3.0 beschrieben. Wenn Sie keine WPF-Anwendung zum Portieren zur Verfügung haben, den Prozess aber ausprobieren möchten, können Sie die Beispiel-App **Bean Trader** verwenden, die auf [GitHub](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader) verfügbar ist. Die ursprüngliche App (für .NET Framework 4.7.2) ist im Ordner „NetFx\BeanTraderClient“ verfügbar. Zuerst werden die erforderlichen Schritte zum Portieren von Apps im Allgemeinen erläutert. Anschließend werden die spezifischen Änderungen schrittweise beschrieben, die für das Beispiel **Bean Trader** gelten.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

Zum Migrieren zu .NET Core müssen Sie zuerst Folgendes ausführen:

01. Verstehen und Aktualisieren von NuGet-Abhängigkeiten:

    01. Aktualisieren Sie NuGet-Abhängigkeiten, um das `<PackageReference>`-Format zu verwenden.
    01. Überprüfen Sie die NuGet-Abhängigkeiten der obersten Ebene auf .NET Core- oder .NET Standard-Kompatibilität.
    01. Aktualisieren Sie die NuGet-Pakete auf neuere Versionen.
    01. Verwenden Sie [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md), um .NET-Abhängigkeiten zu verstehen.

01. Migrieren der Projektdatei in das neue Format im SDK-Stil:

    01. Wählen Sie aus, ob Sie sowohl .NET Core als auch .NET Framework oder nur .NET Core als Ziel verwenden möchten.
    01. Kopieren Sie relevante Projektdateieigenschaften und -elemente in die neue Projektdatei.

01. Beheben von Buildproblemen:

    01. Fügen Sie einen Verweis auf das [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/)-Paket hinzu.
    01. Suchen und beheben Sie Unterschiede auf API-Ebene.
    01. Entfernen Sie *app.config*-Abschnitte mit Ausnahme von `appSettings` oder `connectionStrings`.
    01. Generieren Sie ggf. generierten Code neu.

01. Laufzeittests:

    01. Bestätigen Sie, dass die portierte App erwartungsgemäß funktioniert.
    01. Beachten Sie <xref:System.NotSupportedException>-Ausnahmen.

## <a name="about-the-sample"></a>Über das Beispiel

In diesem Artikel wird auf die Beispiel-App [Bean Trader](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader) verwiesen, da sie eine Vielzahl von Abhängigkeiten verwendet, die denen von echten WPF-Apps ähneln. Die App ist nicht groß, soll aber in Bezug auf Komplexität einen Schritt weiter gehen als „Hello World“. Die App zeigt einige Probleme, die bei der Portierung von echten Apps auftreten können. Die App kommuniziert mit einem WCF-Dienst. Damit sie ordnungsgemäß ausgeführt werden kann, müssen Sie das BeanTraderServer-Projekt (verfügbar im gleichen GitHub-Repository) ausführen und sicherstellen, dass die BeanTraderClient-Konfiguration auf den richtigen Endpunkt verweist. (Standardmäßig nimmt das Beispiel an, dass der Server auf demselben Computer unter `http://localhost:8090` ausgeführt wird, was zutrifft, wenn Sie BeanTraderServer lokal starten.)

Beachten Sie, dass diese Beispiel-App dazu gedacht ist, Herausforderungen bei der .NET Core-Portierung zu zeigen und-Lösungen zu veranschaulichen. Er soll keine bewährten Methoden für WPF zeigen. Tatsächlich enthält es absichtlich einige Antimuster, um sicherzustellen, dass Sie bei der Portierung mit einigen interessanten Herausforderungen konfrontiert werden.

## <a name="getting-ready"></a>Vorbereitung

Die Hauptaufgabe der Migration einer .NET Framework-App zu .NET Core besteht darin, dass ihre Abhängigkeiten möglicherweise anders oder überhaupt nicht funktionieren. Die Migration ist viel einfacher als früher: Viele NuGet-Pakete verwenden jetzt .NET-Standard als Ziel. Ab .NET Core 2.0 sind die .NET Framework- und .NET Core-Oberflächenbereiche ähnlich. Dennoch bleiben einige Unterschiede (sowohl bei der Unterstützung von NuGet-Paketen als auch bei den verfügbaren .NET-APIs) bestehen. Der erste Schritt bei der Migration besteht darin, die Abhängigkeiten der App zu überprüfen und sicherzustellen, dass Verweise in einem Format vorliegen, das leicht zu .NET Core migriert werden kann.

### <a name="upgrade-to-packagereference-nuget-references"></a>Upgrade auf `<PackageReference>`-NuGet-Verweise

Ältere .NET Framework-Projekte enthalten in der Regel Ihre NuGet-Abhängigkeiten in einer Datei *packages.config*. Das neue Projektdateiformat im SDK-Stil verweist auf NuGet-Pakete als [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files)-Elemente in der CSPROJ-Datei selbst anstatt in einer separaten Konfigurationsdatei.

Bei der Migration gibt es zwei Vorteile bei der Verwendung von Verweisen im `<PackageReference>`-Format:

- Dies ist das Format des NuGet-Verweises, das für die neue .NET Core-Projektdatei erforderlich ist. Wenn Sie `<PackageReference>` bereits verwenden, können diese Projektdateielemente kopiert und direkt in das neue Projekt eingefügt werden.
- Im Gegensatz zu einer Datei „packages.config“ verweisen `<PackageReference>`-Elemente nur auf die Abhängigkeiten auf oberster Ebene, von denen Ihr Projekt direkt abhängig ist. Alle anderen transitiven NuGet-Pakete werden zum Zeitpunkt der Wiederherstellung bestimmt und in der automatisch generierten Datei „obj\project.assets.json“ aufgezeichnet. Dies erleichtert es erheblich, zu ermitteln, welche Abhängigkeiten Ihr Projekt aufweist. Dies ist nützlich, wenn Sie bestimmen, ob die erforderlichen Abhängigkeiten für .NET Core funktionieren.

Der erste Schritt bei der Migration einer .NET Framework-App zu .NET Core besteht darin, sie so zu aktualisieren, dass `<PackageReference>`-NuGet-Verweise verwendet werden. In Visual Studio ist dies ganz einfach. Klicken Sie im **Projektmappen-Explorer** von Visual Studio einfach mit der rechten Maustaste auf die Datei *packages.config* des Projekts, und wählen Sie dann **packages.config zu PackageReference migrieren** aus.

![Aktualisieren auf PackageReference](./media/convert-project-from-net-framework/package-reference-migration.png)

Es wird ein Dialogfeld mit berechneten NuGet-Abhängigkeiten auf oberster Ebene angezeigt, und Sie werden gefragt, welche anderen NuGet-Pakete auf die oberste Ebene höher gestuft werden sollen. Keines dieser anderen Pakete muss für das Bean Trader-Beispiel auf oberster Ebene sein, sodass Sie alle diese Felder deaktivieren können. Klicken Sie dann auf **OK**. Die Datei *packages.config* wird entfernt, und `<PackageReference>`-Elemente werden der Projektdatei hinzugefügt.

Verweise im `<PackageReference>`-Format speichern keine NuGet-Pakete lokal in einem Paketordner. Stattdessen werden Sie global als eine Optimierung gespeichert. Nachdem die Migration abgeschlossen ist, bearbeiten Sie die CSPROJ-Datei, und entfernen Sie alle `<Analyzer>`-Elemente, die auf die Analyzer verweisen, die zuvor im Verzeichnis *..\packages* enthalten waren. Keine Sorge: Da Sie noch über die NuGet-Paketverweise verfügen, werden die Analyzer in das Projekt eingebunden. Sie müssen nur die alten `<Analyzer>`-Elemente im packages.config-Format bereinigen.

### <a name="review-nuget-packages"></a>Überprüfen von NuGet-Paketen

Nun können Sie die NuGet-Pakete der obersten Ebene sehen, von denen das Projekt abhängt, und Sie können überprüfen, ob diese Pakete für .NET Core verfügbar sind. Sie können ermitteln, ob ein Paket .NET Core unterstützt, indem Sie seine Abhängigkeiten auf [nuget.org](https://www.nuget.org/) untersuchen. Die von der Community erstellte Website [fuget.org](https://www.fuget.org/) zeigt diese Informationen hervorgehoben am oberen Rand der Seite mit den Paketinformationen an.

Wenn .NET Core 3.0 als Zielplattform verwendet wird, sollten alle Pakete für .NET Core oder .NET Standard funktionieren (da .NET Core den .NET Standard-Oberflächenbereich implementiert). In einigen Fällen ist die spezifische Version eines Pakets, das verwendet wird, nicht für .NET Core oder .NET Standard geeignet, neuere Versionen sind es jedoch schon. In diesem Fall sollten Sie ein Upgrade auf die neueste Version des Pakets in Erwägung ziehen.

Sie können auch Pakete für .NET Framework verwenden, dies birgt aber ein gewisses Risiko. Abhängigkeiten zwischen .NET Core und .NET Framework sind zulässig, da sich die Oberflächenbereiche von .NET Core und .NET Framework so ähnlich sind, dass solche Abhängigkeiten *häufig* funktionieren. Wenn das Paket jedoch versucht, eine .NET-API zu verwenden, die in .NET Core nicht vorhanden ist, tritt eine Laufzeitausnahme auf. Aus diesem Grund sollten Sie nur dann auf .NET Framework-Pakete verweisen, wenn keine anderen Optionen verfügbar sind, und es muss Ihnen bewusst sein, dass dies eine Testbelastung darstellt.

Wenn es Pakete gibt, auf die verwiesen wird, die nicht für .NET Core oder .NET Standard vorgesehen sind, müssen Sie über andere Alternativen nachdenken:

- Gibt es andere ähnliche Pakete, die stattdessen verwendet werden können? Manchmal veröffentlichen NuGet-Autoren separate „Core“-Versionen ihrer Bibliotheken, die speziell auf .NET Core abzielen. Enterprise Library-Pakete sind ein Beispiel für die Veröffentlichung von „.NetCore“-Alternativen durch die Community. In anderen Fällen sind neuere SDKs für einen bestimmten Dienst (manchmal mit unterschiedlichen Paketnamen) für .NET Standard verfügbar. Wenn keine Alternativen verfügbar sind, können Sie mit den .NET Framework-Zielpaketen fortfahren. Dabei sollten Sie bedenken, dass Sie diese bei Ausführung unter .NET Core gründlich testen müssen.

Das Bean Trader-Beispiel weist die folgenden NuGet-Abhängigkeiten auf oberster Ebene auf:

- [**Castle.Windsor, Version 4.1.1**](https://www.castleproject.org/projects/windsor/)  

  Dieses Paket ist auf .NET Standard 1.6 ausgerichtet, sodass es unter .NET Core funktioniert.

- [**Microsoft.CodeAnalysis.FxCopAnalyzers, Version 2.6.3**](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.3)  
  Da es sich um ein Metapaket handelt, ist nicht sofort ersichtlich, welche Plattformen unterstützt werden, aber aus der [Dokumentation](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisfxcopanalyzers) geht hervor, dass die neueste Version (2.9.2) sowohl für .NET Framework als auch für .NET Core funktioniert.

- [**Nito.AsyncEx, Version 4.0.1**](https://www.nuget.org/packages/Nito.AsyncEx/4.0.1)  

  Dieses Paket ist nicht für .NET Core bestimmt, die neuere Version 5.0 hingegen schon. Dies ist bei der Migration häufig der Fall, da viele NuGet-Pakete in letzter Zeit Unterstützung für den .NET-Standard hinzugefügt haben, ältere Projektversionen jedoch nur auf .NET-Framework abzielen. Wenn sich der Versionsunterschied nur auf eine Nebenversion bezieht, ist es häufig einfach, ein Upgrade auf die neuere Version durchzuführen. Da dies eine Hauptversionsänderung ist, müssen Sie beim Upgrade vorsichtig sein, da das Paket möglicherweise Breaking Changes aufweist. Es ist jedoch ein Vorwärtspfad vorhanden, was gut ist.

- [**MahApps.Metro, Version 1.6.5**](https://www.nuget.org/packages/MahApps.Metro/1.6.5)  

  Dieses Paket ist ebenfalls nicht für .NET Core gedacht, die neuere Vorabversion (2.0-alpha) jedoch schon. Auch hier müssen Sie nach Breaking Changes suchen, aber das neuere Paket ist ermutigend.

Die NuGet-Abhängigkeiten des Bean Trader-Beispiels zielen alle entweder auf .NET Standard/.NET Core ab oder verfügen über neuere Versionen, bei denen dies der Fall ist, sodass es hier wahrscheinlich keine Blockierungsprobleme geben wird.

### <a name="upgrade-nuget-packages"></a>Aktualisieren von NuGet-Paketen

Wenn möglich, wäre es gut, die Versionen aller Pakete, die nur auf .NET Core oder .NET Standard abzielen, zu diesem Zeitpunkt mit neueren Versionen zu aktualisieren (wobei das Projekt immer noch auf .NET Framework abzielt), um eventuelle Breaking Changes frühzeitig zu entdecken und zu behandeln.

Wenn Sie keine Materialänderungen an der vorhandenen .NET Framework-Version der App vornehmen möchten, kann dies warten, bis Sie über eine neue Projektdatei verfügen, die für .NET Core gedacht ist. Ein vorzeitiges Upgrade der NuGet-Pakete auf .NET Core-kompatible Versionen macht den Migrationsprozess nach Erstellung der neuen Projektdatei jedoch noch einfacher und verringert die Anzahl der Unterschiede zwischen den .NET Framework- und .NET Core-Versionen der App.

Mit dem Bean Trader-Beispiel können alle erforderlichen Upgrades einfach (unter Verwendung des NuGet-Paket-Managers von Visual Studio) durchgeführt werden. Dabei gibt es eine Ausnahme: Ein Upgrade von **MahApps.Metro 1.6.5** auf Version **2.0** bedeutet Breaking Changes in Bezug auf Design- und Akzentverwaltungs-APIs.

Im Idealfall wird die App so aktualisiert, dass sie die neuere Version des Pakets verwendet (da diese wahrscheinlicher in .NET Core funktioniert). In einigen Fällen ist dies jedoch ggf. nicht möglich. In diesen Fällen sollten Sie **MahApps.Metro** nicht aktualisieren, da die erforderlichen Änderungen nicht trivial sind. Dieses Tutorial konzentriert sich nur auf die Migration zu .NET Core 3, nicht zu **MahApps.Metro**. Dies ist auch eine .NET Framework-Abhängigkeit mit geringem Risiko, weil die Bean Trader-App nur einen kleinen Teil von **MahApps.Metro** verwendet. Natürlich sind Tests erforderlich, um sicherzustellen, dass alles funktioniert, nachdem die Migration abgeschlossen wurde. Wenn es sich um ein reales Szenario handeln würde, wäre es sinnvoll, ein Problem zu melden, um die Aufgaben beim Umstieg auf **MahApps.Metro** Version 2.0 nachzuverfolgen, da die Nichtdurchführung der Migration nun eine technische Schuld hinterlässt.

Nachdem die NuGet-Pakete auf die neuesten Versionen aktualisiert wurden, sollte die `<PackageReference>`-Elementgruppe in der Projektdatei des Bean Trader-Beispiels wie folgt aussehen.

```xml
<ItemGroup>
  <PackageReference Include="Castle.Windsor">
    <Version>4.1.1</Version>
  </PackageReference>
  <PackageReference Include="MahApps.Metro">
    <Version>1.6.5</Version>
  </PackageReference>
  <PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers">
    <Version>2.9.2</Version>
  </PackageReference>
  <PackageReference Include="Nito.AsyncEx">
    <Version>5.0.0</Version>
  </PackageReference>
</ItemGroup>
```

### <a name="net-framework-portability-analysis"></a>.NET Framework-Portabilitätsanalyse

Wenn Sie den Status der NuGet-Abhängigkeiten Ihres Projekts verstanden haben, müssen Sie als nächstes .NET Framework-API-Abhängigkeiten berücksichtigen. Mit dem Tool [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) können Sie ermitteln, welche der .NET-APIs, die Ihr Projekt verwendet, auf anderen .NET-Plattformen verfügbar ist.

Das Tool ist als [Visual Studio-Plug-In](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer), als [Befehlszeilentool](https://github.com/Microsoft/dotnet-apiport/releases) oder mit einer [einfachen grafischen Benutzeroberfläche](https://github.com/Microsoft/dotnet-apiport-ui) verfügbar, die seine Optionen vereinfacht. Weitere Informationen zur Verwendung von .NET Portability Analyzer (API Port) über die grafische Benutzeroberfläche finden Sie im Blogbeitrag [Porting desktop apps to .NET Core](https://devblogs.microsoft.com/dotnet/porting-desktop-apps-to-net-core/) (Portieren von Desktop-Apps zu .NET Core). Wenn Sie lieber die Befehlszeile verwenden möchten, sind die folgenden Schritte erforderlich:

1. Laden Sie den [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport/releases) herunter, wenn dies noch nicht geschehen ist.
1. Stellen Sie sicher, dass die zu portierende .NET Framework-App erfolgreich erstellt wurde (dies ist immer eine gute Idee vor der Migration).
1. Führen Sie API Port mit einer Befehlszeile wie dieser aus.

    ```console
    ApiPort.exe analyze -f <PathToBeanTraderBinaries> -r html -r excel -t ".NET Core"
    ```

    Das `-f`-Argument gibt den Pfad an, der die zu analysierenden Binärdateien enthält. Das `-r`-Argument gibt das gewünschte Ausgabedateiformat an. Das `-t`-Argument gibt an, mit welcher .NET-Plattform die API-Verwendung analysiert werden soll. In diesem Fall geben Sie .NET Core an.

Wenn Sie den HTML-Bericht öffnen, werden im ersten Abschnitt alle analysierten Binärdateien und der Prozentsatz der von ihnen verwendeten .NET-APIs aufgeführt, die auf der Zielplattform verfügbar sind. Der Prozentsatz allein ist nicht aussagekräftig. Hilfreicher ist es, die spezifischen APIs anzuzeigen, die fehlen. Wählen Sie hierzu entweder einen Assemblynamen aus, oder scrollen Sie nach unten zu den Berichten, um einzelne Assemblys anzuzeigen.

Konzentrieren Sie sich auf die Assemblys, für die Sie Besitzer des Quellcodes sind. Im ApiPort-Bericht des Bean Trader-Beispiels werden beispielsweise zahlreiche Binärdateien aufgelistet, aber die meisten von ihnen gehören zu NuGet-Paketen. `Castle.Windsor` zeigt, dass eine Abhängigkeit von einigen System.Web-APIs besteht, die in .NET Core fehlen. Dies ist kein Problem, da Sie zuvor bestätigt haben, dass `Castle.Windsor` .NET Core unterstützt. Es ist üblich, dass NuGet-Pakete unterschiedliche Binärdateien für die Verwendung mit verschiedenen .NET-Plattformen aufweisen, sodass es irrelevant ist, ob die .NET Framework-Version von `Castle.Windsor` System.Web APIs verwendet oder nicht, solange das Paket auch auf .NET Standard oder .NET Core abzielt (was der Fall ist).

Bei dem Bean Trader-Beispiel ist die einzige Binärdatei, die Sie berücksichtigen müssen, **BeanTraderClient**, und der Bericht zeigt, dass nur zwei .NET-APIs fehlen: `System.ServiceModel.ClientBase<T>.Close` und `System.ServiceModel.ClientBase<T>.Open`.

![BeanTraderClient-Portabilitätsbericht](./media/convert-project-from-net-framework/portability-report.png)

Es ist unwahrscheinlich, dass es sich dabei um blockierende Probleme handelt, da WCF-Client-APIs (meistens) unter .NET Core unterstützt werden, sodass es Alternativen für diese zentralen APIs geben muss. Wenn Sie sich die .NET Core-Oberfläche von `System.ServiceModel` ansehen (unter Verwendung von <https://apisof.net>), erkennen Sie tatsächlich, dass es stattdessen asynchrone Alternativen in .NET Core gibt.

Basierend auf diesem Bericht und der vorherigen NuGet-Abhängigkeitsanalyse sieht es so aus, als sollte es keine größeren Probleme bei der Migration des Bean Trader-Beispiels zu .NET Core geben. Sie sind bereit für den nächsten Schritt, in dem Sie die Migration tatsächlich starten.

## <a name="migrating-the-project-file"></a>Migrieren der Projektdatei

Wenn Ihre App nicht das neue [Projektdateiformat im SDK-Stil](../../core/tools/csproj.md) verwendet, benötigen Sie eine neue Projektdatei für .NET Core. Sie können die vorhandene CSPROJ-Datei ersetzen oder, wenn Sie es vorziehen, das vorhandene Projekt in seinem aktuellen Zustand unverändert zu belassen, eine neue CSPROJ-Datei hinzufügen, die auf .NET Core abzielt. Sie können Versionen der App für .NET Framework und .NET Core mit einer einzelnen Projektdatei im SDK-Stil erstellen, indem Sie [mehrere Zielversionen](../../standard/library-guidance/cross-platform-targeting.md) angeben (mehrere `<TargetFrameworks>`-Ziele angeben).

Um die neue Projektdatei zu erstellen, können Sie ein neues WPF-Projekt in Visual Studio erstellen oder den Befehl `dotnet new wpf` in einem temporären Verzeichnis verwenden, um die Projektdatei zu generieren und sie dann an den richtigen Speicherort zu kopieren bzw. umzubenennen. Es gibt auch ein von der Community erstelltes Tool, [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017), mit dem ein Teil der Projektdateimigration automatisiert werden kann. Das Tool ist hilfreich, benötigt aber trotzdem eine Überprüfung der Ergebnisse durch einen Menschen, um sicherzustellen, dass alle Details der Migration richtig sind. Ein bestimmter Bereich, den das Tool nicht optimal behandelt, ist das Migrieren von NuGet-Paketen aus *packages.config*-Dateien. Wenn das Tool für eine Projektdatei ausgeführt wird, die noch eine Datei *packages.config* verwendet, um auf NuGet-Pakete zu verweisen, migriert es automatisch zu `<PackageReference>`-Elementen, fügt aber `<PackageReference>`-Elemente für *alle* Pakete anstatt nur für die Pakete der obersten Ebene hinzu. Wenn Sie bereits mit Visual Studio zu `<PackageReference>`-Elementen migriert sind (wie in diesem Beispiel geschehen), kann Sie das Tool bei der restlichen Konvertierung unterstützen. Wie Scott Hanselman in [diesem Blogbeitrag zum Migrieren von CSPROJ-Dateien empfiehlt](https://www.hanselman.com/blog/UpgradingAnExistingNETProjectFilesToTheLeanNewCSPROJFormatFromNETCore.aspx), ist das manuelle Portieren lehrreich und führt zu besseren Ergebnissen, wenn Sie nur einige wenige Projekte portieren müssen. Wenn Sie jedoch Dutzende oder Hunderte von Projektdateien portieren, kann ein Tool wie [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) hilfreich sein.

Um eine neue Projektdatei für das Bean Trader-Beispiel zu erstellen, führen Sie `dotnet new wpf` in einem temporären Verzeichnis, verschieben Sie die generierte *CSPROJ*-Datei in den Ordner *BeanTraderClient*, und benennen Sie sie dann in **BeanTraderClient.Core.csproj** um.

Da das neue Projektdateiformat automatisch C#-Dateien, *RESX*-Dateien und XAML-Dateien einschließt, die es in oder unter seinem Verzeichnis findet, ist die Projektdatei bereits fast vollständig! Um die Migration abzuschließen, öffnen Sie die alte und die neue Projektdatei nebeneinander, und sehen Sie die alte Datei durch, um zu ermitteln, ob irgendwelche darin enthaltenen Informationen migriert werden müssen. Im Bean Trader-Beispielfall sollten die folgenden Elemente in das neue Projekt kopiert werden:

- Die Eigenschaften `<RootNamespace>`, `<AssemblyName>` und `<ApplicationIcon>` sollten kopiert werden.

- Außerdem müssen Sie der neuen Projektdatei eine `<GenerateAssemblyInfo>false</GenerateAssemblyInfo>`-Eigenschaft hinzufügen, da das Bean Trader-Beispiel Attribute auf Assemblyebene (wie `[AssemblyTitle]`) in einer Datei „AssemblyInfo.cs“ enthält. Standardmäßig generieren Projekte im neuen SDK-Stil diese Attribute automatisch basierend auf den Eigenschaften in der CSPROJ-Datei. Da Sie nicht möchten, dass dies in diesem Fall geschieht (die automatisch generierten Attribute würden mit denen aus „AssemblyInfo.cs“ in Konflikt geraten), deaktivieren Sie die automatisch generierten Attribute mit `<GenerateAssemblyInfo>`.

- Obwohl *RESX*-Dateien automatisch als eingebettete Ressourcen eingeschlossen werden, gilt dies für andere `<Resource>`-Elemente wie Bilder nicht. Kopieren Sie daher die `<Resource>`-Elemente zum Einbetten von Bild- und Symboldateien. Sie können die PNG-Verweise auf eine einzelne Zeile vereinfachen, indem Sie die Unterstützung des neuen Projektdateiformats für Globmuster verwenden: `<Resource Include="**\*.png" />`.

- Ebenso werden `<None>`-Elemente automatisch eingeschlossen, jedoch nicht standardmäßig in das Ausgabeverzeichnis kopiert. Da das Bean Trader-Projekt ein `<None>`-Element enthält, das (mit `PreserveNewest` Verhalten) in das Ausgabeverzeichnis kopiert *wird*, müssen Sie das automatisch aufgefüllte `<None>`-Element für diese Datei wie hier gezeigt aktualisieren.

  ```xml
  <None Update="BeanTrader.pfx">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </None>
  ```

- Das Bean Trader-Beispiel enthält eine XAML-Datei (Default.Accent.xaml) als `Content` (anstatt als `Page`), da in dieser Datei definierte Designs und Akzente zur Laufzeit aus dem XAML-Code der Datei geladen werden, anstatt in die App selbst eingebettet zu werden. Das neue Projektsystem schließt diese Datei jedoch automatisch als `<Page>` ein, da es sich um eine XAML-Datei handelt. Daher müssen Sie die XAML-Datei als Seite (`<Page Remove="**\Default.Accent.xaml" />`) entfernen und als Inhalt hinzufügen.

  ```xml
  <Content Include="Resources\Themes\Default.Accent.xaml">
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </Content>
  ```

- Fügen Sie schließlich NuGet-Verweise hinzu, indem Sie die `<ItemGroup>` mit allen `<PackageReference>`-Elementen kopieren. Wenn Sie die NuGet-Pakete zuvor nicht auf mit .NET Core kompatible Versionen aktualisiert haben, kann dies jetzt geschehen, da die Paketverweise in einem .NET Core-spezifischen Projekt enthalten sind.

An diesem Punkt sollte es möglich sein, das neue Projekt der BeanTrader-Projektmappe hinzuzufügen und in Visual Studio zu öffnen. Das Projekt sollte im **Projektmappen-Explorer** ordnungsgemäß aussehen, und `dotnet restore BeanTraderClient.Core.csproj` sollte Pakete erfolgreich wiederherstellen (mit zwei erwarteten Warnungen in Bezug auf die von Ihnen verwendete MahApps.Metro-Version, die auf .NET Framework abzielt).

Obwohl es möglich ist, beide Projektdateien nebeneinander zu verwalten (und dies vielleicht sogar wünschenswert ist, wenn Sie das alte Projekt weiterhin genau so erstellen möchten, wie es zuvor war), erschwert es den Migrationsprozess (die beiden Projekte werden versuchen, die gleichen bin- und obj-Ordner zu verwenden) und ist normalerweise nicht notwendig. Wenn Sie das Projekt sowohl für .NET Core- als auch für .NET Framework-Ziele erstellen möchten, können Sie die `<TargetFramework>netcoreapp3.0</TargetFramework>`-Eigenschaft in der neuen Projektdatei stattdessen durch `<TargetFrameworks>netcoreapp3.0;net472</TargetFrameworks>` ersetzen. Löschen Sie für das Bean Trader-Beispiel die alte Projektdatei („BeanTraderClient.csproj“), da sie nicht mehr benötigt wird. Wenn Sie beide Projektdateien beibehalten möchten, müssen Sie sicherstellen, dass der Buildvorgang in andere Ausgabe- und Zwischenausgabepfade erfolgt.

## <a name="fix-build-issues"></a>Beheben von Buildproblemen

Der dritte Schritt des Portierungsvorgangs besteht darin, das Projekt zu erstellen. Einige Apps werden bereits erfolgreich erstellt, sobald die Projektdatei in ein Projekt im SDK-Stil konvertiert wurde. Wenn dies für Ihre App der Fall ist, herzlichen Glückwunsch! Sie können mit Schritt 4 fortfahren. Andere Apps benötigen einige Updates, damit sie für .NET Core erstellt werden können. Wenn Sie jetzt beispielsweise versuchen, `dotnet build` für das Bean Trader-Beispielprojekt auszuführen (oder es in Visual Studio zu erstellen), werden viele Fehler auftreten, die aber schnell behoben werden können.

### <a name="systemservicemodel-references-and-microsoftwindowscompatibility"></a>System.ServiceModel-Verweise und Microsoft.Windows.Compatibility

Eine häufige Fehlerquelle sind fehlende Verweise auf APIs, die für .NET Core verfügbar sind, aber nicht automatisch im .NET Core-App-Metapaket enthalten sind. Um dieses Problem zu beheben, sollten Sie auf das `Microsoft.Windows.Compatibility`-Paket verweisen. Das Kompatibilitätspaket umfasst eine breite Palette von APIs, die in Windows-Desktop-Apps üblich sind, etwa einen WCF-Client, Verzeichnisdienste, Registrierung, Konfiguration, ACL-APIs und vieles mehr.

Beim Bean Trader-Beispiel ist die Mehrzahl der Buildfehler auf fehlende <xref:System.ServiceModel>-Typen zurückzuführen. Diese können durch Verweisen auf die erforderlichen WCF NuGet-Pakete behoben werden. WCF-Client-APIs gehören jedoch zu den APIs, die im `Microsoft.Windows.Compatibility`-Paket enthalten sind, sodass ein Verweis auf das Kompatibilitätspaket eine noch bessere Lösung darstellt (da es auch alle Probleme im Zusammenhang mit APIs sowie Lösungen für die WCF-Probleme behandelt, die das Kompatibilitätspaket zur Verfügung stellt). Das `Microsoft.Windows.Compatibility`-Paket hilft bei den meisten .NET Core 3.0 WPF- und WinForms-Portierungsszenarien. Nach dem Hinzufügen des NuGet-Verweises zu `Microsoft.Windows.Compatibility`wird nur noch ein Buildfehler ausgegeben!

### <a name="cleaning-up-unused-files"></a>Bereinigen von nicht verwendeten Dateien

Eine Art von Migrationsproblem, das häufig auftritt, bezieht sich auf C#- und XAML-Dateien, die zuvor nicht im Build enthalten waren und von den neuen Projekten im SDK-Stil, die *alle* Quelldateien automatisch enthalten, übernommen werden.

Der nächste Buildfehler, den Sie im Bean Trader-Beispiel sehen, bezieht sich auf eine fehlerhafte Schnittstellenimplementierung in *OldUnusedViewModel.cs*. Der Dateiname ist ein Hinweis, aber bei der Überprüfung werden Sie feststellen, dass diese Quelldatei falsch ist. Sie hat bisher keine Probleme verursacht, weil sie nicht im ursprünglichen .NET Framework-Projekt enthalten war. Quelldateien, die auf dem Datenträger vorhanden waren, aber nicht in der alten *CSPROJ*-Datei, werden jetzt automatisch eingeschlossen.

Bei einmaligen Problemen wie diesem ist es einfach, einen Vergleich mit der vorherigen *CSPROJ*-Datei vorzunehmen, um zu bestätigen, dass die Datei nicht mehr benötigt wird, und dann entweder `<Compile Remove="" />` zu verwenden oder sie zu löschen, wenn die Quelldatei nicht mehr benötigt wird. In diesem Fall ist es sicher, nur *OldUnusedViewModel.cs* zu löschen.

Wenn Sie über viele Quelldateien verfügen, die auf diese Weise ausgeschlossen werden müssten, können Sie die automatische Einbindung von C#-Dateien deaktivieren, indem Sie die `<EnableDefaultCompileItems>`-Eigenschaft in der Projektdatei auf FALSE festlegen. Anschließend können Sie `<Compile Include>`-Elemente aus der alten Projektdatei in die neue Projektdatei kopieren, um nur die Quellen zu erstellen, die Sie einschließen möchten. Ebenso kann `<EnableDefaultPageItems>` verwendet werden, um die automatische Einbindung von XAML-Seiten zu deaktivieren, und `<EnableDefaultItems>` kann beides mit einer einzelnen Eigenschaft steuern.

### <a name="a-brief-aside-on-multi-pass-compilers"></a>Eine kurze Anmerkung zu Multipass-Compilern

Nachdem Sie die beanstandete Datei aus dem Bean Trader-Beispiel entfernt haben, können Sie die Datei neu erstellen und erhalten vier Fehler. Zuvor war es doch nur ein Fehler? Warum ist die Anzahl der Fehler angestiegen? Der C#-Compiler ist ein [Multipass-Compiler](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes). Dies bedeutet, dass die einzelnen Quelldateien zwei Mal durchlaufen werden. Zuerst prüft der Compiler nur die Metadaten und Deklarationen in jeder Quelldatei und identifiziert alle Probleme auf Deklarationsebene. Dies sind die Fehler, die Sie korrigiert haben. Anschließend durchläuft er den Code erneut, um die C#-Quelle in IL zu erstellen. Dabei entsteht der zweite Fehlersatz, den Sie jetzt sehen.

> [!NOTE]
> Der C#-Compiler führt [mehr als nur zwei Durchläufe](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes) aus, aber das Endergebnis besteht darin, dass Compilerfehler für große Codeänderungen wie diese in der Regel in zwei Wellen auftreten.

### <a name="third-party-dependency-fixes-castlewindsor"></a>Abhängigkeitskorrekturen von Drittanbietern (Castle.Windsor)

Eine weitere Problemklasse, die in einigen Migrationsszenarien auftritt, sind API-Unterschiede zwischen .NET Framework und .NET Core-Versionen von Abhängigkeiten. Auch wenn ein NuGet-Paket sowohl .NET Framework als auch .NET Standard oder .NET Core als Ziel besitzt, können verschiedene Bibliotheken für die Verwendung mit verschiedenen .NET-Zielen vorhanden sein. Dies ermöglicht es den Paketen, viele verschiedene .NET-Plattformen zu unterstützen, die möglicherweise verschiedene Implementierungen erfordern. Dies bedeutet auch, dass es für verschiedene .NET-Plattformen zu kleinen API-Unterschieden in den Bibliotheken kommen kann.

Die nächste Reihe von Fehlern, die im Bean Trader-Beispiel angezeigt werden, beziehen sich auf `Castle.Windsor`-APIs. Das .NET Core-Bean Trader-Projekt verwendet dieselbe Version von `Castle.Windsor` wie das Projekt mit dem Ziel .NET Framework (4.1.1), aber die Implementierungen für diese beiden Plattformen unterscheiden sich geringfügig.

In diesem Fall treten die folgenden Probleme auf, die behoben werden müssen:

1. `Castle.MicroKernel.Registration.Classes.FromThisAssembly` ist unter .NET Core nicht verfügbar. Es ist jedoch eine ähnliche API `Classes.FromAssemblyContaining` verfügbar, sodass wir beide Verwendungsmöglichkeiten von `Classes.FromThisAssembly()` durch Aufrufe von `Classes.FromAssemblyContaining(t)` ersetzen können, wobei `t` der Typ ist, der den Aufruf ausführt.
1. Ähnlich in *Bootstrapper.cs*: `Castle.Windsor.Installer.FromAssembly`. Dies ist unter .NET Core nicht verfügbar. Stattdessen kann der Aufruf durch `FromAssembly.Containing(typeof(Bootstrapper))` ersetzt werden.

### <a name="updating-wcf-client-usage"></a>Aktualisieren der WCF-Clientsyntax

Wenn Sie die `Castle.Windsor`-Unterschiede korrigiert haben, ist der letzte verbleibende Buildfehler im .NET Core-Bean Trader-Projekt, dass `BeanTraderServiceClient` (von `DuplexClientBase`abgeleitet) keine `Open`-Methode aufweist. Dies ist nicht überraschend, da es sich um eine API handelt, die zu Beginn dieses Migrationsvorgangs von .NET Portability Analyzer hervorgehoben wurde. Der Blick auf `BeanTraderServiceClient` lenkt unsere Aufmerksamkeit jedoch auf ein größeres Problem. Dieser WCF-Client wurde vom Tool [Svcutil.exe](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) automatisch generiert.

**WCF-Clients, die von Svcutil generiert werden, sind für die Verwendung in .NET Framework gedacht.**

Lösungen, die von Svcutil generierte WCF-Clients verwenden, müssen mit .NET Standard kompatible Clients für die Verwendung mit .NET Core neu generieren. Einer der Hauptgründe, warum die alten Clients nicht funktionieren, besteht darin, dass sie von der App-Konfiguration zum Definieren von WCF-Bindungen und -Endpunkten abhängen. Da .NET Standard-WCF-APIs plattformübergreifend arbeiten können (wo System.Configuration-APIs nicht verfügbar sind), müssen WCF-Clients für .NET Core- und .NET Standard-Szenarien Bindungen und Endpunkte programmgesteuert anstatt in der Konfiguration definieren.

Tatsächlich muss jede WCF-Clientsyntax, die vom Abschnitt `<system.serviceModel>` der Datei „app.config“ abhängig ist (unabhängig davon, ob mit Svcutil oder manuell erstellt), geändert werden, damit sie unter .NET Core funktioniert.

Es gibt zwei Möglichkeiten, mit .NET Standard kompatible WCF-Clients automatisch zu generieren:

- Das Tool `dotnet-svcutil` ist ein .NET-Tool, mit dem WCF-Clients auf eine Weise generiert werden, die Svcutil ähnelt.
- Visual Studio kann WCF-Clients mithilfe der Option [WCF-Webdienstverweis](../../core/additional-tools/wcf-web-service-reference-guide.md) des Features „Verbundene Dienste“ generieren.

Beide Ansätze funktionieren gut. Natürlich können Sie den WCF-Clientcode auch selbst schreiben. In diesem Beispiel habe ich mich für die Verwendung des Features „Verbundene Dienste“ von Visual Studio entschieden. Klicken Sie hierzu im Projektmappen-Explorer von Visual Studio mit der rechten Maustaste auf das Projekt *BeanTraderClient.Core*, und wählen Sie **Hinzufügen** > **Verbundener Dienst** aus. Wählen Sie dann den Anbieter für den WCF-Webdienstverweis aus. Daraufhin wird ein Dialogfeld angezeigt, in dem Sie die Adresse des Back-End-Bean Trader-Webdiensts angeben können (`localhost:8080`, wenn Sie den Server lokal ausführen), sowie den Namespace, den die generierten Typen verwenden sollten (z. B. **BeanTrader.Service**).

![Dialogfeld „WCF-Webdienstverweis“ für „Verbundener Dienst“](./media/convert-project-from-net-framework/connected-service-dialog.png)

Nachdem Sie die Schaltfläche **Fertigstellen** ausgewählt haben, wird dem Projekt ein neuer Knoten „Verbundene Dienste“ und unter diesem Knoten eine Datei „Reference.cs“ hinzugefügt, die den neuen .NET Standard-WCF-Client für den Zugriff auf den Bean Trader-Dienst enthält. Wenn Sie sich die `GetEndpointAddress`- oder `GetBindingForEndpoint`-Methoden in dieser Datei ansehen, werden Sie feststellen, dass Bindungen und Endpunkte jetzt programmgesteuert (anstatt über die App-Konfiguration) generiert werden. Die Funktion „Verbundene Dienste hinzufügen“ kann auch Verweise auf einige System.ServiceModell-Pakete in der Projektdatei hinzufügen, die nicht benötigt werden, da alle erforderlichen WCF-Pakete über Microsoft.Windows.Compatibility enthalten sind. Überprüfen Sie die CSPROJ-Datei, um festzustellen, ob zusätzliche `<PackageReference>`-Elemente von System.ServiceModel hinzugefügt wurden. Wenn dies der Fall ist, entfernen Sie diese.

Unser Projekt verfügt jetzt über neue WCF-Clientklassen (in *Reference.cs*), aber auch weiterhin über die alten (in „BeanTrader.cs“). An diesem Punkt gibt es zwei Optionen:

- Wenn Sie in der Lage sein möchten, das ursprüngliche .NET Framework-Projekt (neben dem neuen .NET Core-Projekt) zu erstellen, können Sie ein `<Compile Remove="BeanTrader.cs" />`-Element in der CSPROJ-Datei des NET Core-Projekts verwenden, damit die .NET Framework-Version und die .NET Core-Version der App unterschiedliche WCF-Clients verwenden. Dies hat den Vorteil, das vorhandene .NET Framework-Projekt unverändert zu belassen, aber den Nachteil, dass Code, der die generierten WCF-Clients verwendet, im .NET Core-Fall etwas anders sein muss als im .NET Framework-Projekt, sodass Sie wahrscheinlich `#if`-Anweisungen verwenden müssen, um WCF-Clientsyntax (z. B. das Erstellen von Clients) bedingt zu kompilieren, damit sie bei der Erstellung für .NET Core auf die eine Weise und bei der Erstellung für .NET Framework auf eine andere Weise funktionieren.

- Wenn andererseits eine gewisse Codeänderung im vorhandenen .NET Framework-Projekt akzeptabel ist, können Sie *BeanTrader.cs* insgesamt entfernen. Da der neue WCF-Client für .NET Standard erstellt wird, funktioniert er sowohl in .NET Core- als auch in .NET Framework-Szenarien. Wenn Sie für .NET Framework zusätzlich zu .NET Core Builds erstellen (durch Angeben mehrerer Ziele oder durch zwei CSPROJ-Dateien), können Sie diese neue Datei *Reference.cs* für beide Ziele verwenden. Dieser Ansatz hat den Vorteil, dass der Code nicht gegabelt werden muss, um zwei verschiedene WCF-Clients zu unterstützen. Es wird überall derselbe Code verwendet. Der Nachteil besteht darin, dass das (vermutlich stabile) .NET Framework-Projekt geändert werden muss.

Im Fall des Bean Trader-Beispiels können Sie kleine Änderungen am ursprünglichen Projekt vornehmen, wenn dies die Migration erleichtert. Befolgen Sie also diese Schritte, um die WCF-Clientsyntax abzustimmen:

01. Fügen Sie die neue Datei „Reference.cs“ mithilfe des Kontextmenüs „Vorhandenes Element hinzufügen“ im Projektmappen-Explorer dem .NET Framework-Projekt *BeanTraderClient.csproj* hinzu. Stellen Sie sicher, dass Sie sie „als Link“ hinzufügen, damit dieselbe Datei von beiden Projekten verwendet wird (im Gegensatz zum Kopieren der C#-Datei). Wenn Sie sowohl für .NET Core als auch für .NET Framework mit einer einzelnen CSPROJ-Datei (unter Angabe mehrerer Zielplattformen) Builds erstellen, ist dieser Schritt nicht erforderlich.

01. Löschen Sie *BeanTrader.cs*.

01. Der neue WCF-Client ähnelt dem alten, aber eine Reihe von Namespaces im generierten Code unterscheiden sich. Aus diesem Grund ist es erforderlich, das Projekt zu aktualisieren, sodass WCF-Clienttypen aus BeanTrader.Service (oder einem beliebigen von Ihnen gewählten Namespacenamen) anstelle von BeanTrader.Model oder ohne einen Namespace verwendet werden. Wenn Sie *BeanTraderClient.Core.csproj* erstellen, können Sie ermitteln, wo diese Änderungen vorgenommen werden müssen. Korrekturen werden sowohl in C#- als auch in XAML-Quelldateien erforderlich sein.

01. Schließlich werden Sie feststellen, dass ein Fehler in *BeanTraderServiceClientFactory.cs* vorliegt, weil sich die verfügbaren Konstruktoren für den `BeanTraderServiceClient`-Typ geändert haben. Früher war es möglich, ein `InstanceContext`-Argument anzugeben (das mit einem `CallbackHandler` aus dem `Castle.Windsor`-IoC-Container erstellt wurde). Die neuen Konstruktoren erstellen neue `CallbackHandler`. Es gibt jedoch Konstruktoren im Basistyp von `BeanTraderServiceClient`, die Ihren Anforderungen entsprechen. Da der automatisch generierte WCF-Clientcode vollständig in partielle Klassen vorliegt, können Sie ihn leicht erweitern. Erstellen Sie zu diesem Zweck eine neue Datei namens *BeanTraderServiceClient.cs*, und erstellen Sie dann eine partielle Klasse mit dem gleichen Namen (mit dem BeanTrader.Service-Namespace). Fügen Sie dann wie hier gezeigt dem partiellen Typ einen Konstruktor hinzu.

    ```csharp
    public BeanTraderServiceClient(System.ServiceModel.InstanceContext callbackInstance) :
        base(callbackInstance, EndpointConfiguration.NetTcpBinding_BeanTraderService)
            { }
    ```

Nachdem diese Änderungen vorgenommen wurden, verwendet das Bean Trader-Beispiel jetzt einen neuen, mit .NET-Standard kompatiblen WCF-Client, und Sie können die endgültige Korrektur vornehmen, indem Sie den `Open`-Aufruf in *TradingService.cs* so ändern, dass stattdessen `await OpenAsync` verwendet wird.

Da die WCF-Probleme behoben sind, wird die .NET Core-Version des Bean Trader-Beispiels nun ordnungsgemäß erstellt!

## <a name="runtime-testing"></a>Laufzeittests

Es wird leicht vergessen, dass die Migrationsarbeiten nicht abgeschlossen sind, sobald das Projekt ordnungsgemäß unter .NET Core erstellt wird. Es ist wichtig, auch Zeit für das Testen der portierten App vorzusehen. Sobald der Build erfolgreich abgeschlossen wurde, stellen Sie sicher, dass die App wie erwartet ausgeführt wird und funktioniert, insbesondere wenn Sie Pakete verwenden, die auf .NET Framework abzielen.

Versuchen wir, die portierte Bean Trader-App zu starten, und sehen wir, was passiert. Die App kommt nicht weit, bevor sie mit der folgenden Ausnahme fehlschlägt.

```output
System.Configuration.ConfigurationErrorsException: 'Configuration system failed to initialize'

Inner Exception
ConfigurationErrorsException: Unrecognized configuration section system.serviceModel.
```

Das macht natürlich Sinn. Erinnern Sie sich daran, dass WCF keine Anwendungskonfiguration mehr verwendet, weshalb der alte Abschnitt system.serviceModel der Datei „app.config“ entfernt werden muss. Der aktualisierte WCF-Client enthält diese gesamten Informationen im Code, sodass der Konfigurationsabschnitt nicht mehr benötigt wird. Wenn Sie möchten, dass der WCF-Endpunkt in „app.config“ konfigurierbar ist, könnten Sie ihn als App-Einstellung hinzufügen und den WCF-Clientcode aktualisieren, um den WCF-Dienstendpunkt aus der Konfiguration abzurufen.

Nach dem Entfernen des Abschnitts system.serviceModel aus *app.config* wird die App gestartet, schlägt aber mit einer weiteren Ausnahme fehl, wenn sich ein Benutzer anmeldet.

```output
System.PlatformNotSupportedException: 'Operation is not supported on this platform.'
```

Die nicht unterstützte API ist `Func<T>.BeginInvoke`. Wie in [dotnet/corefx#5940](https://github.com/dotnet/corefx/issues/5940) erläutert, unterstützt .NET Core die Methoden `BeginInvoke` und `EndInvoke` für Delegiertentypen aufgrund der zugrunde liegenden Remotingabhängigkeiten nicht. Dieses Problem und seine Behebung werden im Blogbeitrag [Migrating Delegate.beginInvoke Calls for .NET Core](https://devblogs.microsoft.com/dotnet/migrating-delegate-begininvoke-calls-for-net-core/) (Migrieren von Delegate.beginInvoke-Aufrufen für .NET Core) ausführlicher erläutert, aber der Kerngedanke ist, dass `BeginInvoke`- und `EndInvoke`-Aufrufe durch `Task.Run` ersetzt werden sollten (oder asynchrone Alternativen, wenn möglich). Wenn Sie die allgemeine Lösung hier anwenden, kann der `BeginInvoke`-Befehl durch einen `Invoke`-Befehl ersetzt werden, der von `Task.Run` aufgerufen wird.

```csharp
Task.Run(() =>
{
    return userInfoRetriever.Invoke();
}).ContinueWith(result =>
{
    // BeginInvoke's callback is replaced with ContinueWith
    var task = result.ConfigureAwait(false);
    CurrentTrader = task.GetAwaiter().GetResult();
}, TaskScheduler.Default);
```

Nachdem Sie die `BeginInvoke`-Syntax entfernt haben, wird die Bean Trader-App unter .NET Core erfolgreich ausgeführt!

![Unter .NET Core ausgeführte Bean Trader-App](./media/convert-project-from-net-framework/running-on-core.png)

Alle Anwendungen sind unterschiedlich, so dass die spezifischen Schritte, die für die Migration Ihrer eigenen Apps zu .NET Core erforderlich sind, abweichen können. Hoffentlich zeigt das Bean Trader-Beispiel jedoch den allgemeinen Workflow und die Arten von Problemen, die zu erwarten sind. Und trotz der Länge dieses Artikels waren die tatsächlich erforderlichen Änderungen im Bean Trader-Beispiel, damit es unter .NET Core funktioniert, ziemlich gering. Viele Anwendungen werden auf die gleiche Weise zu .NET Core migriert, wobei nur eingeschränkte oder gar keine Codeänderungen erforderlich sind.
