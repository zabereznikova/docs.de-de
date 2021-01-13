---
title: .NET-Standard
description: Erfahren Sie mehr über .NET Standard, dessen Versionen und die .NET-Implementierungen, von denen es unterstützt wird.
ms.date: 10/05/2020
ms.prod: dotnet
ms.technology: dotnet-standard
ms.custom: updateeachrelease
ms.assetid: c044882c-af15-45f2-96d1-534557a5ee9b
ms.openlocfilehash: 93fb10538441d939e95bb48dcdd0e61d9267dde0
ms.sourcegitcommit: c0b803bffaf101e12f071faf94ca21b46d04ff30
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/24/2020
ms.locfileid: "97765032"
---
# <a name="net-standard"></a>.NET-Standard

[.NET Standard](https://github.com/dotnet/standard) ist eine formale Spezifikation von .NET-APIs, die für verschiedene .NET-Implementierungen verfügbar sind. Die Motivation hinter .NET Standard war es, mehr Einheitlichkeit im .NET-Ökosystem zu erreichen. .NET 5 übernimmt jedoch einen anderen Ansatz, um diese Einheitlichkeit sicherzustellen. Durch diesen neuen Ansatz entfällt die Notwendigkeit von .NET Standard in vielen Szenarios. Weitere Informationen finden Sie später in diesem Artikel unter [.NET 5 und .NET Standard](#net-5-and-net-standard).

## <a name="net-implementation-support"></a>Unterstützung der .NET-Implementierung

Die verschiedenen .NET-Implementierungen verwenden spezifische Versionen von .NET Standard als Ziel. Jede .NET-Implementierung kündigt die höchste .NET Standardversion an, die von ihr unterstützt wird, was bedeutet, dass sie auch frühere Versionen unterstützt. .NET Framework 4.6 implementiert z. B. .NET Standard 1.3 und stellt damit alle APIs bereit, die in den Versionen 1.0 bis 1.3 von .NET Standard definiert sind. Auf ähnliche Weise implementiert .NET Framework 4.6.1 .NET Standard 1.4, während .NET 5.0 .NET Standard 2.1 implementiert.

In der folgenden Tabelle sind die **mindestens** erforderlichen Implementierungsversionen aufgeführt, die sämtliche .NET Standard-Versionen unterstützen. Dies bedeutet, dass höhere Versionen einer aufgelisteten Implementierung auch die entsprechende Version von .NET Standard unterstützen. Beispielsweise unterstützen .NET Core 2.1 und höhere Versionen auch .NET Standard 2.0 und frühere Versionen.

[!INCLUDE [net-standard-table](../../includes/net-standard-table.md)]

Führen Sie die folgenden Schritte aus, um die höchste Version von .NET Standard zu ermitteln, die Sie als Ziel verwenden können:

1. Suchen Sie die Zeile, die die .NET-Implementierung angibt, die Sie ausführen möchten.
1. Suchen Sie in dieser Zeile die Spalte, in der Ihre Version angegeben ist (von rechts nach links).
1. Die Spaltenüberschrift gibt die .NET Standard-Version an, die Ihr Ziel unterstützt. Sie können auch eine niedrigere .NET Standard-Version als Ziel verwenden. Auch höhere .NET Standard-Versionen unterstützen die Implementierung.
1. Wiederholen Sie diesen Vorgang für jede Plattform, die als Ziel verwendet werden soll. Wenn Sie mehrere Zielplattformen verwenden, sollten Sie die kleinste unterstützten Versionen auswählen. Wenn Sie .NET Standard z. B. auf .NET Framework 4.8 und .NET 5.0 ausführen möchten, ist die höchste .NET Standard-Version, die Sie verwenden können, .NET Standard 2.0.

### <a name="which-net-standard-version-to-target"></a>Auswahl der .NET Standard-Zielversion

Bei der Auswahl der .NET Standard-Zielversion sollten Sie diesen Kompromiss berücksichtigen:

- Je höher die Version, desto mehr APIs stehen für den Code Ihrer Bibliothek zur Verfügung.
- Je niedriger die Version, desto mehr Apps und Bibliotheken können Ihre Bibliothek verwenden.

Es wird empfohlen, die *niedrigste* mögliche Version von .NET Standard als Zielversion zu verwenden. Nachdem Sie also die höchste .NET Standard-Zielversion gefunden, gehen Sie folgendermaßen vor:

1. Wählen Sie die nächst niedrigere .NET Standard-Version als Zielversion, und erstellen Sie Ihr Projekt.
2. Wenn das Projekt erfolgreich erstellt wurde, wiederholen Sie Schritt 1. Andernfalls wählen Sie die nächst höhere Version als Zielversion aus, und das ist die Version, die Sie verwenden sollten.

Das Auswählen niedrigerer .NET Standard-Versionen führt jedoch zu mehreren Unterstützungsabhängigkeiten. Wenn Sie für Ihr Projekt .NET Standard 1.x auswählen, empfehlen wir *auch* .NET Standard 2.0 auszuwählen. Dies vereinfacht das Abhängigkeitsdiagramm für Benutzer Ihrer Bibliothek, die .NET Standard 2.0-kompatible Implementierungen verwenden, und reduziert die Anzahl von Paketen, die heruntergeladen werden müssen.

### <a name="net-standard-versioning-rules"></a>Regeln für die .NET Standard-Versionskontrolle

Es gibt zwei primäre Versionskontrollregeln:

- Additiv: .NET Standard-Versionen sind logisch konzentrische Kreise: höhere Versionen umfassen alle APIs früherer Versionen. Zwischen den Versionen gibt es keine die Lauffähigkeit der Anwendung beeinträchtigenden Änderungen.
- Unveränderlich: Nach der Auslieferung von .NET Standard-Versionen erfolgen keine Änderungen.

Nach Version 2.1 gibt es keine neuen .NET Standard-Versionen. Weitere Informationen finden Sie später in diesem Artikel unter [.NET 5 und .NET Standard](#net-5-and-net-standard).

## <a name="specification"></a>Spezifikation

Die Spezifikation von .NET Standard ist ein standardisierter Satz von APIs. Die Spezifikation wird durch Implementierungsprogramme von .NET verwaltet, insbesondere Microsoft (einschließlich des .NET Frameworks, .NET Core und Mono) und Unity.

### <a name="official-artifacts"></a>Offizielle Artefakte

Die offizielle Spezifikation ist eine Reihe von *CS*-Dateien zur Definition der APIs, die Bestandteile des Standards sind. Das [ref-Verzeichnis](https://github.com/dotnet/standard/tree/master/src/netstandard/ref) im [dotnet/standard-Repository](https://github.com/dotnet/standard) definiert die .NET Standard-APIs.

Das [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library)-Metapaket ([Quelle](https://github.com/dotnet/standard/blob/master/src/netstandard/pkg/NETStandard.Library.dependencies.props)) beschreibt den Satz von Bibliotheken, die (teilweise) eine oder mehrere Versionen von .NET Standard definieren.

Eine bestimmte Komponente wie `System.Runtime` beschreibt Folgendes:

- Teil von .NET Standard (nur der Bereich).
- Mehrere Versionen von .NET Standard für diesen Bereich.

Abgeleitete Elemente werden bereitgestellt, um ein einfacheres Lesen und bestimmte Entwicklungsszenarios (z.B. die Verwendung eines Compilers) zu ermöglichen.

- [API-Liste in Markdown](https://github.com/dotnet/standard/tree/master/docs/versions)
- Referenzassemblys, die als NuGet-Pakete verteilt und vom Metapaket [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library/) referenziert werden.

### <a name="package-representation"></a>Paketdarstellung

Das primäre Verteilungsinstrument für .NET Standard sind NuGet-Pakete. Implementierungen werden in einer Vielzahl von Methoden abgeleitet, die jeweils für die einzelnen .NET-Implementierungen geeignet sind.

NuGet-Pakete sind auf mindestens ein [Framework](frameworks.md) ausgerichtet. .NET Standard-Pakete zielen auf das Framework „.NET Standard“ ab. Sie können über den `netstandard` [komprimierten TFM](frameworks.md) (z. B. `netstandard1.4`) das .NET Standard-Framework als Ziel angeben. Bibliotheken, die auf mehreren Implementierungen von .NET ausgeführt werden sollen, sollten dieses Framework als Ziel haben. Ein Großteil der APIs sollte auf `netstandard2.0` ausgerichtet sein, da sich die Anzahl an verfügbaren APIs im Laufe der Versionen .NET Standard 1.6 und 2.0 mehr als verdoppelt hat.

Das Metapaket [`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library/) verweist auf den vollständigen Satz von NuGet-Paketen, die .NET Standard definieren.  Die gängigste Methode, `netstandard` als Ziel auszuwählen, ist das Verweisen auf dieses Metapaket. Es beschreibt und bietet Zugriff auf etwa 40 .NET-Bibliotheken und zugehörige APIs, die .NET Standard definieren. Sie können auf zusätzliche Pakete verweisen, die `netstandard` als Ziel verwenden, um Zugriff auf weitere APIs zu erhalten.

### <a name="versioning"></a>Versionskontrolle

Die Spezifikation ist nicht singulär, sondern eine Reihe linear versionierter APIs. In der ersten Version des Standards wird ein Basissatz von APIs eingerichtet. Nachfolgende Versionen fügen APIs hinzu und erben APIs, die in früheren Versionen definiert wurden. Es gibt keine festgelegte Möglichkeit zum Entfernen von APIs aus dem Standard.

.NET Standard ist weder spezifisch auf eine bestimmte .NET-Implementierung ausgelegt, noch entspricht die Spezifikation dem Versionierungsschema einer dieser Implementierungen.

Wie bereits erwähnt gibt es nach Version 2.1 keine neuen .NET Standard-Versionen.

## <a name="target-net-standard"></a>Verwenden von .NET Standard als Ziel

Sie können [.NET Standard-Bibliotheken](../core/tutorials/libraries.md) mithilfe einer Kombination aus dem `netstandard`-Framework und dem `NETStandard.Library`-Metapaket erstellen.

## <a name="net-framework-compatibility-mode"></a>Der .NET Framework-Kompatibilitätsmodus

Mit .NET Standard 2.0 wurde der .NET Framework-Kompatibilitätsmodus eingeführt. Mit diesem Kompatibilitätsmodus können .NET Standard-Projekte auf .NET Framework-Bibliotheken verweisen als wären sie für .NET Standard kompiliert. Es kann nicht für alle Projekte auf .NET Framework-Bibliotheken verwiesen werden. Dies ist zum Beispiel bei Bibliotheken der Fall, die Windows Presentation Foundation-APIs (WPF) verwenden.

Weitere Informationen finden Sie unter [Der .NET Framework-Kompatibilitätsmodus](../core/porting/third-party-deps.md#net-framework-compatibility-mode).

## <a name="net-standard-libraries-and-visual-studio"></a>.NET Standard-Bibliotheken und Visual Studio

Vergewissern Sie sich, dass unter Windows [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder Visual Studio 2017 Version 15.3 oder höher bzw. unter macOS [Visual Studio für Mac Version 7.1](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) oder höher installiert ist, damit Sie .NET Standard-Bibliotheken in Visual Studio erstellen können.

Wenn Sie nur .NET Standard 2.0-Bibliotheken in Ihren Projekten verarbeiten müssen, können Sie auch Visual Studio 2015 verwenden. Allerdings muss dabei der NuGet-Client 3.6 oder höher installiert sein. Sie können den NuGet-Client für Visual Studio 2015 auf der Seite [NuGet-Downloads](https://www.nuget.org/downloads) herunterladen.

## <a name="net-5-and-net-standard"></a>.NET 5 und .NET Standard

.NET 5 ist die Implementierung von .NET, die Microsoft aktiv entwickelt. Dabei handelt es sich um ein einzelnes Produkt mit einheitlichen Funktionen und APIs, die für Windows-Desktop-Apps und plattformübergreifende Konsolen-Apps, Clouddienste und Websites verwendet werden können. Die [.NET 5.0-Zielframeworkmoniker (TFMs)](frameworks.md) spiegeln diese große Bandbreite von Szenarios wider:

* `net5.0`

  Dieser TFM ist für Code bestimmt, der überall ausgeführt werden kann. Mit wenigen Ausnahmen sind nur Technologien enthalten, die plattformübergreifend funktionieren. Für .NET 5-Code ersetzt `net5.0` die TFMs `netcoreapp` und `netstandard`.

* `net5.0-windows`

  Dies ist ein Beispiel für [betriebssystemspezifische TFMs](frameworks.md#net-5-os-specific-tfms), die allen Elementen, auf die `net5.0` verweist, betriebssystemspezifische Funktionen hinzufügen.

### <a name="when-to-target-net50-vs-netstandard"></a>Informationen zum Abzielen auf „net5.0“ bzw. „netstandard“

Bei vorhandenem Code, der auf `netstandard` abzielt, ist es nicht erforderlich, den TFM in `net5.0` zu ändern. .NET 5.0 implementiert .NET Standard 2.1 und frühere Versionen. Der einzige Grund für das erneute Abzielen von .NET Standard auf .NET 5.0 wäre der Zugriff auf weitere Runtimefeatures, Sprachfeatures oder APIs. Sie müssen .NET 5.0 als Ziel verwenden, um beispielsweise C# 9 verwenden zu können. Sie können auch .NET 5.0 und .NET Standard als Zielversion festlegen, um Zugriff auf neuere Features zu erhalten und Ihre Bibliothek weiterhin anderen .NET-Implementierungen zur Verfügung zu stellen.

Hier finden Sie einige Richtlinien für neuen Code für .NET 5:

* App-Komponenten

  Wenn Sie Bibliotheken verwenden, um eine Anwendung in verschiedene Komponenten aufzuteilen, empfiehlt es sich, `net5.x` als Ziel zu verwenden, wobei `5.x` die früheste Version von .NET 5 ist, auf die Ihre Anwendung abzielen kann. Der Einfachheit halber sollten Sie für alle Projekte, aus denen Ihre Anwendung besteht, dieselbe .NET-Version verwenden. Folglich können Sie die gleichen BCL-Features von überall aus verwenden.

* Wiederverwendbare Bibliotheken

  Wenn Sie wiederverwendbare Bibliotheken erstellen, die NuGet enthalten soll, sollten Sie den Kompromiss zwischen Reichweite und verfügbaren Features berücksichtigen. .NET Standard 2.0 ist die neueste von .NET Framework unterstützte Version, sodass diese Spezifikation eine große Reichweite und relativ viele Features bietet. Es wird nicht empfohlen, .NET Standard 1.x als Ziel festzulegen, da Sie so die Anzahl der verfügbaren Features für eine minimal größere Reichweite reduzieren würden.

  Wenn Sie .NET Framework nicht unterstützen müssen, können Sie .NET Standard 2.1 oder .NET 5 verwenden. Es wird empfohlen, .NET Standard 2.1 zu überspringen und direkt .NET 5 zu verwenden. Die am häufigsten verwendeten Bibliotheken haben mit .NET Standard 2.0 und .NET 5 mehrere Zielversionen. Die Unterstützung von .NET Standard 2.0 bietet die größte Reichweite, während durch die Unterstützung von .NET 5 sichergestellt wird, dass Sie die neuesten Plattformfeatures für Kunden nutzen können, die bereits .NET 5 verwenden.

### <a name="net-standard-problems"></a>Probleme mit .NET Standard

Im Folgenden werden einige Probleme mit .NET Standard erläutert, die aufzeigen, warum .NET 5 die bessere Wahl beim Freigeben von Code für Plattformen und Workloads ist:

- Langsames Hinzufügen neuer APIs

  .NET Standard wurde als API-Satz erstellt, der von allen .NET-Implementierungen unterstützt werden sollte, sodass es einen Überprüfungsprozess für Vorschläge zum Hinzufügen neuer APIs gab. Ziel war es, nur die APIs zu standardisieren, die in alle aktuellen und zukünftigen .NET-Plattformen implementiert werden könnten. Dies hatte zur Folge, dass Sie möglicherweise einige Jahre warten mussten, bis ein Feature, das zuvor nicht in einem Release verfügbar war, zu einer Version des Standards hinzugefügt wurde. Dann mussten Sie noch länger warten, bis die neue Version von .NET Standard umfassend unterstützt wird.

  **Lösung in .NET 5:** Wenn ein Feature implementiert wird, ist es bereits für jede .NET 5-App und -Bibliothek verfügbar, da die Codebasis freigegeben ist. Da es keinen Unterschied zwischen der API-Spezifikation und der Implementierung gibt, können Sie neue Features viel schneller nutzen als mit .NET Standard.

- Komplexe Versionsverwaltung

  Die Trennung der API-Spezifikation von ihren Implementierungen führt zu einer komplexen Zuordnung zwischen API-Spezifikationsversionen und Implementierungsversionen. Diese Komplexität wird in der zuvor in diesem Artikel gezeigten Tabelle und in den Anweisungen zur Interpretation erläutert.

  **Lösung in .NET 5:** Es gibt keine Trennung zwischen einer .NET 5.x-API-Spezifikation und ihrer Implementierung. Das Ergebnis ist ein vereinfachtes TFM-Schema. Es gibt ein TFM-Präfix für alle Workloads: `net5.0` wird für Bibliotheken, Konsolen-Apps und Web-Apps verwendet. Die einzige Variation ist ein [Suffix, das plattformspezifische APIs](frameworks.md#net-5-os-specific-tfms) für eine bestimmte Plattform angibt (z. B. `net5.0-windows`). Dank dieser TFM-Namenskonvention können Sie leicht erkennen, ob eine bestimmte App eine bestimmte Bibliothek verwenden kann. Es ist keine äquivalente Tabelle mit Versionsnummern wie jene für .NET Standard erforderlich.

- Nicht von der Plattform unterstützte Ausnahmen zur Laufzeit

  .NET Standard macht plattformspezifische APIs verfügbar. Der Code wird möglicherweise fehlerfrei kompiliert und scheint auf jede beliebige Plattform portierbar zu sein, auch wenn er nicht portierbar ist. Bei der Ausführung auf einer Plattform, die über keine Implementierung für eine bestimmte API verfügt, erhalten Sie Laufzeitfehler.

  **Lösung in .NET 5:** Das .NET 5 SDK umfasst Codeanalysetools, die standardmäßig aktiviert sind. Das Analysetool für die Plattformkompatibilität erkennt die unbeabsichtigte Verwendung von APIs, die auf den Plattformen, auf denen Sie sie ausführen möchten, nicht unterstützt werden. Weitere Informationen finden Sie unter [Analysetool für die Plattformkompatibilität](analyzers/platform-compat-analyzer.md).

### <a name="net-standard-not-deprecated"></a>.NET Standard nicht veraltet

Für die Bibliotheken, die von mehreren .NET-Implementierungen verwendet werden können, wird .NET Standard weiterhin benötigt. Es wird empfohlen, .NET Standard in den folgenden Szenarios als Ziel zu verwenden:

* Verwenden Sie `netstandard2.0`, um Code für .NET Framework und alle anderen Implementierungen von .NET freizugeben.
* Verwenden Sie `netstandard2.1`, um Code für Mono, Xamarin und .NET Core 3.x freizugeben.

## <a name="see-also"></a>Weitere Informationen

- [.NET Standard-Versionen (Quelle)](https://github.com/dotnet/standard/blob/master/docs/versions.md)
- [.NET Standard-Versionen (interaktive Benutzeroberfläche)](https://dotnet.microsoft.com/platform/dotnet-standard#versions)
- [Erstellen einer .NET Standard-Bibliothek](../core/tutorials/library-with-visual-studio.md)
- [Plattformübergreifende Ziele](./library-guidance/cross-platform-targeting.md)
