---
title: Analysieren von Abhängigkeiten zum Portieren von Code zu .NET Core
description: Erfahren Sie, wie Sie externe Abhängigkeiten analysieren können, um Ihr Projekt von .NET Framework auf .NET Core portieren zu können.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: 430da45052e3953ab49f182b1773fc6d74bd2221
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223600"
---
# <a name="analyze-your-dependencies-to-port-code-to-net-core"></a>Analysieren Ihrer Abhängigkeiten zum Portieren von Code zu .NET Core

Um den Code zu .NET Core oder .NET Standard portieren zu können, müssen Sie Ihre Abhängigkeiten verstehen. Externe Abhängigkeiten sind die NuGet-Pakete oder `.dll`-Dateien, auf die Sie in Ihrem Projekt verweisen, die Sie aber nicht selbst erstellen.

## <a name="migrate-your-nuget-packages-to-packagereference"></a>Migrieren von NuGet-Paketen zu `PackageReference`

.NET Core verwendet [PackageReference](/nuget/consume-packages/package-references-in-project-files) zum Angeben von Paketabhängigkeiten. Wenn Sie [packages.config](/nuget/reference/packages-config) verwenden, um die Pakete in Ihrem Projekt anzugeben, konvertieren Sie diese in das `PackageReference`-Format, da `packages.config` in .NET Core nicht unterstützt wird.

Informationen zum Migrieren finden Sie im Artikel [Migrieren von „packages.config“ zu PackageReference](/nuget/reference/migrate-packages-config-to-package-reference).

## <a name="upgrade-your-nuget-packages"></a>Aktualisieren von NuGet-Paketen

Nachdem Sie Ihr Projekt zum `PackageReference`-Format migriert haben, überprüfen Sie, ob Ihre Pakete mit .NET Core kompatibel sind.

Aktualisieren Sie zunächst Ihre Pakete auf die neueste Version, die verfügbar ist. Dies kann über die Benutzeroberfläche des NuGet-Paket-Managers in Visual Studio erfolgen. Es ist wahrscheinlich, dass neuere Versionen ihrer Paketabhängigkeiten bereits mit .NET Core kompatibel sind.

## <a name="analyze-your-package-dependencies"></a>Analysieren der Paketabhängigkeiten

Wenn Sie noch nicht überprüft haben, ob die konvertierten und aktualisierten Paketabhängigkeiten in .NET Core funktionieren, gibt es einige Möglichkeiten, dies zu bestätigen:

### <a name="analyze-nuget-packages-using-nugetorg"></a>Analysieren von NuGet-Paketen mit nuget.org

