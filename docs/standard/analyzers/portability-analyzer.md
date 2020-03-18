---
title: .NET Portability Analyzer – .NET
description: Erfahren Sie, wie Sie mit dem Tool .NET Portability Analyzer bewerten, wie portabel Ihr Code zwischen den verschiedenen .NET-Implementierungen, wie .NET Core, .NET Standard, UWP und Xamarin, ist.
ms.date: 09/13/2019
ms.technology: dotnet-standard
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.openlocfilehash: e0a5c791926b36fe5a35c5446471c3dcdb75cd7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "72774391"
---
# <a name="the-net-portability-analyzer"></a>.NET Portability Analyzer

Sollen Ihre Bibliotheken mehrere Plattformen unterstützen? Möchten Sie wissen, wie viel Arbeit erforderlich ist, damit Ihre .NET Framework-Anwendung unter .NET Core ausgeführt werden kann? [.NET Portability Analyzer](https://github.com/microsoft/dotnet-apiport) ist ein Tool, das Assemblys analysiert und einen detaillierten Bericht zu fehlenden .NET-APIs bereitstellt, damit die Anwendungen oder Bibliotheken auf die von Ihnen angegebenen .NET-Zielplattformen portiert werden können. Der Portability Analyzer wird zur projektweise zugeordneten Analyse eines Assemblys als [Visual Studio-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) sowie zur Analyse von Assemblys nach angegebenen Dateien oder angegebenem Verzeichnis als [ApiPort-Konsolenanwendung](https://aka.ms/apiportdownload) bereitgestellt.

Sobald Sie Ihr Projekt für Ihre neue Zielplattform (z.B. .NET Core) konvertiert haben, können Sie das Roslyn-basierte [API Analyzer Tool](api-analyzer.md) verwenden, um APIs zu identifizieren, die <xref:System.PlatformNotSupportedException>-Ausnahmen und einige andere Kompatibilitätsprobleme verursachen.

## <a name="common-targets"></a>Allgemeine Ziele

- [.NET Core](../../core/index.md): Besitzt einen modularen Aufbau, verwendet die parallele Ausführung und ist auf plattformübergreifende Szenarios ausgerichtet. Die parallele Ausführung ermöglicht Ihnen die Übernahme neuer Versionen von .NET Core, ohne andere Apps zu beeinträchtigen. Wenn Sie Ihre Anwendung auf Plattformen portieren möchten, die .NET Core unterstützen, wird dieses Ziel empfohlen.
- .[NET Standard](../../standard/net-standard.md): Enthält die in allen .NET-Implementierungen verfügbaren .NET Standard-APIs. Wenn Sie möchten, dass Ihre Bibliothek auf allen Plattformen ausgeführt werden kann, die .NET unterstützen, wird dieses Ziel empfohlen.
- [ASP.NET Core](/aspnet/core): Ein modernes Webframework, das auf .NET Core basiert. Wenn Sie Ihre Webanwendung zur Unterstützung von mehreren Plattformen nach .NET Core portieren möchten, wird dieses Ziel empfohlen.
- .NET Core-Plattform + [Plattformerweiterungen](../../core/porting/windows-compat-pack.md): Enthält die .NET Core-APIs sowie den Windows Compatibility Pack, der zahlreiche in .NET Framework verfügbare Technologien bereitstellt. Dieses Ziel wird zum Portieren der Anwendung von .NET Framework nach .NET Core unter Windows empfohlen.
- .NET Standard-Plattform + [Plattformerweiterungen](../../core/porting/windows-compat-pack.md): Enthält die .NET Standard-APIs sowie den Windows Compatibility Pack, der zahlreiche in .NET Framework verfügbare Technologien bereitstellt. Dieses Ziel wird zum Portieren der Bibliothek von .NET Framework nach .NET Core unter Windows empfohlen.

## <a name="how-to-use-the-net-portability-analyzer"></a>Verwenden von .NET Portability Analyzer

Laden Sie .NET Portability Analyzer in Visual Studio zunächst von [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) herunter, um mit der Verwendung dieser Erweiterung zu beginnen. Er wird in Visual Studio 2017 und älteren Versionen unterstützt. Sie können ihn in Visual Studio über **Analyze** > **Portability Analyzer Settings** (Analysieren/Portability Analyzer-Einstellungen) konfigurieren und Ihre Zielplattformen, also die .NET-Plattformen/Versionen auswählen, für die Sie Portabilitätslücken im Vergleich zu der Plattform/Version analysieren möchten, mit der Ihre aktuelle Assembly erstellt wurde.

![Screenshot von Portability Analyzer.](./media/portability-analyzer/portability-screenshot.png)

Sie können auch die ApiPort-Konsolenanwendung verwenden. Laden Sie sie aus dem [ApiPort-Repository](https://aka.ms/apiportdownload) herunter. Sie können die Befehlsoption `listTargets` verwenden, um die Liste mit verfügbaren Zielen anzuzeigen. Anschließend wählen Sie Zielplattformen aus, indem Sie die Befehlsoption `-t` oder `--target` angeben.

### <a name="analyze-portability"></a>Analysieren der Portabilität
Um das gesamte Projekt in Visual Studio zu analysieren, klicken Sie mit der rechten Maustaste im **Projektmappen-Explorer** auf Ihr Projekt, und wählen Sie **Assemblyportabilität analysieren** aus. Wechseln Sie andernfalls zum Menü **Analysieren**, und wählen Sie **Assemblyportabilität analysieren**. Wählen Sie dort die ausführbare Datei oder DLL-Datei des Projekts aus.

![Screenshot von Portability Analyzer aus dem Projektmappen-Explorer.](./media/portability-analyzer/portability-solution-explorer.png)

Sie können auch die [ApiPort-Konsolenanwendung](https://aka.ms/apiportdownload) verwenden.

- Geben Sie den folgenden Befehl an, um das aktuelle Verzeichnis zu analysieren: `ApiPort.exe analyze -f .`
- Um eine bestimmte Liste von DLL-Dateien zu analysieren, geben Sie den folgenden Befehl ein: `ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`
- Ausführen von `ApiPort.exe -?`, um weitere Unterstützung zu erhalten

Es wird empfohlen, alle zugehörigen EXE- und DLL-Dateien, die Sie besitzen und die Sie portieren möchten, einzubeziehen, und die Dateien auszuschließen, von denen Ihre Anwendung abhängt, die Sie jedoch nicht besitzen möchten und die Sie nicht portieren können. Dadurch erhalten Sie einen entsprechend sachdienlichen Portabilitätsbericht.

### <a name="view-and-interpret-portability-result"></a>Anzeigen und Interpretieren des Portabilitätsergebnisses

Im Bericht werden nur die APIs angegeben, die von einer Zielplattform nicht unterstützt werden.
Nach dem Ausführen der Analyse in Visual Studio wird der Link für die Datei des .NET-Portabilitätsberichts angezeigt. Wenn Sie die [ApiPort-Konsolenanwendung](https://aka.ms/apiportdownload) verwendet haben, wird der .NET Portabilitätsbericht als Datei im angegebenen Format gespeichert. Die Standardeinstellung ist eine Excel-Datei ( *.xlsx*) im aktuellen Verzeichnis.

#### <a name="portability-summary"></a>Zusammenfassung zur Portabilität

![Screenshot der Zusammenfassung zur Portabilität.](./media/portability-analyzer/api-catalog-portablility-summary.png)

Im Berichtsabschnitt mit der Portabilitätszusammenfassung wird für jede in der Ausführung enthaltene Assembly der Portabilitätsprozentsatz angezeigt. Im vorherigen Beispiel sind 71,24 Prozent der in der App `svcutil` verwendeten .NET Framework-APIs in .NET Core und Plattformerweiterungen verfügbar. Wenn Sie das Tool .NET Portability Analyzer für mehrere Assemblys ausführen, gibt es im Bericht „Zusammenfassung zur Portabilität“ für jede Assembly eine Zeile.

#### <a name="details"></a>Details

![Screenshot der Portabilitätsdetails.](./media/portability-analyzer/api-catalog-portablility-details.png)

Im Abschnitt **Details** des Berichts werden die APIs aufgeführt, die in einer der **Zielplattformen** fehlen.

- Zieltyp: Der Typ enthält APIs, die in einer Zielplattform fehlen.
- Zielmember: Die Methode fehlt in einer Zielplattform.
- Assemblyname: Die .NET Framework-Assembly, in der sich die fehlende API befindet.
- Jede ausgewählte Zielplattform wird als eine Spalte dargestellt, z. B. „.NET Core“: Der Wert „Nicht unterstützt“ bedeutet, dass die API auf dieser Zielplattform nicht unterstützt wird.
- Empfohlene Änderungen: Empfohlene API oder Technologie, zu der gewechselt werden sollte. Dieses Feld ist für viele APIs derzeit leer oder nicht mehr aktuell. Aufgrund der Vielzahl von APIs ist es eine große Herausforderung, auf dem Laufenden zu bleiben. Wir suchen nach alternativen Lösungen, um Kunden nützliche Informationen anbieten zu können.

#### <a name="missing-assemblies"></a>Fehlende Assemblys

![Screenshot der fehlenden Assemblys.](./media/portability-analyzer/api-catalog-missing-assemblies.png)

Ihr Bericht enthält möglicherweise einen Abschnitt mit der Überschrift „Fehlende Assemblys“. In diesem Abschnitt wird Ihnen mitgeteilt, dass die Assemblys in der Liste von Ihren analysierten Assemblys referenziert werden, aber nicht analysiert wurden. Wenn es sich um eine Assembly in Ihrem Besitz handelt, beziehen Sie sie in die Ausführung von API Portability Analyzer ein, sodass Sie dafür die im Portabilitätsbericht angegebene API-Ebene erhalten. Wenn es sich um die Bibliothek eines Drittanbieters handelt, erkundigen Sie sich, ob es eine neuere Version gibt, die Ihre Zielplattform unterstützt. Ist dies der Fall, sollten Sie zur neueren Version wechseln. Letztlich soll diese Liste alle Assemblys von Drittanbietern enthalten, von denen Ihre Anwendung abhängig ist, und diese müssen nachweislich eine Version aufweisen, die Ihre Zielplattform unterstützt.

Weitere Informationen zum .NET Portability Analyzer, finden Sie auf der [GitHub-Dokumentation](https://github.com/Microsoft/dotnet-apiport#documentation) und im Channel 9-Video [Eine kurze Betrachtung des .NET Portability Analyzer](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer).
