---
title: Migrieren von WPF-Apps zu .NET Core 3.0
description: Erfahren Sie, wie Sie eine Windows Presentation Foundation (WPF)-App zu .NET Core 3.0 migrieren.
author: mjrousos
ms.date: 09/12/2019
ms.author: mikerou
ms.openlocfilehash: f52005e7c8a6312b8c4e09a950f1f635af1894e4
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "81432593"
---
# <a name="migrating-wpf-apps-to-net-core"></a>Migrieren von WPF-Apps zu .NET Core

In diesem Artikel werden die Schritte behandelt, die zum Migrieren einer Windows Presentation Foundation (WPF)-App von .NET Framework zu .NET Core 3.0 erforderlich sind. Wenn Sie keine WPF-App zur Verfügung haben, um portieren zu können, aber den Prozess ausprobieren möchten, können Sie die **Bean** Trader-Beispiel-App verwenden, die auf [GitHub](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader)verfügbar ist. Die ursprüngliche App (für .NET Framework 4.7.2) ist im Ordner NetFx-BeanTraderClient verfügbar. Zuerst erklären wir die Schritte, die notwendig sind, um Apps im Allgemeinen zu portieren, und dann gehen wir durch die spezifischen Änderungen, die für das **Bean Trader-Beispiel** gelten.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

Um zu .NET Core zu migrieren, müssen Sie zunächst Folgendes tun:

01. Verstehen und Aktualisieren von NuGet-Abhängigkeiten:

    01. Aktualisieren Sie NuGet-Abhängigkeiten, um das `<PackageReference>` Format zu verwenden.
    01. Überprüfen Sie NuGet-Abhängigkeiten der obersten Ebene für .NET Core- oder .NET Standard-Kompatibilität.
    01. Aktualisieren Sie NuGet-Pakete auf neuere Versionen.
    01. Verwenden Sie [.NET Portability Analyzer,](../../standard/analyzers/portability-analyzer.md) um .NET-Abhängigkeiten zu verstehen.

01. Migrieren Sie die Projektdatei in das neue SDK-Format:

    01. Wählen Sie aus, ob sowohl .NET Core als auch .NET Framework als Auch .NET Core als Ziel gesetzt werden sollen.
    01. Kopieren Sie relevante Projektdateieigenschaften und Elemente in die neue Projektdatei.

01. Beheben von Buildproblemen:

    01. Fügen Sie einen Verweis auf das [Microsoft.Windows.Compatibility-Paket hinzu.](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/)
    01. Suchen und beheben Sie Unterschiede auf API-Ebene.
    01. Entfernen Sie *app.config-Abschnitte,* die nicht `appSettings` oder sind. `connectionStrings`
    01. Generierten Code bei Bedarf neu generieren.

01. Laufzeittests:

    01. Bestätigen Sie, dass die portierte App wie erwartet funktioniert.
    01. Hüten <xref:System.NotSupportedException> Sie sich vor Ausnahmen.

## <a name="about-the-sample"></a>Über das Beispiel

