---
title: Portieren auf .NET Core – Analysieren der Abhängigkeiten von Drittanbietern
description: Erfahren Sie, wie Sie Drittanbieterabhängigkeiten analysieren können, um Ihr Projekt von .NET Framework auf .NET Core portieren zu können.
author: cartermp
ms.author: mairaw
ms.date: 02/15/2018
ms.openlocfilehash: a5affd8f1c493a87b2a4f7cd4096d168d404626a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="analyze-your-third-party-dependencies"></a>Analysieren Ihrer Drittanbieterabhängigkeiten

Wenn Sie Ihren Code auf .NET Core oder .NET Standard portieren möchten, ist der erste Schritt zum Portieren das Verstehen Ihrer Drittanbieterabhängigkeiten. Drittanbieterabhängigkeiten sind entweder [NuGet-Pakete](#analyze-referenced-nuget-packages-on-your-project) oder [DLLs](#analyze-dependencies-that-arent-nuget-packages), auf die Sie in Ihrem Projekt verweisen. Bewerten Sie jede Abhängigkeit, und entwickeln Sie einen Alternativplan für Abhängigkeiten, die nicht mit .NET Core kompatibel sind. In diesem Artikel wird gezeigt, wie Sie bestimmen, ob die Abhängigkeit mit .NET Core kompatibel ist.

## <a name="analyze-referenced-nuget-packages-in-your-project"></a>Analysieren von NuGet-Paketen, auf die in Ihrem Projekt verwiesen wird

Wenn Sie in Ihrem Projekt auf NuGet-Pakete verweisen, müssen Sie überprüfen, ob diese mit .NET Core kompatibel sind.
Es gibt zwei Möglichkeiten, dies zu erreichen:

* [Die NuGet-Paket-Explorer-App](#analyze-nuget-packages-using-nuget-package-explorer) (am zuverlässigsten).
* [die Website nuget.org](#analyze-nuget-packages-using-nugetorg).

Wenn sich bei der Analyse herausstellt, dass die Pakete nicht mit .NET Core sondern nur mit .NET Framework kompatibel sind, können Sie prüfen, ob der [.NET Framework-Kompatibilitätsmodus](#net-framework-compatibility-mode) Ihnen beim Portieren helfen kann.

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a>Analysieren von NuGet-Paketen mit dem NuGet-Paket-Explorer

Ein NuGet-Paket besteht wiederum aus mehreren Ordnern, die plattformspezifische Assemblys enthalten. Also müssen Sie prüfen, ob es im Paket einen Ordner gibt, der eine kompatible Assembly enthält.

Am einfachsten überprüfen Sie die NuGet-Paket-Ordner mit dem Tool [NuGet-Paket-Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer). Führen Sie nach der Installation folgende Schritte durch, um die Ordnernamen anzuzeigen:

1. Öffnen Sie den NuGet-Paket-Explorer.
2. Klicken Sie auf **Open package from online feed** (Paket über Onlinefeed öffnen).
3. Suchen Sie nach dem Namen des Pakets.
4. Wählen Sie den Paketnamen aus den Suchergebnissen aus, und klicken Sie auf **Öffnen**.
5. Erweitern Sie den Ordner *Lib* (Bibliotheken) auf der rechten Seite, und suchen Sie in den Ordnernamen.

Suchen Sie nach einem Ordner mit einem der folgenden Namen:

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netstandard2.0
netcoreapp1.0
netcoreapp1.1
netcoreapp2.0
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

Bei diesen Werten handelt es sich um [Target Framework Moniker (TFMs)](../../standard/frameworks.md), die den Versionen des [.NET-Standard](../../standard/net-standard.md) und .NET Core-Profils und der herkömmlichen PCL-Profilen (Portable Class Library) zugeordnet sind, die mit .NET Core kompatibel sind.

> [!IMPORTANT]
> Beachten Sie bei TFMs, die von einem Paket unterstützt werden, dass `netcoreapp*` trotz Kompatibilität, nur für .NET Core-Projekte konzipiert ist und nicht für .NET Standard-Projekte.
> Eine Bibliothek, die nur auf `netcoreapp*` und nicht auf `netstandard*` ausgerichtet ist, kann nur von anderen .NET Core-Apps verwendet werden.

Es gibt auch einige ältere TFMs, die in Vorabversionen von .NET Core verwendet wurden, die möglicherweise ebenfalls kompatibel sind:

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

Die Wahrscheinlichkeit ist hoch, dass diese TFMs mit Ihrem Code funktionieren, eine Garantie für die Kompatibilität besteht jedoch nicht. Pakete mit diesen TFMs wurden mit der Vorabversion von .NET Core-Paketen erstellt. Achten Sie darauf, wann (und ob) Pakete, die diese TFMs verwenden, auf .NET Standard aktualisiert werden.

> [!NOTE]
> Wenn Sie ein Paket, das auf eine herkömmliche PCL oder Vorabversion von .NET Core ausrichtet ist, verwenden möchten, müssen Sie das `PackageTargetFallback`-MSBuild-Element in Ihrer Projektdatei verwenden.
> Weitere Informationen zu diesem MSBuild-Element finden Sie unter [`PackageTargetFallback`](../tools/csproj.md#packagetargetfallback).

### <a name="analyze-nuget-packages-using-nugetorg"></a>Analysieren von NuGet-Paketen mit nuget.org

Alternativ können Sie unter [nuget.org](https://www.nuget.org/) im Abschnitt **Dependencies** (Abhängigkeiten) der Seite für jedes Paket auch sehen, welche TFMs von einem Paket unterstützt werden.

Es ist leichter, die Website zum Überprüfen der Kompatibilität zu verwenden. Allerdings stehen dort nicht für alle **Abhängigkeiten** Informationen zur Verfügung.

### <a name="net-framework-compatibility-mode"></a>Der .NET Framework-Kompatibilitätsmodus

Nachdem Sie die NuGet-Pakete analysiert haben, zeigt sich möglicherweise, dass sie nur auf .NET Framework ausgerichtet sind, wie dies bei den meisten NuGet-Paketen der Fall ist.

Mit .NET Standard 2.0 wurde der .NET Framework-Kompatibilitätsmodus eingeführt. Mit diesem Kompatibilitätsmodus können .NET Standard- und .NET Core-Projekte auf .NET Framework-Bibliotheken verweisen. Das Verweisen auf .NET Framework-Bibliotheken funktioniert nicht bei allen Projekten. So funktioniert es z.B. nicht, wenn die Bibliothek Windows Presentation Foundation-APIs (WPF) verwendet. Dadurch werden jedoch viele Portierungsszenarios ermöglicht.

Wenn Sie in Ihrem Projekt auf NuGet-Pakete verweisen, die auf .NET Framework ausgerichtet sind, wie z.B. [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), wird eine Paketfallbackwarnung ([NU1701](/nuget/reference/errors-and-warnings#nu1701)) wie die folgende ausgegeben:

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

Diese Warnung wird angezeigt, wenn Sie das Paket hinzufügen und jedes Mal, wenn Sie etwas erstellen, um sicherzustellen, dass Sie das Paket mit Ihrem Projekt testen. Wenn Ihr Projekt wie gewünscht funktioniert, können Sie die Warnung unterdrücken, indem Sie die Paketeigenschaften in Visual Studio bearbeiten oder die Projektdatei in Ihrem bevorzugten Code-Editor manuell bearbeiten.

Um die Warnung durch Bearbeiten der Projektdatei zu unterdrücken, suchen Sie den `PackageReference`-Eintrag für das Paket, für das Sie die Warnung unterdrücken möchten, und fügen Sie das `NoWarn`-Attribut hinzu. Das `NoWarn`-Attribut akzeptiert eine durch Trennzeichen getrennte Liste aller Warnungs-IDs. Im folgenden Beispiel wird gezeigt, wie Sie die `NU1701`-Warnung für das `Huitian.PowerCollections`-Paket unterdrücken, indem Sie Ihre Projektdatei manuell bearbeiten:

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

Weitere Informationen zum Unterdrücken von Compilerwarnungen in Visual Studio finden Sie unter [Unterdrücken von Compilerwarnungen](/visualstudio/ide/how-to-suppress-compiler-warnings#suppressing-warnings-for-nuget-packages) im Abschnitt zum Unterdrücken von Warnungen für NuGet-Pakete.

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a>Vorgehensweise, wenn die NuGet-Paket-Abhängigkeit unter .NET Core nicht ausgeführt wird

Es gibt einige Dinge, die Sie tun können, wenn ein NuGet-Paket, auf das Sie angewiesen sind, unter .NET Core nicht ausgeführt wird:

1. Wenn es sich um ein Open Source-Projekt handelt, das beispielsweise von GitHub gehostet wird, können Sie sich direkt an die Entwickler wenden.
2. Sie können den Autor direkt über [nuget.org](https://www.nuget.org/) kontaktieren. Suchen Sie nach dem Paket, und klicken Sie links auf der Paketseite auf **Contact Owners** (Besitzer kontaktieren).
3. Sie können nach einem anderen Paket suchen, das unter .NET Core ausgeführt wird und denselben Zweck erfüllt wie das Paket, das Sie bisher verwendet haben.
4. Sie können den vom Paket ausgeführten Code selbst schreiben.
5. Sie können die Abhängigkeit für das Paket eliminieren, indem Sie die Funktionalität Ihrer Anwendung ändern, zumindest bis eine kompatible Version des Pakets verfügbar ist.

Denken Sie daran, dass Open-Source-Projektverwalter und NuGet-Paketherausgeber häufig Freiwillige sind. Sie beteiligen sich, weil Ihnen eine bestimmte Domäne wichtig ist. Sie arbeiten daran unentgeltlich und haben häufig einen anderen Job, für den sie unter der Woche arbeiten. Denken Sie daran, wenn Sie sie kontaktieren, um sie nach Hilfe mit .NET Core zu fragen.

Wenn es Ihnen mit den genannten Vorschlägen nicht gelingt, Ihr Problem zu beheben, müssen Sie sich mit dem Portieren auf .NET Core noch etwas gedulden.

Das .NET-Team würde gerne wissen, welche Bibliotheken von .NET Core unterstützt werden sollten. Sie können uns gerne mit einer E-Mail an dotnet@microsoft.com mitteilen, welche Bibliotheken Sie gerne verwenden würden.

## <a name="analyze-dependencies-that-arent-nuget-packages"></a>Analysieren von Abhängigkeiten, bei denen es sich nicht um NuGet-Pakete handelt

Möglicherweise verfügen Sie über eine Abhängigkeit, bei der es sich nicht um ein NuGet-Paket, sondern beispielsweise um eine DLL im Dateisystem handelt. Wenn Sie feststellen möchten, ob diese Abhängigkeit portiert werden kann, haben Sie nur die Möglichkeit, das Tool [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport) auszuführen. Das Tool kann Assemblys analysieren, die auf .NET Framework ausgerichtet sind, und APIs identifizieren, die nicht auf andere .NET-Plattformen wie .NET Core portiert werden können. Sie können das Tool als Konsolenanwendung oder als [Visual Studio-Erweiterung](../../standard/analyzers/portability-analyzer.md) ausführen.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie eine Bibliothek portieren, lesen Sie [Portieren von Bibliotheken](libraries.md).