Sie können die TFMs (Target Framework Monikers, Zielframeworkmoniker), die die einzelnen Pakete unterstützen, unter [nuget.org](https://www.nuget.org/) im Abschnitt **Dependencies** (Abhängigkeiten) der Paketseite anzeigen.

Es ist einfacher, die Website zum Überprüfen der Kompatibilität zu verwenden. Allerdings stehen dort nicht für alle **Abhängigkeiten** Informationen zur Verfügung.

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a>Analysieren von NuGet-Paketen mit dem NuGet-Paket-Explorer

Ein NuGet-Paket besteht wiederum aus mehreren Ordnern, die plattformspezifische Assemblys enthalten. Überprüfen Sie, ob es im Paket einen Ordner gibt, der eine kompatible Assembly enthält.

Am einfachsten überprüfen Sie die NuGet-Paketordner mit dem Tool [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer). Führen Sie nach der Installation folgende Schritte durch, um die Ordnernamen anzuzeigen:

1. Öffnen Sie den NuGet-Paket-Explorer.
2. Klicken Sie auf **Open package from online feed** (Paket über Onlinefeed öffnen).
3. Suchen Sie nach dem Namen des Pakets.
4. Wählen Sie den Paketnamen aus den Suchergebnissen aus, und klicken Sie auf **Öffnen** .
5. Erweitern Sie den Ordner *Lib* (Bibliotheken) auf der rechten Seite, und suchen Sie in den Ordnernamen.

Suchen Sie nach einem Ordner mit Namen mit einem der folgenden Muster: `netstandardX.Y` oder `netcoreappX.Y`.

Bei diesen Werten handelt es sich um [Zielframeworkmoniker](../../standard/frameworks.md), die den Versionen von [.NET Standard](../../standard/net-standard.md), .NET Core sowie den herkömmlichen Portable Class Library-Profilen (PCL) zugeordnet sind, die mit .NET Core kompatibel sind.

> [!IMPORTANT]
> Beachten Sie bei TFMs, die von einem Paket unterstützt werden, dass `netcoreapp*` trotz Kompatibilität, nur für .NET Core-Projekte konzipiert ist und nicht für .NET Standard-Projekte.
> Eine Bibliothek, die nur auf `netcoreapp*` und nicht auf `netstandard*` ausgerichtet ist, kann nur von anderen .NET Core-Apps verwendet werden.

## <a name="net-framework-compatibility-mode"></a>Der .NET Framework-Kompatibilitätsmodus

Nachdem Sie die NuGet-Pakete analysiert haben, zeigt sich möglicherweise, dass sie nur .NET Framework als Ziel verwenden.

Mit .NET Standard 2.0 wurde der .NET Framework-Kompatibilitätsmodus eingeführt. Mit diesem Kompatibilitätsmodus können .NET Standard- und .NET Core-Projekte auf .NET Framework-Bibliotheken verweisen. Das Verweisen auf .NET Framework-Bibliotheken funktioniert nicht bei allen Projekten. So funktioniert es z.B. nicht, wenn die Bibliothek Windows Presentation Foundation-APIs (WPF) verwendet. Dadurch werden jedoch viele Portierungsszenarios ermöglicht.

Wenn Sie in Ihrem Projekt auf NuGet-Pakete verweisen, die .NET Framework als Ziel verwenden, etwa [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), wird eine Paketfallbackwarnung ([NU1701](/nuget/reference/errors-and-warnings/nu1701)) wie die folgende ausgegeben:

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

Diese Warnung wird angezeigt, wenn Sie das Paket hinzufügen und jedes Mal, wenn Sie etwas erstellen, um sicherzustellen, dass Sie das Paket mit Ihrem Projekt testen. Wenn Ihr Projekt wie gewünscht funktioniert, können Sie die Warnung unterdrücken, indem Sie die Paketeigenschaften in Visual Studio bearbeiten oder die Projektdatei in Ihrem bevorzugten Code-Editor manuell bearbeiten.

Um die Warnung durch Bearbeiten der Projektdatei zu unterdrücken, suchen Sie den `PackageReference`-Eintrag für das Paket, für das Sie die Warnung unterdrücken möchten, und fügen Sie das `NoWarn`-Attribut hinzu. Das `NoWarn`-Attribut akzeptiert eine durch Trennzeichen getrennte Liste aller Warnungs-IDs. Im folgenden Beispiel wird gezeigt, wie Sie die `NU1701`-Warnung für das `Huitian.PowerCollections`-Paket unterdrücken, indem Sie Ihre Projektdatei manuell bearbeiten:

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

Weitere Informationen zum Unterdrücken von Compilerwarnungen in Visual Studio finden Sie unter [Unterdrücken von Compilerwarnungen](/visualstudio/ide/how-to-suppress-compiler-warnings#suppress-warnings-for-nuget-packages) im Abschnitt zum Unterdrücken von Warnungen für NuGet-Pakete.

## <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a>Vorgehensweise, wenn die NuGet-Paket-Abhängigkeit unter .NET Core nicht ausgeführt wird

Es gibt einige Dinge, die Sie tun können, wenn ein NuGet-Paket, auf das Sie angewiesen sind, unter .NET Core nicht ausgeführt wird:

- Wenn es sich um ein Open Source-Projekt handelt, das beispielsweise von GitHub gehostet wird, können Sie sich direkt an die Entwickler wenden.
- Sie können den Autor direkt über [nuget.org](https://www.nuget.org/) kontaktieren. Suchen Sie nach dem Paket, und klicken Sie links auf der Paketseite auf **Contact Owners** (Besitzer kontaktieren).
- Sie können nach einem anderen Paket suchen, das unter .NET Core ausgeführt wird und denselben Zweck erfüllt wie das Paket, das Sie bisher verwendet haben.
- Sie können den vom Paket ausgeführten Code selbst schreiben.
- Sie können die Abhängigkeit für das Paket eliminieren, indem Sie die Funktionalität Ihrer Anwendung ändern, zumindest bis eine kompatible Version des Pakets verfügbar ist.

Denken Sie daran, dass Open-Source-Projektverwalter und NuGet-Paketherausgeber häufig Freiwillige sind. Sie beteiligen sich, weil Ihnen eine bestimmte Domäne wichtig ist. Sie arbeiten daran unentgeltlich und haben häufig einen anderen Job, für den sie unter der Woche arbeiten. Denken Sie daran, wenn Sie diese Personen kontaktieren, um sie um Unterstützung bezüglich .NET Core zu bitten.

Wenn es Ihnen mit den genannten Optionen nicht gelingt, Ihr Problem zu beheben, müssen Sie sich mit dem Portieren in .NET Core noch etwas gedulden.

Das .NET-Team würde gerne wissen, welche Bibliotheken von .NET Core unterstützt werden sollten. Sie können uns gerne mit einer E-Mail an dotnet@microsoft.com mitteilen, welche Bibliotheken Sie gerne verwenden würden.

## <a name="analyze-dependencies-that-arent-nuget-packages"></a>Analysieren von Abhängigkeiten, bei denen es sich nicht um NuGet-Pakete handelt

Möglicherweise verfügen Sie über eine Abhängigkeit, bei der es sich nicht um ein NuGet-Paket, sondern beispielsweise um eine DLL im Dateisystem handelt. Wenn Sie feststellen möchten, ob diese Abhängigkeit portiert werden kann, haben Sie nur die Möglichkeit, das Tool [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport) auszuführen. Das Tool analysiert Assemblys, die .NET Framework als Ziel verwenden, und identifiziert APIs, die nicht auf andere .NET-Plattformen wie .NET Core portiert werden können. Sie können das Tool als Konsolenanwendung oder als [Visual Studio-Erweiterung](../../standard/analyzers/portability-analyzer.md) ausführen.

## <a name="next-steps"></a>Nächste Schritte

>[!div class="nextstepaction"]
>[Portbibliotheken](libraries.md)