Dieser Artikel verweist auf die [Bean Trader-Beispiel-App,](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader) da sie eine Vielzahl von Abhängigkeiten verwendet, die denen ähnlich sind, die reale WPF-Apps haben könnten. Die App ist nicht groß, sondern soll in Bezug auf die Komplexität ein Schritt nach oben von "Hello World" sein. Die App zeigt einige Probleme, die Benutzer beim Portieren echter Apps auftreten können. Die App kommuniziert mit einem WCF-Dienst, damit er ordnungsgemäß ausgeführt werden kann, müssen Sie auch das BeanTraderServer-Projekt (verfügbar im selben GitHub-Repository) ausführen und sicherstellen, dass die BeanTraderClient-Konfiguration auf den richtigen Endpunkt verweist. (Standardmäßig geht das Beispiel davon aus, dass *http://localhost:8090*der Server auf demselben Computer unter ausgeführt wird, was wahr ist, wenn Sie BeanTraderServer lokal starten.)

Beachten Sie, dass diese Beispiel-App dazu dient, Herausforderungen und Lösungen für die Portierung von .NET Core zu demonstrieren. Es ist nicht dazu gedacht, Die Best Practices von WPF zu demonstrieren. In der Tat, es enthält absichtlich einige Anti-Muster, um sicherzustellen, dass Sie auf mindestens ein paar interessante Herausforderungen während der Portierung stoßen.

## <a name="getting-ready"></a>Vorbereitung

Die hauptherausforderung beim Migrieren einer .NET Framework-App zu .NET Core besteht darin, dass ihre Abhängigkeiten möglicherweise anders oder gar nicht funktionieren. Die Migration ist viel einfacher als früher; viele NuGet-Pakete zielen jetzt auf .NET Standard ab. Ab .NET Core 2.0 sind die Flächen .NET Framework und .NET Core ähnlich geworden. Dennoch bleiben einige Unterschiede (sowohl in der Unterstützung von NuGet-Paketen als auch in verfügbaren .NET-APIs) bestehen. Der erste Schritt bei der Migration besteht darin, die Abhängigkeiten der App zu überprüfen und sicherzustellen, dass Verweise in einem Format vorliegen, das leicht zu .NET Core migriert werden kann.

### <a name="upgrade-to-packagereference-nuget-references"></a>Upgrade `<PackageReference>` auf NuGet-Referenzen

Ältere .NET Framework-Projekte listen in der Regel ihre NuGet-Abhängigkeiten in einer *packages.config-Datei* auf. Das neue Projektdateiformat im SDK-Stil [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) verweist auf NuGet-Pakete als Elemente in der csproj-Datei selbst und nicht in einer separaten Konfigurationsdatei.

Bei der Migration bietet die `<PackageReference>`Verwendung von -style-Referenzen zwei Vorteile:

- Dies ist der Stil des NuGet-Verweises, der für die neue .NET Core-Projektdatei erforderlich ist. Wenn Sie bereits `<PackageReference>`verwenden, können diese Projektdateielemente direkt in das neue Projekt kopiert und eingefügt werden.
- Im Gegensatz zu einer `<PackageReference>` packages.config-Datei beziehen sich Elemente nur auf die Abhängigkeiten der obersten Ebene, von denen Ihr Projekt direkt abhängt. Alle anderen transitiven NuGet-Pakete werden zur Wiederherstellungszeit ermittelt und in der automatisch generierten Datei obj-project.assets.json aufgezeichnet. Dies erleichtert die Bestimmung der Abhängigkeiten Ihres Projekts erheblich, was nützlich ist, um zu bestimmen, ob die erforderlichen Abhängigkeiten auf .NET Core funktionieren oder nicht.

Der erste Schritt zum Migrieren einer .NET Framework-App `<PackageReference>` zu .NET Core besteht darin, sie auf NuGet-Referenzen zu aktualisieren. Visual Studio macht dies einfach. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei *packages.config* des Projekts , und wählen Sie dann **Packages.config zu PackageReference migrieren**aus.

![Aktualisieren auf PackageReference](./media/convert-project-from-net-framework/package-reference-migration.png)

Es wird ein Dialogfeld angezeigt, in dem berechnete NuGet-Abhängigkeiten der obersten Ebene angezeigt und gefragt werden, welche anderen NuGet-Pakete auf die oberste Ebene heraufgestuft werden sollen. Keines dieser anderen Pakete muss top-level für die Bean Trader-Probe sein, so dass Sie alle diese Felder deaktivieren können. Klicken Sie dann auf **OK,** und die `<PackageReference>` Datei *packages.config* wird entfernt, und elemente werden der Projektdatei hinzugefügt.

`<PackageReference>`-style-Referenzen speichern NuGet-Pakete nicht lokal in einem Paketordner. Stattdessen werden sie global als Optimierung gespeichert. Bearbeiten Sie nach Abschluss der Migration die datei `<Analyzer>` csproj, und entfernen Sie alle Elemente, die sich auf die Analysatoren beziehen, die zuvor von der *.. Verzeichnis von spackages.* Keine Sorge; Da Sie noch über die NuGet-Paketreferenzen verfügen, werden die Analysatoren in das Projekt einbezogen. Sie müssen nur die alten packages.config-stil-Elemente `<Analyzer>` bereinigen.

### <a name="review-nuget-packages"></a>NuGet-Pakete überprüfen

Nachdem Sie nun die NuGet-Pakete der obersten Ebene sehen können, von denen das Projekt abhängt, können Sie überprüfen, ob diese Pakete in .NET Core verfügbar sind. Sie können bestimmen, ob ein Paket .NET Core unterstützt, indem Sie sich dessen Abhängigkeiten [von nuget.org](https://www.nuget.org/). Die von der Community [erstellte fuget.org-Website](https://www.fuget.org/) zeigt diese Informationen deutlich oben auf der Paketinformationsseite an.

Wenn Sie auf .NET Core 3.0 abzielen, sollten alle Pakete, die auf .NET Core oder .NET Standard abzielen, funktionieren (da .NET Core die .NET Standard-Oberfläche implementiert). In einigen Fällen zielt die bestimmte Version eines verwendeten Pakets nicht auf .NET Core oder .NET Standard ab, aber neuere Versionen werden dies tun. In diesem Fall sollten Sie ein Upgrade auf die neueste Version des Pakets in Betracht ziehen.

Sie können auch Pakete verwenden, die auf .NET Framework abzielen, aber das birgt ein gewisses Risiko. .NET Core to .NET Framework-Abhängigkeiten sind zulässig, da .NET Core- und .NET Framework-Oberflächenbereiche so ähnlich sind, dass solche Abhängigkeiten *häufig* funktionieren. Wenn das Paket jedoch versucht, eine .NET-API zu verwenden, die nicht in .NET Core vorhanden ist, wird eine Laufzeitausnahme gefunden. Aus diesem Grund sollten Sie auf .NET Framework-Pakete nur verweisen, wenn keine anderen Optionen verfügbar sind, und verstehen, dass dies eine Testlast mit sich bringt.

Wenn auf Pakete verwiesen wird, auf die nicht auf .NET Core oder .NET Standard ausgerichtet ist, müssen Sie über andere Alternativen nachdenken:

- Gibt es andere ähnliche Pakete, die stattdessen verwendet werden können? Manchmal veröffentlichen NuGet-Autoren separate ' Core-Versionen ihrer Bibliotheken, die speziell auf .NET Core abzielen. Enterprise Library-Pakete sind ein Beispiel für die Community-Veröffentlichung ". NetCore"-Alternativen. In anderen Fällen sind neuere SDKs für einen bestimmten Dienst (manchmal mit unterschiedlichen Paketnamen) für .NET Standard verfügbar. Wenn keine Alternativen verfügbar sind, können Sie mit den auf .NET Framework ausgerichteten Paketen fortfahren, wobei Sie berücksichtigen müssen, dass Sie sie gründlich testen müssen, sobald Sie auf .NET Core ausgeführt werden.

Das Bean Trader-Beispiel hat die folgenden NuGet-Abhängigkeiten der obersten Ebene:

- [**Castle.Windsor, Version 4.1.1**](https://www.castleproject.org/projects/windsor/)  

  Dieses Paket zielt auf .NET Standard 1.6 ab, sodass es auf .NET Core funktioniert.

- [**Microsoft.CodeAnalysis.FxCopAnalyzers, Version 2.6.3**](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.3)  
  Dies ist ein Metapaket, daher ist nicht sofort klar, welche Plattformen es unterstützt, aber die [Dokumentation](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisfxcopanalyzers) zeigt an, dass die neueste Version (2.9.2) sowohl für .NET Framework als auch für .NET Core funktioniert.

- [**Nito.AsyncEx, Version 4.0.1**](https://www.nuget.org/packages/Nito.AsyncEx/4.0.1)  

  Dieses Paket zielt nicht auf .NET Core ab, aber die neuere Version 5.0. Dies ist bei der Migration üblich, da viele NuGet-Pakete kürzlich .NET Standard-Unterstützung hinzugefügt haben, ältere Projektversionen jedoch nur auf .NET Framework abzielen. Wenn der Versionsunterschied nur ein kleiner Versionsunterschied ist, ist es oft einfach, auf die neuere Version zu aktualisieren. Da es sich um eine wichtige Versionsänderung handelt, müssen Sie ein vorsichtiges Upgrade durchführen, da es zu Änderungen im Paket führen könnte. Es gibt jedoch einen Weg nach vorn, der gut ist.

- [**MahApps.Metro, Version 1.6.5**](https://www.nuget.org/packages/MahApps.Metro/1.6.5)  

  Dieses Paket zielt auch nicht auf .NET Core ab, sondern verfügt über eine neuere Vorabversion (2.0-alpha), die dies tut. Auch hier müssen Sie auf die bahnbrechenden Änderungen achten, aber das neuere Paket ist ermutigend.

Die NuGet-Abhängigkeiten des Bean Trader-Beispiels zielen entweder auf .NET Standard/.NET Core ab oder verfügen über neuere Versionen, sodass es hier wahrscheinlich keine Blockierungsprobleme geben wird.

### <a name="upgrade-nuget-packages"></a>Aktualisieren von NuGet-Paketen

Wenn möglich, wäre es gut, die Versionen von Paketen, die nur auf .NET Core oder .NET Standard abzielen, mit neueren Versionen zu diesem Zeitpunkt zu aktualisieren (wobei das Projekt immer noch auf .NET Framework abzielt), um änderungen dezentrale Änderungen frühzeitig zu ermitteln und zu beheben.

Wenn Sie keine wesentlichen Änderungen an der vorhandenen .NET Framework-Version der App vornehmen möchten, kann dies warten, bis Sie eine neue Projektdatei für .NET Core haben. Das vorherige Upgrade der NuGet-Pakete auf .NET Core-kompatible Versionen erleichtert den Migrationsprozess jedoch noch einfacher, wenn Sie die neue Projektdatei erstellen, und verringert die Anzahl der Unterschiede zwischen den .NET Framework- und .NET Core-Versionen der App.

Mit dem Bean Trader-Beispiel können alle erforderlichen Upgrades einfach durchgeführt werden (mit Visual Studio NuGet-Paketmanager) mit einer Ausnahme: Ein Upgrade von **MahApps.Metro 1.6.5** auf **2.0** zeigt brechende Änderungen im Zusammenhang mit Design- und Akzentverwaltungs-APIs.

Im Idealfall wird die App aktualisiert, um die neuere Version des Pakets zu verwenden (da dies wahrscheinlicher auf .NET Core funktioniert). In einigen Fällen ist dies jedoch möglicherweise nicht durchführbar. Aktualisieren Sie **MahApps.Metro** in diesen Fällen nicht, da die erforderlichen Änderungen nicht trivial sind und sich dieses Tutorial auf die Migration zu .NET Core 3 und nicht auf **MahApps.Metro 2 konzentriert.** Außerdem ist dies eine risikoarme .NET Framework-Abhängigkeit, da die Bean Trader-App nur einen kleinen Teil von **MahApps.Metro**ausübt. Natürlich müssen Tests durchgeführt werden, um sicherzustellen, dass alles funktioniert, sobald die Migration abgeschlossen ist. Wäre dies ein reales Szenario, wäre es gut, ein Problem einzureichen, um die Arbeit zu verfolgen, um zu **MahApps.Metro** Version 2.0 zu wechseln, da die Migration jetzt nicht erfolgt, hinterlässt einige technische Schulden.

Sobald die NuGet-Pakete auf aktuelle `<PackageReference>` Versionen aktualisiert wurden, sollte die Artikelgruppe in der Projektdatei des Bean Trader-Beispiels wie folgt aussehen.

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

Sobald Sie den Status der NuGet-Abhängigkeiten Ihres Projekts verstanden haben, sollten Sie als nächstes die .NET Framework-API-Abhängigkeiten berücksichtigen. Das [.NET Portability Analyzer-Tool](../../standard/analyzers/portability-analyzer.md) ist nützlich, um zu verstehen, welche der .NET-APIs, die Ihr Projekt verwendet, auf anderen .NET-Plattformen verfügbar sind.

Das Tool kommt als [Visual Studio-Plugin](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer), ein [Befehlszeilen-Tool](https://github.com/Microsoft/dotnet-apiport/releases), oder in eine [einfache GUI](https://github.com/Microsoft/dotnet-apiport-ui)eingewickelt , die seine Optionen vereinfacht. Sie können mehr über die Verwendung von .NET Portability Analyzer (API Port) mithilfe der GUI in den [Porting-Desktop-Apps zu .NET](https://devblogs.microsoft.com/dotnet/porting-desktop-apps-to-net-core/) Core-Blogbeitrag lesen. Wenn Sie die Befehlszeile verwenden möchten, sind die folgenden Schritte erforderlich:

1. Laden Sie [den .NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport/releases) herunter, wenn Sie ihn noch nicht haben.
1. Stellen Sie sicher, dass die .NET Framework-App erfolgreich portiert wird (dies ist unabhängig vor der Migration eine gute Idee).
1. Führen Sie API Port mit einer solchen Befehlszeile aus.

    ```console
    ApiPort.exe analyze -f <PathToBeanTraderBinaries> -r html -r excel -t ".NET Core"
    ```

    Das `-f` Argument gibt den Pfad an, der die zu analysierenden Binärdateien enthält. Das `-r` Argument gibt an, welches Ausgabedateiformat Sie verwenden möchten. Das `-t` Argument gibt an, gegen welche .NET-Plattform die API-Nutzung analysiert werden soll. In diesem Fall soll .NET Core.

Wenn Sie den HTML-Bericht öffnen, werden im ersten Abschnitt alle analysierten Binärdateien und der Prozentsatz der von ihnen eingesetzten .NET-APIs auf der Zielplattform aufgeführt. Der Prozentsatz ist für sich genommen nicht aussagekräftig. Was noch nützlicher ist, ist, die spezifischen APIs zu sehen, die fehlen. Wählen Sie dazu entweder einen Assemblynamen aus, oder scrollen Sie zu den Berichten für einzelne Assemblys nach unten.

Konzentrieren Sie sich auf die Assemblys, für die Sie den Quellcode besitzen. Im Bean Trader ApiPort-Bericht sind beispielsweise viele Binärdateien aufgeführt, aber die meisten von ihnen gehören zu NuGet-Paketen. `Castle.Windsor`zeigt, dass dies von einigen System.Web-APIs abhängt, die in .NET Core fehlen. Dies ist kein Problem, da `Castle.Windsor` Sie zuvor überprüft haben, dass .NET Core unterstützt wird. Es ist üblich, dass NuGet-Pakete über unterschiedliche Binärdateien für die Verwendung mit `Castle.Windsor` verschiedenen .NET-Plattformen verfügen, sodass es irrelevant ist, ob die .NET Framework-Version von System.Web-APIs verwendet oder nicht, solange das Paket auch auf .NET Standard oder .NET Core abzielt (was dies tut).

Mit dem Bean Trader-Beispiel ist die einzige Binärdatei, die Sie berücksichtigen müssen, **BeanTraderClient** und der Bericht zeigt, dass nur zwei .NET-APIs fehlen: `System.ServiceModel.ClientBase<T>.Close` und `System.ServiceModel.ClientBase<T>.Open`.

![BeanTraderClient-Portabilitätsbericht](./media/convert-project-from-net-framework/portability-report.png)

Es ist unwahrscheinlich, dass sie Probleme blockieren, da WCF-Client-APIs (meist) auf .NET Core unterstützt werden, sodass für diese zentralen APIs Alternativen verfügbar sein müssen. Wenn Sie sich `System.ServiceModel`die .NET Core-Oberfläche <https://apisof.net>von sehen (verwenden ), sehen Sie stattdessen, dass es stattdessen Async-Alternativen in .NET Core gibt.

Basierend auf diesem Bericht und der vorherigen NuGet-Abhängigkeitsanalyse scheint es keine größeren Probleme bei der Migration des Bean Trader-Beispiels zu .NET Core zu geben. Sie sind bereit für den nächsten Schritt, in dem Sie die Migration tatsächlich starten.

## <a name="migrating-the-project-file"></a>Migrieren der Projektdatei

Wenn Ihre App nicht das neue [Projektdateiformat im SDK-Stil](../../core/tools/csproj.md)verwendet, benötigen Sie eine neue Projektdatei, um .NET Core als Ziel zu verwenden. Sie können die vorhandene csproj-Datei ersetzen oder, wenn Sie es vorziehen, das vorhandene Projekt im aktuellen Zustand unberührt zu lassen, eine neue csproj-Datei hinzufügen, die auf .NET Core abzielt. Sie können Versionen der App für .NET Framework und .NET Core mit einer einzigen Projektdatei `<TargetFrameworks>` im SDK-Stil mit [Multi-Targeting](../../standard/library-guidance/cross-platform-targeting.md) (unter Angabe mehrerer Ziele) erstellen.

Um die neue Projektdatei zu erstellen, können Sie ein neues `dotnet new wpf` WPF-Projekt in Visual Studio erstellen oder den Befehl in einem temporären Verzeichnis verwenden, um die Projektdatei zu generieren und sie dann an den richtigen Speicherort zu kopieren/umbenennen. Es gibt auch ein von der Community erstelltes Tool, [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017), das einen Teil der Projektdateimigration automatisieren kann. Das Tool ist hilfreich, benötigt aber immer noch einen Benutzer, um die Ergebnisse zu überprüfen, um sicherzustellen, dass alle Details der Migration korrekt sind. Ein besonderer Bereich, den das Tool nicht optimal behandelt, ist das Migrieren von NuGet-Paketen aus *packages.config-Dateien.* Wenn das Tool auf einer Projektdatei ausgeführt wird, die immer noch eine *packages.config-Datei* verwendet, um auf NuGet-Pakete zu verweisen, wird es automatisch zu `<PackageReference>` Elementen migriert, fügt `<PackageReference>` jedoch Elemente für *alle* Pakete hinzu, anstatt nur die Pakete der obersten Ebene. Wenn Sie bereits`<PackageReference>` zu Elementen mit Visual Studio migriert haben (wie in diesem Beispiel), kann das Tool bei der restlichen Konvertierung helfen. Wie Scott Hanselman empfiehlt in [seinem Blog-Beitrag über die Migration von csproj-Dateien](https://www.hanselman.com/blog/UpgradingAnExistingNETProjectFilesToTheLeanNewCSPROJFormatFromNETCore.aspx), Portieren von Hand ist pädagogisch und wird bessere Ergebnisse geben, wenn Sie nur ein paar Projekte zu portieren haben. Aber wenn Sie Dutzende oder Hunderte von Projektdateien portieren, dann kann ein Tool wie [CsprojToVs2017] eine Hilfe sein.

Um eine neue Projektdatei für das Bean Trader-Beispiel zu erstellen, `dotnet new wpf` führen Sie in einem temporären Verzeichnis aus und verschieben Sie die generierte *.csproj-Datei* in den *BeanTraderClient-Ordner* und benennen Sie sie in **BeanTraderClient.Core.csproj**um.

Da das neue Projektdateiformat automatisch C-Dateien, *Resx-Dateien* und XAML-Dateien enthält, die es in oder unter seinem Verzeichnis findet, ist die Projektdatei bereits fast vollständig! Um die Migration abzuschließen, öffnen Sie die alten und neuen Projektdateien nebeneinander, und schauen Sie sich die alte an, um zu sehen, ob die darin enthaltenen Informationen migriert werden müssen. Im Beispielfall Bean Trader sollten die folgenden Elemente in das neue Projekt kopiert werden:

- Die `<RootNamespace>` `<AssemblyName>`, `<ApplicationIcon>` und Eigenschaften sollten alle kopiert werden.

- Sie müssen der `<GenerateAssemblyInfo>false</GenerateAssemblyInfo>` neuen Projektdatei auch eine Eigenschaft hinzufügen, da das Bean `[AssemblyTitle]`Trader-Beispiel Attribute auf Assemblyebene (wie ) in einer AssemblyInfo.cs-Datei enthält. Standardmäßig werden neue Projekte im SDK-Stil diese Attribute automatisch basierend auf Eigenschaften in der csproj-Datei automatisch generieren. Da dies in diesem Fall nicht geschehen soll (die automatisch generierten Attribute würden mit denen `<GenerateAssemblyInfo>`von AssemblyInfo.cs in Konflikt stehen), deaktivieren Sie die automatisch generierten Attribute mit .

- Obwohl *resx-Dateien* automatisch als eingebettete Ressourcen eingeschlossen werden, sind andere `<Resource>` Elemente wie Bilder nicht enthalten. Kopieren Sie `<Resource>` also die Elemente zum Einbetten von Bild- und Symboldateien. Sie können die Png-Referenzen auf eine einzelne Zeile vereinfachen, indem Sie `<Resource Include="**\*.png" />`die Unterstützung des neuen Projektdateiformats für Globbing-Muster verwenden: .

- Ebenso `<None>` werden Elemente automatisch eingeschlossen, aber standardmäßig nicht in das Ausgabeverzeichnis kopiert. Da das Bean Trader-Projekt `<None>` ein Element enthält, das in das Ausgabeverzeichnis kopiert *wird* (mit `PreserveNewest` Verhalten), müssen Sie das automatisch ausgefüllte `<None>` Element für diese Datei wie diese aktualisieren.

  ```xml
  <None Update="BeanTrader.pfx">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </None>
  ```

- Das Bean Trader-Beispiel enthält eine XAML-Datei (Default.Accent.xaml) als `Content` (anstelle als `Page`) da in dieser Datei definierte Designs und Akzente zur Laufzeit aus dem XAML der Datei geladen werden, anstatt in die App selbst eingebettet zu werden. Das neue Projektsystem enthält diese `<Page>`Datei jedoch automatisch als , da es sich um eine XAML-Datei handelt. Sie müssen also sowohl die XAML-Datei`<Page Remove="**\Default.Accent.xaml" />`als Seite ( ) entfernen als auch als Inhalt hinzufügen.

  ```xml
  <Content Include="Resources\Themes\Default.Accent.xaml">
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </Content>
  ```

- Fügen Sie schließlich NuGet-Referenzen hinzu, indem Sie die `<ItemGroup>` mit allen `<PackageReference>` Elementen kopieren. Wenn Sie die NuGet-Pakete zuvor nicht auf .NET Core-kompatible Versionen aktualisiert haben, können Sie dies jetzt tun, da sich die Paketverweise in einem .NET Core-spezifischen Projekt befinden.

An dieser Stelle sollte es möglich sein, das neue Projekt zur BeanTrader-Lösung hinzuzufügen und es in Visual Studio zu öffnen. Das Projekt sollte im **Projektmappen-Explorer**korrekt aussehen und `dotnet restore BeanTraderClient.Core.csproj` Pakete erfolgreich wiederherstellen (mit zwei erwarteten Warnungen im Zusammenhang mit der MahApps.Metro-Version, die Sie für .NET Framework verwenden).

Obwohl es möglich ist, beide Projektdateien nebeneinander zu halten (und sogar wünschenswert sein kann, wenn Sie das alte Projekt so weiterbauen möchten, wie es war), erschwert es den Migrationsprozess (die beiden Projekte versuchen, dieselben Ordner bin und obj zu verwenden) und ist normalerweise nicht erforderlich. Wenn Sie sowohl für .NET Core- als auch für `<TargetFramework>netcoreapp3.0</TargetFramework>` .NET Framework-Ziele `<TargetFrameworks>netcoreapp3.0;net472</TargetFrameworks>` erstellen möchten, können Sie die Eigenschaft in der neuen Projektdatei stattdessen ersetzen. Löschen Sie für das Bean Trader-Beispiel die alte Projektdatei (BeanTraderClient.csproj), da sie nicht mehr benötigt wird. Wenn Sie es vorziehen, beide Projektdateien beizubehalten, stellen Sie sicher, dass sie auf unterschiedliche Ausgabe- und Zwischenausgabepfade erstellt werden.

## <a name="fix-build-issues"></a>Beheben von Buildproblemen

Der dritte Schritt des Portierungsprozesses besteht darin, das Projekt zu erstellen. Einige Apps werden bereits erfolgreich erstellt, sobald die Projektdatei in ein Projekt im SDK-Stil konvertiert wurde. Wenn das der Fall für Ihre App ist, herzlichen Glückwunsch! Sie können zu Schritt 4 gehen. Andere Apps benötigen einige Updates, um sie für .NET Core erstellen zu lassen. Wenn Sie versuchen, jetzt beispielsweise auf dem Bean Trader-Beispielprojekt auszuführen `dotnet build` (oder es in Visual Studio zu erstellen), gibt es viele Fehler, aber Sie werden sie schnell beheben.

### <a name="systemservicemodel-references-and-microsoftwindowscompatibility"></a>System.ServiceModel-Referenzen und Microsoft.Windows.Compatibility

Eine häufige Fehlerquelle sind fehlende Verweise für APIs, die für .NET Core verfügbar sind, aber nicht automatisch im .NET Core-App-Metapaket enthalten sind. Um dies zu beheben, sollten Sie auf das `Microsoft.Windows.Compatibility` Paket verweisen. Das Kompatibilitätspaket enthält eine breite Palette von APIs, die in Windows-Desktop-Apps üblich sind, z. B. WCF-Client, Verzeichnisdienste, Registrierung, Konfiguration, ACLs-APIs und mehr.

Mit dem Bean Trader-Beispiel sind die meisten <xref:System.ServiceModel> Buildfehler auf fehlende Typen zurückzuführen. Diese können durch Verweisen auf die erforderlichen WCF NuGet-Pakete behoben werden. WCF-Client-APIs gehören jedoch `Microsoft.Windows.Compatibility` zu den im Paket vorhandenen ApIs, daher ist das Verweisen auf das Kompatibilitätspaket eine noch bessere Lösung (da es auch alle Probleme im Zusammenhang mit APIs sowie Lösungen für die WCF-Probleme behandelt, die das Kompatibilitätspaket zur Verfügung stellt). Das `Microsoft.Windows.Compatibility` Paket hilft in den meisten .NET Core 3.0 WPF- und WinForms-Portierungsszenarien. Nach dem Hinzufügen des `Microsoft.Windows.Compatibility`NuGet-Verweises zu bleibt nur ein Buildfehler übrig!

### <a name="cleaning-up-unused-files"></a>Bereinigen nicht verwendeter Dateien

Eine Art von Migrationsproblem, das häufig auftaucht, bezieht sich auf C-Dateien und XAML-Dateien, die zuvor nicht im Build enthalten waren und von den neuen SDK-Projekten übernommen werden, die *alle* Quellen automatisch enthalten.

Der nächste Buildfehler, den Sie im Bean Trader-Beispiel sehen, bezieht sich auf eine fehlerhafte Schnittstellenimplementierung in *OldUnusedViewModel.cs*. Der Dateiname ist ein Hinweis, aber bei der Überprüfung werden Sie feststellen, dass diese Quelldatei falsch ist. Zuvor wurden keine Probleme verursacht, da es nicht im ursprünglichen .NET Framework-Projekt enthalten war. Quelldateien, die auf dem Datenträger vorhanden waren, aber nicht im alten *csproj* enthalten waren, werden jetzt automatisch eingeschlossen.

Bei einmaligen Problemen wie diesem ist es einfach, mit dem vorherigen *csproj* zu vergleichen, um `<Compile Remove="" />` zu bestätigen, dass die Datei nicht benötigt wird, und dann entweder oder, wenn die Quelldatei nirgendwo mehr benötigt wird, sie zu löschen. In diesem Fall ist es sicher, *einfach OldUnusedViewModel.cs*zu löschen.

Wenn Sie viele Quelldateien haben, die auf diese Weise ausgeschlossen werden müssen, können `<EnableDefaultCompileItems>` Sie die automatische Einbindung von C-Dateien deaktivieren, indem Sie die Eigenschaft in der Projektdatei auf false festlegen. Anschließend können Sie `<Compile Include>` Elemente aus der alten Projektdatei in die neue kopieren, um nur Quellen zu erstellen, die Sie einschließen möchten. Auf `<EnableDefaultPageItems>` ähnliche Weise kann verwendet werden, um die `<EnableDefaultItems>` automatische Integration von XAML-Seiten zu deaktivieren und beide mit einer einzigen Eigenschaft zu steuern.

### <a name="a-brief-aside-on-multi-pass-compilers"></a>Eine kurze Nebenbemerkung zu Multipass-Compilern

Nachdem Sie die beleidigende Datei aus dem Bean Trader-Beispiel entfernt haben, können Sie neu erstellen und erhalten vier Fehler. Hatten Sie nicht vorher eine? Warum ist die Anzahl der Fehler gestiegen? Der C-Compiler ist ein [Multi-Pass-Compiler](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes). Dies bedeutet, dass es durch jede Quelldatei zweimal geht. Zunächst betrachtet der Compiler nur Metadaten und Deklarationen in jeder Quelldatei und identifiziert Probleme auf Deklarationsebene. Das sind die Fehler, die Sie behoben haben. Dann wird der Code erneut durchgehen, um die C-Quelle in IL zu erstellen. Dies sind die zweiten Fehler, die Sie jetzt sehen.

> [!NOTE]
> Der C-Compiler führt [mehr als nur zwei Durchläufe](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes)durch, aber das Endergebnis ist, dass Compilerfehler bei großen Codeänderungen wie diesem in zwei Wellen auftreten.

### <a name="third-party-dependency-fixes-castlewindsor"></a>Abhängigkeitsfixes von Drittanbietern (Castle.Windsor)

Eine weitere Problemklasse, die in einigen Migrationsszenarien auftritt, sind API-Unterschiede zwischen .NET Framework- und .NET Core-Versionen von Abhängigkeiten. Selbst wenn ein NuGet-Paket sowohl auf .NET Framework als auch auf .NET Standard oder .NET Core abzielt, können unterschiedliche Bibliotheken für die Verwendung mit unterschiedlichen .NET-Zielen vorhanden sein. Dadurch können die Pakete viele verschiedene .NET-Plattformen unterstützen, die möglicherweise unterschiedliche Implementierungen erfordern. Dies bedeutet auch, dass es kleine API-Unterschiede in den Bibliotheken geben kann, wenn verschiedene .NET-Plattformen ausgerichtet sind.

Der nächste Satz von Fehlern, die Sie im Bean Trader-Beispiel sehen, bezieht sich auf `Castle.Windsor` APIs. Das .NET Core Bean Trader-Projekt `Castle.Windsor` verwendet dieselbe Version des auf .NET Framework ausgerichteten Projekts (4.1.1), aber die Implementierungen für diese beiden Plattformen unterscheiden sich geringfügig.

In diesem Fall werden die folgenden Probleme angezeigt, die behoben werden müssen:

1. `Castle.MicroKernel.Registration.Classes.FromThisAssembly`ist auf .NET Core nicht verfügbar. Es ist jedoch die `Classes.FromAssemblyContaining` ähnliche API verfügbar, so `Classes.FromThisAssembly()` dass wir `Classes.FromAssemblyContaining(t)`beide `t` Verwendungen von durch Aufrufe von ersetzen können, wobei der Typ der Aufruf ist.
1. Ebenso in *Bootstrapper.cs*Bootstrapper.cs `Castle.Windsor.Installer.FromAssembly`, . Dies ist auf .NET Core nicht verfügbar. Stattdessen kann dieser Aufruf `FromAssembly.Containing(typeof(Bootstrapper))`durch ersetzt werden.

### <a name="updating-wcf-client-usage"></a>Aktualisieren der WCF-Clientnutzung

Nachdem die `Castle.Windsor` Unterschiede behoben wurden, ist der letzte verbleibende Buildfehler `BeanTraderServiceClient` im .NET `DuplexClientBase`Core Bean Trader-Projekt, dass (das von ableitet) keine `Open` Methode hat. Dies ist nicht verwunderlich, da es sich um eine API handelt, die vom .NET Portability Analyzer zu Beginn dieses Migrationsprozesses hervorgehoben wurde. Ein `BeanTraderServiceClient` Blick auf die Aufmerksamkeit lenkt unsere Aufmerksamkeit jedoch auf ein größeres Problem. Dieser WCF-Client wurde vom Tool [Svcutil.exe](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) automatisch generiert.

**Von Svcutil generierte WCF-Clients sind für die Verwendung in .NET Framework vorgesehen.**

Lösungen, die svcutil-generierte WCF-Clients verwenden, müssen .NET Standardkompatible Clients für die Verwendung mit .NET Core regenerieren. Einer der Hauptgründe, warum die alten Clients nicht funktionieren, ist, dass sie für die Definition von WCF-Bindungen und Endpunkten von der App-Konfiguration abhängig sind. Da .NET Standard-WCF-APIs plattformübergreifend arbeiten können (wobei System.Configuration-APIs nicht verfügbar sind), müssen WCF-Clients für .NET Core- und .NET-Standardszenarien Bindungen und Endpunkte programmgesteuert und nicht in der Konfiguration definieren.

Tatsächlich muss jede WCF-Clientnutzung, `<system.serviceModel>` die vom Abschnitt app.config abhängt (ob mit Svcutil oder manuell erstellt), geändert werden, um auf .NET Core zu funktionieren.

Es gibt zwei Möglichkeiten, .NET Standardkompatible WCF-Clients automatisch zu generieren:

- Das `dotnet-svcutil` Tool ist ein .NET-Tool, das WCF-Clients auf eine Ähnliche generiert, die der früheren Arbeitsweise von Svcutil ähnelt.
- Visual Studio kann WCF-Clients mithilfe der [WCF-Webdienstreferenzoption](../../core/additional-tools/wcf-web-service-reference-guide.md) der Funktion "Verbundene Dienste" generieren.

Beide Ansätze funktionieren gut. Alternativ können Sie den WCF-Clientcode selbst schreiben. Für dieses Beispiel habe ich die Visual Studio Connected Service-Funktion verwendet. Klicken Sie dazu mit der rechten Maustaste auf das *BeanTraderClient.Core-Projekt* im Lösungs-Explorer von Visual Studio, und wählen Sie**Connected Service** **hinzufügen** > aus. Wählen Sie als Nächstes den WCF-Webdienstreferenzanbieter aus. Dadurch wird ein Dialogfeld ausgelöst, in dem Sie die Adresse`localhost:8080` des Backend Bean Trader-Webdienstes (wenn Sie den Server lokal ausführen) und den Namespace angeben können, den generierte Typen verwenden sollen ( beanTrader.Service , z. B.**BeanTrader.Service).**

![WCF Web Service Reference Connected Service Dialog](./media/convert-project-from-net-framework/connected-service-dialog.png)

Nachdem Sie die Schaltfläche **Fertig stellen** ausgewählt haben, wird dem Projekt ein neuer Connected Services-Knoten hinzugefügt, und unter diesem Knoten wird eine Reference.cs-Datei hinzugefügt, die den neuen .NET Standard WCF-Client für den Zugriff auf den Bean Trader-Dienst enthält. Wenn Sie sich `GetEndpointAddress` `GetBindingForEndpoint` die oder Methoden in dieser Datei ansehen, werden Sie sehen, dass Bindungen und Endpunkte jetzt programmgesteuert generiert werden (anstelle von App config). Die Funktion "Verbundene Dienste hinzufügen" kann auch Verweise auf einige System.ServiceModel-Pakete in der Projektdatei hinzufügen, die nicht benötigt werden, da alle erforderlichen WCF-Pakete über Microsoft.Windows.Compatibility enthalten sind. Überprüfen Sie die csproj, um festzustellen, ob zusätzliche System.ServiceModel-Elemente `<PackageReference>` hinzugefügt wurden, und wenn ja, entfernen Sie sie.

Unser Projekt hat jetzt neue WCF-Clientklassen (in *Reference.cs*), aber es hat auch noch die alten (in BeanTrader.cs). An dieser Stelle gibt es zwei Möglichkeiten:

- Wenn Sie das ursprüngliche .NET Framework-Projekt (neben dem neuen .NET Core-Zielprojekt) erstellen möchten, können Sie ein `<Compile Remove="BeanTrader.cs" />` Element in der csproj-Datei des .NET Core-Projekts verwenden, sodass die .NET Framework- und .NET Core-Versionen der App unterschiedliche WCF-Clients verwenden. Dies hat den Vorteil, dass das vorhandene .NET Framework-Projekt unverändert bleibt, hat jedoch den Nachteil, dass Code, der die generierten WCF-Clients verwendet, `#if` im .NET Core-Fall möglicherweise etwas anders sein muss als im .NET Framework-Projekt.

- Wenn hingegen eine Codeabwanderung im vorhandenen .NET Framework-Projekt akzeptabel ist, können Sie *BeanTrader.cs* alle zusammen entfernen. Da der neue WCF-Client für .NET Standard erstellt wurde, funktioniert er sowohl in .NET Core- als auch in .NET Framework-Szenarien. Wenn Sie zusätzlich zu .NET Core für .NET Framework erstellen (entweder durch Multi-Targeting oder durch zwei csproj-Dateien), können Sie diese neue *Reference.cs-Datei* für beide Ziele verwenden. Dieser Ansatz hat den Vorteil, dass der Code nicht bifurcate muss, um zwei verschiedene WCF-Clients zu unterstützen. der gleiche Code wird überall verwendet. Der Nachteil besteht darin, dass es sich um die Änderung des (vermutlich stabilen) .NET Framework-Projekts handelt.

Im Fall des Bean Trader-Beispiels können Sie kleine Änderungen am ursprünglichen Projekt vornehmen, wenn diemigration dadurch vereinfacht wird. Führen Sie daher die folgenden Schritte aus, um die WCF-Clientnutzung abzugleichen:

01. Fügen Sie die neue Reference.cs Datei zum .NET Framework *BeanTraderClient.csproj-Projekt* hinzu, indem Sie das Kontextmenü "Vorhandenes Element hinzufügen" aus dem Projektmappen-Explorer verwenden. Achten Sie darauf, 'als Link' hinzuzufügen, damit dieselbe Datei von beiden Projekten verwendet wird (im Gegensatz zum Kopieren der C-Datei). Wenn Sie für .NET Core und .NET Framework mit einem einzelnen csproj (mit Multi-Targeting) erstellen, ist dieser Schritt nicht erforderlich.

01. Löschen Sie *BeanTrader.cs*.

01. Der neue WCF-Client ähnelt dem alten, aber eine Reihe von Namespaces im generierten Code unterscheiden sich. Aus diesem Grund ist es notwendig, das Projekt so zu aktualisieren, dass WCF-Clienttypen von BeanTrader.Service (oder dem beliebigen Namespacenamen) anstelle von BeanTrader.Model oder ohne Namespace verwendet werden. Das Erstellen von *BeanTraderClient.Core.csproj* hilft ihnen, zu ermitteln, wo diese Änderungen vorgenommen werden müssen. Korrekturen werden sowohl in den XAML-Quelldateien als auch in XAML-Quelldateien benötigt.

01. Schließlich stellen Sie fest, dass ein Fehler in *BeanTraderServiceClientFactory.cs* vorliegt, da sich die verfügbaren Konstruktoren für den `BeanTraderServiceClient` Typ geändert haben. Früher war es möglich, `InstanceContext` ein Argument zu `CallbackHandler` liefern `Castle.Windsor` (das mit einem aus dem IoC-Container erstellt wurde). Die neuen Konstruktoren `CallbackHandler`erstellen neue s. Es gibt jedoch Konstruktoren `BeanTraderServiceClient`im Basistyp von, die ihren Wünschen entsprechen. Da der automatisch generierte WCF-Clientcode alle in Partiellenklassen vorhanden ist, können Sie ihn problemlos erweitern. Erstellen Sie dazu eine neue Datei mit dem Namen *BeanTraderServiceClient.cs* und dann eine Partipartenklasse mit demselben Namen (mit dem Namespace BeanTrader.Service). Fügen Sie dann dem teilartiger Typ einen Konstruktor hinzu, wie hier gezeigt.

    ```csharp
    public BeanTraderServiceClient(System.ServiceModel.InstanceContext callbackInstance) :
        base(callbackInstance, EndpointConfiguration.NetTcpBinding_BeanTraderService)
            { }
    ```

Mit diesen Änderungen wird das Bean Trader-Beispiel nun einen neuen .NET Standard-kompatiblen WCF-Client verwenden, und Sie können die letzte Korrektur des Änderns des `Open` Aufrufs in *TradingService.cs* stattdessen vornehmen. `await OpenAsync`

Nachdem die WCF-Probleme behoben wurden, wird die .NET Core-Version des Bean Trader-Beispiels jetzt sauber erstellt!

## <a name="runtime-testing"></a>Laufzeittests

Es ist leicht zu vergessen, dass die Migrationsarbeit nicht ausgeführt wird, sobald das Projekt sauber für .NET Core erstellt wird. Es ist wichtig, auch Zeit für das Testen der portierten App zu lassen. Stellen Sie nach erfolgreicher Erstellung der Dinge sicher, dass die App wie erwartet ausgeführt wird und funktioniert, insbesondere wenn Sie Pakete verwenden, die auf .NET Framework abzielen.

Lassen Sie uns versuchen, die portierte Bean Trader App zu starten und zu sehen, was passiert. Die App kommt nicht weit, bevor sie mit der folgenden Ausnahme fehlschlägt.

```output
System.Configuration.ConfigurationErrorsException: 'Configuration system failed to initialize'

Inner Exception
ConfigurationErrorsException: Unrecognized configuration section system.serviceModel.
```

Das macht natürlich Sinn. Denken Sie daran, dass WCF keine App-Konfiguration mehr verwendet, daher muss der alte Abschnitt system.serviceModel der Datei app.config entfernt werden. Der aktualisierte WCF-Client enthält alle gleichen Informationen in seinem Code, sodass der Konfigurationsabschnitt nicht mehr benötigt wird. Wenn der WCF-Endpunkt in app.config konfigurierbar sein soll, können Sie ihn als App-Einstellung hinzufügen und den WCF-Clientcode aktualisieren, um den WCF-Dienstendpunkt aus der Konfiguration abzurufen.

Nach dem Entfernen des Abschnitts system.serviceModel von *app.config*wird die App gestartet, schlägt jedoch mit einer anderen Ausnahme fehl, wenn sich ein Benutzer anmeldet.

```output
System.PlatformNotSupportedException: 'Operation is not supported on this platform.'
```

Die nicht unterstützte `Func<T>.BeginInvoke`API ist . Wie in [dotnet/corefx-5940](https://github.com/dotnet/corefx/issues/5940)erläutert, unterstützt .NET `BeginInvoke` `EndInvoke` Core die und Methoden für Delegattypen aufgrund zugrunde liegender Remoting-Abhängigkeiten nicht. Dieses Problem und seine Lösung werden im [Blogbeitrag "Migrating Delegate.BeginInvoke Calls for .NET Core"](https://devblogs.microsoft.com/dotnet/migrating-delegate-begininvoke-calls-for-net-core/) ausführlicher erläutert, aber der Kern ist, dass `BeginInvoke` und `EndInvoke` Aufrufe durch `Task.Run` (oder asynchrone Alternativen, wenn möglich) ersetzt werden sollten. Wenn Sie hier die `BeginInvoke` allgemeine Lösung anwenden, kann der Aufruf durch einen `Invoke` Aufruf ersetzt werden, der von `Task.Run`gestartet wird.

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

Nach dem `BeginInvoke` Entfernen der Nutzung wird die Bean Trader App erfolgreich auf .NET Core ausgeführt!

![Bean Trader läuft auf .NET Core](./media/convert-project-from-net-framework/running-on-core.png)

Alle Apps sind unterschiedlich, sodass die spezifischen Schritte zum Migrieren Ihrer eigenen Apps zu .NET Core variieren. Aber hoffentlich zeigt das Bean Trader-Beispiel den allgemeinen Workflow und die Arten von Problemen, die zu erwarten sind. Und trotz der Länge dieses Artikels waren die tatsächlichen Änderungen, die im Bean Trader-Beispiel erforderlich waren, um es auf .NET Core funktionieren zu lassen, ziemlich begrenzt. Viele Apps werden auf die gleiche Weise zu .NET Core migriert. mit begrenzten oder gar keinen Codeänderungen erforderlich.
